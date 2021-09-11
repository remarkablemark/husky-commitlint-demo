# husky-commitlint-demo

Demo of how to lint Git commit messages with [commitlint](https://b.remarkabl.org/commitlint) and [husky](https://b.remarkabl.org/husky). Read [blog post](https://b.remarkabl.org/3u0Vdlc) or watch [YouTube video](https://youtu.be/2J9VnYiZ_Ts?list=PLVgOtoUBG2mdLpj6qT5DXfg5_pGPTDrJZ).

## Prerequisites

- [Node.js](https://b.remarkabl.org/nodejs-site)

## Install

Clone repository:

```sh
git clone https://github.com/remarkablemark/husky-commitlint-demo.git
cd husky-commitlint-demo
```

Install dependencies:

```sh
npm install
```

## husky

Enable Git hooks:

```sh
npx husky install
```

Add the `commit-msg` hook:

```sh
npx husky add .husky/commit-msg 'npx commitlint --edit $1'
```

Uninstall husky:

```sh
npm uninstall husky
```

## package.json

Private package:

```json
{
  "private": true,
  "scripts": {
    "postinstall": "husky install"
  },
  "devDependencies": {
    "@commitlint/cli": "^13.1.0",
    "@commitlint/config-conventional": "^13.1.0",
    "husky": "^7.0.2"
  }
}
```

Public package:

```json
{
  "private": false,
  "scripts": {
    "postinstall": "husky install",
    "prepublishOnly": "pinst --disable",
    "postpublish": "pinst --enable"
  },
  "devDependencies": {
    "@commitlint/cli": "^13.1.0",
    "@commitlint/config-conventional": "^13.1.0",
    "husky": "^7.0.2",
    "pinst": "^2.1.4"
  }
}
```

## License

[MIT](LICENSE)
