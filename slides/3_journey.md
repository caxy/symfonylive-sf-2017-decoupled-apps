# OUR JOURNEY TO<br/> DECOUPLED APPS

---

## REST API - First Iteration

///

### Basic Requirements

- Support JSON
- User authentication
- Cross-Origin Resource Sharing (CORS) headers
- Basic CRUD for REST resources
- API Documentation

///

### Bundles used to handle REST API

| Bundle | Related Requirement(s) |
|--------|--------------------------|
| FOSRestBundle | Support JSON,<br/>Basic CRUD |
| LexikJWTAuthenticationBundle | User authentication |
| JMSSerializerBundle | Support JSON,<br/>Basic CRUD |
| NelmioCORSBundle | CORS headers |
| NelmioApiDocBundle | API Documentation |

///

### Outcome

Met the basic requirements with limitations:

- Hard-coded paths to REST resources in front-end code
- Embedded relationships in REST data are not self-describing
- Not able to easily accommodate different contexts of the same REST resource

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

///

### Outcome

We ended up using HATEOAS a great deal on the project that this iteration was done on, and it got the job done nicely. 
<br/><br/>

The front-end was built in AngularJS and relies on the HATEOAS links and embedded resources for almost all cases where it interfaces with the back-end.  
