---
layout: post
title: The logic of feeling&#58; Teaching computers to identify emotions
author: Gabe Cherry
author_link: https://cm.engin.umich.edu/contact/
comments: true
tags: interview emotions machine-learning
---
<i>This is an interview with Professor Emily Mower Provost that was first published by The Michigan Engineer News Center.</i>

{% include figure.html url="/assets/2018-12-20/emily-provost-profile.png" description="Emily Mower Provost, Associate Professor of Electrical Engineering and Computer Science, speaks at the Ada Lovelace Opera: A Celebration of Women in Computing event. Photo: Joseph Xu" %}
Using machine learning to decode the unpredictable world of human emotion might seem like an unusual choice. But in the ambiguity of human expression, U-M computer science and engineering associate professor Emily Mower Provost has discovered a rich trove of data waiting to be analyzed.

Mower Provost uses machine learning to help measure emotion, mood, and other aspects of human behavior; for example, she has developed a smartphone app that analyzes the speech of patients with bipolar disorder to track their mood, with the ultimate goal of helping them more effectively manage their health.

<b>How do you quantify something as ambiguous as emotion in a field where, traditionally, ambiguity is the enemy?</b>

As a machine learning researcher, we generally expect data examples to be accompanied by clear and unambiguous labels. The task is then to discover new ways to associate the patterns in the data with their labels.

But in emotion modeling, the whole idea of “unambiguity” is invalid. Ambiguity is a natural component of how we express ourselves and contributes to the richness of our interactions. Emotion modeling research asks how we can quantify the ambiguity in human expression and use that information to do something useful.

<b>Can you give an example?</b>

Sure–consider an example of one person talking loudly to his/her friend. An outside observer might perceive that the interaction is positive. Someone else may note the volume of the interaction and, instead, perceive that the interaction is negative. Who is right? To some extent they both are.

There’s useful data not just in the different interpretations, but in the degree of variation between the interpretations. We have been researching methods to predict how groups of people, rather than a single person, would perceive an emotional display. We can turn them into multi-dimensional descriptions called “emotion profiles”, which enable us to express ambiguity mathematically.

<br/>
<blockquote><b>&ldquo;We, as engineers, must change the way we think about modeling these types of behavior, asking what we can quantify and then investigating how we can use these measures to understand more about the individuals with whom we work.&rdquo;</b><cite> - Emily Mower Provost, EECS-CSE associate professor</cite></blockquote>
<br/>

<b>What sorts of adjustments did you have to make to transition your work to the medical field?</b>

One big difference is that, in machine learning, we’re often very comfortable speaking about data labels—a description of the information that is present in a given data source. For example, we might say that a given interaction is “positive” or that a given image contains a cat.

In the medical community, the notion of a label may not be valid. For example, an individual may be diagnosed with bipolar disorder, but the label of “bipolar disorder” does not describe who that person is or even what that person may be doing or thinking at any given time.

We, as engineers, must change the way we think about modeling these types of behavior, asking what we can quantify and then investigating how we can use these measures to understand more about the individuals with whom we work.

<b>How do you think machine learning will change the medical landscape in the years ahead?</b>

Machine learning is in such an exciting place right now. For so long, we’ve worked to demonstrate what machine learning tools can do, demonstrating that we can automatically predict aspects of health, and, critically, demonstrating that this is a worthwhile thing to do.

Now we get to ask how we can help: how we can help reduce burdens on individual patients, on caregivers, on the healthcare system. We get to ask how we can learn more about health and wellness by stepping outside of laboratory settings and measuring people in their own environments.

