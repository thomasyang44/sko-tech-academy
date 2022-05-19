---
title: Business Rules Related Concepts
description: Main Concepts
---

## Business Rule

Business rules are an expression of business policy in a form that is both comprehensible to business users and executable by a rule engine. From a business perspective, a business rule is a precise statement that describes, constrains, or controls some aspect of the business.

Let's illustrate this concept with a simple example coming from the lending industry. The following business policy can be established to limit the loan amount a bank can purchase:

Only prime loans are eligible for purchase

This policy may be split into two implemented rules, one defining what a prime loan is and the second taking the decision on purchasing it or not.

```
If the loan amount is less than the prime loan limit, then the loan type is Prime

If the loan type is not Prime then reject the loan
```

Implementing these rules using an Object Oriented Language may look like two if statements testing conditions on objects, and applying actions on the same or other objects

```javascript

if (loan.amount < PrimeLoanLimit) {
    loan.type = PrimeType;
}

if (loan.type != PrimeType) {
    case = new Case("Loan is not Prime");
    loan.status = REJECT;
}
```

The concept of business rules is not new, and for decades analysts and developers were implementing them within business applications. Since the introduction of a Business Rule Management System application, early 2000, which provides tools to manage the rule as a standalone element, outside of the core business application, and in a form which is executable by a rule engine.

Business rules are packaged as a Rule Set which can be considered as a piece of software executed by a rule engine. Integrated in a business application, the rule set implements a sub-set of the business logic. This logic is externalized from the traditional code and can be easily changed, and maintained by business analysts instead of developers.

As opposed to business logic embedded and hidden in functions, procedures, macros or databases, business rules are clearly separated from the rule engine, a software component which executes and activates rules based on matching conditions on a set of data.

Figure 1 below illustrates this fundamental approach in implementing business logic, with the old embedded model on the left and the new architecture on the right. In many ways the approach is similar to the separation of code and data which Data Base Management Systems (DBMS) brought in the 1970s.

![0](./images/legacy2bre.JPG)

A piece of business logic or rule embedded in code will be more difficult to identify, locate, and change, therefore increases costs of maintenance.

A rule which is externalized in a BRMS platform, and whose versions are controlled in a rule repository and deployed and executed in a rule engine, will be much easier to modify, thus reducing dramatically the time and cost to implement changes required by the business.

Traditional software life cycles such as the V cycle or waterfall model are notorious for leading to systems which costs more than expected, come to market later than planned and with outcomes not matching the clients' initial expectations. With such approaches, the business users have little ownership of the solution, and the time required to implement changes can easily range from 3 to 6 months if not more. As a result, policy owners don't feel comfortable with change which translates into a loss of agility to respond to new business and competitive situations: too much time passes between policy owners submitting requirements to IT and the actual deployment of new rules.

Also, with all the fine tuning and iterations, policy owners cannot really be sure that the policy is being implemented according to their needs. The only way to actually know is to keep performing tests and hope that all the cases are covered in such tests.

As important element of the business decision, the business rules need strong management processes and tools to support their life cycle.

A BRMS provides solutions to make this management more efficient, both for developers and for the business users of the applications. Obviously tooling is not the single answer to the software and business challenges behind the development of decision-support systems. Deploying BRMS, BRE, and BPM components into business applications requires to modify current development methodologies and practices in order to take into account new concepts as well as providing a better collaboration framework between IT and business.

The Agile Business Rule Development methodology corresponds to such a need. It is an incremental and iterative software development process leveraging the Agile Alliance manifesto (Agile Manifesto). Here are some of the Agile development values particularly relevant to the implementation of a rule set using the ABRD approach:

* Individuals and interactions over processes and tools. The rule discovery, analysis and validation activities require an active and efficient communication between the rule developer and the Subject Matter Experts (SMEs). Such processes are defined as light as possible.

* Working software over comprehensive documentation. The proposed rule set development done per iteration, with its validation step, is based on the evidence that a working and executable rule set has much more business value than a rule description manual. All the project stakeholders benefit from such a principle but in particular the business users who are then sure that what they see (the rules) is what gets executed in the deployed system.

* Customer collaboration over contract negotiation. Subject Matter Experts who define the business policies and the business rules are strongly involved in the development process. They are the customers of the final system, owners of the policies and are conveniently co-located with the development team during the project.

* Responding to change over following a plan. Business rules evolve, more often and faster than other standard pieces of software. This is actually one of the key values of the business rule approach. For this fundamental reason the methodology to support the rule set development has to be tailored to such rapid life cycle and include the appropriate activities, processes, best practices and work products to support such changes efficiently.

Two fundamental drivers govern successful rule set developments:

* The unforgiving honesty of executable rules
* The effectiveness of people working together with goodwill, shared vision and common interests (the business user and the development team).

Executable or working rules tell the developers and the Subject Matter Expert what they really do as opposed to promise through a paper-based design or specification.

## Rule Engine

Software component used to execute business rule. The rule engine uses two major entities:

* a Ruleset: The set of rules that are processed by the rule engine, and rule execution flow information.
* an object set: The set of objects to be treated by rules.

A rule engine is executing a cycle consisting of three action states: match rules, select rules, and execute rules until there is no more rule to execute.

The rule engine evaluates the conditions of rules in the ruleset against the objects to determine (match) which rules are eligible to be executed. During execution, the engine collects all eligible rules in an “agenda”.

The object set is referenced in the engine’s working memory, which also contains the current state of the objects which lead to the current rules in the agenda.

All objects are examined by all rules. The effects of the execution are to create new data, or to modify existing ones.
The agenda  is a logical workspace where rule instances that have conditions matching objects in the working memory are put. There can be several rule instances for the same rule. When all the candidate rule are matched the engine turns to the agenda for rule execution.

One execution mode is the RetePlus algorithm used to match many patterns with many objects, it helps to minimize the number of rules and conditions that need to be evaluated, computes which rules should be executed, and identifies in which order these rules should be fired.

Rules engine is designed to be complete, and ensures that the effects of one rule execution (or firing) is propagated so that everything that can be inferred is done in one run.
The power of rule engines comes from the fact that complex behaviors result from simple rules, this is known as rule chaining. This is a major change in the programming model developer used to have.There is no more static control structure of the program where function is calling one another, rules are “communicating” with other rule only by way of the data. This is a data change that trigger potential rule execution. Rules are not executed sequentially and it is not always possible to determine through inspection of a set of rules which rule will be executed first or cause the inference engine to terminate.

## Business Rule Analyst

The Business Rule Analyst is a special kind of business analyst with a strong knowledge of how a business rule applications are developed. In his day-to-day work, he helps the business team turning business policy into rules, but also helps to clearly define the business view, or fact model, for developers to implement.

He is a bridge between the business side and technical side of an application, translating business policies into a formal specifications (model) for developers, then validates it with the different business managers. With the IT developer, he shares the vocabulary definition used in rules, then captures, writes, and organizes the business logic into business rules. His responsibilities include:

* Identify business sponsors for issues relating to business rules.
* Articulate the benefits of implementing a decision management solution with Operational Decision Manager
* Identify the key user roles that are involved in designing and developing a decision manager solution, and the tasks that are associated with each role
* Establish and maintain traceability from the business policies to the executable business rules.
* Assist business in identifying existing business rules.
* Research the meaning and origin of the business rules
* Create rule templates for rule writers and analyst
* Analyze rules for completeness, correctness, optimization (from a logical, not performance perspective)
* Identify how rules are used in processes that implement business policies
* Ensure the quality of the business rules
* Ensure that consistent terminology is used in the business rules in order to build a common vocabulary and a domain data model
* Analyze business rules to identify conflicts, redundancies
* Ensure consistency of business rules across functions, geographies and systems
* Conduct impact analysis for revision or replacement of business rules
* Integrate new or revised rules into existing rule set
* Make recommendations for business rule changes based on business knowledge
* Facilitate resolution of business rules issues
* Act as consultant for the project team
* Act as a liaison between business and IT

### Skills


The Business Rule Analyst is responsible for putting in place the rule approach and the rule stewardship. He is responsible for the execution of the ABRD process, and helps extract and write the business rules.

Competency includes:

* Object-oriented analysis and design
* Java development: light to medium skilled, Java Bean programming at a minimum
* Rule programming: inference, rule chaining, pattern matching, working memory and agenda
* Understanding of the different rule engine algorithm
* ABRD: rule discovery and rule analysis practices
* Decision Validation Services to validate business requirement for each decision service.
* Rule Governance
* Familiarity with the Decision Model Notation (DMN)


## Decision Management System

Used to be named Business Rule Management System, Decision management system designed to modify and manage business logic independently from the enterprise application. A BRMS provides a way to automate decision making and execute precisely on business policy. Consequently, policies and decisions form the core of all business processes and activities. A BRMS platform should include facilities to enable:

* Full life-cycle maintenance of business rules by business analysts and developers
* Assured consistency by representing business knowledge uniformly with centralized control
* Facilities for testing, scenario generation, and impact analysis

BRMS is a method and means to treat rules as a true corporate asset.


## Agile Estimation

There are three main concepts you need to understand to do agile estimation:

* **Estimation of Size** gives a high-level estimate for the work item, typically measured using a neutral unit such as points
* **Velocity** tells us how many points this project team can deliver within an iteration;
* **Estimation of Effort** translates the size (measured in points) to a detailed estimate of effort typically using the units of Actual Days or Actual Hours. The estimation of effort indicates how long it will take the team member(s) to complete the assigned work item(s).

### Estimation of Size

**Points** is a relative measure that can be used for agile estimation of size. The team decides how big a point is, and based on that size, determines how many points each work item is. To make estimation go fast, use only full points, 1, 2, 3, 5, 8, and so on, rather than fractions of a point, such 0.25, or 1.65 points. To get started, look at 10 or so representative work items, give the smallest the size of one point, and then go through all other work items and give them a relative point estimate based on that point. Note that points are used for high-level estimates, so do not spend too much time on any one item. This is especially true for work items of lower priority, to avoid wasting effort on things that are unlikely to be addressed within the current iteration.

A key benefit of points is that they are neutral and relative. Let’s say that Ann is 3 times more productive than Jack. If Ann and Jack agree that work item A is worth 1 point, and they both think work item B is roughly 5 times as big, they can rapidly agree that work item B is worth 5 points. Ann may however think work item B can be done in 12 hours, while Jack thinks it can be done in 36 hours. That is fine, they may disagree about the actual effort required to do it, but we do not care at this point in time, we only want the team to agree on the relative size. We will later use Velocity to determine how much ‘size’, or how many points, the team can take on within an iteration.

One project team may say that a work item of a certain size is worth 1 point. Another project team would estimate the same sized work item to be worth 5 points. That is fine, as long as you are consistent within the same project. Make sure that the entire team is involved in assessing size, or at least that the same people are involved in all your size estimates, to ensure consistency within your project. We will see how the concept of velocity will fix also this discrepancy in a point meaning different things to different project teams.

You can also use other measures of size, where the most common alternative is Ideal Days.

### Velocity

**Velocity** is a key metric used for iteration planning. It indicates how many points are delivered upon within an iteration for a certain team and project. As an example, a team planned to accomplish 20 points in the first iteration. At the end of the iteration, they noticed that they only delivered upon 14 points, their velocity was hence 14. For the next iteration, they may plan for fewer points, let’s say 18 points, since they think they can do a little better than in previous iteration. In this iteration, they delivered 17 points, giving them a velocity of 17.

Expect the velocity to change from iteration to iteration. Some iterations go smoother than others, and points are not always identical in terms of effort. Some team members are more effective than others, and some problems end up being harder than others. Also, changes to the team structure, learning new skills, changes to the tool environment, better teaming, or more overhead with meetings or tasks external to the project will all impact velocity. In general, velocity typically increases during the project as the team builds skills and becomes more cohesive.

Velocity compensates for differences between teams in terms of how big a point is. Let’s assume that project team Alpha and project team Beta are equally efficient in developing software, and they run the same project in parallel. Team Alpha, however, assesses all work items as being worth 3 times as many points as team Beta's estimates. Team Alpha assesses work item A, B, C, and D to correspond to 30 points, and team Beta estimates the same work items to correspond to 10 points. Both teams deliver upon those 4 work items in the next iteration, giving team Alpha a velocity of 30, and team Beta a velocity of 10. It may sound as if team Alpha is more effective, but let’s look at what happens when they plan the next iteration. They both want to take on work item E-H, which team Alpha has estimated to be 30 points, and team Beta as normal has estimated to be 1/3 as many points, or 10 points. Since a team can typically take on as many points as indicated by their velocity, they can both take on all of E-H. The end result is that it does not matter how big a point is, as long as you are consistent within your team.

Velocity also averages out the efficiency of different team members. Let’s look at an example; Let’s assume that Ann always works 3 times as fast as Jack and Jane. Ann will perhaps deliver 9 points per iteration, and Jack and Jane 3 points each per iteration. The velocity of that 3-person team will be 15 points. As mentioned above, Ann and Jack may not agree on how much effort is associated with a work item, but they can agree on how many points it is worth. Since the team velocity is 15, the velocity will automatically translate the point estimate to how much work can be taken on. As you switch team members, or as team members become more or less efficient, your velocity will change, and you can hence take on more or less points. This does however not require you to change the estimate of the size. The size is still the same, and the velocity will help you to calculate how much size you can deliver upon with the team at hand for that iteration.

### Estimation of Effort

Estimation of Effort translates the size (measured in points) to a detailed estimate of effort typically using the units of Actual Days or Actual Hours. As you plan an iteration, you will take on a work item, such as detail, design, implement and test a scenario, which may be sized to 5 points. Since this is still a reasonably big work item, break it down into a number of smaller work items, such as 4 separate work items for Detailing, Designing, Implementing and Testing Server portion, and Implementing and Testing Client portion of the scenario. Team members are asked to sign up for the tasks, and then detail the estimate of the actual effort, measured in hours or days, for their tasks. In this case, the following actual estimates were done (with person responsible within parenthesis):

* Detailing scenario (Ann): 4 hours
* Designing scenario (Ann and Jack):  6 hours
* Implementing and Testing Server portion of scenario (Jack): 22 hours
* Implementing and Testing Client portion of scenario (Ann): 12 hours
* Total Effort Estimate for Scenario: 44 hours

If other people would be assigned to the tasks, the estimated actual hours could be quite different. There is hence no point doing detailed estimates until you know who will do the work, and what actual problems you will run into. Often, some level of analysis and design of the work item needs to take place before a reasonable estimate can be done. Remember that estimates are still estimates, and a person assigned to a task should feel free (and be encouraged) to re-estimate the effort required to complete the task, so we have a realistic view of progress within an iteration.
