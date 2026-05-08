---
layout: post
title: Plato and Domain Driven Design
description: A small translation note that reveals a distinction being and becoming and how it relates to domain driven design.
category: posts
published: true
---

The quote in question is from **Timaeus**, which is often used to describe Plato's Forms and particulars or Being and Becoming.:

> "What is that which always is and has no becoming; and what is that which is always becoming and never is?". 27a Timaeus

The correct translation should read:

> "What is that which always is **(in the same state)** and has no becoming **(and perishing)**, and what is that which is always becoming **(and perishing)** ~~but~~ **(and)** never is **(in the same state)**"

You could see this is correct translation because in the very next sentence he elaborates:

> That which is apprehended by intelligence and reason **is always in the same state**; but that which is conceived by opinion with the help of sensation and without reason, is always in a process of **becoming and perishing** and never really is.

He also repeats this distinction in several other books, but with different wordings.

Exact distinction exists in software modeling as Value objects vs Entities objects in Domain Driven Design.

Where Entities:

- have **lifecycle** (can be created and deleted or **become and perish**)
- have state and can be **updated** (**they are never in the same state**)
- have multiple instances (particulars) of a class
- are identifiable by ID / changing properties does not influence it's identity

Value objects:

- don't have lifecycle (**have no becoming and perishing**)
- are immutable (**they are always in the same state**)
- have only one instance (abstraction/form)
- identifiable by properties / changing single property causes it to be different abstraction

> τί τὸ ὂν ἀεί, γένεσιν δὲ οὐκ ἔχον, καὶ τί τὸ γιγνόμενον μὲν ἀεί, ὂν δὲ οὐδέποτε; 27d

> τὸ μὲν δὴ νοήσει μετὰ λόγου περιληπτόν, ἀεὶ κατὰ ταὐτὰ ὄν, τὸ δ᾽ αὖ δόξῃ μετ᾽ αἰσθήσεως ἀλόγου δοξαστόν, γιγνόμενον καὶ ἀπολλύμενον, ὄντως δὲ οὐδέποτε ὄν. 28a


What this tells me is how loaded are the terms Being and Becoming in philosophy. From section above you could see they are just a shorthand for "**being** in the same state" (Immutable objects that can not change without changing their identity)  and "**becoming** and perishing" (Objects that can change their internal state but still stay the same).

