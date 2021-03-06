communityfolder.com
=======
Allows customers to sign into a client area and create/pay/run/manage website(s) or "tenants" that are powered by communityfolder.

Allows anyone to search and find websites that are powered by communityfolder.

https://communityfolder.com

main:
- https://github.com/trabur/communityfolder.com

source code:
- https://github.com/trabur/communityfolder-backend
- https://github.com/trabur/communityfolder-frontend
- https://github.com/trabur/communityfolder-mobile

containers:
- https://hub.docker.com/r/istrav/communityfolder-backend
- https://hub.docker.com/r/istrav/communityfolder-frontend

third party services:
- credit card: https://www.npmjs.com/package/nestjs-stripe
- sms: https://www.npmjs.com/package/nestjs-twilio
- email: https://www.npmjs.com/package/@ntegral/nestjs-sendgrid
- cron: https://github.com/cloudflare/wrangler
- logger: https://www.npmjs.com/package/nest-winston
- files: https://www.npmjs.com/package/nestjs-minio-client
- keys: https://www.npmjs.com/package/jsonwebtoken
- consensus: https://github.com/unshiftio/liferaft
- chains: https://www.npmjs.com/package/js-markov
- bots: https://www.npmjs.com/package/node-nlp
- ai: https://beta.openai.com/

### web-station
```bash
# node.js
$ curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
$ sudo apt-get install nodejs -y

# show firewall
$ sudo ufw status verbose

# toggle
$ sudo ufw enable
$ sudo ufw disable
# command line
$ sudo ufw allow ssh
$ sudo ufw allow http
$ sudo ufw allow https
# app
$ sudo ufw allow 1337/tcp
$ sudo ufw allow 1337/udp
# vnc
$ sudo ufw allow 5900/tcp
$ sudo ufw allow 5900/udp
# apply
$ sudo ufw reload
# delete ufw rules
$ sudo ufw status numbered
$ sudo ufw delete 3

# fix reverse tabbing in vscode
$ xmodmap -e 'keycode 23 = Tab'
$ sudo vim /usr/share/X11/xkb/symbols/pc
# change line from:
key <TAB> { [ Tab, ISO_Left_Tab ] };
# change line to:
key <TAB> { [ Tab ] };
```

### run
```bash
# fetch deps
$ npm install

# development
$ npm run dev
```

### versioning
```bash
# check version
$ npm run id

# tag a vew version
$ npm version v0.0.14 --no-git-tag-version

# check everything in
$ git add . && git commit -m "version" && git push

# then check version tag in
$ git tag v0.0.14
$ git push --tags
```

### clear port
```bash
$ lsof -i tcp:3000
$ kill -9 PID
```

# create-svelte

Everything you need to build a Svelte project, powered by [`create-svelte`](https://github.com/sveltejs/kit/tree/master/packages/create-svelte).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npm init svelte

# create a new project in my-app
npm init svelte my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.
