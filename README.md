# Learning Lighthouse CI

Just one of the things I'm learning. <https://github.com/hchiam/learning>

Have Lighthouse CI tool run with Travis for every commit or PR to a web app project hosted on GitHub.

## Results upon commit

[![Build Status](https://travis-ci.com/hchiam/learning-lighthouse-ci.svg?branch=master)](https://travis-ci.com/hchiam/learning-lighthouse-ci)

Automated test run info here: <https://travis-ci.com/hchiam/learning-lighthouse-ci> (or click on the badge above)

Example PR here (click "View details"): <https://github.com/hchiam/learning-lighthouse-ci/pull/1#issuecomment-555602268>

## Setup steps (after you `git clone` this repo)

1. (Steps coming soon.)

## Setup steps (from an empty folder)

1. For `lhci autorun` to work, you need a web app set up that has things like a dist or public folder, etc. To do that, you can run a one-liner command to set up a React app:

```bash
# cd to desktop or containing folder
create-react-app my-app
```

1. To make sure it's working locally:

```bash
cd my-app
npm start
```

and in another CLI tab:

```bash
cd my-app
npm install -g @lhci/cli@0.3.x
lhci autorun
```

1. The key is [setting up](https://github.com/GoogleChrome/lighthouse-ci#quick-start) the Travis file `.travis.yml`:

```yml
language: node_js
node_js:
  - 10
before_install:
  - npm install -g @lhci/cli@0.3.x
script:
  - npm run build
  - lhci autorun
addons:
  chrome: stable
```
