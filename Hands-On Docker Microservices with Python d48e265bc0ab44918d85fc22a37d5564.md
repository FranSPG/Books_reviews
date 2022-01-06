# Hands-On Docker Microservices with Python

## Preface

> The microservice architecture has gained traction in recent years as an effective technique for dealing with complex web services and allowing more people to work on the same system without interfering with one another. In a nutshell, it creates small web services where each one solves a specific problem, and they all coordinate together through well-defined APIs.
> 

## The traditional monolith approach and its problems

> What defines a monolith is the requirement to deploy the system as a whole, without being able to make partial deployments.
> 

## Preparing and adapting by measuring usage

> If your system is a web service, by default, it will have activated its access log. This will log each HTTP request that comes into the system and store the URL, result, and time when it happens. Check with your team where these logs are located, as they will provide good information on what URLs are being called.
> 

## Web services’ best friend - The load balancer

> Any web server capable of acting in reverse proxy mode, such as NGINX, is capable of working as a load balancer, but, for this task, probably the most complete option is HAProxy (http://www.haproxy.org/).
HAProxy is a specialized in acting as a load balancer in situations of high availability and high demand. It’s very configurable and accepts traffic from HTTP to lower-level TCP connection if necessary. It also has a fantastic status page that will help to monitor the traffic going through it, as well as taking fast action such as disabling a failing worker.
Amazon Web Services is called Elastic Load Balancing (ELB)—[https://aws.amazon.com/elasticloadbalancing/.](https://aws.amazon.com/elasticloadbalancing/.%E2%80%9D)
> 

## Designing the RESTful API

> We will follow the principles of RESTful design for our API. This means we will use constructed URIs that represent resources and then use the HTTP methods to perform actions over these resources.
> 

## Specifying the API endpoints

> One final detail: there is some debate over whether it's best to end URI resources with a final slash or not. When working with Flask, though, defining them with a slash will return a redirect status code, 308 PERMANENT_REDIRECT, for a request without the proper ending. In any case, try to be consistent to avoid confusion.
>