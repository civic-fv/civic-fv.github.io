---
#(don't forget to change file name to id of software in question)
# You MUST Modify these:
id: romp # this should be the entry key in the _data/software.yml
title: ${the full title of the software}
author: Andrew Osterhout, Ajantha Varadharaaj, Ganesh Gopalakrishnan
date: 2023/05/08
published: true   # set to true to make it public
tags: [software, romp] #, ${additional tags -optional-}]
# modify these if you want to:
categories: [software ] #, ${additional catagories}]
# image: ${image url}
# DON'T MODIFY THESE:
layout: info-post
permalink: software/:basename
info_type: software
---

### romp: a parallel random walkign model checker

test content

this allows for limmited multimedia support, and you will need to either know how to use jekyll or link it with absolute URI from an external source to get it to work.
The later is recomended fo rmost people. 

gobldey gook

test image w/ jekyll liquid comments (image is in the `/site-src/images` directory already)

![test-image]({{ "/images/DecidabilityDiagram.png" | absolute_url }})


test image w/ external media:

![Test-Image-2](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSXqq3j05ykEU69GBIwyuuuiFhePdmiIIk3zMJ6gfim7Sv3yaJ0v86GjGf4_W9P-BqgHjA&usqp=CAU)


that is all for now
