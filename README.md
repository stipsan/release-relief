# release-relief &middot; [![CircleCI Status](https://img.shields.io/circleci/project/github/stipsan/release-relief.svg?style=flat-square)](https://circleci.com/gh/stipsan/release-relief) [![npm version](https://img.shields.io/npm/v/release-relief.svg?style=flat-square)](https://www.npmjs.com/package/release-relief) [![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg?style=flat-square)](https://github.com/semantic-release/semantic-release)

It's easy to burnout when you're being an Open Source maintainer. Reducing chores around releasing helps with the fatigue.

I'm making this package to help reduce boilerplate and make it easier to setup a semantic-release flow for my npm published packages.
My decisions on what CI to primarily use and commit conventions is specific to my needs. I don't expect others to use this package directly so documentation will be scarce.
Should this change then feel free to open an issue with any question you might have if this package is helpful to you :smile:

# Setup

Add `release-relief` to your devDependencies:

```bash
yarn add --dev release-relief
```

Add the following to your package.json:

```json
  "scripts": {
    "changelog:preview": "sr-changelog",
    "changelog:commit": "sr-changelog commit",
    "semantic-release": "semantic-release pre && npm publish && semantic-release post"
  },
  "release": {
    "analyzeCommits": "semantic-release-tamia/analyzeCommits",
    "verifyConditions": "condition-circle",
    "generateNotes": "semantic-release-tamia/generateNotes",
    "verifyRelease": "semantic-release-tamia/verifyRelease"
  },
```

Then setup your CI, I prefer circleci which is why [condition-circle](https://www.npmjs.com/package/condition-circle) is set as the `verifyConditions` step, even on [this repo](https://github.com/stipsan/release-relief/blob/f25c65ddff64aff74555db92f80197bc3a9c7352/.circleci/config.yml#L24).

Read more about the setup here: https://github.com/tamiadev/semantic-release-tamia
