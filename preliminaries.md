# Preliminaries

This section attempts to find a useful answer to the question "What is the best way to make the world a better place?".
It does so by focusing first on improving the question itself, and then incrementally adds information that we consider crucial for a good response.

## Improving the question

The initial question is a fairly natural way of posing it, but is too broad and vague for a good response. Here we will attempt to create a more
precise question, whose answers should qualify as answers to the original question in the same way.

The first obvious vagueness is the use of "best" and "better". How, and by what standards, are these qualities measured? Let us focus on the first of these two.

### The best way

How can we further qualify "the best way" without losing the original broad intent it captures. "The best way" demands an actionable plan that is somehow better than all its alternatives.
The way it is better is dependent on how we formalize "A better place". That clause will determine the expected quality-improvements of the state of the world for each alternative plan.

The work performed by "The best plan" is to provide an ordering for the quality improvements. How this is to be understood depends on how we formalize "A better place"

### A better place

In game theory, we have concepts such as Nash equilibria and Pareto improvements. These concepts concern situations where there are a number of rational agents, 
each capable of choosing actions for their own benefit. 

A Nash equilibrium is then a stable situation, where given that agents' intentions are to some extent public knowledge, 
no agent would expect to benefit by changing their plans. Zero to many Nash equilibria may exist for a given situation.
Of interest are those situations where communication is limited, and where agents are required to reason about what other
agents will do, such that they can take the action with highest expected utility. In those cases, plans are not public
knowledge. But possible plans, and their expected utility for the respective agent, are.

A given set of plans is considered to be a Pareto improvement if the outcome of executing those plans benefits at least one agent, without being detrimental to any agent. 
Pareto improvements form a partial order, with a Pareto optimum being one that itself has no further Pareto improvements. A Pareto frontier is the subset of Pareto improvements
that are Pareto optimal, i.e. those improvements that are considered incomparable w.r.t. the partial order defined.

These formal concepts capture intuitions about rationality. Nash equilibria capture what it is to reason rationally as a self-interested agent, whereas Pareto improvements
 capture intuitions about when a group of people acts collectively rational. It is of course possible for these concepts to coincide, but there are many interesting examples of
 Nash equilibria that are not Pareto optimal, and vice versa. Much of game theory is dedicated to capturing interesting situations in formal games
 examples consider situations where communication is not an option, and/or where possible game options are closed; reality often does not have these constraints. Its strength lies
 in modeling agents in any given situation as self-interested. A Pareto improvement may require an agent to forego its self-interest, for the sake of an outcome that is collectively
 better.