# Branch strategy

- Primary development happens on the `cbx` branch.
- The `master` branch is used to track upstream changes.

# Start a feature branch

```sh
$ git checkout cbx
$ git checkout -b feature/xxx # create new branch from cbx
```

# Develop

```
yarn install
yarn test
```

# Bundle js

```
yarn build
```

# Deploy

- Get the npm credentials from 1Password: `https://start.1password.com/open/i?a=CGQKO46HGZDUHI7PFEQCOHKGOY&v=xwwjaoahqx2weou5zjmidzijva&i=4x7ckqzkkvpq2zzmge4hirvupi&h=cbxio.1password.com`
- Bump the version in `package.json` by incrementing the `cbx.x` suffix by 1 (e.g. `3.0.1-cbx.0` → `3.0.1-cbx.1`).
- Run login and deploy in order:

```
npm login
yarn deploy
```

- After deploying, create a GitHub Release (add the corresponding tag and release notes).

# Yarn install troubleshooting

If you see the `packageManager: yarn@4.1.0` message (Yarn v1 vs Corepack), enable Corepack and activate the required Yarn version:

```sh
❯ yarn
error This project's package.json defines "packageManager": "yarn@4.1.0". However the current global version of Yarn is 1.22.22.

Presence of the "packageManager" field indicates that the project is meant to be used with Corepack, a tool included by default with all official Node.js distributions starting from 16.9 and 14.19.
Corepack must currently be enabled by running corepack enable in your terminal. For more information, check out https://yarnpkg.com/corepack.

❯ corepack enable
❯ corepack prepare yarn@4.1.0 --activate
Preparing yarn@4.1.0 for immediate activation...
❯ yarn -v
4.1.0
```
