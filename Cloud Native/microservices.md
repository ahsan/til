# Microservices
> Also known as the microservices architecture, is an architectural style that structures an application as a collection of loosely coupled services, which implement business capabilities.

## Benefits
- This architecture enables the continuous delivery/deployment of large, complex applications.
- Easier to understand and build smaller components that are responsible for individual functionality
- Speeds up development
- Makes it a lot easier to adapt to changed/new requirements
- Allows more efficient scaling (just start another container) - horizontal scaling. Monoliths need to be scaled vertically
- Containerized applications are a lot easier to distribute
- Improved encapsulation
- Encourages maintainable components

## Challenges
- Distributed systems are more complex
- Latency due to remote calls
- Have to handle non-responding services
- Multiple databases and transaction management is complex
- Testing is relatively more complex than a monolith
- Deployment of microservices is complex
- It may allow non-uniform application tech stack
- Requires reliable and fast network
- Inter-service communication needs to be secured
- Monitoring in production is complex

### Remedies
- Ensure least possible inter-services dependency for lesser complexity
- Dependent services should find each other and communicate efficiently