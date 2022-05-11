# HAKONIWA Web Setup

## Setup

    git clone -b web https://github.com/toppers/hakoniwa.git
    cd hakoniwa
    git submodule update --init

## Preview on localhost

    $ hugo server -D

or Reviewing the generated content.

    $ hugo --minify --baseURL="$(pwd)/public"

## Requirements

[Install Hugo](https://gohugo.io/getting-started/installing/) (v0.98.0 or later)

## or Open in Gitpod

Click the button below to start "web branch" development environment:

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/toppers/hakoniwa/tree/web)

## Create new article

    $ hugo new hoge.md

### e.g. in `docs` section

    $ hugo new docs/hoge.md

if only text article, you can remove `images` elements at front matter.
