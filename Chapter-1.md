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

| Film Production        | Game Production   |
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

## Section 1.5: An Overview of a Film Production

Visual effects pipelines are complex due to a mixture of technical and philosophical considerations.

### Technical Considerations

#### A. Data Volume and Management

The raw materials of the visual effects "production line" are varied and numerous, including plates&#185; of different formats and aspet ratios, LIDAR scans&#178;, reference photography, chrome balls&#179; and HDRI&#8308; to capture the lighting of the environment, matte paintings&#8309;, data sheets with camera lens information and frame counts, etc.

Each iteration also creates more data. With FX elements, the data-sets can occupy many terabytes of storage space. Although smaller, textures, animation data, matte paintings, and plates also occupy a significant amount of space.

Sometimes it is necessary to revert to older versions or work with several alternatives in parallel. Given the sheer volume of data, archiving is a complex process.

#### B. Rendering

Rendering involves converting 3D data into 2D images, a crucial part of the VFX pipeline.

Simulation complexities contribute to rendering challenges, with avalanche simulations taking significant computational time:  around half a day for one sub-simulation and up to 72 hours for more complex sequences. 

Rendering goals typically aim for each frame to be rendered within one to two hours per pass. Complex shots with multiple FX layers, airplane interiors, exteriors, and environments may require around ten hours per frame. For example, a shot comprising 197 frames may necessitate 2,000 hours of render time for a complete iteration. Some frames, termed "trouble frames," may require additional manual processing.

Rendering tasks are executed alongside simulations on the facility's server farm, necessitating efficient scheduling and resource management.

#### C. Multi-Specialty Coordination

Collaboration brings shots to life:
 
* Accurately tracking the movement of live-action cameras is crucial for integrating CG elements into the scene and ensuring that they match the perspective and movement of the live footage.

* Rotoscoping involves manually tracing the outlines of live-action actors or objects in each frame of footage, an essential process for isolating elements that need to be composited into the scene, such as CG characters or effects.

* The layout department uses iterations of rotoscoped data to determine the position of the virtual camera, block* the characters, and create a rough animation track, ensuring that the material conforms to the set and fits the continuity of the sequence. 

* The animation department takes the rough animation track and finesses it until it looks perfect.

* The asset department craetes digital models, textures, and rigs for various elements in the shot that are used by the rotoscoping, layout, and animation departments. A great number of asset variations are craeted to be uysed in several different sequences. Likewise, different LOD (level of detail) models are created for different purposes, e.g. high-res models specifically for cloth simulation and low-res models for physics simulations. 

As timescales are short, multiple teams work simultaneously on various tasks. For example, the lighting department begins setup before animation has begun, and the FX department starts blocking something out for digital simulations while awaiting updated animations.

#### D. Sharing Amongst Facilities

VFX studios collaborate with external partners or subcontractors involved in the production process by sharing assets. When outside facilities run different pipelines, exchange formats need to be negotiated. 

#### E. Iterative Approval Process

The iterative approval process involves presenting work-in-progress to clients or stakeholders at regular intervals and incorporating their feedback into subsequent iterations.

#### F. Destructive vs. Non-Destructive

There are often variations of digital models with different appearances and attributes. 

**Destructive** workflows involve _directly altering the original image or data_, potentially eliminating or irreversibly altering pixels or information.

**Non-destructive** workflows involve working with _layers or separate elements_ that can be adjusted and modified without altering the original data.

Examples:

| destructive | non-destructive |
| - | - |
| directly painting a beard onto an original image | painting a beard on a separate layer |

#### G. Terminology

1. **plate** &mdash; footage or high-res images of a scene, usually without any actors or props, serving as the foundational material upon which visual effects artists work
2. **LIDAR (Light Detection and Ranging) scans** &mdash; remote sensing method that uses pulsed laser light to measure distances to objects and create precise, detailed 3D representations of environments, used in the film industry for digital set extension, virtual production, visual effects integration, and previsualization
3. **chrome balls** &mdash; strategically placed within live-action scenes to capture surrounding lighting conditions and reflections from the environment, to be replicated on computer-generated elements in post-production
4. **HDRI (High Dynamic Range Imaging)** &mdash; a technique used to capture and store a wide range of luminance values from a real-world scene, involving capturing multiple images of the same scene at different exposure levels ranging from underexposed to overexposed which are then later combined to create an HDR image that preserves details in the brightest and darkest areas of the scene
5. **matte paintings** &mdash; a painted representation of a landscape, set, or distant location that allows filmmakers to create the illusion of an environment that is not present at the filming location

### Philosophical Considerations

Important and deeply consequential questions are raised in VFX:

> Should all VFX processes be redesigned to be non-destructive?

Although it may be obvious that this should be the case, practical considerations stand in the way:

* Third-party tools, designed by software vendors for specific functions, limit customization options.
* Modifying these tools to suit new workflows may prove challenging.
* Artists may resist adopting non-standard workflows within familiar tools.
* Each department uses a different suite of third-party software tools (e.g. Maya, Mari, Photoshop, Katana, RenderMan, Houdini, Nuke), many of which lack compatibility with each other.

> Which file formats should be used to transfer data between different software tools in the VFX pipeline?

* Considerations include when to use native data formats versus application-agnostic formats, with trade-offs inherent in each decision.
* These decisions can have far-reaching consequences for the efficiency and interoperability of the VFX pipeline. For example:
    * In shot production, the FX department's tool for managing boulder variants in avalanches creates challenges due to file transfer limitations with the lighting department.
    * At the end of the pipeline, the compositing department requires specific camera information not currently exported, prompting updates to the asset management system and camera export/import code for this particular project.
* Collaboration is essential in rectifying issues and streamlining the overall process.

These complications teach us 3 things:
1. VFX pipelines need to be flexible since they will undergo constant change.
2. The capacity to make such changes varies greatly between departments.
3. People are often happy to make changes that, while great for them, have significant impact downstream.

## Section 1.6: An Overview of Game Production

_This funny, engaging, and informative section was written by [Ben Carter](http://www.saillune.net), game developer and author. I highly recommend reading it yourself, but here's a brief overview of the steps he described for developing an action/adventure game with linear gameplay:_

* Prototyping and planning phases
* Iterative level development with weekly reviews and feedback integration from stakeholders
* Reuse of assets from previous projects
* Concurrent workflows with designers creating whitebox layouts, programmers experimenting with AI, and cut-scene storyboard creation
* Integration process where all the work comes together, inevitably leading to more iteration to address visual style adjustments, scaling issues, discrepancies between level layouts and assets, and other unexpected changes
* Alpha-beta-final process where levels are content-locked one by one, prompting rush to supply missing assets and/or fill in placeholder assets
* Final rounds of polishing and bug-fixing
* Test team reports any bugs, which require creative solutions given budget and time constraints
* As the bug count dwindles, so does the number of people on the team, leaving a handful of programmers fixing final bugs reported by QA as well as producers determing DLC scheduling to match sales projections

