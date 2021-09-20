# Imagine that one of your colleagues accidentally applied all the “production” config-maps to the “beta” environment.

## What impacts could this have ?

The beta environment could write on the production database for example, or use production service, and production data, leading to fake mail send to users, or word, data corruption.

## How would you get things running properly again ?

Stopping the beta env as soon as possible.
If no data corruption occurred, bring back the old config.

Otherwise investigate the impact of the error, and if needed restore database in a state of non corruption.

## Find what has been impacted ?

Check with de dev team what can be impacted.
Check for connection log, from the beta env.
Check with the business what can be impacted.

## Prevent a re-occurrence of the issue ?

Improve code review when something will be run in production.
Add merge check (check by + 2 devops)
Add some network boundaries around beta env, so they can't reach de production database for example.

# Even though we’re not Netflix, what’s your opinion on chaos engineering ? Would you recommend it and, if so, what should be tested and how ?

Chaos engineering is a great methodology who put control over confidence.

It's a great way to put team not "on pressure" but in a context of work where they have to think about a resilient system, where everything can fail at one point.

From this point, SLO and SLA can be created and shared between SRE teams and business, and everything will be created with failure tolerance in mind.

You can use chaos engineering in three area : Infrastructure failure, Application failure, Network failure.

I would recommend it in an enterprise / teams where you can have the time and the knowledge to be able to manage a chaos monkey or something like that.

The critical part of your system should be tested, like a DNS server who failed, or application or database node who does not respond.
Some tools exist to allow this kind of methodology :

chaoskube
chaos-mesh
chaosmonkey

The advantages of this solution is to create resilient and high available system, and put the teams in effort to do so.

The biggest disadvantages is that this solution add an overhead of work for each features you ask, and complexify your infrastructure / costs.