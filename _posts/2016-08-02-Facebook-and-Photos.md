---
layout:     post
title:      Facebook and limitations of Learners
date:       2016-08-02
summary:    In the age of Learning Algorithms, we can still see first hand limitations of Learners.
categories: Machine_Learning Facebook
---

Note: This post is meant to be a general explanation of learning algorithms, and their 
limitations for a lay person. 

This past weekend my wife, Anna, was posting quite a few pictures to Facebook after we 
went on a trip together and she noticed something very peculiar when she was uploading to 
Facebook. Almost every picture had Anna mislabeled as another friend of hers, lets call 
her Julie. 

This then led my wife to ask "Why is Facebook doing this?". Isn't this an interesting 
question?! The first step to figuring out a solution is understanding the problem. 

So let's talk a little bit about what happens with a classical learning algorithm 
(learner), and  the three basics a learner needs to operate:

* The algorithm itself
* A well manicured training dataset
* A verification/testing set.

For the purpose of explanation, we are going to approach the algorithm with a "black box" 
mentality. Which means we don't care what happens with the algorithm, we just care what 
goes in and what comes out.

When we feed the training dataset to the learning algorithm, it will learn what it is designed to,
for our example, we will say that a training set for Facebook, is likely all pictures that have
been user labeled by a human as a Facebook user would be a terrific training set for determining 
what name to give a picture. Assuming that everything goes well, we can then feed pieces of our testing dataset.
In this case, we would just send the learner pictures of people in Facebook, and see what labels the 
algorithm would affix to the pictures. If it affixed correct users at a high rate of correctness,
we would know that the algorithm worked well.

From here on out, we would now feed pictures to the algorithm, with the hope that it would label 
the picture with the correct user. Knowing this, we can figure out what has happened with the
mislabeling of Anna's pictures. Why had Anna been labeled as Julie? It all comes down to the 
training dataset. We have a training dataset problem, and the thing is Facebook doesn't necessarily
know about it. With so many users, and so many people uploading pictures to Facebook, it's 
pretty amazing how good the recognition is now, but there is a limitation to learning algorithms.
The limitation of learners , if we have an inaccurate dataset, or in our case a dataset
without enough data, we will have a learned algorithm that will produce inaccurate results.

So how do we "help" Facebook to recognize Anna's face? Let's look at three approaches to helping
to manipulate Facebooks data.

1. We remove all references to Julie on Anna's photos.
2. We add Anna's reference to all photos that have Julie referenced.
3. We manually label all pictures which we are in.

Many times, we may be tempted to perform one or two of the above, but I would like to make an argument 
that it is important to then do all of the above, for the purpose of modifying the learner's training set.

1. We remove all references to Julie on Anna's photos.
	- If we do this, we will remove all references of Julie to Anna's photo. But this does not 
	affect what the algorithm has already learned. As we continue to add photos, the information
	the learner had been trained on doesn't change at all. So we can predict that the learner
	will continue to reference Julie for Anna's photos well into the future.
2. We add Anna's reference to all photos that have Julie referenced.
	- This is a move in the right direction. We are now adding to the training set, by not only 
	removing Julie from photos, but giving information to the algorithm to use in the future.
	
3. We manually label all pictures which we are in.
	- This move would be ideal for the future, but depending on the complexity of the algorithm
	it may slightly inhibit learning. Given a more complex learner, removing pictures that have 
	already been correctly identified, could be counterproductive to the learner. We are assuming 
	a basic learner, so manually labeling all pictures won't be counterproductive, and will just be 
	a bit of effort. 

Hopefully, this gives a little better idea of what you can do if you encounter such a problem.
I hope this shows a smidgen into what a learner does. Learners are much more complex than this, 
but most are still very reliant on the dataset that they are presented for learning.
