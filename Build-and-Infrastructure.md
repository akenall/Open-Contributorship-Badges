# Build and Infrastructure
There has already been some discussion as to how badges would integrate into the journal article via a “PaperBadger”, a third party site where authors of a paper would complete a matrix on contributorship and iterate until they all had agreed. (The workflow for this idea is described below "Publisher-Badge-Author Workflow.") But is this the best workflow? How will this integrate with organisations like ORCiD? 

This group's aim is to better think through how issuing, earning, and displaying badges will work in the research community. It's goal is to end with a storyboard and future plans. Time allowing, can we put together a rough and ready prototype with DigitalMe's email issuer?

Time Keeper?: 


## What Architecture is Out There?

Before starting to work out a workflow, what pieces are we working with? Much architecture currently exists. What is it capable of?

Some architecture has briefly been brainstormed below, but a more thorough list exists in [this Google Doc](https://docs.google.com/spreadsheet/ccc?key=0AsHml-k4XnX7dHJQSDBrdUphYlprc1N0N09KMzFzckE&usp=drive_web#gid=0), pointed out by Billy Meinke. It might be worth adding to the Google Doc.

### Mozilla Badges Architecture (40min)

[**BadgeLab.**](http://badgelab.herokuapp.com/)

**Mozilla Backpack.**
The core authorized data store and management interface of Mozilla’s reference implementation of the Backpack. Each earner has their own Backpack where their badge data is stored.

**Assertion Specification.**
Badge metadata is represented as an assertion. The assertion specification defines the information within a badge. An assertion includes multiple items of data, such as: badge name and description, issuer, date, criteria URL, evidence URL and badge image URL. The assertion should carry all the information needed to process a badge. This ensures that badges can be fully understood and verified no matter where they are shared.

**Badge Baking.**
A badge is an image combined with assertion data - badge baking embeds assertion data into an image to produce a portable badge.

**Issuer API.**
The Issuer API provides a script for issuers to let earners send badges to the Backpack. The Issuer API is a script that can be dropped-in to any badge issuer's website to provide a way for users to add an issuer's badges to their backpack. It's a lightweight alternative to the Backpack Connect API.

There's no need to bake the badges yourself. The API takes care of it for you. The badge creation workflow is simple.
1. Create and host an assertion on your site
2. Create and host the badge PNG, this is a single PNG for all badges, not a single physical PNG per issued badge.
3. Integrate your site with the backpack via the Issuer API!
4. High five yourself, you're issuing badges!

**Displayer API.**
The Displayer API provides specifications for displaying badges beyond the Backpack.

**Verification.**
Displayers are responsible for verifying badges, i.e. checking that a badge is valid and was issued to the person claiming it.

**BadgeKit.**
A new set of tools to simplify badging for issuers - provides an interface for creating and managing badges/ assessing badge applications. The BadgeKit API lets issuers control interaction with their own community of badge earners while supporting much of the badge admin process through a Web app.
https://github.com/mozilla/openbadges-badgekit/wiki/BadgeKit-Self-Hosting-Guide


[**Discovery.**](http://discover.openbadges.org/)

**ORCiD Architecture.**

**Publisher APIs.**

**Figshare.**

**[For MozFest: Email Issuer].**

## Summing it Up: Issue, Earn, Display (20min) 
What does one need to issue a badge?
What does one need to earn a badge?
What does one need to display a badge

## Storyboard: Receiving a badge and displaying it in ORCiD (30min)
In groups of 5 or fewer, develop a storyboard of how someone would eventually receive a contributor badge. Consider social, political, legal, and cultural drivers as you develop your storyboard to develop what your group feels is the most feasible story path.

## Midway Presentation (10min each group)

## Rough and Ready Prototype (30min)
With the architecture currently out there, can we put something together now (eg, using the email issuer) for a rough and ready prototype showing badges being issued and displayed?

## Planning (20min)
Where will the PaperBadger data live?
Who will be the issuer?
How to divide up the work?



## Extra time??!
*Wireframes: Machine-to-Person Interface.*
For the components where there is a machine-to-person interface, develop a wireframe of what would be included. Don't worry about images, UI/UX design, etc; concentrate on what information needs to be on the page. Put each design on a separate page. 

When done, travel your workflow storyboard using your designed pictures. Make adjustments in your flow and designs where things don't work as expected.

## Publisher-Badge-Author Workflow
Below is a very rough draft of what the workflow for issuing and displaying might look like (NB: this needs to be ammeded to include how it will communicate with ORCiD)

1. Journal accepts paper and sends email to third party “arbitrator” site (aka PaperBadger) with MS DOI alerting them to acceptance.
2. Journal sends paper contributors a one-time URL to PaperBadger.
3. Contributors log in to PaperBadger using ORCID. 
4. Contributors are presented with a matrix: contributors are rows, contribution categories are columns. (Categories we envision include "principal author", "contributing author", "data analyst", "programmer", "conducted experiment", but we'll figure these out as part of the pilot, pulling from some existing work in this space around contributorship.)
5. Each contributor ticks off the categories that she thinks apply to her.  (This is a many-to-many relationship: one contributor can deserve several badges, and several contributors can deserve a single badge for a single paper.)
6. Once all contributors have entered categories, the system mails them all to ask them to agree to the final distribution of badges.
7. Contributors iterate if necessary to converge on an agreed set of badges.
8. Once all contributors have agreed (which we hope will only take one pass, but...), the badge distribution is frozen and the publisher's site is told that badges are available.
9. When the paper is subsequently displayed on the publisher's site, the badges appear beside the contributors' names (or alternatively there's a button that pops up an overlay of the badges).
Note that the badges aren't stored on the publisher's site (at least for the MVP): instead, the publisher just needs to know that badges are available, and what URL to query to get them. Similarly, PaperBadger doesn't know anything about the paper beyond its DOI; it either stores a list of contributor names and emails (uploaded from the publisher's site), or queries the publisher's site as needed to get those when someone tries to access the badging matrix for a particular paper.
