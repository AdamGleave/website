---
abstract: The majority of online content is written in languages other than English,
  and is most commonly encoded in UTF-8, the world’s dominant Unicode character encoding.
  Traditional compression algorithms typically operate on individual bytes. While
  this approach works well for the single-byte ASCII encoding, it works poorly for
  UTF-8, where characters often span multiple bytes. Our paper introduces a technique
  to modify byte-by-byte compressors to operate directly on Unicode characters. We
  demonstrate this technique applied to LZW and PPM, finding our variant substantially
  outperforms the original unmodified compressors.
abstract_short: " "
authors: [AdamGleave, Christian Steinruecken]
date: "2017-03-26"
image_preview: ""
math: true
publication: In *Proceedings of the Data Compression Conference*
publication_short: Data Compression Conference
publication_types: ["1"]
selected: false
title: Making Compression Algorithms for Unicode Text
url_code: https://github.com/AdamGleave/UnicodeCompressor
url_pdf: https://arxiv.org/pdf/1701.04047.pdf
links:
- name: Extended Abstract
  url: papers/2017-unicode-compression.pdf
- name: Master's thesis
  url: papers/2016-masters-thesis.pdf
---

