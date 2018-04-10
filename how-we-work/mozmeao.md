# How we work in 2018 - DRAFT

Our team manages it's work via a [Github project in the MozMEAO organization](https://github.com/orgs/mozmeao/projects/2). The goal of this team-centric Kanban board is to help manage backend and infra/SRE tasks. This will allow us to:

- prioritize and assign work in a fair and balanced way
- communicate status within the MozMEAO team and marketing organization
- identify risks, blockers and high priority issues
- foster collaboration on the server side

All data in the project is "standalone": we try to keep all links and references as public as possible, but there are obviously tasks that include sensitive data. These sensitive tasks are managed internally, and can also tracked in private Bugzilla issues.


# Project board

[Our project](https://github.com/orgs/mozmeao/projects/2) is located in the MozMEAO Github organization. Note that projects at this level are not specific to any one repo. A project at the organization level allows us to easily link and track issues and PRs from `mozmeao` repos. For the rest of this document, we'll use the name `MozMEAO backend/infra` to identify this project.


## Backlogs

Each project will keep it's own backlog of tasks. Each project owner will periodically identify work from their project to be linked to the `MozMEAO backend/infra` project. This will be discussed more in the `Weekly board review section` and in the [Adding issues to the project section](#addingissues).

## Adding issues to the project

### Issues and PR's in `mozmeao` repos <a name="addingissues"></a>

From the [project UI](https://github.com/orgs/mozmeao/projects/2), click the `Add cards` link and drag the card to the appropriate column.

### Issues and PR's in external repos

Click the `+` sign in any column of the project and add a brief description *AND links to one or more external issues that you'd like to track*, then click the `Add` button. 

> Adding multiple links in the body of a note will enable a 'Show' button that can be expanded to show additional detail for each linked issue.

### Issue Labels

Issues should be labeled during our weekly review meeting. It is not required that we wait until a meeting to label incoming issues.

As a general rule, try to use existing labels. However, if none of the existing labels work for you and the label will most likely be used more than once, go ahead and create a new one.


### Tracking Bugzilla issues

When tickets are created in Bugzilla, they can be tracked in our [MozMEAO backend/infra](https://github.com/orgs/mozmeao/projects/2) project. This is not required, but can be helpful for bookkeeping on our end, including the need to perform followup tasks when a bug is closed.

The issue should contain a link to the Bugzilla bug and any relevant labels and assignees. It can also serve as a place for team discussion related to the Bugzilla ticket without cluttering the original request. These cards can be moved directly to the `In Progress` column of the [MozMEAO backend/infra](https://github.com/orgs/mozmeao/projects/2).

### High priority issues

Urgent/high priority issues should be marked with the `high priority` label and moved to the top of the `In Progress` (or `Queued`) column. Engineers's should communicate the status of high priority issues at _least_ once a day, and note any updated status on the issue.

### Non-project support issues

The SRE team frequently has to react to events in order to ensure reliable service delivery. While the main `In Progress` queue is periodically refined, it's ok for non-urgent support tasks to be interleaved into our weekly work. This is at the discretion of the SRE team and management.

##### Examples:

- non-critical security updates to any of our managed servers
    - critical security updates should be labeled as `high priority`.
- troubleshooting / updating Jenkins
- submitting tickets to webops in response to developer needs
- and more!


## Project Columns Defined

### Queued

Work that is scheduled for the next 1-2 weeks. These tasks are identified by project owners from a repo-specific backlog (bedrock, basket, infra, etc). Tasks in this column can be thought of as _ready_ and can be started at any time.

### In Progress

Tasks that are actively being worked on. This can include (but is not limited to) analysis, development and/or troubleshooting. We should not have more than our WIP number of cards in this column. See the WIP section [TODO: link] for more info.

### Review

Tasks that are waiting for QA, PR review, discussion, and/or merging. Once a card is in this column, you can pull a new card off the Queued column.

### Complete

The task is complete, it is _live_ and no additional work is required. Cards left in this column can be added to the biweekly blog post [TODO]. Once the blog post is written, move cards to `dev/null`.

### dev/null

This is where cards go to collect dust, as their doesn't seem to be an easy way to hide completed cards.

## Work-in-progress limits

Each engineer should have between 1-3 issues that they are working on, which we'll call the `WIP limit`. For a team of 4 backend engineers/SRE's, let's start with 4 * 3. While this limit is not strictly enforced, exceeding it will cause more context switching and possibly slow down other work.

The title of for the `In progress` column should include `(limit 12)`, or whatever limit we decide is appropriate.


## Meetings

### Weekly board review meeting

We have a weekly project review meeting on Tuesdays at 7:30am pacific. 
The goal of this meeting is to review our project board, replenish the `Queued` column of the board with new work, and to identify blockers or at-risk tasks.

#### Process:

- Start with the top of the `Review` column, ensure that each issue is receiving appropriate review. If the issue has already been resolved/merged/closed, move to the **top** of the `Complete` column.
- Next, review each card in the `In Progress` column to ensure the issue isn't blocked. Blocked issues should be updated with an appropriate note. When an engineer has submitted a PR, the card should be moved to the **top** of the `Review` column. Pull requests are _usually_ reviewed within 1 business day, and don't need to wait until the weekly triage meeting to be moved to the `Review` column.
    - Let's make sure the `In Progress` column is obeying the WIP limit.
- Next, review the `Queued` column starting from the top. The top represents the highest priority queued tasks that engineers should work on next.
    - are there any cards in this column that have been deferred? If so, do they still belong on this project board?
    - move cards from `Queued` to `In Progress`, and assign one or more engineers to work on the issue.
- Project owners will add cards to this column for their respective projects. We should strive to keep ~2 weeks of work in the `Queued` column.
- Once the board has been reviewed, decide who will write the bi-weekly blog post and assign a card in the `Queued` column.


### Standups

***DRAFT***

We'll run a standup on Monday, Wednesday and Thursday for ***10 minutes*** at 7:30am pacific.

- The goal of this meeting is to ensure that cards are able to flow across the board, to identify blockers, and to spin off other 1-1 pairing sessions if needed.
- This meeting **IS NOT** for technical discussions.
- If the meeting runs > 10 minutes, we're doing it wrong.
- Please review the project board _before_ the meeting.


# Communications

## MozMEAO blog post

Bi-weekly status is communicated to the organization via the [https://mozilla.github.io/meao/](https://mozilla.github.io/meao/) blog. New posts are submitted against [this](https://github.com/mozilla/meao) repo.

- Do not include the following:
  - anything confidential or sensitive
  - links to sites that have not yet launched
- Include the following:
  - future work that may impact other projects or teams. 
  - external contributions

Each member will take turns writing this post. We'll decide who will be the next author at the weekly board review meeting.

