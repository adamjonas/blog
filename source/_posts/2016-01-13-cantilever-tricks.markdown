---
layout: post
title: "cantilever tricks"
date: 2016-01-13 15:45
comments: true
categories: css
---

- `@extend` means that the element just get a comment where the extended
class was previously.

- inline svg styling is preferred -- think of it like an iframe.

- gradients are crazy powerful: You can specify that the white area at the bottom starts at 50% from the bottom as specified here -- `background: linear-gradient(to bottom, rgba(255,255,255,0), rgba(255,255,255,0.8) 50%, rgba(255,255,255,1) );`. And you can repeat it to make like a rainbow effect. Really cool.

- [baseline alignment](https://www.smashingmagazine.com/2012/12/css-baseline-the-good-the-bad-and-the-ugly/)

## SVGs
  - [Chris Coyer's SVG use external references](https://css-tricks.com/svg-use-with-external-reference-take-2/)
  - [svg sprite creation techniques](https://24ways.org/2014/an-overview-of-svg-sprite-creation-techniques/)

## OOCSS
- [Nicole Sullivan](http://www.stubbornella.org/content/)

## Floating
  - if things are longer than expected -> it will overflow with
  abosolutely positioned
  - more predictable behavior for overflow

## border box
  - [`box-sizing: border-box`](http://www.w3schools.com/cssref/css3_pr_box-sizing.asp) includes padding but not margin in the width
  measurements.

## whitespace
  - `nowrap`
