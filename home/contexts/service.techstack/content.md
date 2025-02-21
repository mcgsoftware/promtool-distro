# Microservice Tech Stack

## Usage
For microservices being worked on, assume the following tech stack is used:

| Software                            | Usage                           |
|-------------------------------------|---------------------------------|
| Spring Boot 3.4.2                   | Framework for web and rest api  |
| Resilience4j | Library for resilience patterns |
| MySQL | Persistence data store          |
| Redis | For caching data                |
| Lombok | For DTO java beans              |
| Jakarta | for DTO validation |

## Coding instructions
- All controllers must use Webflux to implement endpoints