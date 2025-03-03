# Refactoring Toward Deeper Insight
## Continuous Refactoring
So far we have been talking about the domain and the importance of creating a model which expresses the domain, we gave some guidelines about the techniques to be used to create a useful model

The model has to be tightly associated with the domain it comes from, we also said that the code design has to be done on design decisions, designing without a model can lead to software which is not true to the domain it servies

During the design and development process, we need to stop from time to time, and take a look at the code, it may be time for a refactoring

Refactoring is the process of redesigning the code to make it better without changing application behaviour, refactoring is usually done in small, controllable steps, with great care so we don't break functionality or introuduce bugs

There are refactoring patterns that represent an automated approach to refactoring, there are tools built on such pattenrns making the developer's life much easier than it use to be, without those tools refactoring can be very difficult, this kind of refactoring deals more with the code and its quality

There is another type of refactoring, one related to the domain and its model, sometimes there is new insight into the domain, something becomes clearer, or a relationship between two elements is discovered, all that should be included in the design through refactoring

## Bringing Key Concepts into Light
Refactoring is done in small steps, the result is also a series of small improvements, there are times when lots of small changes add very little value to the design, and there are times when few canges make a lot of difference, its a breakthrough

We first start with a coarse, shallow model and we refine it and the design based on deeper knowledge about the domain, on a better understanding of the concerns

We add new concepts and abstractins to it, the design is then refactored, each refinement adds more clarity to the design, this creates in turn the premises for a "breakthrough"

A breakthrough often involves a change in thinking, in the way we see the model it, it is also a source of great progress in the project, though it also has its drawbacks

A breakthrough may imply a large amount of refactoring, that means time and resources, something we never seem to have enough of, it is also risky because ample refactoring may introduce behavioural changes in the application

To reach a Breakthrough, we need to make the implicit concepts explicit, when we talk to the domain experts, we exchange a lot of ideas and knowledge, some of the concepts make their way into the Ubiquitous Language, but some remaine unnoticed at the beginning

They are implicit concepts, used to explain other concepts which are already in the model, during this process of design refinement, some of those implicit concepts draw our attention, we discover that some of them play a key role in the design

At that point, we should make the respective concepts explicit, we should create classes and relationships for them, when that happens we may have the chance of a breakthrough

Implicit concepts should not stay that way, if they are domain concepts, they should remaine present in the model and the design, but how do we recognize them?

The first way to discover implicit concepts is to listen to the language, the language we are using during modeling and design contains a lot of information about the domain, at the beginning it may not be so much, or some of the information may not be correctly used, and other concepts may not be fully understood, or even misunderstood, this is all part of learning a new domain

As we build our Ubiquitous Language, the key concepts make their way into it, this is where we look for implicit concepts

Sometimes sections of the design may not be so clear, there is a set of relationships that makes the path of computation hard to follow, or the procedures are doing something complicated which is hard to understand, this awkwardness in the deisgn is a good place to look for hidden concepts, if one is found, make it explicit, refactor the design to make it simpler and suppler

### Specification
The last method to make concepts explicit is Specification

Specification is used to test an object to see if it satisfies a certain criteria, the domain layer contains business rules which are applied to Entities and Value Objects

Those rules are usually incorporated into the objects they apply to, some of these rules are just a set of questions whose answer is "yes" or "no", such rules can be expressed through a series of logical operations performed oin Boolean values, and the final result is also a Boolean

One such example is the test performed on a Customer object to see if it is eligible for a certain credit, the rule can be expressed as a method, named `isEligible()`, and can be attached to the Customer object

But this rule is not a simple method which operates strictly on Customer data, evalating the rule involves verifiying the customer's credentials, checking to see if he paid his debts in the past, checking to see if he has any outstanding balances, etc

Such business rules can be large and complex, bloating the object to the point that it no longer serves its original purpose, at this point we might be tempted to move the entire rule to the application level, because it seems that it stretches beyond the domain level, but actually it is time for refactoring

The rule should be encapsulated into an object of its own, which becomes the Specification of the Customer, and should be kept in the domain layer

The new object will contain a series of Boolean methods which test if a certain Customer object is eligible for credit or not

Each method plays the role of a small test, and all methods combined give the answer to the original question, if the business rule is not comprised in one Specification object, the corresponding code will end up being spread over a number of objects, making it inconsistent

The Specification is used to test objects to see if they fulfill some need, or if they are ready for some purpose, it can also be used to select a certain object from a collection, or as a condition during the creation of an object

Often a single Specification checks if a simple rule is satisfied, and then a number of such specifications are combined itno a composite one expressing the complex rule as such:

```java
Customer customer =
customerRepository.findCustomer(customerIdentiy);
…
Specification customerEligibleForRefund = new
Specification(
    new CustomerPaidHisDebtsInThePast(),
    new CustomerHasNoOutstandingBalances());
if(customerEligibleForRefund.isSatisfiedBy(customer)
{
    refundService.issueRefundTo(customer);
} 
```
Testing simple rules is simpler, and just from reading this code it is obvious what it means that a customer is eligible for a refund