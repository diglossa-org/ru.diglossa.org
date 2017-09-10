---
title: About
type: sanskrit
order: 1
---

> Morpheus for Sanskrit

Now it is in a form of a browser addon (only for a Chromium for a time being), based on simple practical samAsa parser and morphology analyzer. It will be completely rewritten as standalone desktop application, like Morpheus for Greek and Eastern languages. It was my first attempt to write Morpheus, and now this code is deprecated. But the addon itself is still in play.

Morpheus for Sanskrit has three main objectives:

- to break long compound word - samasa - into parts, i.e. padas
- to determine the morphology of each pada
- to show dictionary meaning of a pada

the separation of a compound word - samAsa - to it's padas is as follows.

- the word is divided (according to sandhi-rules (sandhi.js)) into all possible segments - flakes, from any character to any one following it. Impossible flakes are discarded. Then, with the help of a recursive function, probable chains of the flakes are compiled. This is a very resource-consuming procedure. A 50-character word can give 150,000 possible combinations. Depending on the complexity and ambiguity of the padas taking into account sandhi-rules. (vigraha.js)
- indeclinable flakes are allocated into a separate array and so a potentially declined flakes determined
- for every declined flake, it's possible dictionary forms are determined
- separately for verbs (tiNanta.js):
- and names (subanta.js)
- only chains consisting of the padas which have its counterparts in a dictionary, remains
- they are given weights to make the more plausible go in the beginning of a list
- the results returns

as tests for vigraha.js, I have used the decomposition of all the complex words of Bhagavad-gita, available in a reputable source on the network [1], [2]
