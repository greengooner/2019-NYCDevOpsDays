# Ignite Talk

## Control - launchdarkley.com
* Planes have a budget of failures that will still allow operation when failed
* Control is an illusion, There will always be failure
* Don't we know when or where things will fail
* Error budgets - Design for failure, how much is tolerable
* Reduce catastrophies - Circuit Breakers
* Rapid Rollback
* Assume Brekage
* Everyone's backend is someone's front end
* Depend on nothing. Assume good effort. 

## Better Documentation through Empathy
* Empathize with your audiaence
* Ability to image what someone is thnking or feeling
* Imagine why they are reeading in the first place
* Types
    * Service ovierview
        * Whatis the product? What is it for?
        * Whould I even be reading these docs?
    * Tutorial
        * Ordered number of steps
    * Reference
        * What are all of my options?
        * Who are reference docs for?
        * What would you want in a reference?
    * Troubleshooting
        * What the heck does this error message mean?
        * How do you help yourself 
        * Use structure to help users help themselves
* Use empathcy to image what your audience needs

## Prioritizing Explosions
* Failure Mode Effects Analysis
    * Analyzing ways things can fail, set ranks
    * Object method of what matters
    * EMEA Workflow

## Inner-Source
* Best of Open Source into Company
* Build once, use many times
* Improve code quality
* Prepared for Open Source
* We must remove all barriers to collaberation.
* Siloed business
* Percieved business risk
* Myths:
    1. Innersource gives me more people - Need users first
    2. Innersource creates more defects - More eyes on code, defects rise to the top
    3. Innersource creates more risk - Add checks to ensure that no info is being pushed
    4. Innersource creats more risk - 
    5. Innersource my role and move on - Needs at the very least a maintainer and product owner
    6. Innersource is only for the unicorns - For everyone of every size.

## Recording Arch Decisions
* Most of us take theses decisions seriously
* We then implement and context is lost
* Future changes may not be made in the same knowledge of context
* ADRs
    * Save with project in incrementing sequence (using .md)
    * Date
    * Status
    * Context of decision
    * Decision
    * Consequences
* Leverage existing workflow
* What should require an ADR?
    * If there is a question, do it.
* Multiproject decisions in seperate repository
* New team member onboarding
* Thoughtworks use ADRs

