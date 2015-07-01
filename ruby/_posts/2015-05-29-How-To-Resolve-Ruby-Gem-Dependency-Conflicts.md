---
layout:     post
title:      How to Solve Ruby Gem Dependency Conflicts
date:       2015-05-29 12:00:00
summary:    Gem::ImpossibleDependenciesError?
categories: Gems
---

On a recent `bundle install` I ran into gem which relied on an old version of [Celluloid](https://github.com/celluloid/celluloid) which
was already installed on my computer. I got this error:

    While executing gem ... (Gem::ImpossibleDependenciesError)
    adhearsion-2.6.0 requires celluloid (~> 0.14) but it conflicted:
    Activated celluloid-0.16.0 instead of (~> 0.15.2) via:     punchblock-2.6.0, adhearsion-2.6.0
    ...

What’s the solution? Create a Gemfile which you can bundle instead of trying to resolve it with `rbenv` or `rvm`:

    source ‘https://rubygems.org’

    gem ‘adhearsion’, ‘2.5.4’
    gem ‘punchblock’, ‘2.5.2’
    gem ‘celluloid’, ‘0.15.2’

[Source](https://github.com/adhearsion/adhearsion/issues/515) for this solution.




