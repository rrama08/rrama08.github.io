---
layout: article
title: Determine or Change a File's Encoding
permalink: /filencode/
comments: true
published: true
---

This is a quick way to understand the encoding of a file and also to convert a file from one encoding to another. I have used on OSX, but will work for unix/linux variants

1. Determine the file encoding type
```
shell>file -I  file1.csv
file1.csv: text/plain; charset=utf-16le
```

2. If needed convert the file to the necessary format
for e.g.
```
shell>iconv -f utf-16le -t utf-8 < file1.csv > file1.utf8.csv
```
