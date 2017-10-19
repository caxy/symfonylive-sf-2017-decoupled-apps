## WHO IS JOSH, WHAT IS A CAXY,<br/> AND WHY DO DECOUPLED APPS MATTER?

---

## Hi, I'm Josh!

- Full stack developer with 12 years experience 
- Exclusive with Symfony for the last 5 years
- Currently the Senior Developer at Caxy
- Currently geeking out over **React** + **Redux** // **Symfony** + **API Platform**

Note:
Well! I'm josh...

i've worked in a lot of frameworks and languages for that 12 years... but i'm pretty much exclusively with symfony for the last almost 5 years

my first symfony install was 2.1 - pretty excited about 4.0 by the way!

currently i am the senior developer for caxy and i'm right now i'm investing most of my energy in leveraging the power of react and react 

and symfony with api platform

NEXT : so a little bit more about this caxy you keep hearing about


///

## CAXY IS NOT AN ABBREVIATION OR A TECH TERM.

IT MEANS “RIBBIT” IN ANCIENT GREEK AND WAS OUR FOUNDER’S HIGH SCHOOL MASCOT.<br/> #themoreyouknow

Note:
CONTRARY to popular belief CAXY is NOT an abbreviation or a tech term!

it's actually a more obscure reference... heh.

it actually is ancient greek for the "ribbit" sound a frog makes...

the tie in to tech is that our founder... mike lavista... went to school a suburb in illinois and their mascot was a frog... and yep you guessed it named caxy

so there ya go! quiz is later.

NEXT: on a more serious note... caxy is a web development agency

///

#### Caxy is a web application development company

**we build custom sites and applications.**
<br/><br/>
**Our mission:**<br/> Improve the digital world with products that our clients<br/> and their users love long after launch day

Note:
we built... pretty much anything... but USUALLY custom sites and applications... 

and we build them for a number of industries and sectors.

over the last couple of years we've specialize in non-profits, universities, and health care.

We also have really exciting projects in the financial sector, in manufactoring, and our favorite ... of course... is the small start up with big ideas!

we are a full service agency - so everything from ideation to content strategy, design to development and support - it's what we do!

quick humble brag... we're pretty good at it! 

we receive awards and recognitions every year...

most recently we were recognized by clutch co as a top web development agency and top custom software development agency.

and of course we appreciate the recognition.. but that's not the only reason we do this ...

our mission at caxy is to Improve the digital world with products that our clients 
and their users love long after launch day.

And for some products, to be the best they could be... we had to think about doing something different.

NEXT: We needed to start building decoupled apps..  

---

# DECOUPLED APPS

Note:
So now the reason you're here! let's talk about decoupled apps!

///

## WHAT IS A DECOUPLED APPLICATION?

In the context of this talk: 

**An application which has its front-end decoupled from its back-end,<br/> where the front-end interfaces with a back-end API**

Note:
First... what is a decoupled application?

some of you may know and some of you may not. and there are a few ways to answer that question...

but for the context of this talk... a decoupled app is an application which has its front-end decoupled from its back-end,
where the front-end interfaces with a back-end API

an example of this would be:

A single-page application (SPA) built in React that interfaces with a REST API built in Symfony.

but what does that mean? and why does that matter? ...

---

## WHY DECOUPLED APPS MATTER

Decoupled applications and single-page applications (SPAs)<br/> are becoming widely-used, **and for good reason**.

Note:
Single-page applications (SPAs) bring significant benefits that unlock capabilities on the web that cannot be rivaled by multi-page applications (MPAs).

Many are moving towards decoupled architectures and the future of the front-end technologies seem like they will continue down that path.

NEXT: I could talk about a ton of them... but i'm going to focus on just a few for today...

///

### Advantages of Decoupling front-end & back-end

- Ability to build the Front-end as a SPA
- Better performance & scalability
- Develop faster
- Improved deployments & infrastructure
- Additional abstraction layer

Note:
- Ability to build the Front-end as a SPA
- Better performance & scalability
- Develop faster
- Improved deployments & infrastructure
- Additional abstraction layer

///

#### Single-Page Applications (SPAs)

- Ability to deliver a greatly improved user experience
- Better performance
    - smaller request load
    - less server-side load
    - code splitting
- Advanced front-end tooling

Note:
A key advantage of decoupled apps is the ability to build the front-end as a single-page application.

Doing that prevents you from having to reload the page fully on each new page, which can be a really terrible user experience.

The beauty of a single-page app is that you control what happens on the page while things are loading in the background.

And directly with that comes better performance & scalability.

///

#### Better performance & scalability

- Front-end as static deploy can scale out of box
- Back-end scaling easier
- Back-end can use HTTP caching for API resources

Note:
Front-end is served as a static site that can be cached and scaled as needed.

On the back-end, it is much less effort to build an API that can be distributed across instances when it is decoupled from the front-end.

Thanks to having stateless user auth there's no need to implement shared PHP sessions across server nodes.  

Since the back-end data is all accessed through the REST API over HTTP, back-end can utilize HTTP caching as needed.

NEXT: Not only does the app get faster, but development can too!

///

#### Develop faster

- Front-end and back-end can work independently with a well-defined API interface
- Front-end developers work in familiar code and environment
- Back-end developers work in familiar code and environment
- Allows for rapid prototyping without writing code that will ultimately be scrapped

Note:
First off, the front-end and back-end could technically be developed indepedently from the other, and in some cases even in parallel, as long as there's a well defined API interface.

NEXT: In additional to development being smoother, deployments and managing infrastructure can too!

///

#### Deployments & Infrastructure

- Can have separate deploy pipelines
- Front-end deployed as static application
- More granular versioning

Note:
Separate deploy pipelines: deployments become simpler and independent of each other.

NEXT: Onto the last advantage i'm going to cover now!! 

///

#### Additional abstraction layer

- Front-end and back-end code completely separated
- Can have different conventions and standards
- Release front-end from the structures and opinions of the back-end
