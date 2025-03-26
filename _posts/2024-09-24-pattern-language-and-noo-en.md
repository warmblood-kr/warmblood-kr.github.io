---
layout: post
title: "Design Patterns, Pattern Languages, and the Nature of Order"
date: 2024-09-24
categories: dev-practice
author: jeongsoo.park
description: Exploring the connections between Christopher Alexander's pattern languages, software design patterns, and the deeper concepts of The Nature of Order
image: 
---

In my previous post about [technical debt]({{ site.baseurl }}{% link _posts/2024-09-23-technical-debt.md %}), I mentioned Christopher Alexander and the pattern language he advocated. I also talked about how people in the software industry actively embraced pattern languages, with design patterns being one of the results.

In this post, I'd like to introduce pattern languages, Christopher Alexander who first proposed them, and the research developments that evolved after pattern languages. I hope this will encourage more people to apply Alexander's ideas beyond design patterns, applying them to software development in a deeper and broader way.

## The Birth of Design Patterns and the Pattern Community

Rather than following a chronological order, let's start with design patterns, which are familiar to software developers. In the programming field, the widely known 'design patterns' typically refer to the 23 design patterns documented in the book _Design Patterns: Elements of Reusable Object-Oriented Software_, written by four authors sometimes called the Gang of Four: Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides.

These patterns—such as Factory, Observer, Singleton, and Strategy—have become ubiquitous in software development education and practice. They provide standardized solutions to common programming problems, helping developers communicate and implement robust solutions efficiently. However, the story of how these patterns came to be is deeply intertwined with architectural theory and a broader intellectual movement.

What was the background that led these four authors to write this book? How did they meet? The convergence of these minds wasn't a coincidence but rather the result of a growing intellectual community interested in applying architectural thinking to software design.

The GOF Design Pattern book was published in 1995, but the groundwork for this influential text was laid years earlier. The software patterns movement began to take shape in the late 1980s and early 1990s, drawing direct inspiration from Christopher Alexander's work in architecture.

In 1987, Ward Cunningham and Kent Beck presented one of the earliest papers on using patterns in software at the OOPSLA conference. Their work, [available here](https://c2.com/doc/oopsla87.html), began to establish connections between Alexander's architectural patterns and object-oriented programming. This early work recognized that software design, like building design, could benefit from a catalog of proven solutions to recurring problems.

The history of patterns in software continued to evolve through various conferences and meetings. As documented on the [C2 Wiki page on pattern history](https://wiki.c2.com/?HistoryOfPatterns), what started as informal discussions gradually coalesced into a more structured approach to software design.

Erich Gamma was writing his doctoral thesis on ET++, an object-oriented application framework, when he first encountered these ideas. A pivotal moment came when Bruce Anderson gave a lecture at TOOLS 90, which Erich Gamma attended. At that time, Bruce introduced OOPSLA 90, where he led a BOF (Birds of a Feather) small group meeting called _Toward an Architecture Handbook_. It was there that Erich Gamma and Richard Helm first met each other, finding common ground in their approach to software design challenges.

The group continued to grow as Ralph Johnson and John Vlissides [joined the conversation](https://wiki.c2.com/?KentAndRalphAtTheArchitectureWorkshop) at OOPSLA 91. These meetings and discussions laid the intellectual foundation for what would eventually become the Gang of Four's seminal work on design patterns.

It's important to note that this movement was growing in parallel with Alexander's continued work. Alexander's "The Timeless Way of Building" (TWOB) was published in 1979, and his comprehensive work "A Pattern Language" (PL) was published in 1977. These works established the theoretical framework that the software patterns community would adapt and extend.

For those interested in firsthand accounts of this period, Ward Cunningham's interview, [The Starting Point of Software Patterns](https://www.youtube.com/watch?v=_V0kVOLOCrY), provides valuable insights into the early days of the patterns movement in software.

The enthusiasm for patterns eventually led to the formation of the [Hillside Group](https://hillside.net/home/history), which began organizing the Pattern Languages of Programs (PLoP) conferences. These conferences created a space for pattern authors to gather, share ideas, and refine their work through a unique "writers' workshop" format that emphasized collaborative improvement rather than traditional academic presentation.

It's worth emphasizing that design patterns are just one type of architectural pattern. The pattern community has since expanded to include various types, fields, and layers of patterns such as architecture patterns, implementation patterns, reengineering patterns, and more. PLoP continues to be held annually, and new patterns are still being discovered and documented today, demonstrating the enduring value of this approach to software design.

## Pattern Languages, Christopher Alexander

While design patterns have become a cornerstone of software engineering education, they represent just one application of a much broader concept: pattern languages. To truly understand the significance of design patterns, we need to look at their intellectual roots in the work of Christopher Alexander.

Christopher Alexander isn't a computer scientist or software engineer—he's an architect and architectural theorist whose ideas crossed disciplinary boundaries to profoundly influence software design. His concepts of patterns and pattern languages offered a new way to think about complex systems and their design.

Some people memorize design patterns diligently as a set of recipes to apply in their code. However, if you look at the context and history of how design patterns emerged, you'll see that the individual patterns themselves are not what's important—it's the underlying philosophy and approach to design that truly matters.

Interestingly, Ward Cunningham, who also contributed significantly to wiki technology and Agile development, appears here as a key figure in translating Alexander's ideas to software. Cunningham recognized the potential of pattern languages to address the complex, human-centered nature of software development.

What exactly is a pattern language? Alexander's "The Timeless Way of Building" provides the philosophical foundation. At its core, Alexander argues that good design emerges from identifying and implementing patterns that solve recurring problems in a way that enhances the quality of the whole. A pattern language is essentially a structured collection of these patterns that work together to create coherent, living systems.

Why call it a pattern "language" rather than just "patterns"? Because the combination of pattern elements isn't a simple enumeration but has a certain semantic structure. Patterns relate to one another in specific ways, forming a kind of grammar for design. Just as words in a language can be combined to create meaningful sentences, patterns can be combined to create meaningful designs.

Alexander's approach was revolutionary because it sought to codify the subtle, often tacit knowledge that makes designs work well for people. His patterns range from the macro scale (how cities should be organized) to the micro scale (how to design a comfortable window seat). Each pattern addresses a specific problem and provides a solution that balances multiple forces in a way that creates what Alexander calls "the quality without a name"—a sense of aliveness, wholeness, and human connection.

The software community's engagement with Alexander's ideas reached a significant milestone when he was invited to give a keynote address at ACM OOPSLA 96. In this talk, he both acknowledged the software community's adoption of his ideas and challenged them to go deeper—to consider not just the mechanics of patterns but their ability to create living structures that enhance human experience.

## Beyond Pattern Languages, Exploring the Nature of Order

After developing pattern languages, Alexander didn't stop there. His intellectual journey led him to an even more ambitious project: "The Nature of Order," a four-volume work that represents the culmination of his thinking about design, life, and the universe.

This progression from pattern languages to The Nature of Order reflects Alexander's continuous search for deeper principles underlying good design. To understand this evolution, we can look at a brief but illuminating interview.

[Jenny Quillen's interview: History from A Pattern Language to the Nature of Order](https://www.youtube.com/watch?v=ad5XAPgKJoM) provides valuable context in just six minutes. It offers a fascinating glimpse into what sparked Alexander to create pattern languages and why he later wrote The Nature of Order.

The story begins with a research project commissioned by the US government, which Alexander's team undertook. The research topic was remarkably ambitious: to discover 'the impact of space and environment on people's happiness and mental health.' This wasn't just about aesthetics or functionality—it was about how the built environment affects human wellbeing at a fundamental level.

When Alexander's team took on the research, they had no predetermined methodology. Pattern language wasn't a concept they brought to the project; rather, it emerged organically as they grappled with the complex relationship between spaces and human experience. It was a discovery rather than an application of existing ideas.

That's how pattern language emerged—as a way to capture and communicate the elusive qualities that make spaces work for people. However, Alexander was very disappointed when he saw how people were utilizing pattern languages in practice. The pattern languages that people were creating often seemed to lack beauty and vitality—something essential seemed to be missing from the implementation.

So during the 30 years between publishing "A Pattern Language" and completing "The Nature of Order," Alexander went back to first principles. He reconsidered the fundamental question: if pattern language isn't the complete answer for creating living structures, what is? This led him to explore more deeply the qualities that make certain designs feel alive and whole.

In "The Nature of Order," Alexander proposes that pattern languages exist on multiple levels. Each pattern acts as a center within a larger whole. Some patterns have subordinate patterns, creating a hierarchical structure. Patterns are interconnected in complex ways, forming a web rather than a linear sequence. A truly good pattern language has a certain meta-quality that goes beyond the individual patterns themselves.

Alexander's later work focuses on these meta-qualities and the connections between patterns. He started by examining the joints between patterns—how they connect and reinforce each other to create a coherent whole. This led him to identify 15 fundamental properties that characterize living structures, from "strong centers" to "gradients" to "local symmetries."

In essence, "The Nature of Order" represents Alexander's attempt to articulate the deeper geometric and structural principles that underlie the patterns he had previously identified. It's a profound exploration of how certain configurations of space seem to resonate with human beings, creating a sense of life and wholeness that transcends cultural and historical boundaries.

For software developers, Alexander's journey from pattern languages to The Nature of Order suggests that there may be deeper principles underlying good software design—principles that go beyond specific patterns or practices to touch on the fundamental nature of well-structured systems that serve human needs.
