---
layout: post
title:  "NLP is Cool"
date:   2019-07-08 22:17:56 -0400
categories: nlp
---

<!-- At my work (Northrop Grumman), a large portion of our project involves extracting information from unstructured text. Cybersecurity reports, to be more specific. Why? Well, imagine you're an analyst whose job is to handle security events for an IT system. Most of them will probably be one and done - a few of them need more digging. That's when you need to read intelligence reports, from the thousands that go out every few months. It's a classic NLP problem, applied to a different domain. 

There's a lot of info you could extract with some basic rule-matching - IoCs, threat actors, malware aliases, etc. Okay, but where's the NLP?  

Another reason NLP is cool: Text is information-dense. Much more than, say, the pixels of an image. -->


This summer I learned a little about Natural Language Processing (NLP). I thought it was pretty cool (and still do), so I want to try and summarize what I've learned about this field, in addition to diving deeper into some specifics.

Some quick reasons why I think NLP is cool:
1. Deciphering human text is one of those things that is easy for us, but notoriously hard for machines.
2. Text is information-dense. Much more than, say, the pixels of an image.
3. Turing test.

So, what can NLP be used for? It's not too hard to think of some big ones. Reading documents, extracting knowledge, discovering knowledge, using that knowledge to answer questions. These are all [ongoing fields of research][NLP progress].

[NLP progress]: http://nlpprogress.com/

Currently, NLP models can be roughly divided into two categories: broad coverage + shallow understanding, or narrow coverage + deep-er understanding. There's debate as to how much today's models [truly understand text][meaning v semantics]. It may be instructive to explore techniques from each side of this spectrum.

[meaning v semantics]: https://medium.com/huggingface/learning-meaning-in-natural-language-processing-the-semantics-mega-thread-9c0332dfe28e
![The NLP hierarchy](/images/NLP_hierarchy.png)

Early NLP used rule-based models to parse text. [See SHRDLU][SHRDLU]. Problem was, they weren't very robust. The 80s and 90s saw statistical models that took advantage of broad patterns in text. This is useful for things like spam classifiers or document retrieval. But those methods disregard things like word order, and loses much of the fine-grained meaning of sentences. Nowadays we see a lot of machine learning models that leverage the huge amount of raw text data, and learn representations that can be fine-tuned on many specific tasks.

[SHRDLU]: https://en.wikipedia.org/wiki/SHRDLU

I'm going to dive into **information extraction**, which is still huge, but a smaller subset of NLP to talk about. It would be cool to have an algorithm that extracts useful information from text. The meaning of 'useful information', of course, depends a lot on the end goal. There are a couple of tasks that generalize pretty well across domains: 

* **Named entities**: names of things like people, places, dates and times.
* **Relationships**: between (usually two) things, like "is married to".
* **Concepts**: more abstract, requires a dictionary definition. Could be part of a hierarchy, with synonyms, categories, etc.

These aren't rigorous definitions, but you get the idea. Now I'll dive a little more into each of these tasks.

# Named-entity recognition

This is probably one of the more well known tasks, since it has strong support from big NLP libraries: NLTK, spaCy, and StanfordNLP. NER is usually the last step of a common feature extraction pipeline: tokenize, part-of-speech (POS) tags, dependency parsing, then NER. 

![NLP pipeline](/images/NLP_pipeline.png)

<!-- You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/ -->
