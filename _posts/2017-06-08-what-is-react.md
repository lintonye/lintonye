---
layout: post
last-modified: '2017-06-08'

title: "What is React?"
subtitle: "React terms in plain English and doodles"
#cover_image: "navigation-custom-transition/transit.jpg"

excerpt: "React terms explained in plain English and doodles🌴🎄⚛"

author:
  name: Linton Ye
  twitter: lintonye
  bio: Freelance full-stack developer in BC Canada (GMT-8). Android, React Native, Node.js, MongoDB, PostgreSQL. <a href="mailto:linton@jimulabs.com">Contact me.</a>
  image: linton.jpg
---

_This series of posts will be the very first part of the ["React for Designers" course](TODO) I'm creating. Be sure to [sign up](TODO) to receive exclusive updates!_

- _What is React? (this post)_
- _React, ReactJS, React.js, React Native, Which is Which? (coming soon)_

---

React, ReactJS, React.js, React Native... How many times have you heard about these things this week? Are you confused by what they are really for?

If you are a designer in a team that uses (or considers to use) React, or if you are simply curious about this React thing, this series of posts is for you.

In plain English and doodles🌴🎄, I'll explain the terms in React family and dive into what makes React special. No coding knowledge is required to read this post. But what you'd learn will become a solid foundation when we actually get our hands dirty with code in future posts.

Are you ready?

# Learning Goals
After reading this post, I hope you can easily answer these questions:

- What is DOM?
- What is React? Where does it fit in the development of an app?
- How is React different from jQuery?
- What are the core ideas in React?
- Why do we need Virtual DOM?
- What is a reactive UI?
- What are some benefits of components?

# Background Stories
Let's begin with a couple of other terms that you might have heard of for years. The first one, DOM.

## DOM
Well, DOM is Document Object Model. Get it? It's an object model for the document.

Forget about it. Let's check out the prestigious art studio "Web Browser"!

![Domo poses, Browsera draws](/images/what-is-react/02-domo-browsera.png)

So, DOM is a ... tree? Yup a tree. Oddly enough, a lot of things in your computer look like a tree[^1].

DOM is a tree who works as a model at the studio "Web Browser" -- Let's give him a nickname Domo. Domo's job is to pose in front of Browsera the artist who paints a portrait (or perhaps millions of portraits).

The portraits are what we see in the web browser when visiting a website. A developer's job is to tell Domo what to wear and what pose to make, which determine what those portraits look like in the end. Libraries like jQuery or React are the tools a developer uses to communicate with Domo.

## jQuery
jQuery is a JavaScript library that makes it easier for a developer to manipulate the DOM. How does it fit in the story of Domo and Browsera?

It is a tool that makes it easier for you to talk to Domo, just like a phone. You can call him wherever you are, whenever you want. It's a lot more convenient than before (raw JavaScript) -- you used to have to be in the same room in order to have a conversation.

![Use phone with a label "jQuery" to talk to Domo, or perhaps just a phone with label](/images/what-is-react/04-jquery-phone.png)

For years we have been using jQuery to directly communicate with Domo. It's handy but not without issues.

# React
Now meet our model agent, React:

![React, model agent](/images/what-is-react/05-model-agent.png)

With React, we no longer directly talk to Domo. React acts as a middleman between a developer and Domo. She smoothes out the communication and streamlines the process of portrait creation.

![React as a middleman](/images/what-is-react/06-middleman.png)

React has a few tricks to address the issues of jQuery and other tools. Here are her three main tricks:

- Reactive UI
- Virtual DOM
- Components

## Reactive UI
To update the DOM with jQuery, you'd have to specify what element to change at the right time, in the right order. This is equivalent to describing to Domo how to position his head, arms and legs step by step, for each and every portrait.

![sequential commands about how to pose](/images/what-is-react/07-step-by-step.png)

Heck, this sounds tedious and error-prone! Why can't we just tell Domo **what** we want instead of **how** to pose[^2]?

![a few sketches of yoga poses on a piece of paper, in sketched tree forms, or perhaps just stickman](/images/what-is-react/08-thinker.png)

More importantly, you can leave placeholders in your request to represent different variations of a same pose.

This way, when somebody asks for portraits where Domo wear a different hat, you don't have to talk to Domo again. You can just sit back and let him change it himself.

![Sketch with ornaments placeholders, Domo with different ornaments](/images/what-is-react/09-thinker-with-hat.png)

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

React pulls another trick to fix that. She's very fast at drawing quick sketches. Almost immediately after you tell her your requirement, she's done with a sketch and ready to take the next one. Now no more wait! You can keep telling React about the portraits you want, nonstop. React keeps record of everything with sketches and show it to Domo at the right time.

![React looks at a pile of sketches, quickly builds sketches and arrange them in a queue; Domo poses according to a sketch](/images/what-is-react/11-sketches.png)

More importantly, React is smart. He can sort through the sketches and remove any duplication to streamline the process.TODO

![React holds two sketch trees in each hand, similar poses, and tells Domo to only lift up his leg (or whatever minor adjustment)](/images/what-is-react/12-optimize-sketches.png)

These sketches are called "Virtual DOM". Virtual DOM is much faster to manipulate than DOM. Developers work with Virtual DOM most of the time instead of directly managing DOM. React handles the dirty work of managing the slow DOM.

## Components
The third trick of React is the concept of components.

Components should be straightforward to understand because it's the way how our real world works. Our cars, houses and even our bodies are all made up of identifiable components that are individual, functional units. These components are made up of smaller components which consist of even smaller components, all the way down to atoms.

Back to our studio "Web Browser", you describe your requirement for portraits as components, React translates it into what Domo understands. This saves you a lot time because you don't have to repeat common parts in your requirement.

![sketch made up of components](/images/what-is-react/13-components.png)

Another cool thing about components is that, if you change a component, everything that includes this component will be updated automatically.

![change hair style](/images/what-is-react/14-hair-style.png)

# Conclusion
TODO

---

# Footnotes:

[^1]: Fair enough, in reality, computers are not giant containers stuffed with tree branches. But in order to study how to organize information, people draw charts which look like upside down trees (like [this](TODO) and [this](TODO)).

[^2]: TODO: Declarative vs imperative, you define **what** you want instead of **how** you want it to be done.



<a name="endofpost">
