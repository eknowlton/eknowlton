# Distributed Systems, Good or Great?

There seems to be a lot of popularity around distributed systems these days, especially with the growing hype of new languages such as Go, Elixir and Rust. These new languages all lend themselves very well to concurrent distributed system services. 

It seems that a lot of programmers are gunning straight for the Distributed Systems approach even when the approach won't be the best fit. When designing a distributed system there a many considerations.

- Concurrency
- Scale-ability
- Compose-ability
- Security
- Quality of Service
- Reliability
- Performance
- Management

### Concurrency

One of the major wins with distributed systems is the ability to run multiple process concurrently. I'm not going to get into the details of what true concurrency is (see [stackoverflow](https://stackoverflow.com/questions/1050222/what-is-the-difference-between-concurrency-and-parallelism) ). If your program needs to run multiple tasks with out an interdependence at all, then distributed systems may be a win for you.

### Scale-ability

A very common to run into in a monolith application is scaling becomes tricky. Even though there are multiple ways to scale a single large application ( vertically, horizontally, cdn/caching, and load balancing ) they won't evenly scale specific services of the monolith. In a distributed system you only need to scale specific services that require higher availability.

### Compose-ability

A advantage to distributed systems is that the openness to add new services can be higher. Adding a new service can be as simple as creating and deploy a new application, and maybe even publishing a API. 

### Security

Maintaining the security of a distributed systems doesn't have to be difficult although it surely can prove more difficult. In order to manage confidentiality, integrity and availability of services communications sent over a open network must be encrypted and secured, most likely with TLS. 

### Quality of Service

In order to provide the best quality of service among distributed systems, many factors must be considered. Network latency being the biggest one since most distributed systems communicate over the wire. Hosting services in the same data center can make network latency almost disappear. Also load balancing to closer-to-client endpoints can make a huge difference. 

### Reliability

An advantage of distributed systems is the idea of maintaining service reliability. When one service may fail, another may be able to pick up the slack. When a single large application fails, most likely all services involved will be affected until recovered.

### Performance

Touching on performance a little bit in scale-ability, performance can be increased with a distributed system. Not saying that all applications will gain performance from a move to distributed systems, but when your application spends resources working on a specific service in a single-application those resources are then depleted for basic services that your monolith might provide. 

Large long-running tasks such as image/video processing will most likely benefit from being moved to a separate service.

### Management

When maintaining a large monolith, management might be easier. You usually have only a few servers to manage, with only a few endpoints. When managing multiple distributed services, things can get a little more tricky. Continuous integration and continuous deployment involves multiple pipelines for each specific service multiplied by the amount of redundant services.  
