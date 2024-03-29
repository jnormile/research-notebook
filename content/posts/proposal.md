---
title: "Proposal"
date: 2023-05-04T12:07:03-05:00
draft: false
---

Having just formally submitted a project proposal for the endeavor entertained by this research notebook, I've taken the liberty of distilling the highlights from said proposal for a more informal look at `playbook`--the working name for the project I plan on tackling next year, and have already spent considerably time laying groundwork for.

To begin with, I'll first revisit the question of **why?**

As is often the case with anything that someone compellingly pursues and devotes much of their time to, the motivation for this project is a particularly personal one. I haven't mentioned it here yet, but my academic career has been unconventional: I enrolled in undergraduate studies in my late twenties. After spending about a decade being disenchanted with a middle management position with a nation-spanning retailer, I opted to make a dramatic pivot and go back to school, hoping to open a few doors towards a work experience that I could personally deem more fulfilling and meaningful. Through a series of fortuituous happenstances, that pivot was much less cost-intensive than it generally proves to be, and I found myself able to seize a unique opportunity not generally presented to working American adults.

The personal backstory aside, the premise behind my project is equal parts simple and ambitious. I want to create a way for others to experience even a fraction of the personal growth that I have through my current educational journey pursuing a degree in computer science. I want to open a door of opportunity to other disenchanted adults looking for a new path, and I want to do it at no cost to them other than their time.

It's worth noting that the structure of this endeavor is motivated by external research as well. Though I've spent my time (and yours) within numerous posts elaborating on research related to the gamification of pedagogy, there's couple key pieces of research that much of my proposed idea hinges on. First, there's [this previously discussed text on the teaching of complex materials via dynamic media](https://www.jstor.org/tc/accept?origin=%2Fstable%2Fpdf%2Fjeductechsoci.11.1.279.pdf&is_image=False), which finds that increasingly complex subject matter tends to see increasingly large benefits (in terms of learner retention) when taught via "dynamic" media (as opposed to static, text/lecture-based media). Secondly, there's [this more contemporary study on gamification and flipped/traditional classrooms]() that demonstrates a *blend* of both traditional educational approaches with hands-on activities (all with a coat of gamification) results in the highest learner achievement *and* engagement.

The appeals to complexity and blended educational approaches inform both the proposed subject matter of `playbook` as well as how it aims to deliver it, which, of course, now brings us the the **what** of it all.

The proposed `playbook` project will aim to offer users a browser-based platform for learning the fundamentals of the Rust programming language. I plan for it to leverage three components in order to do so: 

- Educational text pertaining to specific programming fundamentals in the Rust programming language (with a planned writing style of "recipe blog meets classroom teacher", weaving in anecdotes and a more informal tone to keep the platform presenting as friendly and engaging) 

- Corresponding hands-on coding activities related to the aforementioned text that will invite users to put principles laid out in writing into practice of their own

-  Progress bars, badges, and similar gamification elements designed to prompt the user towards further exploration of the text and the activities and reward user progress

And without further ado, it's worth investigating (in as few words as possible) the somewhat complex architecture that constitutes the **how** of `playbook`.

My proposed project is comprised of four distinct components that work together:

- A user-facing webpage that makes up the entirety of the user experience, and is comprised of the aforementioned three elements from the list above

- A collection of activity repositories housed on GitHub that contain the necessary data for the hands-on coding activities presented by the webpage, including any starter code for coding activities as well as information pertaining to expected output and possible test cases that users are required to pass

- A database that stores and collects data pertaining to the progress made by specific users, to be called for and referenced when populating the various progress bars, badges, and other possible gamification elements that present themselves to the user on the webpage

- A containerized runtime environment powered by Docker that is equipped with a Rust installation and any related dependencies required by the various hands-on activities presented by the webpage

Of course, each of these components functioning in isolation would amount to very little, so there's also a need for a server facilitating the numerous requests for data made between these entities.

This is, in hopefully fewer words than it takes to bore a reader, the **why, how, and what** behind `playbook` and its envisioned future. But it's worth mentioning--for *particularly* invested readers, I suppose--that `playbook` already has something of a *past* as well.

Over the past couple of months, I've labored over a couple of prototypes that aim to demonstrate the feasibility of the proposed project, as well as address some of the most glaring gaps in my technical knowledge and capabilities. One of those prototypes and the resultant experimentation of its capabilities is already detailed in [this post](https://jnormile.github.io/research-notebook/posts/experiment/), so if you're interested in the work that went into building a simplistic containerized runtime environment for running pre-written Rust code, then I'll kindly direct your attention there so as to avoid repeating myself within this medium.

On the other hand, I've yet to discuss the other, arguably more important prototype that I've been at work developing alongside a faculty advisor in my undergraduate program. This saw the integration of my containerized runtime environment into a setup that involves a server handing off Rust code submitted from a client webpage (imitating the future hands-on coding activities I envision) to said runtime environment and retrieving the container's logs to write output files containing both program output and any information contained in a `stderr` channel (including all of `cargo`'s messages regarding compile time and helpful stack trace errors and warnings). The final piece of the puzzle that has yet to be developed is the hand-off the newly created text file *back* to the initial client, to completely implement a web-based coding platform not unlike those produced by [Replit](https://replit.com/).

Finishing the hand-off implemented by this prototype is just the first step in realizing the vision proposed by `playbook`. From there, I'll still have to engage in the following tasks:

- Implement functionality to store and retrieve data pertaining to user progress within a database, and leverage this functionality within gamification elements presented in the user's webpage

- Create activity files housed in GitHub that contain the aforementioned starter code and solution data for each hands-on activity

- Implement functionality to actually *retrieve* the data stored in those GitHub repositories to populate activities with starter code and provide a means to compare user-submitted program output with expected output

- Develop style elements for the user experience (the current prototype is a crude black-and-white page with a line of text, a submission form, and a submit button)

- Actually write curriculum for `playbook`!

This last piece is the part I'm personally most excited for, but unfortunately a number of tasks stand between me and actually developing the curriculum leveraged by `playbook`. In all likelihood, this "curriculum" considered by `playbook` will be *very* limited in scope--no more than a lesson or two--given the major time constraint imposed by my impending graduation.

All that having been said, that's as concise a possible look at both where `playbook` has been and where I hope it will go. As always, thank you for joining me for this endeavor via these posts.
