# Preserving Model Integrity
This chapter is about large projects which require the combined effort of multiple teams

We are faced with a different set of challenges when multiple teams, under different management and coordination are set on the task of developing a project

Enterprise projects are usually large projects, which employ various technologies and resources, the design of such projects should still be based on a domain model, and we need to take appropriate measure to ensure the success of the project

When multiple teams work on a project, code development is done in paralle, each team being assigned a specific part of the model

Those parts are not independent, but are more or less interconnected, each team being assigned a specific part of the model, they all start with one big model, and they are given a share of it to implement

Let's say that one of the teams has created a module, and they make it available for other teams to use, a developer from another team starts using the module, and discovers that it is missing some functionality needed for his own module, he adds the needed functionality and checks-in the code so it can be used by all

What he might not realize is that this is actually a chance of the model, and it is quite possible that this change will break application functionality, this can easily happen, as nobody takes the time to fully understand the entire modle, everybody knows his own backyard, but other areas are not known in enough detail

It is easy to start from a good model and progress toward an inconsistent one, the first requirement of a model is to be consistent, with invariable terms and contradictions, the internal consistency of a model is called **unification**

An enterprise project could have one model covering the entire domain of the enterprise, with no contradictions and overlapping terms, a unified enterprise model is an ideal which is not easily accomplished, and sometimes it is not even worth trying

Such projects need the combined effort of many teams, the teams need a large degree of independences in the development process, because they do not have the time to constantly meet and discuss the design

The coordination of such teams is a daunting task, they might belong to a different department and have separate management, when the design of the model evolves partially indepdently, we are facing the possibility to lose model integrity

Preserving the model integrity by striving to maintain one large unified model for the entire enterprise is not going to work, the solution is not so obvious, because it is the opposite of all we have learned so far

Instead of trying to keep one big model that will fall apart later, we should consciouly divide it into several models, several models well integrated can evolve independently as long as they obey the contract they are bound to, each model should have a clearly delimited border, and the relationships between models should be defined with precision

We will present a set of techniques used to maintain model integrity, the following diagram presents these techniques and the relationship between them