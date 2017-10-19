# WHAT WE’RE DOING NOW

///

## API Platform

Once we found API Platform, we decided to use it for our decoupled applications going forward. 

https://api-platform.com/

API Platform: "The ultimate PHP framework to build modern web APIs."

Built on top of the Symfony framework.

Default distribution of API Platform is a Symfony full-stack application.

///

### High-Level Overview

Create a CRUD API in minutes (I'm not even kidding!)

It is able to create a full REST API with CRUD functionality from your PHP model classes. If using Doctrine, API Platform takes care of the rest.

Note:
**Features**

- creating, retrieving, updating and deleting (CRUD) resources
- data validation
- pagination
- filtering
- sorting
- a nice UI and machine-readable documentation (Swagger/OpenAPI, Hydra)
- hypermedia/HATEOAS and content negotiation support (JSON-LD, HAL)
- authentication (Basic HTTP, cookies as well as JWT and OAuth through extensions)
- CORS headers
- security (tested against OWASP recommendations)
- HTTP caching
- and basically everything needed to build modern APIs.

///

### Our REST API Requirements

The basic requirements for our REST APIs up until now were:

- Support JSON
- User authentication
- CORS headers
- Basic CRUD for REST resources
- API Documentation
- HATEOAS

Note:
API Platform meets all of these requirements out of the box, and includes many more on top of it.

For example, it supports JSON-LD (JSON for Linked Data).

It has machine-readable documentation of the API in the Hydra format.

///

### API Platform Features

- creating, retrieving, updating and deleting (CRUD) resources
- data validation
- pagination
- filtering
- sorting
- a nice UI and machine-readable documentation (Swagger/OpenAPI, Hydra)
- hypermedia/HATEOAS and content negotiation support (JSON-LD, HAL)
- authentication (Basic HTTP, cookies as well as JWT and OAuth through extensions)
- CORS headers
- security (tested against OWASP recommendations)
- HTTP caching
- and basically everything needed to build modern APIs.

---

# A (very) short intro to API Platform

///

### Mapping Entities

<pre class="stretch"><code data-trim>
&lt;?php

// src/AppBundle/Entity/Product.php

namespace AppBundle\Entity;

use ApiPlatform\Core\Annotation\ApiResource;
use Doctrine\ORM\Mapping as ORM;
use Symfony\Component\Validator\Constraints as Assert;

/**
 * @ApiResource
 * @ORM\Entity
 */
class Product // The class name will be used to name exposed resources
{
    /**
     * @ORM\Column(type="integer")
     * @ORM\Id
     * @ORM\GeneratedValue(strategy="AUTO")
     */
    public $id;

    /**
     * @param string $name A name property - this description will be avaliable in the API documentation too.
     *
     * @ORM\Column
     * @Assert\NotBlank
     */
    public $name;
}
</code></pre>

///

### Mapping Entities (cont)

<pre class="stretch"><code data-trim>
&lt;?php

// src/AppBundle/Entity/Offer.php

namespace AppBundle\Entity;

use ApiPlatform\Core\Annotation\ApiResource;
use Doctrine\ORM\Mapping as ORM;
use Symfony\Component\Validator\Constraints as Assert;

/**
 * An offer from my shop - this description will be automatically extracted form the PHPDoc to document the API.
 *
 * @ApiResource(iri="http://schema.org/Offer")
 * @ORM\Entity
 */
class Offer
{
    /**
     * @ORM\Column(type="integer")
     * @ORM\Id
     * @ORM\GeneratedValue(strategy="AUTO")
     */
    public $id;

    /**
     * @ORM\Column(type="text")
     */
    public $description;

    /**
     * @ORM\Column(type="float")
     * @Assert\NotBlank
     * @Assert\Range(min=0, minMessage="The price must be superior to 0.")
     * @Assert\Type(type="float")
     */
    public $price;

    /**
     * @ORM\ManyToOne(targetEntity="Product")
     */
    public $product;
}
</code></pre>

///

### Configuring Operations

How to limit resource to *only* GET method for item and collection operations.

<pre><code data-trim>
<?php

// src/AppBundle/Entity/Book.php

use ApiPlatform\Core\Annotation\ApiResource;

/**
 * @ApiResource(collectionOperations={"get"={"method"="GET"}}, itemOperations={"get"={"method"="GET"}})
 */
class Book
{
    // ...
}
</code></pre>

Note:
NEXT: Unfortunately, this is as deep into API platform we're going to go today...

BUT! Don't fret, the documentation is actually really solid and it continues to get better and better.

///

### More Information

Check out the API Platform documentation at https://api-platform.com/ for more information.

Get started with the [API Platform Standard Edition](https://api-platform.com/docs/distribution/).
