# husky-commitlint-demo

Demo of how to lint Git commit messages with [commitlint](https://github.com/conventional-changelog/commitlint) and [husky](https://github.com/typicode/husky). Read [blog post](https://b.remarkabl.org/3u0Vdlc).

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

## Husky

Enable Git hooks:

```sh
npx husky install
```

Add `commit-msg` hook:

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
    "@commitlint/cli": "^11.0.0",
    "@commitlint/config-conventional": "^11.0.0",
    "husky": "^5.0.9"
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
    "@commitlint/cli": "^11.0.0",
    "@commitlint/config-conventional": "^11.0.0",
    "husky": "^5.0.9",
    "pinst": "^2.1.4"
  }
}
```

## License

[MIT](LICENSE)
