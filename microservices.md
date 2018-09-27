# What are microservices?
Microservices - also known as the microservice architecture - is an architectural style that structures an application as a collection of loosely coupled services, which implement business capabilities. The microservice architecture enables the continuous delivery/deployment of large, complex applications. It also enables an organization to evolve its technology stack.

# Monolithic Architecture

## Context
You are developing a server-side enterprise application. It must support a variety of different clients including desktop browsers, mobile browsers and native mobile applications. The application might also expose an API for 3rd parties to consume. It might also integrate with other applications via either web services or a message broker. The application handles requests (HTTP requests and messages) by executing business logic; accessing a database; exchanging messages with other systems; and returning a HTML/JSON/XML response. There are logical components corresponding to different functional areas of the application.

## Problem
What’s the application’s deployment architecture?

## Forces
There is a team of developers working on the application
New team members must quickly become productive
The application must be easy to understand and modify
You want to practice continuous deployment of the application
You must run multiple copies of the application on multiple machines in order to satisfy scalability and availability requirements
You want to take advantage of emerging technologies (frameworks, programming languages, etc)


## Solution
Build an application with a monolithic architecture. For example:

* a single Java WAR file.
* a single directory hierarchy of Rails or NodeJS code
