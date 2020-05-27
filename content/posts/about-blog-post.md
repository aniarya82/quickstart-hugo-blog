---
title: "About Blog Post"
date: 2020-05-27T10:58:13+05:30
draft: false
tags: ["blog", "hugo", "first"]
---

## About Hugo

So I was browsing open source projects when I came across CNCF's project promethous. It was majorly written in Golang.
One of its contributor [bwplotka](https://github.com/bwploatka) was using Hugo for his static blog. It looked neat and easy to setup.
Then I look at my current blog page and it was messed up badly.

## Setting up new blog

So immediately I looked at bwplotka's [blog](https://github.com/bwplotka/my) repository. There I got started to look for new [themes](https://themes.gohugo.io/). Here I shorlisted two of themes:

- [Anatole](https://themes.gohugo.io/theme/anatole)
- [Paper](https://themes.gohugo.io/theme/hugo-paper)

### Anatole

I cloned the repo and started fiddeling with it. Running up the exampleSite in localhost and playing with the config file to personalize it according to my needs. Once things looked good in localhost. It was time to host it. My previous blog was hosted using Github Pages feature, so this one too will go at the same place.

But Hugo's documentation related to hosting was confusing to me. As it talked about a public folder, which I was unable to find. in the anatole theme's repository. At that moment I didn't realised it was just a theme repository and was meant to be included in other project folder as a dependency.

Later I got about to quick start section of Hugo docs. There I followed step by step and understood the concept of how themes are to be used. Then with modifiying the config files I was able to update my blog successfully.
