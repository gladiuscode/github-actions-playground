# Changelog

## [0.1.1](https://github.com/gladiuscode/github-actions-playground/compare/0.1.0...0.1.1) (2025-01-26)


### Bug Fixes

* release-it workflows names ([#6](https://github.com/gladiuscode/github-actions-playground/issues/6)) ([8d9dec6](https://github.com/gladiuscode/github-actions-playground/commit/8d9dec64f989a339c83a9f5669b952d78b10ddef))

# 0.1.0 (2025-01-26)


### Bug Fixes

* lint script ([5154014](https://github.com/gladiuscode/github-actions-playground/commit/51540142c8b6a077212081e4170ac9a7aa055298))
* missing pipe in configure git user step ([fda0d65](https://github.com/gladiuscode/github-actions-playground/commit/fda0d65d853bb8912e66184ec72dff67fcc8f126))
* relase script --ci tag usage ([962886d](https://github.com/gladiuscode/github-actions-playground/commit/962886dfac7ba196a0c6357687e65c8ad1ea5ca5))


### Features

* add -ci flag to release script ([5aa92d8](https://github.com/gladiuscode/github-actions-playground/commit/5aa92d80257240a4ad0cf96aee1624595fd80eb3))
* add back env.GITHUB_TOKEN override in last release step ([a151c34](https://github.com/gladiuscode/github-actions-playground/commit/a151c345b18f4ac30e89d3defc228be4f817c07c))
* add build folder to .gitignore ([e0d189b](https://github.com/gladiuscode/github-actions-playground/commit/e0d189b4f9a9d421fba04a006ce92a462e335535))
* add build script ([715344e](https://github.com/gladiuscode/github-actions-playground/commit/715344edc56c3e766ff7c11cc9deb7b6b7659b0c))
* add configure git user step ([d698979](https://github.com/gladiuscode/github-actions-playground/commit/d6989798c7054b79de111c844d0ea81fac6bcc66))
* add create-github-app-token step to use github app to bypass ruleset for pr only in main ([d7f02f0](https://github.com/gladiuscode/github-actions-playground/commit/d7f02f06721e701e71df7057c049756d160b4335))
* add lint job ([d7955d5](https://github.com/gladiuscode/github-actions-playground/commit/d7955d56f67c963a114f6cf2e2591f2bb4f4016e))
* add missing env with github token ([f51c071](https://github.com/gladiuscode/github-actions-playground/commit/f51c071452e5392f88f650134319a7fadbfcf6ee))
* add persist-credentials false to checkout step ([2ac91d0](https://github.com/gladiuscode/github-actions-playground/commit/2ac91d0e639754f2230d515c03337ab0e9701496))
* add push empty commit step ([b1acfbe](https://github.com/gladiuscode/github-actions-playground/commit/b1acfbe0d2926c9b337859d70977c215ffd366ed))
* add release step to release job ([b9cbc91](https://github.com/gladiuscode/github-actions-playground/commit/b9cbc913a7e3407345c3c8a75106dd1f183572dc))
* add typescript ([def4f9a](https://github.com/gladiuscode/github-actions-playground/commit/def4f9a1157216b19955b1ff6daf4996f810f2d0))
* add upload-artifact step after build ([2fb097b](https://github.com/gladiuscode/github-actions-playground/commit/2fb097bef3390f4b14522bcf4789ea5224635617))
* configure @release-it/conventional-changelog ([#1](https://github.com/gladiuscode/github-actions-playground/issues/1)) ([6f8cc59](https://github.com/gladiuscode/github-actions-playground/commit/6f8cc597a129ff0afbabf659cd3d0ffeaeffc650))
* configure build step ([679ea53](https://github.com/gladiuscode/github-actions-playground/commit/679ea5355c8097e36f87f61c5abab35320590d14))
* configure checkout and setup steps ([afae90b](https://github.com/gladiuscode/github-actions-playground/commit/afae90b071e6eed7baab67315a4a660d05b0584a))
* configure tsc output dir ([1b47393](https://github.com/gladiuscode/github-actions-playground/commit/1b47393674ad555259ced5ca301ac530872aa9f8))
* create deploy.yml basic file ([a59aacd](https://github.com/gladiuscode/github-actions-playground/commit/a59aacd4c6d60b60f9a5aeaa7d3725fdd1c1d69f))
* create fake release job ([0b8dcf2](https://github.com/gladiuscode/github-actions-playground/commit/0b8dcf2120d34156dfade4774fe03f7df29214c3))
* create index.ts ([aa34531](https://github.com/gladiuscode/github-actions-playground/commit/aa3453167557324b42de3d6048910157dc19789f))
* disable npm publish ([8727de5](https://github.com/gladiuscode/github-actions-playground/commit/8727de5948d440cbb61801ca94b8db95d61ab42a))
* improve repository docs ([#3](https://github.com/gladiuscode/github-actions-playground/issues/3)) ([42a9261](https://github.com/gladiuscode/github-actions-playground/commit/42a92618006c128a7dff74455e74604198300584))
* improve workflows ([#4](https://github.com/gladiuscode/github-actions-playground/issues/4)) ([a4975e5](https://github.com/gladiuscode/github-actions-playground/commit/a4975e5bbc668fe304e212e4f817fc356903e621))
* init release-it ([302cc51](https://github.com/gladiuscode/github-actions-playground/commit/302cc5147e4a6b15f58f8c1af67c556d33906beb))
* install and init eslint ([0c6ed6d](https://github.com/gladiuscode/github-actions-playground/commit/0c6ed6df758b65874a6c5c28031f025f28e14aec))
* lock node version to hydrogen lts ([31bcefe](https://github.com/gladiuscode/github-actions-playground/commit/31bcefe179563786ac426c9ca052f9e5b5b144d0))
* move env block outside steps ([291ade3](https://github.com/gladiuscode/github-actions-playground/commit/291ade35031948c580682165e3de282742e18d20))
* move env outside jobs ([8b9f3fe](https://github.com/gladiuscode/github-actions-playground/commit/8b9f3fe7ec07ba94c81413a60803f1bef83dad8e))
* remove env block and add with.token in checkout step ([50d6daf](https://github.com/gladiuscode/github-actions-playground/commit/50d6dafddd54b70c6f345cea16606e6aa6ec90ee))
* remove persist-credentials flag to revert it to true ([744598b](https://github.com/gladiuscode/github-actions-playground/commit/744598bb96f1d18903a4d081558d35426025e6c8))
* remove push empty commit ([9a34d05](https://github.com/gladiuscode/github-actions-playground/commit/9a34d05b9de3a40fcde737b1f18a7a0be808db63))
* set github token permissions contents to write ([729337f](https://github.com/gladiuscode/github-actions-playground/commit/729337f37074ec3af28d53a0efcf9a749bcda2be))
* set GITHUB_TOKEN value to secret PAT ([00c5e94](https://github.com/gladiuscode/github-actions-playground/commit/00c5e9499aefc8198ccc80959a1d5c058f345369))
* setup .yarnrc.yml with nodeLinker: node-modules ([#2](https://github.com/gladiuscode/github-actions-playground/issues/2)) ([dbe2705](https://github.com/gladiuscode/github-actions-playground/commit/dbe2705cb01e4e03c6f0f55f3e34d4e594ae1076))
* update gitignore to include .idea folder ([1785bbb](https://github.com/gladiuscode/github-actions-playground/commit/1785bbbc6b767237581b2ef62460aeb77436c29e))
* update setup action to read node version from .nvmrc ([c6aa070](https://github.com/gladiuscode/github-actions-playground/commit/c6aa070e1ad1b3c5afa4885b58b5fd92c13b52c5))
* yarn tsc --init ([bb2bece](https://github.com/gladiuscode/github-actions-playground/commit/bb2bece8b654358deade68770c2338042f435fcb))
