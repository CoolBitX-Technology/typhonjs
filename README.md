


```
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
