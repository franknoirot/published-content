---
title: Using Obsidian as a CMS
category: technology
growthStage: seedling
created: 2022-06-20
updated: 2022-06-20
description: I'm testing out using Obsidian as my CMS to power my personal website right from within my knowledge garden.
---
Okay I think I have this working well now.

I've created a blog site using NextJS and Content Layer, and placed an Obsidian vault in the repo to act as my content source. I broke this vault off into its own Git submodule and placed it in a private GitHub repo, then placed the `/public` directory of that vault into yet another submodule pointing to a *public* GitHub repo

Then I removed the private stuff from the vault in my site's repository, leaving only the public stuff. I have it set up so that I `--recurse-submodules` wheen publishing my vault to GitHub, so whenever I push changes to my personal notes I push changes to the public contents. I have a build hook set up for Netlify on my public content repository that fires on every push to `main` using GitHub Actions.

A little mind-bending, but what it means is that I can take notes like normal in Obsidian, backing up my notes as I like. If I want to publish a note or other thought I simply move the note into the appropriate folder and make sure it has the right fields in its frontmatter, then when I back it up the changes in the public directory will be pushed, triggering a rebuild of my website!

All of this effort was to have my website be a true subset of my personal Obsidian knowledge graph, the parts of my second brain that are ready to show the world, without losing any of the niceties of working in Obsidian.