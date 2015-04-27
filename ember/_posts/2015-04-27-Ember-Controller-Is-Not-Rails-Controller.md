---
layout:     post
title:      Ember Controller != Rails Controller
date:       2015-04-27 12:00:00
summary:    What is the Ember controller? It is most certainly not a Rails controller.
categories: core-terminology
---
What is the Ember controller? It is most certainly not a Rails controller.

Coming to the Ember framework with a Rails perspective has caused a bit
of confusion for me.

There are a few assumptions that I have made, and now realize the need to go back and get the basic 
terminology correct before proceeding. Without further ado... the `Ember controller`...

According to the Ember docs, [Ember controllers](http://guides.emberjs.com/v1.11.0/controllers/):

    allow you to decorate your models with display logic

The Ember controller is a decorator! (Check out Martin Folwer's [Presentation model](http://martinfowler.com/eaaDev/PresentationModel.html)
or the similar [Model-View-ViewModel](http://en.wikipedia.org/wiki/Model_View_ViewModel) for more on the pattern)

This controller is auto-generated in Ember if not explicitly defined, and provides logic to the template. It does handle
custom actions from the template that you do not necessarily want to store in the model e.g. a form in the process of being
edited by the user.

Perhaps this is a Rails issue and not an Ember issue, I don’t know.

Fortunately, the `Controller` terminology will be deprecated in favor of web components in [Ember 2.0](http://discuss.emberjs.com/t/ember-2-0-moving-away-from-controllers/6728/5). 
The functionality will largely be the same, but the conflicting definitions between Rails and Ember will disappear.

