---
ID: 5202
post_title: Debounce by requestAnimationFrame
author: James DiGioia
post_date: 2016-08-28 17:33:13
post_excerpt: ""
layout: post
permalink: >
  http://jamesdigioia.com/debounce-by-requestanimationframe/
published: true
_format_link_url: >
  http://jamesdigioia.com/gistpens/debounce-by-requestanimationframe/
---
Not sure this is best, but using Kefir's `withHandler`, this debounce's the values from the stream to only emit the latest value on `requestAnimationFrame`.