---
layout: post
title: Dynamic Factory Pattern for Android
published: false
---


### Introduction

The Dynamic Factory Pattern describes a factory that can create service instances based on concrete type definitions stored in external plugins which can be later loaded without having to modify the factory class or the core implementation.

### Context

You are building a framework that is composed of different modules that can be fully or partially included in a project. Your framework core is not aware of the contents of the underlying modules in order to offer full flexibility and modularity. The implementing system should be able to implement the framework and later add new modules without having to change the core implementation of the framework.

### Example

The framework system has a rule evaluation module. Each rule implements a well defined interface, and is injected into a container that evaluates it.
The framework vendor supplies a fixed set of modules. New modules could be added by simply implementing the core module interface. The problem comes at module instantiation, since the factories that contain the logic for creating instances of the module services may need to be modified to support new modules.

### Problem

How can we define an interface for creating objects that implement a given contract without tying it to concrete implementations of these contracts?

### Achievements

By implementing the Dynamic Factory Pattern we are trying to achieve the following results:

  1. Flexibility. The implementers of the products should be easily modifiable, even when the system is running, allowing the injection of new product types into an existing system.
  2. Extensibility. New product types should be easily added without requiring neither a new factory class nor modifying any existing one.
  3. Controlled Evolution: users can create new types of products conforming to the product interface, but providing unanticipated behavior or features.
  4. Agility. New types of products should added to the system in a quick and agile manner, avoiding reworking of a factory class any time a new concrete product is created.
  5. Simplicity. The client interface should be simple, hiding from the client the complex details of dynamic product creation.
  


