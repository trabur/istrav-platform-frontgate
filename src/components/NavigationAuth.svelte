<script>
  import { onMount } from "svelte";
  import { parseJwt } from '../parseJwt'

  let authenticated = false
  let token = {
    id: '',
    email: ''
  }

  onMount(() => {
    let lsToken = localStorage.getItem('token')
    if (lsToken) {
      token = parseJwt(lsToken)
    }

    if (token.email) {
      authenticated = true
    } else {
      authenticated = false
    }
  })
</script>
<nav class="members-only blue lighten-2">
  <div class="nav-wrapper">
    <div class="container">
      <a href="/" class="brand-logo"><i class="large material-icons">lock</i>Members Only</a>
      <ul id="nav-mobile" class="right hide-on-med-and-down">
        {#if authenticated}
          <li><a href={`/accounts/${token.id}`}>{token.email}</a></li>
        {:else}
          <li><a href="/auth/login">Login</a></li>
          <li><a href="/auth/register">Register</a></li>
        {/if}
      </ul>
    </div>
  </div>
</nav>
    
<style>
  .members-only {
    /* box-shadow: 0 0 1em #333; */
  }
</style>