---
layout: post
title: "History Repeats Itself, But I Have Hope"
date: 2026-10-09 16:58:00 -0700
categories: engineering ai complexity
---

Take a look at this graph:

![Code Complexity vs. Years of Programming]({{ site.baseurl }}/images/original_complexity_curve.jpg)

Most tenured engineers recognize this curve immediately.

When you start programming, you write simple code because you only know the basics.

Then comes the middle phase, fueled by Clean Code hype and enterprise nonsense. Suddenly, printing a string needs a `PrintHelloWorldToConsoleAbstractStrategyFactoryBean`. A senior engineer blocks your pull request demanding you replace a four-line switch statement with the Command Pattern, simply because he read a blog post that morning calling it a "best practice."

People spent all their energy on this theater. Endless arguments over indentation, trailing commas, and whether a line hit 81 characters. Cutting a working 150-line file into six pieces just because someone said no file should ever be over 100 lines. Every single class had to have an interface, so codebases drowned in `UserService` and `UserServiceImpl` that did the exact same thing. People wrote endless mapper code just to copy fields from an Entity to a DAO to a DTO to a ViewModel, just to move an ID and an email across two functions. Developers spent days writing tests where mocks just tested other mocks, without testing if the software actually worked. In annual reviews, people got feedback like "you should learn to use Checkstyle" instead of talking about what they actually built (true story).

Years of engineering work were completely wasted on this nonsense. It ruined careers, created codebases nobody could read, and taught developers to care more about the plumbing than the actual product.

Worse, it stopped a whole generation of developers from learning how computers actually work. People spent years learning how to pass an object through fifteen layers of code just to call one method, with no clue what came out at the end. All that time could have been spent understanding memory, CPU caches, operating systems, networking, and the actual problem they were trying to solve. Instead, the industry created developers who only knew how to connect frameworks.

Eventually, this realization hit, but only for very few of us, and by then it was already too late. Very few of us came full circle to see that simple, boring, readable code beats clever abstractions every single day. Most people never woke up from it, and the damage was already done.

You would think we learned our lesson. We didn't. Instead, we doubled down on the frontend.

If enterprise Java was the disease on the backend, JavaScript was the absolute circus on the frontend. 

Look at what we did to ourselves for fifteen years. 

First you used jQuery and Prototype. Then someone said you needed MVC in the browser, so you migrated to Backbone, Knockout, Ember, and AngularJS. You installed Yeoman to scaffold an entire project with 800 files of configuration before writing one line of code. You used Bower, Grunt, and Gulp. 

Then Angular broke everyone with Angular 2, so the entire industry threw away their codebases and jumped to React. But plain React was not enough, so you needed Redux with action creators, reducers, thunks, sagas, and reselect just to toggle a modal. Then React decided class components were bad, so you rewrote everything in hooks. Then client-side rendering was bad, so you needed Gatsby. Gatsby died, so everyone rushed to Next.js. Then Next.js rewrote their own router from Pages to App Router and forced React Server Components down everyone's throat.

And the tools were an even bigger nightmare. From Bower to npm, Yarn, pnpm, and Bun. You spent weeks debugging 400-line Webpack configs and Babel plugins, only to throw them in the trash for Rollup, Parcel, esbuild, and Vite. You had 500MB of `node_modules` just to center a `<div>` on a web page. Developers spent more time fixing build errors, hydration mismatches, and dependency hell than actually writing business logic.

It got so absurd that Ryan Dahl, the creator of Node.js himself, had to get on stage at JSConf and give a talk titled [10 Things I Regret About Node.js](https://www.youtube.com/watch?v=M3BM9TB-8yA). The person who built the foundation of the ecosystem had to publicly admit that choices like `node_modules` and the module resolution system turned into massive regrets.

And after fifteen years of this madness, where did the industry land? People cheering for HTMX, realizing that sending plain HTML from a server was the right answer all along.

Did that teach us anything? Not a chance.

Now look at what we are doing with AI:

![AI Stack Complexity vs. Experience Building with AI]({{ site.baseurl }}/images/ai_complexity_curve.jpg)

It is the exact same curve all over again. Only the buzzwords changed.

Instead of collecting Sun Java certifications, people are collecting Anthropic and Claude Prompting certificates.

People post on LinkedIn claiming "we are training our model." You are not training any model. You are tuning a prompt.

Then comes the framework circus. You have a problem that needs a simple prompt and a basic script, but that feels too small. It does not look like serious AI engineering. So you pull in LangChain, connect twenty tools, and set up autonomous multi-agent swarms with supervisor loops and reflection agents. You end up with one agent passing a messy prompt to another agent, which guesses what you meant, and passes garbage to a third agent. In regular programming, bad code at least crashes and gives you a stack trace. With AI, it is so much worse. It does not crash. It confidently hands you complete garbage, and you have no idea which layer invented it.

On top of that, people are obsessed with the tools. A new model drops every single day. People rush to social media to post about it like they were the first person on earth to find it. They drop whatever they are building just to chase the newest benchmark or the newest wrapper. They get totally distracted from the real problem.

Why? Because nobody wants to do the hard work: actually understanding the problem and writing down clear requirements.

People fell for this dumb idea that if you just stack enough agents together, the agents will magically figure out the requirements for you. They won't.

If I give an AI conflicting requirements, it is not the AI's fault that it generates random code and crap. It is my fault. I am the one in control of how to give commands, exactly like how we write code. When you give a compiler broken logic, it fails. When you give an AI conflicting instructions, it hallucinates. Wrapping those bad instructions in five agents does not make them clearer. It just gives you five agents hallucinating off each other. The more layers of abstractions with hidden meaning you add, the less you understand what is going on.

This does not mean multiple agents are always bad. When you have genuinely separate tasks with isolated boundaries, multi-agent systems have their place. But the machinery is not the answer.

Ultimately, data is the truth, which was always true. Decades ago, Fred Brooks wrote that if you show him your tables, he doesn't need to see your code. Linus Torvalds said the exact same thing: good programmers worry about data structures, bad programmers worry about code. Rob Pike called it Rule 5: data dominates.

It is data-oriented programming. It was always data-oriented programming. What is the shape of the data going into the model? Are your requirements clean and free of contradictions? What exact output are you expecting?

When you actually sit down, clean your data, and write clear requirements, you do not need all that machinery. The whole thing collapses right back to the bottom of the curve: a simple prompt and clean data.

## My Hope

The only real difference this time is speed.

It took thirty years for a few of us to see through enterprise patterns. It took years of JavaScript churn to realize that we did not need so many build tools to show a web page. Both times, we moved slowly and lost years of work.

AI moves so much faster. The hype burns hot and quick.

My hope is that this speed works in our favor. Because everything moves so fast, my hope is that the fever breaks much sooner:

Instead of chasing every new model that drops on social media, I hope developers take the time to learn how these systems work under the hood.

Instead of stacking agent frameworks to hide vague thinking, I hope we learn to describe real problems and write clear requirements.

Instead of blaming the model when bad prompts give bad results, I hope we take ownership of what we ask for.

And instead of obsessing over fancy tools, I hope we respect the data.

It took thirty years of pain for a few of us to learn that simple, boring code wins. My hope is that this time, it does not take another generation to realize it. The answer was always right in front of us: clean data, clear requirements, and keeping it simple.
