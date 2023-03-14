---
title: "Vision"
date: 2023-03-14T10:07:03-05:00
draft: false
---

Since my last post, I've spent some time dreaming up a gamified curricular tool for teaching the fundamentals of a new programming language--namely, *Rust*. Below is a rough vision of what I've mentally cobbled together so far:

![Playbook Blueprint](/excalidraw-playbook.png)

There are four distinct components to this vision:

1. A web-based "textbook" page containing activities and instructional text
2. A containerized runtime environment for running the Rust code input by users of the web application
3. A repository containing starter code and solutions for each of the curriculum's coding activities
4. A database storing user-specific information pertaining to the gamified elements to be displayed on the webpage--badges, progress bars, etc.

This simple drawing has been the culmination of several weeks' worth of brainstorming, talking with my advisor, and tinkering with Docker. The relationships between each component are *heavily* simplified, but it gives me a sense of what I'll need to build--also revealing knowledge gaps that I'll need to close before I'll be able to fully realize the vision laid out here.

It's a humble start (to say the very least) but it is a *start*.