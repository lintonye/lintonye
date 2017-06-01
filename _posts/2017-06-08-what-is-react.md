---
layout: post
last-modified: '2017-06-08'

title: "What is React?"
subtitle: "TODO React terms explained in plain English"
#cover_image: "navigation-custom-transition/transit.jpg"

excerpt: "TODO Should designers code? This is an eternal question."

author:
  name: Linton Ye
  twitter: lintonye
  bio: Freelance full-stack developer in BC Canada (GMT-8). Android, React Native, Node.js, MongoDB, PostgreSQL. <a href="mailto:linton@jimulabs.com">Contact me.</a>
  image: linton.jpg
---

People are talking about React, ReactJS, React.js, React Native, [React Sketch.app](TODO) etc. But to my surprise, many of them are not aware of what React really is and the precise differences between those terms.

This post is my attempt to solve that.

If you are a designer

I'm going to try to explain those concepts with some doodles. As a designer, if you have heard about React many times


If you are a designer who has heard React many times from your developers or clients, but you are not familiar with code, this post is for you.



I'll attempt to explain the terms in React family in plain English and some doodles. This post is for those of you who are not familiar with coding but have heard things like DOM, jQuery and React many times from developers or clients.

I'll only explain concepts with as less code as possible. But I hope what you'd learn becomes a solid foundation when we actually dive into code in future posts.

# Prerequisites

# Learning goals
After reading this post, I hope you could answer the questions below:

- What is React? Where does it fit in the development of an app?
- How is React different from jQuery?
- What are the core ideas in React?
- What do ReactJS, React Native, React Sketch.app have in common? How are they different from each other?

# What is React?

On the [official website](TODO) of React, it is defined as "a JavaScript library for building user interfaces".

Hmm... user interfaces... it sounds relevant to design. But what's special about it? Don't we already have jQuery? Why do we need a new library?

Let me start by explaining an important term: DOM.

## DOM
Well, DOM is Document Object Model. Get it? It's an object model for the document.

Forget about it. Say hi to our super model Domo!

Before you roll your eyes... It's not a model like this:

![super model](/images/what-is-react/super-model.jpg)

But more like this:

![tree man, saying "I am gr..."](/images/what-is-react/01-tree.png)

A tree? Yup a tree. Oddly enough, a lot of things in your computer look like a tree[^1].

As a model, Domo works in the studio "Web Browser" and his favorite thing is to pose in front of Browsera the artist who paints a portrait (or perhaps millions of portraits).

![Domo poses, Browsera draws](/images/what-is-react/02-domo-browsera.png)

The portraits are what we see in Chrome, Firefox or IE when visiting a website. A developer's job is to tell Domo what to wear and what pose to make, which determine what those portraits look like. Libraries like jQuery or React are the tools a developer uses to communicate with Domo.

TODO do we need the section below?
## DOM: A slightly more technical intro
In reality, a developer writes HTML which gets turned into a DOM tree, a hierarchical data structure living in a web browser. What is a hierarchical data structure? You can imagine it as a whole bunch of boxes inside boxes.

![boxes inside boxes](/images/what-is-react/02.1-box-in-box.png)

For convenience, these boxes are represented as a chart as below which looks remotely like a upside-down tree:

![a DOM tree](/images/what-is-react/02.2-dom-tree.png)

The browser then renders a web page using the information in the DOM tree, just as Browsera paints a portrait according to Domo's pose. The developer can write JavaScript code to communicate with and update the DOM tree which, as the result, changes the content of the web page.

![HTML -> DOM -> rendering in browser window, JS change DOM](/images/what-is-react/03-html-dom.png)

## jQuery
jQuery is a JavaScript library that makes it easier for a developer to manipulate the DOM. How does it fit in the story of Domo and Browsera?

It is a tool that makes it easier for you to talk to Domo, just like a phone. You can call him wherever you are, whenever you want. It's a lot more convenient compared to talking to him face to face (raw JavaScript).

![Use phone with a label "jQuery" to talk to Domo, or perhaps just a phone with label](/images/what-is-react/04-jquery-phone.png)

For years we have been using jQuery to directly communicate with Domo. It's handy but not without issues.

Now meet our model agent, React:

![React, model agent](/images/what-is-react/05-model-agent.png)

With React, we no longer directly talk to Domo. React acts as a middleman between a developer and Domo. She smoothes out the communication and streamlines the process of portrait creation.

![React as a middleman](/images/what-is-react/06-middleman.png)

React has a few tricks to address the issues of jQuery and other tools. Here are her three main tricks:

- Reactive UI
- Virtual DOM
- Components

## Reactive UI
To update the DOM with jQuery, you'd have to specify what element to change at the right time, in the right order. This is equivalent to describing to Domo how to change from one pose to the next for each and every portrait.

![sequential commands about how to pose](/images/what-is-react/07-tilt-head.png)

Heck, this sounds tedious and error-prone! Why can't we just sketch out **what** we want instead of telling Domo **how** to pose[^2]? I don't really care about how you get to the next pose, as long as you pose like that!

![a few sketches of yoga poses on a piece of paper, in sketched tree forms, or perhaps just stickman](/images/what-is-react/08-sketches.png)

More importantly, you can leave placeholders on a sketch to represent different variations of a same pose.

This way, when the kids want to hang different ornaments on Domo, you don't have to talk to Domo again. You can just sit back and ask them to change it themselves.

![Sketch with ornaments placeholders, Domo with different ornaments](/images/what-is-react/09-ornaments.png)

This trick is how React got its name. The UI built with React is **reactive**. As a developer, you just need to write down **what** you want and React figures out **how** to do it. When the data change, your UI changes accordingly. You don't need to worry about updating the UI, React does it automatically. The idea of reactive UI greatly simplifies UI development.TODO

[code pen example](TODO)

{% highlight jsx%}
$('')
{% endhighlight %}

## Virtual DOM
Another issue of jQuery is about the speed. As customers of the studio, we are very demanding. We want the portraits to come out as quickly as possible. We don't like to wait.

However, Domo and Browsera are slow. Not really as slow as a sloth, but it takes time for Domo to change clothes and poses, and it takes time for Browsera to paint.

Worse, we'd have to wait for Browsera to finish painting a portrait before being able to talk to Domo again. In fact we cannot do anything but wait. What a waste of time!

![Domo and Browsera tell customer to wait, customer has a lot more requests, customer is frustrated](/images/what-is-react/10-slow-dom.png)

React pulls another trick to fix that. He likes to build trees with clay and he's super fast at it. Almost immediately after you hand him a sketch, he's done with a clay model and ready to take the next one. Now no more wait! You can keep telling React about the portraits you want, nonstop. React keeps record of everything with clay models and show it to Domo at the right time.

![React looks at a pile of sketches, quickly builds clay (胶泥) trees and arrange them in a queue; Domo poses according to a clay model](/images/what-is-react/11-clay-trees.png)

More importantly, React is smart. He can sort through the sketches and remove any duplication to streamline the process.TODO

![React holds two clay trees in each hand, similar poses, and tells Domo to only lift up his leg (or whatever minor adjustment)](/images/what-is-react/12-optimize-clay-trees.png)

These clay trees are called "Virtual DOM". Virtual DOM is much faster to manipulate than DOM. Developers work with Virtual DOM most of the time instead of directly managing DOM. React handles the dirty work of managing the slow DOM.

## Components
The third trick of React is the concept of components.

Components should be straightforward to understand because it's the way how our real world works. Our cars, houses and even our bodies are all made up of identifiable components that are individual, functional units. These components are made up of smaller components which consist of even smaller components, all the way down to atoms.

In React,

![sketch made up of components](/images/what-is-react/13-components.png)

The cool thing about component is that, if you change a component, everything that include this component will be updated as well.

![change hair style](/images/what-is-react/14-hair-style.png)



# Conclusion
TODO

---

# Footnotes:

[^1]: Fair enough, in reality, computers are not giant containers stuffed with tree branches. But in order to study how to organize information, people draw charts which look like upside down trees (like [this](TODO) and [this](TODO)).

[^2]: TODO: Declarative vs imperative, you define **what** you want instead of **how** you want it to be done.



<a name="endofpost">
