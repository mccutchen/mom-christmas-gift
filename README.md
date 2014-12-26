Your Christmas present
======================

Hey Ma,

I sent this email to you way back on April 30, 2014:

> I have an idea for something to try.  Are there any paintings or photographs
that leap to mind if I ask you to name a favorite or some favorites?

This, finally, is the result of that "idea for something to try." From your
response I picked photo *V-J Day in Times Square* and Van Gogh's *Irises*
as the inputs to a little computer program I wrote.

*(Note: it took me a while to realize that there were at least two candidates
for Van Gogh's Irises, and I just picked the one whose colors I liked best. I
really hope it's the one you had in mind!)*

That program (whose source code you can see above), took these inputs:

![](https://raw.githubusercontent.com/mccutchen/mom-christmas-gift/master/examples/input-example.png)

… and produced these three images:

![](https://raw.githubusercontent.com/mccutchen/mom-christmas-gift/master/examples/output-example.png)

Now, you might notice that I took two perfectly beautiful images and turned
them into something abstract and weird. I hope there's still something
beafutiful about them, but I can sometimes get captivated by the process
involved and have a hard time looking at the results with clear eyes.

Also, I have no idea how they'll look when printed on canvas. I hope they turn
out nicely, though!


Some technical details, if you're interested
--------------------------------------------

Every time you run the program, the output will be different. You give it one
or more input images and it builds a [Markov chain][markov-chain] based on the
colors in those images and uses that model to produce a different output image.

This is a horrible oversimplification, but the Markov chain basically lets me
take a color from the input image and ask what color is most likely to come
next.

So, to generate an output image, we start at a random point on a blank canvas,
pick a random starting color from the Markov chain built from the input
image(s), and slowly fill in the canvas by asking the Markov chain for the next
color in the sequence. Each new color chosen is statistically likely to follow
the previous color.

This gets a little interesting when, for the middle output image above, we feed
*both* input images into the Markov chain, and the generated image obviously
has features from both images.

I hope that makes at least a little bit of sense.  Check out
[markovangelo.py][markovangelo], above, if you want to know what the code looks
like.


And a movie, to boot!
---------------------

So, because there is so much variation every time you run the program, I had to
generate a lot of output images to find ones that I liked. This was especially
true for the "combined" image in the middle, which relies so much on chance
that it's actually pretty rare to get a good mixture.

I compounded this problem by first generating a whole lot of images at what
turned out to be an unprintable size when I first picked the three I wanted to
print, so I had to start over.

At the end of all of this, I had more than 3,000 generated images. So I made a
really long, really boring movie out of them:

https://vimeo.com/115136250


### Love,

### Will

P.S. If you're interested and feel like experimenting with other images, this
should be relatively easy to run on your own computer.  I'd be happy to help
with that, if you're interested.


[markov-chain]: http://en.wikipedia.org/wiki/Markov_chain
[markovangelo]: https://github.com/mccutchen/mom-christmas-gift/blob/master/markovangelo.py
