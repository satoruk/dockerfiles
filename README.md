個人的な開発や CI 等に利用している Dockerfile の管理リポジトリです.

[Docker Hub の autobuild](https://docs.docker.com/docker-hub/builds/)を利用しているため git-tag に命名規則をつけています.

## Setup

```sh
git clone git@github.com:satoruk/dockerfiles.git
cd dockerfiles
yarn install
yarn run info
```

git の tag または branch の命名規則

## branch ,tag の命名規則

- `${ENV}-${ENV_VERSION}-${BASE_OS}-${VARIANT}`
  - **BAD** `node`
  - **BAD** `node-10.16.3`
  - **GOOD** `node-latest-buster`
  - **GOOD** `node-10-buster`
  - **GOOD** `node-10.16.3-buster-allure`
  - **GOOD** `node-10.16.3-buster-allure-2.12.1`

意味とフォーマット

- **`ENV`:** メインとなる環境名 (`-`を含まない文字)
- **`ENV_VERSION`:** メインとなる環境のバージョン (`-`を含まない文字)
- **`BASE_OS`:** ベースとなる OS（コードネーム） (`-`を含まない文字)
- **`VARIANT`:** 追加情報があれば任意で指定

## Docker Hub

- prefix `node-`
  - https://hub.docker.com/r/satoruk/node
