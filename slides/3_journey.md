# OUR JOURNEY TO<br/> DECOUPLED APPS

///

## Starting point at Caxy

- Caxy practices user-centered design
- Caxy wants to create the best possible experience for the user
- Decided to start building single-page applications
- This required us to change how we build Symfony apps

Note:
At Caxy, we practice user-centered design and strive to provide the best possible experience for the user.

To be able to deliver on that initiative consistently, we needed to level-up our game on the front-end by building single-page applications.

To accommodate developing SPAs, we needed to change the way we used Symfony.
Instead of building the full web app in Symfony, we needed to build an API for the front-end to interface with.

We had used FOSRestBundle and JMSSerializerBundle to handle AJAX calls on most of our Symfony projects and those worked well for us,
so we decided we would work with those bundles to help built out the REST API of our first decoupled app. 

---

## REST API - First Iteration

///

### Basic Requirements

- Support JSON
- User authentication
- Cross-Origin Resource Sharing (CORS) headers
- Basic CRUD for REST resources
- API Documentation

Note:
We came up with a list of the very basic requirements for the REST API.

It needed to be able to:

- Support JSON - both handling JSON request data as well as returning JSON in responses.
- User authentication - stateless user authentication since the app we were building had user login.
- Use Cross-Origin Resource Sharing (CORS) headers so the front-end can access the API endpoints.
- Basic CRUD for REST resources - for that app, the REST resources would be persisted to a database. 
- API Documentation - this was more of a nice-to-have, but we had been aware of the NelmioApiDocBundle so we knew we could meet this requirement.

///

### Bundles used to handle REST API

| Bundle | Related Requirement(s) |
|--------|--------------------------|
| FOSRestBundle | Support JSON,<br/>Basic CRUD |
| LexikJWTAuthenticationBundle | User authentication |
| JMSSerializerBundle | Support JSON,<br/>Basic CRUD |
| NelmioCORSBundle | CORS headers |
| NelmioApiDocBundle | API Documentation |

Note:
- FOSRestBundle : Fulfils supporting JSON and handles routing for REST resources
- LexikJWTAuthenticationBundle : Handles user authentication
- JMSSerializerBundle : Handles supporting JSON
- NelmioCORSBundle : Handles CORS headers
- NelmioApiDocBundle : Handles API Documentation

///

### Outcome

Met the basic requirements with limitations:

- Hard-coded paths to REST resources in front-end code
- Embedded relationships in REST data are not self-describing
- Not able to easily accommodate different contexts of the same REST resource

Note:
We were able to meet each of the basic requirements for the REST API using those bundles. However, we did identify some limitations with our implementation while working through the project.

---

## REST API - Second Iteration

Set out to solve:

##### “Hard-coded paths to REST resources in front-end code”

##### "Embedded relationships in REST data are not self-describing"

<br/><br/>
Added the following basic requirement for our REST API:

**API is “discoverable” by the consumer without having prior knowledge of the API’s interface**

///

### Solution - HATEOAS

HATEOAS stands for **Hypermedia as the Engine of Application State**.
<br/><br/>
A REST API that implements the HATEOAS constraint will include hypermedia links within the responses for resources which link to resource relations or actions that can be taken.
<br/><br/>
Bundle used: BazingaHateoasBundle (by willdurand)

///

### Example

<div class="row">

<div class="col-left">

User representation without HATEOAS

<pre>
<code data-trim>
{
    "user": {
        "id": 123,
        "first_name": "John",
        "last_name": "Doe"
    }
}
</code>
</pre>

</div>

<div class="col-right">

User representation with HATEOAS

<pre>
<code data-trim>
{
    "id": 42,
    "first_name": "John",
    "last_name": "Doe",
    "_links": {
        "self": {
            "href": "/api/users/42"
        },
        "manager": {
            "href": "/api/users/23"
        }
    },
    "_embedded": {
        "manager": {
            "id": 23,
            "first_name": "Will",
            "last_name": "Durand",
            "_links": {
                "self": {
                    "href": "/api/users/23"
                }
            }
        }
    }
}
</code>
</pre>

</div>

</div>

Example from: https://github.com/willdurand/Hateoas#introduction

Note:
This ends up solving the limitations we set out to solve from the first iteration, which was

"Hard-Coded paths to REST resources in front-end code"

AND

"Embedded relationships in REST data are not self-describing".

The embedded relationship in the example above could be considered self-describing because it includes a
HATEOAS link for `self` which can then be used to retrieve the resource directly, or determine the resource type from the hyperlink.

This is certainly not an all encompassing solution as there could be more metadata included about the resource type itself,
which I have show examples of here in just a little bit. 

///

### Outcome

We ended up using HATEOAS a great deal on the project that this iteration was done on, and it got the job done nicely. 
<br/><br/>

The front-end was built in AngularJS and relies on the HATEOAS links and embedded resources for almost all cases where it interfaces with the back-end.  