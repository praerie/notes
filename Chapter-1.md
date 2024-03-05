# Chapter 1: Introduction

## Section 1.1: Production Pipineline Fundamentals for Film and Games

Art production is a communal enterprise, a collective effort of many artists and technicians. **Pipeline developers** are the unsung heroes of the digital entertainment industry, holding the constellation of artists and technicians together.

## Section 1.2: How This Book Will Help You

* Understanding the impact of code changes on projects and production schedules
* Understanding the differences between film and game production pipelines
* Understanding the needs of your coworkers in other dsiciplines for more effective communication and successful integration of new features
* Understanding how pipelines enables department directors to reduce integration bottlenecks

## Section 1.3: What is a Pipeline?

### Definition

A **production pipeline** is akin to an assembly line, with each artist and technician contributing their part before passing it on. Most pipelines are composed of smaller pipelines that fork and reconnect.

A pipeline is defined by the questions it answers, e.g.:
* How many shots are there?
* How many tasks does each shot break down into?
* How many artists are required to handle these tasks?
* Who is responsible for which tasks?
* Where is the work stored?

Answers to these questions aid in resource allocation:
* Virtual resources, such as server space for files
* Physical resources, like desks for artists

A pipeline's high-level goals:
* Avoid bottlenecks
* Support iteration
* Maximize efficiency 

### Iterative Flow of Data

Graphics production involves both technical and creative elements. As such, the flow of data among pipeline users is _non-linear_ from concept to execution. Necessitating iterative review and modifications, the nature of the pipeline is _cyclical_.

Iterative processes should be _cheap_ and _reliably repeatable_.

While iteration leads to high standard of quality given multiple reworkings, there is the potential of wasted effort. To avoid this, pipelines make use of **placeholder assets**:  low-quality stand-ins for finished versions during iteration. This allows artists to defer the time-consuming task of creating high-quality assets until later in production.

Analyzing the pipeline as a flowchart can highlight potential production bottlenecks, e.g. excessive workload on one individual for approval, preventing them from completing their own tasks and causing delays downstream.

### Upstream Changes

Pipelines must be bidirectional to allow for the communication of upstream changes through the dependency chain without losing or invalidating the changes already made by other departments.

An ideal pipeline enables revisions to occur at any stage of production.

