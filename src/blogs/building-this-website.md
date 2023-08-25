---
layout: blog
title: "Rebuilding my personal website"
tags: [technology, web-dev]
date: Last Modified
created: 2022-07-25
summary: Why I decided to redo this website, my inspirations, and the design decisions that I took.
---
I built the [previous version](https://kafleprabhakar.github.io/) of my personal website during the summer before starting college. I had some experience with JavaScript and CSS through projects I had worked on during my gap years. All of these were multi-page "traditional" websites with plain JS or jQuery. But I wanted to try something new and different. And being a perfectionist as I was (maybe still am??), I went on the internet to find the best tools to build the website and everyone seemed to be rooting for some javascript framework or other. Who was I to not succumb to this force! So, after some research *(read googling)*, I decided to use [Gatsby](https://www.gatsbyjs.com/).

I think it took me a bit more than a month to build the site. *I was also traveling around that time.* It was a good learning experience too. I learnt [React](https://reactjs.org/) and [GraphQL](https://graphql.org/) *(not so much)* and Gatsby and Git. I had worked as a graphics and web designer before that and I wanted to highlight that fact. *So obviously the website should reflect that, right?* To the beginner me, all the particle.js animation and typewriter effect and catchy graphics I made seemed super cool. *I mean I was a designer after all.* But after about an year or so, it started looking a bit too much. Maybe an overkill for a personal website?

So I had been meaning to rebuild this website for quite some time. As far as I knew myself, the task of actually designing and writing code for the website would be the easier part. I wanted the design to be minimal anyways. What would be hard is to decide on just the right tools to build it (and learn it if I didn't already know). It was this task which I procrastinated for almost a year. This summer I finally got around to it.

### The Design and Content
<!--- TODO: Add link to the shelf of links here after first sentence. --->
<!-- *You can find a filtered list here.* -->
For the last couple of years, it had been kind of hobby of mine to bookmark any interesting websites, especially personal blog sites, in Notion. And I always keep an eye out for design of these websites. I have been inspired by quite a few of these. These include personal websites of [Alexey Guzey](https://guzey.com/) *(notice the fonts?)*, [Patrick Collision](https://patrickcollison.com/) *(the simplicity)*, [Paul Graham](http://paulgraham.com/) *(the design has stood the test of time)*, [Chris Kryocho](https://v5.chriskrycho.com/) to name a few. In terms of content, I visioned the website to highlight my blogs and works in photography as a part of *me*.

For someone who procrastinates a lot, a top priority while building the website was to minimize the friction to add any new content. Plus I also wanted to focus more on the content than the design. Thinking more concretely about what I wanted, I came up with a rough list of criteria for how to go about building the website:

- **Minimum friction to add new content.** I want to be able to write a blog or note in Notion or something and get it up on the website with a minimum effort (and procrastination).
- **Scope to add features.** Some sort of futureproofing I guess. If I want to add some feature like interactive content *(like [Bartosz Ciechanowski's blogs](https://ciechanow.ski/)- I love his content)*. Adding these should be like adding a block to the puzzle rather than a major overhaul to the whole codebase.

On more technical note,

- **Static site.** Given the type of content the website will have, it makes sense to have just the HTML, CSS, and JS hosted. It doesn't need any "database". *Can you call the JSON and Markdown file the database?!?*
- **Templating.** The idea is to separate data and code and be apply appropriate template to the content to generate the page for that.
- **Reusable Components.** Overlaps with the first point a bit. I think it is pretty self explanatory- keep the code DRY and prevent monolithic code.
- **Power of JavaScript and NPM.** I love JavaScript. It is not my favorite in terms of the design of the language- it could have been better. But I love the power it provides- being able to interact directly with the browser. So I would rather prefer to work directly with it rather than write program in Python or Go and generate HTML/JS. Also, I want to leverage the community of developers and packages in NPM (but not overuse it like I did in the previous version).
- **Simple and Lightweight.** And I want the site to have nothing more than what is required to render the content the way I want to. Nothing (not much) more than that!

One thing I was sure of was to use a static site generator. I had used it before (in previous version) and it just makes sense. But which one?

Having used Gatsby in the previous iteration of the website, my first consideration was, naturally, Gatsby. It fit most of the criteria above. It is based on React- so checks the Javascript, NPM, and components box. That also meant adding features would not be that hard *(it is React after all!)* as long as I kept that in mind while building the site. You can use a markdown to write content to have Gatsby Node API create page by populating templates with content. So adding new content would be pretty smooth. It is only the last point I was not sure of. It is React after all. I love it, don't get me wrong. But it provided way more than what I needed. Really! I remember reading this blog some time ago comparing React to a fire-breathing-dragon. I felt somewhat similar using Gatsby for this site.

Gatsby was obviously there if I didn't find a better fit, but I decided to search a bit more. People seemed to be fan of Ghost and Jekyll and Hugo besides Gatsby. But these weren't in Javascript. Then I came across [11ty](https://www.11ty.dev/) in this [Kinsta blog](https://kinsta.com/blog/static-site-generator/) while searching for lightweight static site generators. I researched some more and went through [Zach's blog](https://www.zachleat.com/web/introducing-eleventy/) on why he created 11ty. Many of the things I came across vibed with what I was looking for. Most notably,

- the final output is just HTML and CSS (and some JS if I wanted to add for functionality). Just simple and lightweight.
- it is built for just something like this website. It didn't seem to boast too many fancy features, but seemed to have enough for my purpose. Moreover, there is scope to add things on top of it with custom templating.
- it is not based on any JS frameworks. So there won't be much friction due to the opinion of the framework when extending features.
- there is a separation of content and code. So if in the future I want to move to other tool, migrating content will not be a problem.

*Looking back, I think I wanted to learn something new too which might have added some weight in favor of 11ty over Gatsby.*

I also tried looking at much simpler options- like using just [mustache](https://juandavidvega.es/2016/10/07/generating-static-websites-with-mustache-and-node/) or [nunjucks](https://publishing-project.rivendellweb.net/building-my-own-static-site-generator/) with custom logic for templating. But it seemed, to some extent, like reinventing the wheel. Plus with each feature I would ever add, there would be more work to be done, and thus more friction, than just using 11ty.

So 11ty it was. And I am loving it so far. The learning curve is not too steep, and it has the features I need.

<!-- You can see the full list of tools and choices I have made [here](/colophon). -->