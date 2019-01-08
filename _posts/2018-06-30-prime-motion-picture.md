---
layout:     post
title:      The First Prime Motion Picture
date:       2019-01-08 11:21:29
summary:    The First Prime Motion Picture
categories: jekyll pixyll
---

![](https://i.imgur.com/Bq6NeVp.gif)

Every frame of this video is a prime number with 3100 digits. Additionally, this video is a recreation of the first ever motion picture, created by [Eadweard Muybridge in 1878 at Stanford to study a horse’s gallop](https://en.wikipedia.org/wiki/Eadweard_Muybridge). 

![](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d2/The_Horse_in_Motion_high_res.jpg/2880px-The_Horse_in_Motion_high_res.jpg)


The inspiration to create this motion picture came from a video on [Numberphile](https://www.youtube.com/watch?v=fQQ8IiTWHhg) I watched a few months ago about a very special prime: in 1996, James McKee was a mathematician departing Trinity Hall at Cambridge and wanted to honor the tradition of bestowing a farewell gift on the college, he devised a prime number that also depicted the University logo. After seeing the video I wrote a short python script to turn images into primes. The script takes an image and converts it into a sequence of 1’s and 8’s (1’s for the lighter parts of the image and 8’s for the darker parts). It then randomly changes a few digits in the image and tests for primality using the [Miller-Rabin test](https://en.wikipedia.org/wiki/Miller%E2%80%93Rabin_primality_test). This test quickly excludes numbers that are not prime and finds out the ones that are more likely to be prime. Finally, you just need a method to verify the numbers that are actually prime in the group that was pre-selected using the Miller-Rabin test. 

If you want to create your own prime images the code is available [here](https://www.github.com).

A few open questions worth exploring later:
\\
- Are there any special compression/encryption properties for a video where every frame is a prime?
\\
- Would it be possible to have a similar video but in which if we join every frame one after the other into a single number, it would also result in a prime?
\\
<!-- I searched a bit online and this also seems to be the first ever motion picture made solely with prime numbers :)  -->