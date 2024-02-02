---
layout: post
title:  "Using Python to Visualize CTE Risk"
date:   2024-02-01 00:00:00 -0500
image: /assets/images/placeholder-image.png
---

Unfortunately, brain injuries and the chronic degenerative conditions that often come about as a result of them are woefully misunderstood by the general public, even as concerns about player safety and delaying the age of tackle football come more and more into the modern zeitgeist.

<br>

The motivation of this post is to augment, specify, and possibly correct our current belief systems with data obtained through Monte Carlo simulation. This type of simulation proves great for this purpose - we are not trying to publish extremely rigorous research, nor are we going to run little kids through the wringer to measure the effects of brain injury on their future development. Instead, we are going to use our common sense, a little bit of statisics, and some simple data visualization to put the risks of brain injury into the realm of "easily understandable". 

<br> 

<p style="color: #0D99FF;">Skip down to the next blue text if you don't care about the intricacies of Monte Carlo </p>

<br>

First, what is Monte Carlo simulation? It is a way of gaining insights from real world events by specifying models that imitate these situations and running them through many, many trials. One way to understand this is as such: suppose you have a fair coin with heads and tails, and you (somehow) don't know what the probability of heads and tails is given a completely random flip. You could approach the true probability given enough trials. That is, you flip your perfectly fair coin one thousand, one million, approaching an infinite amount of times, to eventually obtain a fifty percent chance of either heads or tails. Frankly, this is a trivial example and is not particularly enlightening nor interesting. 

<br>

However, the true beauty of Monte Carlo simulation comes from messy problems that are difficult to abstract. 

<br>

Going back to the real world, the perfect game that comes to mind is poker. Say you have a given hand and flop at a table with n people all with different personalities and skillsets. While the personality and the skillset portion is accounted for entirely by your ability to read their tells, your ability to succeed in the situation is based on how closely you can approximate the Game Theory Optimal outcome in conjunction with your reads. But where does GTO even come from?

<br>

GTO, in constrast to how poker is actually played, is "clean" and "pure", derived entirely from the realm of computerized mathematical analysis, in which Monte Carlo simulation is one of the oldest and best known tools used to solve these types of problems (although compared to modern techniques, it's admittedly pretty clunky). One way to think about our current understanding of GTO is that we threw every tool in the book (including Monte Carlo) at every possible hand for every possible situation, recording how well each permutation does. Evidently, this paints a much better picture regarding the true chance you win a given hand, much more so than counting your outs or other simplified heuristics.

<br>

Thus, the foundation of poker play at the highest levels is simply dictated by the "truth". *Which play is truly the best under all criterion in a given situation?* And the way that we have managed to reveal a bit of this truth has been through tools such as Monte Carlo simulation (and its much cleverer cousins).

<br>

<p style="color: #0D99FF;">Skip to here if you don't care about the intricacies of Monte Carlo </p>

<br>

Okay. So what does any of this have to do with brain injuries? Simply put, we can create a model that imitates how a typical *(not average!)* person may experience brain injuries over their lifetime. Using a "model first, inference later" thought process, we can get a pretty close approximation of how people really experience these sorts of events in their real lives using statistics such as the average number of car crashes a given person experiences in their life. 

<br>

After this baseline is established, this is where things start to get more interesting. We can adjust our model along a number of dimensions such as gender, sport/position played, length of career, level of play, risk preferences, and much, more. Thus, our model will be flexible, allowing us to adjust based on the sorts of insights we want to glean. 

<br>

A pretty natural place to start would be to define a few time series in Python. Since we now know that CTE risk is highly correlated with total force exposure over time, we'd likely want to record the total force accumulated in one time series. The other time series would simply show the severity of each impact. The motivations for including both are extremely strong. CTE is a devastating, cruel disease with severe ethical implications for how *all* sports should be conducted in modern society. Tracking the force of each impact is also imperative as there is a threshold for which isolated impacts can cause death or increased risk for diseases such as Multiple Sclerosis, Parkinson's, Alzheimer's, and many more. 

<br>

Using the recent 2023 study by 
