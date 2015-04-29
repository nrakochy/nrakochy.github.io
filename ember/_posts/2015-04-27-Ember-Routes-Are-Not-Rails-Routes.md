---
layout:     post
title:      Ember Route != Rails Route
date:       2015-04-29 12:00:00
summary:    What is the Ember route? It is most certainly not a Rails route.
categories: core-terminology
---
What is the Ember route? It is most certainly not a Rails route.

Coming to the Ember framework with a Rails perspective has caused a bit
of confusion for me.

There are a few assumptions that I have made, and now realize the need to go back and get the basic
terminology correct before proceeding.

To understand the Ember route, two things must be noted. First, you have to understand Ember's [fundamental premise](http://guides.emberjs.com/v1.11.0/concepts/core-concepts/):

    the web derives its power from the ability to bookmark and share URLs

Ember is built around a core commitment to the URL.

Second, it is important to distinguish between the `Router` and the `route`. The [`Router` is](http://guides.emberjs.com/v1.11.0/routing/defining-your-routes/):

    responsible for displaying templates, loading data, and otherwise setting up application state.
    It does so by matching the current URL to the routes that you've defined.

So the Router is the basic building block to the app. This is importnat. When you enter

    ember g resource test

You get a User `model`, `route`, `template`, and a  unit test file (perhaps broadly similar to Rails scaffold), and this:

    #app/router.js

    ...

    export default Router.map(function() {
        this.resource('test', function() {});
    });

Under this resource, `Ember routes` can be defined, and you get some for free, but the key takeaway is the `Router`
is loading the application state.

So what is an Ember route? The [Ember route](http://guides.emberjs.com/v1.11.0/concepts/core-concepts/):

    tells the template which model to display.

In Rails-speak, this is functionality is paralleled by the Rails `Controller`, not `root/config/routes.rb`!

So when I hear `Ember route`, it has been helpful for me to compare it to `Rails Controller` (obviously there is not one-to-one
functionality). This has alleviated some preconceived misconceptions that I had as I begin learning Ember.

Further, Rails `root/config/routes.rb` is handled by the `Router`.

I want to dive a bit deeper into the `Router` and write it up for a different post and will keep trying to work through the
clarification of Ember-speak v. Rails-speak. Please hit me up on Twitter if you have any additional insight/clarification/corrections
on this.
















