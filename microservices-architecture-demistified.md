# High level architecture

This is probably one of the most important things to define before starting to code. Some high level architecture decisions and approaches to well known non functional features should be defined before starting.

# Team composition and approach

Each team should be totally independent of other teams. The teams should be created to fit a  micro services implementation and preferentially the teams should be together or as close as possible from each other so they can share their own good practices and approach to solve problems inspired by the high level architecture and guidelines.

# Lessons learned

// todo - reminder - <https://dzone.com/articles/eager-optimisation-is-the-enemy?edition=177459&utm_source=Daily%20Digest&utm_medium=email&utm_content=POS1&utm_campaign=dd%202016-05-21&userid=296256>

- Each component should be treated as a totally independent and isolated application.
- During development is very important to keep the teams focused in developing a single microservice, mixing them during development tends to usually brings the consequence of reflecting this structure in the code, hence causing high coupling. **Remember Conway's law:** <https://en.wikipedia.org/wiki/Conway%27s_law>

> organizations which design systems ... are constrained to produce designs which are copies of the communication structures of these organizations

> -- M. Conway

# Communication

- There are many ways of communication between the microservices, the ones I've heard or seen more often are:

  - Messages

    - JMS
    - MQTT (Commonly used for IoT)

  - REST HTTP calls
  - SOAP REST calls, usually legacy connections or already stablished web services from third party providers.

- Trying to support sessions adds a lot of extra unwanted complexity. I would strongly recommend to totally move to a stateless, based on token security, approach. **sessions should not be used** instead focus on defining a well established stateless based on Oauth2 token.

# Testing and QA

Important to mention that there are some very important rules based on statistics regarding Test Driven Development(TDD). TDD is really controversial even among experts. Check, for instance, this 2 very nice articles that take opposite opinions about TDD a favorable one [from Uncle Bob](http://blog.cleancoder.com/uncle-bob/2016/03/19/GivingUpOnTDD.html?utm_content=bufferf7395&utm_medium=social&utm_source=facebook.com&utm_campaign=buffer) and a different opinion [from Ian Sommerville](http://iansommerville.com/systems-software-and-technology/giving-up-on-test-first-development/?utm_content=buffera712a&utm_medium=social&utm_source=facebook.com&utm_campaign=buffer).

Tests are really important but there's a catch there, the mentality of trying to cover as much as possible of your source code with all types of tests is really an unnecessary burden and delay to your project that doesn't add much in quality, instead the  best approach is to understand each scenario and write the appropriate types of tests for it. See this great article from Eric Elliot for a better understanding of what I am recommending here: <https://medium.com/javascript-scene/5-common-misconceptions-about-tdd-unit-tests-863d5beb3ce9#.dvs85rjln>

## Build mocks / stubs

- Build mocks and even better stubs(capable of supporting Behaviour Testing Design). This is really key as Building microservices can get a lot complex if you can't mock / stub the edges, with the spread of services you run on the risk of havving to spin up many of them together to be in a state where you can execute tests.

# CQRS

# Event Sourcing

# Troubleshooting & Logging

# Monitoring

# Audit & trail

# Identity Management

# CI / CD

# Repositories

Organization of repos is another very important thing to consider. It's very important that a CD pipeline is build and the recommendation here is to have each microservice in it's own repository and whenever there's a new commit of code to the master branch of development a pipeline is triggered that will then Compile -> Test -> Release that specific build of your micro service.

# Development

- Front End Development
- Back End Development
- Mobile Development
- Other devices / Internet of Things (IoT)

# Continuous integration / Continuous Delivery

 -

# Operations

- Platforms
- -
