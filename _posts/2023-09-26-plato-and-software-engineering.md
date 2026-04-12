---
published: false
---

The quote in question is from **Timaeus**, which is often used to describe Plato's Forms and particulars:

> "What is that which always is and has no becoming; and what is that which is always becoming and never is?".

The correct translation should read:

> "What is that which always is **(in the same state)** and has no becoming **(and perishing)**, and what is that which is always becoming **(and perishing)** ~~but~~ **(and)** never is **(in the same state)**"

You could see this is correct translation because in the very next sentence he elaborates:

> That which is apprehended by intelligence and reason **is always in the same state**; but that which is conceived by opinion with the help of sensation and without reason, is always in a process of **becoming and perishing** and never really is.

He also repeats this distinction in several other books, but with different wordings.

Exact distinction exists in software modeling as Value objects vs Entities objects.

Where Entities:  
- have **lifecycle** (can be created and deleted or **become and perish**),  
- can be **changed**. where state is a snapshot of it's properties at some moment in time (**they are never in the same state**)  
- have multiple instances (particulars) of a class  
- are identifiable by ID  

Value objects:  
- are immutable (**they are always in the same state**)  
- don't have lifecycle (never come and go out of existence / **has no becoming and perishing**)  
- have only one instance  
- identifiable by properties  

> τί τὸ ὂν ἀεί, γένεσιν δὲ οὐκ ἔχον, καὶ τί τὸ γιγνόμενον μὲν ἀεί, ὂν δὲ οὐδέποτε; 27d

> τὸ μὲν δὴ νοήσει μετὰ λόγου περιληπτόν, ἀεὶ κατὰ ταὐτὰ ὄν, τὸ δ᾽ αὖ δόξῃ μετ᾽ αἰσθήσεως ἀλόγου δοξαστόν, γιγνόμενον καὶ ἀπολλύμενον, ὄντως δὲ οὐδέποτε ὄν. 28a
