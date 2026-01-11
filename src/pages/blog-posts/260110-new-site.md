---
layout: "../../layouts/BlogLayout.astro"
title: "Cosplaying as a Full Stack Developer"
description: "Why I decided to ditch Squarespace and build my own portfolio from scratch using Astro."
date: "2026-01-10"
author: "Flore Vanackere"
thumbnail: "/images/blog-posts/260110-new-site/thumb.png"
---

## Introduction
Back when I created my first portfolio website in 2015, I built it using basic HTML and CSS using, if memory serves me well, Dreamweaver.

The website was basic, rough and difficult to maintain, but it served its purpose at the time.
<img width="400" src="/images/blog-posts/260110-new-site/website-01.png" alt="website-03">

A few years later, I retired that website and opted to use ArtStation’s built-in website builder. To get the site looking the way I wanted, I subscribed to ArtStation Premium, which cost around £10 per month. Very quickly, I became frustrated with how limited the builder felt. There were many aspects I couldn’t change, but I accepted that it was still better than my old HTML site, so I dealt with it and paid the monthly price. You will notice all the websites share some design aspects. For example, the square gallery and with this one especially I really liked the "resume" page layout.
<div class="gallery">
<img src="/images/blog-posts/260110-new-site/website-02.png" alt="website-02">
<img src="/images/blog-posts/260110-new-site/website-03.jpg" alt="website-03">
</div>

Years later when production on _Forza Horizon 5_ was wrapping up, I didn’t yet have a permanent position at Playground Games and my contract was nearing its end. With that uncertainty in mind, I decided my portfolio website needed a refresh. I explored a few options and eventually settled on Squarespace. It offered significantly more flexibility than ArtStation and felt closer to something like WordPress, with pages composed of modular content blocks.

I was initially very happy with the results and ended up using that website for almost five years. Even though the monthly cost was **£20** (!!), I must have justified it at the time since I was preparing to actively look for a new job. However, once I did end up securing a permanent position at PG, the website was no longer something I strictly needed.

Regardless, this meant I had paid roughly **£1,100** to Squarespace over five years without really getting much value from it. So fast-forward to last week, when my banking app notified me that I had paid another £20 to Squarespace. That was the moment I thought: No more. We’re going full circle, I’m making an HTML website again.

<div class="gallery">
<img src="/images/blog-posts/260110-new-site/website-04.png" alt="website-02">
<img src="/images/blog-posts/260110-new-site/website-05.jpg" alt="website-03">
</div>

## Portfolio and Artstation rant
These days, I spend more of my spare time exploring technical topics or building prototypes and less time producing art. Because of that, a conventional art portfolio no longer feels like the right fit for me. I believe that a decade of experience and more than a handful of shipped titles should be enough to demonstrate what I’m capable of. At the same time, I still enjoy creating experiments and small personal projects and might want to share them with the world.

This leads me to my problem with ArtStation.

I love how quickly ArtStation has become the industry standard for sharing art. At the same time, I dislike that it _is_ the industry standard for art portfolios. I’ve always viewed it as an art community, a place to share things you’ve created, and I think that is still its core purpose. However, it has also become a de facto filtering tool for employers and recruiters.

The old saying _“Your portfolio is only as good as your worst piece”_ still very much applies, and I feel it discourages experimentation on ArtStation. If I wanted to, for example, refresh my character art skills, publishing early attempts there would feel risky, as it could lower the perceived quality of “my ArtStation.” In fact, this has happened to me before. I once had a range of small projects on my profile, ranging from low-poly character models and 3D print designs to 2D drawings. A recruiter advised me to delete all of them, as they felt it was hurting my chances of landing a job.

I remember trying to argue, _“Send them to my curated website portfolio, not my ArtStation.”_ But I digress.

Going forward, If I finish any future art pieces in my spare time, I won’t be following that advice anymore. That said, it would be great if ArtStation offered a better way to share WIPs or experiments in a less formal context. Or maybe it’s simply time to look for a different community altogether. I’ve heard some good things about Mastodon, for example.

## How to make a website
Once I decided to build my own website again, I started searching for modern, visual, and relatively simple ways to create a site that would still give power users the control they need. This turned out to be much harder than I expected. Systems like that were rare, and when I did find them, they were often proprietary solutions hidden behind expensive paywalls.

I had honestly expected there to be some kind of open-source, Dreamweaver-like powerhouse that had become an industry standard. Even when searching for something supposedly simpler as a CSS designer, I came up short. In the end, it seemed that most people simply do things by hand.

Or, in my complete ignorance on the subject, maybe I just didn’t know what to search for.

### How to make a website, from scratch
So people still code (static)websites by hand, but surely they use some kind of framework or tooling to make it easier? I remember that with my first website, whenever I wanted to change how content pages looked, I had to open each HTML file individually and copy-paste the same changes over and over again.

I quickly came across a wide range of frameworks using different languages, JavaScript, Python, C#, PHP, and more. However, it wasn’t immediately clear what their exact purpose was, and to be frank, I still don’t fully understand the extent of how some of them can be used. In the end, the new website remains fairly simple and straightforward.

At the same time, I looked into popular IDEs and editors. I settled on _JetBrains WebStorm_, as I was already familiar with J*etBrains Rider* for Unreal Engine development.

At that point, I simply asked ChatGPT:
>  I want to build a simple, contemporary-looking static website for my portfolio using Webstorm, hosted on Cloudflare pages. I already have a domain there. What are the prerequisites and which framework, if any, should I pick.

It gave me a few suggestions like Vite, React, Astro or even using no framework at all. After I described what I wanted in more detail, like adding this blog, it recommended to use **Astro**.

I watched a short video explaining what Astro is and how it works, and one of the aspects I found most interesting was its ability to compile Markdown into static HTML. This meant the site would need to be built, but it also allowed me to write blog posts in a simple Markdown editor like Obsidian, commit the files to my Git repository, and have them automatically appear on the site.

I also liked the concepts of Layouts and reusable Components.

I was worried that it would involve a lot of complex code or unfamilair syntax but, honestly, this was one of the easier things to learn. I could still make my website fully with HTML and CSS within the Astro framework without using any of its features which meant I had something up and running within minutes and I could gradually add or experiment with the features as I went on.
### "Junie" - Webstorm's AI assistant
Might as well get my take on AI usage out there. AI can be an extremely useful tool and it's here to stay.
Am I sick of getting AI pushed down my throat on every website or software package I use? Or how it has inflated prices for personal computing hardware? ABSOLUTELY.

My biggest problem, aside from the constant push for it, is when people output AI-generated images as-is and present them to the world as finished art. This might come off as hypocritical, which it probably is in some way if I only criticise usage that overlaps with my own profession.  
If you must, use it as a tool to elevate your work. Not as a printer.

With that in mind, I tried to keep the "vibe-coding" to a minimum so I could still understand the generated code. That said, it was extremely useful to ask the AI to turn my messy HTML into a reusable Astro component or layout. And seeing it go through the entire project changing files left and right was impressive to see. It helped me understand how the framework should be used and sped the whole thing along quite nicely.

Webstorm also has some handy context menu options like *"Explain Code"* which will prompt the AI assistant to walk through each line of the selected code.

An example of an Astro component is the production cards on the main page. I have an array at the top of the page with all the relevant information in there:
```
const productions = [
	{  
		  image: "/images/fh5-cover.jpg", 
		  title: "Forza Horizon 5",  
		  year: "2021", 
		  role: "Environment Artist", 
		  company: "Playground Games", 
		  href: "/productions/fh5" 
	},
	{  
		  image: "/images/fh5-hot-wheels-cover.jpg",
		  title: "FH5 - Hot Wheels", 
		  year: "2022",
		  role: "Environment Artist",
		  company: "Playground Games",  
		  href: "/productions/fh5-hot-wheels"
	},
	{
	....
	}
];
```

Further down, where the production grid is rendered, only a few lines are needed to loop through this array and add a component for each element with the correct data. This makes adding new entries trivial, just append another object to the array.

## Conclusion
I think I’ve rattled on long enough. In any case, I love that I can call this website my own again. There is something satisfying about stripping things back to fundamentals and understanding every part of how it works, rather than relying on subscription-based platforms and opaque systems. And that goes for al lot of things beyond building a personal website.

For now, this site does what I need it to do: it showcases my work, gives me space to experiment, and acts as a place where I can write and share without worrying about algorithms, platform rules, or monthly fees. That feels like a good foundation to build on.  

