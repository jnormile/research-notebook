---
title: "Experimentation"
date: 2023-04-13T12:07:03-05:00
draft: false
---

One of the more technically demanding components of my envisioned project is a containerized runtime environment that can run Rust code independent of a given student's local programming environment. To address the feasibility of implementing this component, I recently implemented a simplified version of this.

To test out my implementation, I also designed three simplistic Rust programs--a simple "hello, world" program, one that expectedly errors out when trying to assign an updated value to an immutable variable (to see how the container preserves--or doesn't preserve--stack traces) and a third program that was designed to generate compile-time warnings but still ultimately compile (by writing expressions that are never actually utilized by the program).

After running the three test programs both within my containerized runtime environment *and* a local development environment equipped with a relatively basic installation of Rust, I found two important take-aways central to the continued development of my larger envisioned project.

First, I found that the containerized runtime, while a little slower (as expected) wasn't so impaired so as to hamper the envisioned student experience of the final project. Compile and execution times were on average 65% higher; however, given the miniscule nature of the assumed programs (small tutorial programs meant to demonstrate very specific programming concepts), a 65% increase to compile times shouldn't noticeably diminish runtimes for the browser-based version. (After all, a 65% increase to a 2-3 second compile time is still only 1-2 seconds.)