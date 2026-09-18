# Changelog

All notable changes to this project will be documented in this file.

## [1.2.0](https://github.com/maxime-lenne/github-repository-template/compare/v1.1.0...v1.2.0) (2026-09-18)

### ✨ Features

* Add setup workflow to initialize repository settings ([5a574bc](https://github.com/maxime-lenne/github-repository-template/commit/5a574bcf9d23381cd69ceb8f506fb2a6198e2e86))
* Bootstrap new repositories from the template automatically ([ada2e5a](https://github.com/maxime-lenne/github-repository-template/commit/ada2e5a05d8fd6d011a550951429495680554241))
* Clean up local branches automatically once their PR is merged ([a2d3c0f](https://github.com/maxime-lenne/github-repository-template/commit/a2d3c0f0e68bcdade602b0692375fb65dca91ddf))
* Re-sync develop with main automatically after each release ([838c5e1](https://github.com/maxime-lenne/github-repository-template/commit/838c5e143613ccb3863f9eb662d8915fab7c5f10))

### 🐛 Bug Fixes

* Publish releases on merge into main with version, changelog and release commit ([55893fc](https://github.com/maxime-lenne/github-repository-template/commit/55893fc347767feaef63ef546f30526bc5541313))

### 🔒 Security

* prevent to push public repo if it's a private ([218b2fb](https://github.com/maxime-lenne/github-repository-template/commit/218b2fba306cb73f3075e416c643c7999776386a))

### ⬆️ Dependencies

* Bump @commitlint/cli from 20.5.3 to 21.0.1 ([ef9fd84](https://github.com/maxime-lenne/github-repository-template/commit/ef9fd8491e20c652578d8a741417898894cb4cb4))
* Bump @semantic-release/git from 10.0.1 to 11.0.1 ([87d37f7](https://github.com/maxime-lenne/github-repository-template/commit/87d37f7b6c25d83349fa837578a392c4445649b8))
* Bump actions/checkout from 4 to 6 ([cf1cd8b](https://github.com/maxime-lenne/github-repository-template/commit/cf1cd8b26d698987bdd9aa0871a3ae05bf7671ef))
* Bump actions/checkout from 6 to 7 ([1cb1e61](https://github.com/maxime-lenne/github-repository-template/commit/1cb1e61f567de3943a7f818fc79b26dcfad11fbd))
* Bump actions/setup-node from 4 to 6 ([9ef7fcc](https://github.com/maxime-lenne/github-repository-template/commit/9ef7fccfa1ac8da793ba07c549cc52619b68df07))
* Bump actions/setup-node from 6 to 7 ([ad9f632](https://github.com/maxime-lenne/github-repository-template/commit/ad9f632808e5710fb7f16098fd594c4d065949e8))
* Bump lint-staged from 16.4.0 to 17.0.4 ([9f27d83](https://github.com/maxime-lenne/github-repository-template/commit/9f27d83b6776cb389feb12ad8d798a9cf5891f26))
* Bump markdownlint-cli in the dev-dependencies group ([3f62cf5](https://github.com/maxime-lenne/github-repository-template/commit/3f62cf5e7ee8645a3205779585714ecd160b2b9f))
* Pin conventionalcommits preset to v9 and align Node/Bun versions ([5beaecd](https://github.com/maxime-lenne/github-repository-template/commit/5beaecd4bbdee0f4a02e3ce94823c9a4e3908344))

## [1.1.0](https://github.com/maxime-lenne/github-repository-template/compare/v1.0.0...v1.1.0) (2026-02-04)

### ✨ Features

* Add commitlint script and CI workflow ([b20d116](https://github.com/maxime-lenne/github-repository-template/commit/b20d11611dd947d3f2080428fed88b404b3726f2))

## 1.0.0 (2026-02-03)

### ✨ Features

* Add changelog generation with gitmoji support ([7158a97](https://github.com/maxime-lenne/github-repository-template/commit/7158a97e4f8a29617b3847f299f91ae6bd5a4480))
* Add semantic-release with gitmoji support ([c6e4434](https://github.com/maxime-lenne/github-repository-template/commit/c6e4434ea2a9ed26d2e61d201e81e8bd9072f9c1))
* Initial commit - Repository template setup ([6c9fc72](https://github.com/maxime-lenne/github-repository-template/commit/6c9fc72b7c114db198a58da67750903559994184))
* Support both gitmoji and conventional commit formats ([b4bed7b](https://github.com/maxime-lenne/github-repository-template/commit/b4bed7bcbf24b3f8f032187adab616a69a2f38cc))

### 🐛 Bug Fixes

* Fix Node.js version for semantic-release ([f307677](https://github.com/maxime-lenne/github-repository-template/commit/f307677c78a6b7d6ea383847e78a99d1cb25832d))
* Fix semantic-release configuration ([e849146](https://github.com/maxime-lenne/github-repository-template/commit/e8491464d4edff63b40c5370c1fed68e071e1af5))

### ⬆️ Dependencies

* Bump actions/checkout from 4 to 6 ([9d57470](https://github.com/maxime-lenne/github-repository-template/commit/9d57470bfeae0b17eddb5a17f49a43777e9c9e91))
