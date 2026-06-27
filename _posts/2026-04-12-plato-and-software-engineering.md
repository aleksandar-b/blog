---
layout: post
title: Plato and Domain Driven Design
description: A small translation note that reveals a distinction between being and becoming and how it relates to domain driven design.
category: posts
published: true
---

The quote in question is from **Timaeus**, which is often used to describe Plato's distinction between Forms and particulars or Being and Becoming.:

> "What is that which always is and has no becoming; and what is that which is always becoming and never is?". 27a Timaeus

The correct translation should read:

> "What is that which always is **(in the same state)** and has no becoming **(and perishing)**, and what is that which is always becoming **(and perishing)** but never is **(in the same state)**"

You could see this is the correct translation because in the very next sentence he elaborates:

> That which is apprehended by intelligence and reason **is always in the same state**; but that which is conceived by opinion with the help of sensation and without reason, is always in a process of **becoming and perishing** and never really is.

He also repeats this distinction in several other books but with different wordings.

An exact distinction exists in software modeling as Value objects vs. Entities objects in Domain Driven Design.

Where Entities:

- have **lifecycles** (can be created and deleted or **become and perish**)
- have state and can be **updated** / `"never is (in the same state)"`
- have multiple instances (particulars) of a class
- are identifiable by a single property ID or time&space / changing other properties does not influence its identity

Where Value Objects:
- don't have a lifecycle (**have no becoming and perishing**)
- don't have a state / are immutable / `"always is (in the same state)"`
- have only one instance (abstraction/form)
- identifiable by all properties / changing a single property causes it to be a different abstraction

> τί τὸ ὂν ἀεί, γένεσιν δὲ οὐκ ἔχον, καὶ τί τὸ γιγνόμενον μὲν ἀεί, ὂν δὲ οὐδέποτε; 27d

> τὸ μὲν δὴ νοήσει μετὰ λόγου περιληπτόν, ἀεὶ κατὰ ταὐτὰ ὄν, τὸ δ᾽ αὖ δόξῃ μετ᾽ αἰσθήσεως ἀλόγου δοξαστόν, γιγνόμενον καὶ ἀπολλύμενον, ὄντως δὲ οὐδέποτε ὄν. 28a


What this tells me is how loaded are the terms Being and Becoming in philosophy. From the section above you could see they are just shorthand for "**being** in the same state" (Immutable objects that cannot change without changing their identity) and "**becoming** and perishing" (Objects that can change their internal state but still stay the same).

