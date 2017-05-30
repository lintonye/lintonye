---
layout: post
last-modified: '2017-05-26'

title: "React, ReactJS, React.js, React Native, Which is Which?"
subtitle: "TODO React terms explained in plain English"
#cover_image: "navigation-custom-transition/transit.jpg"

excerpt: "TODO Should designers code? This is an eternal question."

author:
  name: Linton Ye
  twitter: lintonye
  bio: Freelance full-stack developer in BC Canada (GMT-8). Android, React Native, Node.js, MongoDB, PostgreSQL. <a href="mailto:linton@jimulabs.com">Contact me.</a>
  image: linton.jpg
---

React receives a lot of interest not only among developers, but also designers. [Many designers are considering](TODO DN post) to include React into their toolbox. People are talking about React, ReactJS, React.js, React Native, [React Sketch.app](TODO) etc. But to my surprise, many of them are not aware of the precise differences between those terms.

This post is an attempt to explain the terms in React family in plain English and some doodles. After reading this, hopefully you'll understand a bit more about what React is and the relationship and differences between ReactXYZ.

# What is React?

On the [official website](TODO) of React, it is defined as "a JavaScript library for building user interfaces".

Hmm... user interfaces... it sounds relevant to design. But what's special about it? Don't we already have jQuery? Why do we need a new library?

Let me start by explaining an important term that you may have heard over and over again from your developer friends: DOM.

## DOM
Well, DOM is Document Object Model. Get it? It's an object model for the document.

Forget about it. Say hi to our super model Domo!

Before you roll your eyes... It's not a model like this:

![super model](TODO)

But more like this:

![tree man, saying "I am gr..."][TODO]

A tree? Yup a tree. Oddly enough, a lot of things in your computer look like a tree ^1.

As a model, Domo's favorite thing is to pose in front of Browsera the artist who paints a portrait (or perhaps millions of portraits).

![Domo poses, Browsera draws](TODO)

The portraits are what we see in Chrome, Firefox or IE when visiting a website. A developer's job is to tell Domo what to wear and what pose to make, which determine what those portraits look like.

## jQuery
jQuery is a JavaScript library that makes it easier for a developer to manipulate the DOM. How does it fit in the story of Domo and Browsera?

It is a tool that makes it easier for you to talk to Domo, just like a phone. You can call him wherever you are, whenever you want. It's a lot more convenient compared to talking to him face to face (raw JavaScript).

![Use phone with a label "jQuery" to talk to Domo, or perhaps just a phone with label](TODO)

For years, jQuery has been the main way that we use to communicate with Domo about what kind of portraits we want. It's handy but not perfect.

React was created to address the issues of jQuery and other tools. Here are three core ideas of React:

- Reactive UI
- Virtual DOM
- Components

## Virtual DOM
One issue of jQuery is about the speed. As customers of the studio, we are very demanding. We want the portraits to come out as quickly as possible. We don't like to wait.

However, Domo and Browsera are slow. Not really as slow as a sloth, but it takes time for Domo to change clothes and poses, and it takes time for Browsera to paint.

Worse, we'd have to wait for Browsera to finish painting a portrait before instructing Domo about the next pose. In fact we cannot do anything but wait. What a waste of time!

![Domo and Browsera tell customer to wait, customer has a lot more requests](TODO)

Meet Vomo, the super efficient model agent!

TODO Vomo is probably not Virtual DOM, but the manager of Virtual DOM...

![Vomo, the model agent (another tree)](TODO)

Unlike Domo, Vomo is fast. Almost immediately after you give him an instruction, he's ready to take the next one. Now you no longer need to wait anymore! You can keep telling Vomo about the portraits you want, nonstop. Vomo keeps record of everything and pass the instructions to Domo at the right time.

![Vomo fast, interfacing between customer and DOM](TODO)

More importantly, Vomo is smart. He can sort through the requests and remove any duplication to streamline the process.

![A piece of paper showing the optimization done by Vomo](TODO)

- wear clothe A
- pose A
- wear clothe B
- pose A
- wear clothe A
- pose B

becomes:

- wear clothe A
- pose A
- pose B
- wear clothe B
- pose A

Have you heard of Virtual DOM in React? That's Vomo. Virtual DOM is much faster than DOM. Developers work with Virtual DOM most of the time instead of directly managing DOM. React handles the dirty work of managing the slow DOM.

jQuery can (and should) retire now.

## Reactive UI
To update the DOM with jQuery, you'd have to specify exactly what element to change at the right time, in the right order. This is equivalent to describing to Domo how to move from one pose to the next for each and every portrait.

![sequential commands about how to pose](TODO)
- Stick out left hand
- tilt head
- tilt head more
- tilt head even more

Heck, this sounds tedious and error-prone! Why can't we just sketch out **what** we want instead of telling Domo **how** to pose ^2? I don't really care about how you get to the next pose, as long as you get there.

![a few sketches of yoga poses on a piece of paper, in sketched tree forms, or perhaps just stickman](TODO)

{% highlight jsx%}
$('')
{% endhighlight %}

Further,

## Components

# ReactJS, React Native, ReactXYZ...
Hopefully you've got a hang of what React is, right? But what are those other things, such as ReactJS, React.js, React Native? Let's look at those now.

Initially, React was created to build web applications. It's all about portraits from the studio "Browser". It's a small library just like the model agent Vomo (plus some other things) who manages the communication with Domo.

As time goes by, people realized that this is a great process that can be applied to other platforms. Vomo is actually capable of working with other studios, such as studio "Mobile", studio "Mac" and studio "Sketch".

![Perhaps three images: Vomo talks to Domo, the model in studio "Mobile" and the model in studio "Sketch"](TODO)

This is how React Native was born. Using the same ideas of virtual DOM, reactive UI and components, we can build native mobile apps, desktop apps or even convert code to images in Sketch.

The original React for the web was split into two parts: React Core and React DOM.

A lot of people use ReactJS or React.js to refer to ReactDOM. That's why I used it as well.

## Bonus: differences between native mobile apps and web apps?

# Conclusion

---

# Footnotes:

[^1]: Fair enough, in reality, computers are not giant containers stuffed with tree branches. But in order to study how to organize information, people draw charts which look like upside down trees (like [this](TODO) and [this](TODO)).

[^2]: Declarative vs imperative, you define **what** you want instead of **how** you want it to be done.


Say hi to our DOM guy -- Doodle-On-the-wall Man.

His only favorite thing is to listen to your commands and draw stuff on a wall. ^1

^1: In technical terms, DOM is an API that a developer can use to manipulate HTML documents. Essentially, you write code to communicate with DOM and instruct the browser to do stuff. Our DOM-guy analogy isn't that far off, right?



- A Tree
  - I am gr...
  - can pose, change shapes,
  - different yoga poses etc.
- The relation to real terms is more important than the closeness of the analogy
- Components live in the instruction side, mainly to make the "director"'s work easier. Model is the same model, painter is the same painter
- picture of all kinds of trees in a phone
- different kinds of tree men/women, representing object models on different platforms.
- imperative vs declarative:
  - tell exactly how to pose vs. drawing a sketch
- raw js vs jQuery
  - using raw js is like talking to Domo face to face
  - using jquery is like talking to Domo via phone, more powerful, more convenient

- DOM -- Doodle-On-the-wall Man

- important to connect the analogy back to a more technical description

- Static web page:
  - hand a blueprint to DOM guy, who draws a picture on the wall according to the blueprint (perhaps just fill it with colors)
- JQuery:
  - blueprint with blank squares, a person directly tells DOM guy to fill blank squares
- JQuery problem 1:
  - "who told him to draw that rabbit with horns?": the DOM guy looks confused, the two requesters look innocent
  - solution: templates, instead of allowing arbitrary changes, use templates to define possible changes
- Problem 2: Slow DOM:
  - instruction to the DOM guy: draw a blue cow, change the color of rabbit to red, ...; the DOM guy is still drawing the first rabbit, stick out a hand and says: "hold on, let me finish this rabbit first".
- Virtual DOM:
  - another person sitting between the DOM guy and the requester, acting fast. queue up requests and give it to the DOM guy in batches. Smart merge: if a request says: 'draw a rabbit in blue' and then 'draw a rabbit in red', the final request sent to DOM guy is 'draw a rabbit in red, ignore blue', "don't start from scratch, just repaint that rabbit in the corner in yellow"
- Components:
  - in the blueprint: <rabbits-eating-carrots count="2"/>
- Reactive UI
  - spreadsheet
  - __ + __ = __
  - <rabbit-eating food={____} />



- Functional reactive UI
  - new sheet of blueprint instead of easing and updating an existing blueprint
  - sounds crazy but ...
  - benefits of new blueprints?
    - easier to draw blueprints? no need to worry about the history
- Unidirectional data flow



Clock and gears analogy
 - what you've seen in the browser are like the clock hands and the time, DOM is like the gears

- Browser runs JS
- DOM
  - What is it?
  - manipulation is expensive
- imperative vs declarative
  - jquery
    - cross-browser API
    - DOM is slow
    - tight coupling with HTML
    - DOM event handlers?
- no templates


- Clearly state prerequisite and goals
  - Goals need to be precise and validatable
- Draw some doodles?
- Ask readers to say whether the goals are achieved for themselves
- Two-part post
  - Why React? What is React?
    - History of web development
      - static pages => static pages with forms => single page apps
      - jQuery update DOM: cons:
      - JS frameworks: https://www.quora.com/Is-better-to-learn-jQuery-Ember-js-or-Backbone-js
    - What is React in a single sentence?
      - Goal: use terms that V can understand!
    - Core ideas of React
      - Components
        - I love the thoughts behind Atomic design and the thinking about reusable design patterns. Everything is components, and a component can consist of other components making a design pattern.
        - Interactive components combining both presentation and interaction.
        - Templates vs. components
      - Functional, Reactive UI
        - In a traditional JavaScript application, you need to look at what data changed and imperatively make changes to the DOM to keep it up-to-date. Even AngularJS, which provides a declarative interface via directives and data binding requires a linking function to manually update DOM nodes.
        - Reactive programming is about the flow of data and declaratively maintaining the relationships between that data.
        - If you did this in vanilla JavaScript or jQuery, you’d have to explicitly listen to ‘change’ events on the inputs, and then manually update the value of C1.
        - mutable, stateful vs immutable, stateless
        - Update the whole thing
      - Single direction data flow
      - Virtual DOM
    - How do these concepts relate to design?
  - React DOM, React Native, React Sketch.app
    - difference between Web apps, Native apps, and web apps embedded in webview
    - How do these concepts relate to design?
    - React is significantly more SEO friendly than most JavaScript MVC frameworks because it is based on a virtual DOM you can use it on the server
- Ask V to review the posts


- Reader profile
  - Know HTML+CSS
  - Know UI
  - Visually focused

- Reactive user interface

- React as a paradigm, a way of thinking
- RN: batteries included
- RJS: must set up the project; though there is Create React App
- RN vs mobile pages
- Native app vs web app
  - perhaps include a video showing the different performance
- React Sketch.app
- To make it even more complicated:
  - react-native-web: https://github.com/necolas/react-native-web
  - https://github.com/Microsoft/reactxp
- cannot build a fully functional dynamic application with React alone

- layout:
  - RN: flexbox
  - RJ: CSS
- Animations:
  - RN: no CSS Animations

- Links
  - https://medium.com/@alexmngn/from-reactjs-to-react-native-what-are-the-main-differences-between-both-d6e8e88ebf24
  - http://stackoverflow.com/questions/34641582/what-is-difference-between-react-native-vs-react
  - https://www.quora.com/Whats-the-main-difference-between-ReactJS-and-React-Native
  - http://blog.andrewray.me/reactjs-for-stupid-people/
  - https://facebook.github.io/react/blog/2013/06/05/why-react.html
  - https://docs.google.com/presentation/d/1afMLTCpRxhJpurQ97VBHCZkLbR1TEsRnd3yyxuSQ5YY/edit#slide=id.g380053cce_1776
  - https://medium.com/front-end-hacking/react-for-designers-3fbc7b6560dd
  - http://bradfrost.com/blog/post/atomic-web-design/
  - https://emberway.io/ember-js-reactive-programming-computed-properties-and-observers-cf80c2fbcfc

TODOs:
- try out Create React App

<a name="endofpost">
