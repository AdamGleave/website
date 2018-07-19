+++
abstract = "The majority of online content is written in languages other than English, and is most commonly encoded in UTF-8, the world’s dominant Unicode character encoding. Traditional compression algorithms typically operate on individual bytes. While this approach works well for the single-byte ASCII encoding, it works poorly for UTF-8, where characters often span multiple bytes. Our paper introduces a technique to modify byte-by-byte compressors to operate directly on Unicode characters. We demonstrate this technique applied to LZW and PPM, finding our variant substantially outperforms the original unmodified compressors."
abstract_short = " "
authors = ["Adam Gleave", "Christian Steinruecken"]
date = "2017-03-26"
image_preview = ""
publication_types = ["1"]
publication = "In *Proceedings of the Data Compression Conference*"
publication_short = "Proc. Data Compression Conference"
math = true
selected = true
title = "Making compression algorithms for Unicode text"
url_code = "https://github.com/AdamGleave/UnicodeCompressor"

[[url_custom]]
name = "Summary paper"
url = "papers/2017-unicode-compression.pdf"

[[url_custom]]
name = "Full paper"
url = "https://arxiv.org/pdf/1701.04047.pdf"

[[url_custom]]
name = "Master's thesis"
url = "papers/2016-masters-thesis.pdf"

[[url_custom]]
name = "BiBTeX"
url = "papers/2017-unicode-compression.bib"

+++
