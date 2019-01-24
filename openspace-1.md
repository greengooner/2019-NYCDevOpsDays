## Open Spaces - Day 1

* Docs for DevOps
* K8S Too Complex? Getting Started?
* Interviewing Devs Better

# Docs for DevOps

* Understanding the processes is key
* Some use ServiceNow, Others Confluence (use other search or Algolia, Elastic Search, etc) or Jira
* Knowledge Management system for tracking quarterly changes to find stale docs, Someone suggested new hire reviews
* Management buy-in, Rewarding documentation should be rewarded immediately (someone suggested bonusly)
* Maintain documentenation as part of the source code, Sphynx document genearation
* PlantUML to generate graphs; Someone suggested that this format can be an issue with integration overtime, SVG drawing may be better and can cause issues with time.
* Don't start from blank, build from a form or template
* Starting new initatives require documenting via a form (examples of ServiceNow, Confluence, Jira)
* Ensure that the documenation exist for a reason and not just to document
* Suggested a plugin for Confluence that auto fades documentation based on a timeline for visual indication of when it needs to be updated
* Ensure that everyone can update the documetnation
* Hire tech writter and librarian to manage the documentation as the org grows, costs may already be an issue so argument may need to reflect onto that and benefits (including reducing costs) maybe derived from it.
* Responsibility for docs should also be reflected in reviews, etc
* Internal version of StackOverflow, reduced 40% support calls; Cultural issue from service owners trying to drive a certain view instead of peer to peer help
* Reward employees that currate the internal StackOverflow
* Abstracting away for the documentation as long as it goes to the same format/type
* Lack of high level documenation for large scale processes, Documentation Architect, InSpec suggested; Dynatrace, Honeycomb, etc might be auto-discovery solution for this mapping
* Templates/Reference based on complexity
* Cucumber for documenting testing at non-technical ways
* Documenation types - Runbook, Onboard, Contributing - Microservices Ready book
    * Runbook
    * Onboarding
    * Contributing - How to adapting to meet user needs (for common services)
* Swagger (Docs as Code, Product is Documenation books) for documentation in code

# K8S Too Complex? Getting Started?

* Swarm to Kubernetes migration was not a heavy lift; Heavily containterized environment makes it an easier move
* Overhead can be significant; More opinionated
* Public v Internal facing decisions
* Containerization is likely to be a seperate question from orchestration
* Conceptial change with pods, but scaling can be fine tuned in K8S
* Concerns around Docker's investment in Swarm vs. everyone elses inventment in K8s
* How to approach getting K8s setup?
    * Go to containerization first
    * Trying to design K8s implemementation in isolation is unlikely to be a successful approach
    * All in 1 shot unlikely to be successful if concepts not well understood
* Why use it?
    * Self-healing
    * Service Meshing
    * Service packing (service density on a host)
    * Better resource utilization
* What goes wrong?
    * External DNS plugin - Fighting over DNS entries by pods in different namespaces
    * Database usage? NoSQL DBs with redudant/sharding probably ok if arch'd correctly, SQL unlikely; Others suggest not to do it at all; No real benefits and requires substancial work
* Sandbox/Getting Started
    * K8s same front end regardless of location
    * Local setup could be difficult


# Interviewing Devs Better



