---
layout:     post
title:      Facebook and limitations of Learners
date:       2016-08-03
summary:    In the age of Learning Algorithms, we can still see first hand limitations of Learners.
categories: Machine_Learning 
---

Note: This post is meant to be a general explanation of learning algorithms, and their limitations for a lay person. 

This past weekend my wife, Anna, was posting quite a few pictures to Facebook after we went on a trip together and she noticed something very peculiar when she was uploading to Facebook. Almost every picture had Anna mislabeled as another friend of hers, lets call her Julie. 

This then led my wife to ask "Why is Facebook doing this?". Isn't this an interesting question! The first step to figuring out a solution is understanding the problem. 

So let's talk a little bit about what happens with a classical learning algorithm (learner), and  the three basics a learner needs to operate:

* The algorithm itself
* A well manicured training dataset
* A verification set.

For the purpose of explanation, we are going to approach the algorithm with a "black box" mentality. Which means we don't care what happens with the algorithm, we just care what goes in and what comes out. 