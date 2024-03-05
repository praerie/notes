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

## Section 1.4: Differences and Similarities Between Film and Game Pipelines

Although film and game pipelines are often structured differently, both require...
* models,
* textures,
* animation,
* lighting,
* particle effects,
* post-processing, 
* and audio.

### Volume of Data

The biggest challenge in film and game pipelines is managing the sheer volume of information required to produce photo-realistic imagery. During production, terabytes of data are passed through to the renderer or compositor.

For example, a single creature in a VFX film may comprise hundreds, if not thousands, of individual assets that are assembled to generate a working render. 

### Timeline

| Film Production | Game Production |
| ---------------------- | ----------------- |
| avg. 6 months - 1 year | avg. 1 to 4 years |

### Content

In games, the production team decides on story, visual style, and audio, but the player controls how the content plays out via input from devices like controllers, microphones, etc. 

Film and video present the viewer with a complete, polished package representing the _vision of the creative team_. The viewer has no say in how the content of a film unfolds as the action, camera angles, and pacing are _decided by the diretor and production team_.

### Processing 

As games rely on input to direct the content, processing is done in real time:  the 2D and 3D assets, lighting, physics simulations, AI, and audio are stitched together by the code to create an interactive experience.

Compared to a film animator who typically creates long sequences of movements, a game animator will create hundreds of smaller animations that may be triggered in response to the player's input.

### Outputs

Films have standard output formats for their end products, e.g. Blu-ray, DVD, and DCP (Digital Cinema Package) for projectors.

On the other hand, games do not have a standard output format. A large part of the game development process is building the platform itself that the component pipelines are targeting. Games technology is often _proprietary_ and _evolves rapidly_ to integrate different assets.
