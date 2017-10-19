## WHO IS JOSH, WHAT IS A CAXY,<br/> AND WHY DO DECOUPLED APPS MATTER?

---

## Hi, I'm Josh!

- Full stack developer with 12 years experience 
- Exclusive with Symfony for the last 5 years
- Currently the Senior Developer at Caxy
- Currently geeking out over **React** + **Redux** // **Symfony** + **API Platform**

///

## CAXY IS NOT AN ABBREVIATION OR A TECH TERM.

IT MEANS “RIBBIT” IN ANCIENT GREEK AND WAS OUR FOUNDER’S HIGH SCHOOL MASCOT.<br/> #themoreyouknow

///

#### Caxy is a web application development company

**we build custom sites and applications.**
<br/><br/>
**Our mission:**<br/> Improve the digital world with products that our clients<br/> and their users love long after launch day

Note:
- Received Awards and Recognitions from Clutch.co, Acquia, Inc.5000 and others. 
- Our clients work in a number of industries: Universities, Healthcare, Non-Profits, Financial Sectors, Startups, and more.
- We are full service: Ideation, Content Strategy, UX, Design, Architecture, Development, Support
- Our mission: improve the digital world with products that our clients and their users love long after launch day… and for some products to be the best they could be, we needed to think about doing something different - we needed to start building decoupled apps. 

---

# DECOUPLED APPS

///

## WHAT IS A DECOUPLED APPLICATION?

In the context of this talk: 

**An application which has its front-end decoupled from its back-end,<br/> where the front-end interfaces with a back-end API**

///

##### Example

A single-page application (SPA) built in React that interfaces with a REST API built in Symfony. 

Note:
A decoupled application in the context of this talk is an application which has a front-end that is completely decoupled from a back-end API. 

---

## WHY DECOUPLED APPS MATTER

Decoupled applications and single-page applications (SPAs)<br/> are becoming widely-used, **and for good reason**.

Note:
Single-page applications (SPAs) bring significant benefits that unlock capabilities on the web that cannot be rivaled by multi-page applications (MPAs).

Many are moving towards decoupled architectures and the future of the front-end technologies seem like they will continue down that path.

///

### Advantages of Decoupling front-end & back-end

- Front-end can be a SPA
- Better performance & scalability
- Develop faster
- Improved deployments & infrastructure
- Additional abstraction layer
- Easier to test

///

#### Single-Page Applications (SPAs)

- Ability to deliver a greatly improved user experience
- Better performance
    - smaller request load
    - less server-side load
    - code splitting
- Advanced front-end tooling

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

///

#### Develop faster

- Front-end and back-end can work independently with a well-defined API interface
- Front-end developers work in familiar code and environment
- Back-end developers work in familiar code and environment
- Allows for rapid prototyping without writing code that will ultimately be scrapped
- Front-end and back-end of features can be developed in parallel

Note:
Other items could be: 
- less coupling = less regressions
- Having an API on the back-end allows for additional clients in the future for example native mobile apps or exposing a public API.
- Testing becomes much easier
- Can rebuild the front-end without touching back-end or vise versa.

///

#### Deployments & Infrastructure

- Can have separate deploy pipelines
- Front-end deployed as static application
- More granular versioning

Note:
Separate deploy pipelines: deployments become simpler and independent of each other.

///

#### Additional abstraction layer

- Front-end and back-end code completely separated
- Can have different conventions and standards
- Release front-end from the structures and opinions of the back-end

///

#### Testing

- Modular components are much easier to test
- Testing the back-end API
- Integration testing between back-end and front-end