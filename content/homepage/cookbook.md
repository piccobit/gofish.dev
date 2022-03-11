---
title: "Fish Food Cookbook"
date: 2022-03-11
anchor: "cookbook"
weight: 40
---

Fish food is a package definition written in Lua. It can be created with `gofish create <food>`. Fish
food use the Lua runtime to provide simple scripting capabilities that other markdown languages
cannot provide on their own.

## GoFish terminology

| Term    | Description                           | Example                                               |
|---------|---------------------------------------|-------------------------------------------------------|
| Food    | The package definition                | /usr/local/Fish/Rigs/github.com/tinned-fish/fish-food |
| Rig     | A git repository containing fish food | /usr/local/Fish/Rigs/github.com/tinned-fish/fish-food |
| Barrel  | All fish food are installed here      | /usr/local/Fish/Barrel                                |

## An introduction

GoFish uses git for contributing to the project.

GoFish installs to the Barrel and then symlinks some of the installation into /usr/local so that other
programs can see what’s going on. We suggest you use `find` on a few of the food in your Barrel to
see how it is all arranged.

Packages are installed according to their fish food, which are written in Lua and live in `/usr/local/Fish/Rigs/github.com/tinned-fish/fish-food`.

## Basic instructions

Make sure you run `gofish update` before you start. This prepares your Rigs by bumping them to the latest revision.

Before submitting a new food, make sure your package:

- isn’t already in fish-food
- isn’t already waiting to be merged (check the pull request queue)
- is still supported by upstream
- has a stable, tagged version (i.e. not just a work-in-progress with no versions)

Before submitting a new food, make sure you read over our [contribution guidelines](#contributing).

## Create the fish food

```bash
gofish update # make sure we've got a fresh checkout of master
vim $(gofish create foo)
```

## Test the fish food

...By installing it!

```bash
gofish install --log-level 9001 foo
```

## Manuals

GoFish expects to find manual pages in `/usr/local/share/man/`, not in `/usr/local/man/`.

## A quick word on naming

Name the food like the project markets the product. For example, use `pkg-config` over `pkgconfig`,
and `sdl_mixer` over `sdl-mixer` or `sdlmixer`.

## Commit

Everything is built on git, so contribution is easy:

```bash
eval $(gofish tank)
cd $GOFISH_DEFAULT_RIG
# Create a new git branch for your food so your pull request is easy to
# modify if any changes come up during review.
git checkout -b <some-descriptive-name>
git add Food/foo.lua
git commit
```

## Fork

Now you just need to push your commit to GitHub.

If you haven’t forked GoFish yet, go to the fish-food repository and hit the Fork button.

If you have already forked GoFish on GitHub, then you can manually push (just make sure you have been pulling from the tinned-fish/fish-food master):

git push https://github.com/myname/fish-food/ <what-you-called-your-branch>

Now, open a pull request for your changes.

- One formula per commit; one commit per formula
- Keep merge commits out of the pull request

