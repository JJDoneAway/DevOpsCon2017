# Cloud native Continious Delivery
-Christian Deger
-AoutoScout24

# definition
- container packed
- dynamic managed
- µ S oriented

- bring changes into Prod fast reliable, ... fast feedback
- Dev = fastness vs Ops = stability
- gitHub =CD=> Package =CI=> deploy

# recommendation
- use gitHub
- at very first set up your delivery Pipelines
- code your Dev - Pipelines
- have them as a service
- avoid single shared CI
- put the CI into container and make them elastic
- have a new pipeline within seconds
- code the building in scripts executed by CD CI
- **There is just Prod**
- canary releases
- be able to role back
- semantic monitoring
- use feature togles
- feature toggles with % switch

#good questions
- how long dos it take to get a new service to prod with all the SLI non func stuff
- there are always failures be able to recover  
