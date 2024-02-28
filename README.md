# husky-commitlint-demo

Demo of how to lint Git commit messages with [commitlint](https://b.remarkabl.org/commitlint) and [husky](https://b.remarkabl.org/husky).

Read [blog post](https://b.remarkabl.org/3u0Vdlc) or watch [YouTube video](https://youtu.be/2J9VnYiZ_Ts?list=PLVgOtoUBG2mdLpj6qT5DXfg5_pGPTDrJZ).

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
npx husky
```

Add the `commit-msg` hook:

```sh
echo 'npx commitlint --edit $1' > .husky/commit-msg
```

## package.json

Private package:

```json
{
  "private": true,
  "scripts": {
    "prepare": "husky"
  },
  "devDependencies": {
    "@commitlint/cli": "latest",
    "@commitlint/config-conventional": "latest",
    "husky": "latest"
  }
}
```

Public package:

```json
{
  "private": false,
  "scripts": {
    "prepare": "husky"
  },
  "devDependencies": {
    "@commitlint/cli": "latest",
    "@commitlint/config-conventional": "latest",
    "husky": "latest"
  }
}
```

## License

[MIT](LICENSE)
