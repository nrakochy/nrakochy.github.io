---
layout:     post
title:      Forbidden Attributes Error with Grape and Rails 4
date:       2015-06-24 12:00:00
summary:    When POSTing to a Grape endpoint, the Hashie::Mash does not play well with Rails 4 strong params on the model and throws a ForbiddenAttributesProtection error.
categories: Grape
---

When POSTing to a Grape endpoint, the incoming data structure is a [Hashie::Mash](ihttps://github.com/intridea/hashie/blob/master/lib/hashie/mash.rb) by default.

When saving a new instance of a model, this Hashie will throw a HiddenAttributesProtection error in Rails 4, because of the strong params
protection on attribute assignment.

Solution: You need to add [this Gem](https://rubygems.org/gems/hashie-forbidden_attributes) to your Gemfile and bundle it up:

    hashie-forbidden_attributes

This gem allows mass assignment. It prevents the Hashie::Mash from responding to :permitted? and therefore triggering this behavior in ForbiddenAttributesProtection.

More information can be found [here](https://github.com/intridea/grape/issues/404).




