# SuperEdge Documentation

This repo contains the assets used to build the SuperEdge website at https://superedge.io.

## Running and developing the website locally

### 1. To run the site locally, you need to install:

* [npm](https://www.npmjs.com/get-npm)
* [Hugo (extended version)](https://gohugo.io/getting-started/installing) with the version specified in the [netlify.toml](netlify.toml)


### 2. Clone this repo and its submodules
```console
git clone https://github.com/superedge/website.git
cd website
npm install
git submodule update --init --recursive --depth 1
make load-submodule
```

### 3. Serve the site locally
```console
make serve
```
Open http://localhost:1313 in your browser to see the running site. Any code change to the site content will immediately be updated to the running site.

## How to modify the documentation

Most of the documentation lives in:
* Chinese: `content/zh/docs`
* English: `content/en/docs`

### Other assets
* **Attached images** in the docs should be put in `static/images/docs/`.
* **Sample yaml config** should be stored as yaml file in `content/<en/zh>/examples/` and reference using `codenew` shortcut.

For example,
```
{{< codenew file="serviceGroup/edge-health-admission.yaml" >}}
```

## Deployments and PR previews

Commits to the `main` branch will be automatically published to the https://superedge.io by Netlify.

PR triggers Netlify to build a preview site and return the site link on the PR page.
