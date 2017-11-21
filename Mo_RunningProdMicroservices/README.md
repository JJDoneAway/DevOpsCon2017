#Running µ Service in Production

Speaker: Russ Miles / @russmills

What is chaos engineering?

Production hates you and it knows you!

you write it, you run it you panic

## Levels in Production

### People

### Code / application

### Platform
- configuration
- K8

### Infrastructure
- network
- hardware
- monitoring systems / logs
- configuration of infrastructure (manipulated by people)
- command line interfaces
- µ services enables change

## Golden Rules
- always deploy just one µ service at once.
- Production is the base to you get better.
- Help the people to feel the pain.
- We live longer when we listen to stories.
- There is no planing / it is coll to do suggestions
- productive systems are chaotic
- Everything has to be observable

## Availability
- it is measured from the outside in.
- the only availability meters is the outside one
- there is no 100% availability

## Observability
- it is not just dashboards
- you must be able to ask questions
- possibility to explore and learn
- insights from application level, platform, infrastructure
- tracing (request unique IDs and assign it)
- timing event (how long did this or that request take)
- logging

## Disaster recovery games
- should run every week
- a team with Dev, Biz, Ops
- a prod like environment
- parts of the environment is going down
- you have some period of time to bring it back
- 3rd party - how to measure
- Samplings (don't log every thing but maybe just every 10th request)
- run game days continuous
- You don't run chaos tests if you already know the answer.

### My example Game day
**Name** | Odins attack
---|---
**Description** | We are just a view hours ahead of an official opening party for a new Betty party. Every thing is already prepared so that the top management has press just a big red buzzer to switch it on. To remove some final nasty zombie articles out of Betty  it was decided to delete all articles documents out of the cache and run a initial load. ODOut and ODin are running under high speed and are almost finished. Just 10% of the documents are missing. Suddenly the article cache doesn't accept any new documents any more and throws back just http 4xx.
**Who** | AC team, CP team, Odin team, a K* administrator
**What needs to be available** | Swagger, Hyserix, ELK, ...

### Play Book
- provide the necessary tasks if something happen
- do this
- if this
- look at this
- measure this it should look normally look like this
- have your log files available

### Chaos Experiments
- limit the blast radius
- don't do it if you know the outcome
- you should have the hypothesis that your system is able to take it
- start changing things
- see a list of possible chaos monkeys https://medium.com/netflix-techblog/the-netflix-simian-army-16e57fbab116
- an open source api for testing http://chaostoolkit.org/
- an example https://github.com/chaostoolkit

### My chaos experiment
**Name** | flooding with new clipboards
--|--
**Blast Radius** | Existing clip boards aren't available for some minutes
**Actions** | millions of new clip boards are created
**Probe** | the it is still possible to put, pick & delete from the already existing ones

**Name** | adding documents with big reader digest sections
--|--
**Blast Radius** | search is slow / notification clipboards are slow
**Actions** | millions of new documents with big reader digest sections
**Probe** | the it is still possible to search for the already indexed documents. No notification event is lost.
