---
layout: post
title: Exploring data structure
---

Hi, my name is Long Nguyen. I have a background in mechanical engineering but have always been very interested in software developing. I got my first experience with coding during college and occasionally wrote some macros for Autocad and Solidworks during my time working in the automotive industry. But for now, I am focused on learning Javascript and web development. This blog is dedicated to document my journey to become a software developer with Hack Reactor. 

About a week into the program, we start studying data structure, which is extremely interesting to me. One of the problem to explore on my own was to code a trie, a btree and a red and black tree. For now, I will only focus on the prefix tree. The structure for a trie, also called prefix tree is rather simple. The trie start with an empty node and can accept a string as an input. It will iterate through the string and do 2 things: either store the letter and associate it with a trie that contain the rest of the letter, or if the letter match with the existing letter, it will simply traverse down the trie. An example of the trie is below: 

![alt tag](https://upload.wikimedia.org/wikipedia/commons/thumb/b/be/Trie_example.svg/250px-Trie_example.svg.png)

This is [my implementation](https://github.com/deskian/Prefix-Tree-Implementation) of a trie. There are only 2 function implements, which are find and add. I plan to use this data structure later to build a tab autocomplete, similar to tab autocomplete in terminal command line. In order to do so, I will add a frequency counter. This frequency counter will keep track of the number of time a node is visited when addinga word and return the string one node above the frequency change. The location where the frequency change is where there are more than one options and require more input before it can traverse farther down the trie.