# Model Driven Design
The previous chapters undescore the importance of an approach to software development that is centered on the business domain and emphasized the fundamental importance to create a model which is deeply rooted in the domain, and should reflect the essential concepts of the domain with great accuracy

The Ubiquitous Language should be fully exercised throughout the modeling process in order to faciliate communication between the software specialists and the domain experts, and to discover key domain concepts which should be used in the model

The purpose of this modeling process is to create a good model, the next step is to implement the model in code, this is an equally important phase of the software development process, having created a great model but failing to properly transfer it into code will end up in software of questionable quality

Any domain can be expressed with many models, and any model can be expressed in various ways in code, for each particular problem there can be more than one solution, which one do we choose?

Having one analytically correct model does not mean the model can be directly expressed in code, or maybe its implementation will break some software design principles, which is not advisable, it is important to choose a model which can be easily and accurately put into code

## How do we Approach the Transition from Model to Code?
One of the recommended design techniques is the so called **analysis model**, which is seen as separate from code design and is usually done by different people, the analysis model is the result of business domian analysis, resulting in a model which has no consideration for the software used for implementation, such a model is used to understand the domain

A certain level of knowledge is built, and the model resulting may be analytically correct, but software is not taken into account at this stage, however when the model reaches the developers, the developers will have to adapt to it or create a separate design, which destroys the mapping between the model and code, the result is that the anaylsis model is abandoned after codinf starts

One of the main issues with this approach is that analysts cannot foresee some of the defects in their model and all the intricacies of the domain, the analysts may have gone into too much detail with some of the components of the model, and have not detailed enough others, very important details are discovered during the design and implementation process, a model that is truthful to the domain could turn out to have serious problems with object persistence, or unacceptable performance behaviour

A better approach is to closely relate domain modeling and design, the model should be constructed with an eye open to software and design considerations, developers should be included in the modeling process, getting the developers involved provides feedback, it makes sure the model can be implemented in software

If the design or some central part of it does not map to the domain model, that model is of little value, and the correctness of the software is suspect

## OOP and Procedural Languages
Object-oriented programming is suitable for model implementation because they are both based on the same paradigm, object-oriented programming provides classes of objects and associations of classes, object instances, and messaging between them

OOP languages make it possible to create direct mappings between the model object with their relationships, and their programming counterparts

Procedural languages offer limited support for model-driven design, such languages do not offer the constructs necessary to implement key components of a model, some say that OOP can be done with a procedural language like C, and indeed, some of the functionality can be reproduced that way, objects can be simulated as data structures, but such a program can not easily encapsulate the conceptual connections, making mapping between domain and code difficult to realize

Overall, procedural programming is not recommended for model-driven design