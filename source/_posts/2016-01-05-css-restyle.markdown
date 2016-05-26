---
layout: post
title: "CSS restyle"
date: 2016-01-05 10:13
comments: true
categories: CSS
---

#

## Block, Element, Modifier (BEM)
  - [site](https://en.bem.info/)

  - containers and objects are more modular
  - layouts aren't reused

  - clearfix issue
    - using psuedo element hack

  - media element
    - object in css methodology

  - containers
    - an element that can contain other things -> more container-ish
      - doesn't usually contain other elements

    - any decendents are named-spaced of the parent
      - e.g. `.sample-object` and `.sample-object__child`
      - child is indicated by double underscore
      - you should expect to see similar classes up the DOM
        - e.g. `<div class='level'><div
        class='level__inner'></div></div>`
    - options
      - `<div style-color='red'>`
      - `<dic data-count='16'>`
    - extensions
      - modifiers have double dash
      - you should expect to see similar class within the same div
        - e.g. `<div class='module module--island module--island--cap'>`
    - modules
      - usually have a head/body/footer
      - provides margin around it, background and borders

  - object
    - an element that doesn't contain other elements as opposed to
    objects which are more like containers
    - built to fill the width they are in, without explicit width
    - maybe a place where `!important` can live given that other
    elements won't live within it.
    - expect more legos than objects

  - levels
    - makes vertical organization of the grids
    - they stack on top of eachother - levels of a building
    - centers a container in a strip that goes across the page

  - utility class
    - namespaced with url
      - with margin on the bottom
      - `utl__m--bxl` => utility, margin, bottom extra large


 ## ?
  - how is this going to work with vendors (like icons)
  - vertical height for grid

  - user bar is a layout
    - list horizontal
  - level for bubble bar
  - remove rows and cols from markdown to json parser

