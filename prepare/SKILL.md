---
name: prepare
description: Prepares for the development of a feature or fix in a codebase.
model: opus
---

# Prepare Fix Development

This skill performs all the necessary actions to prepare an agent for the development of a fix or featurein a codebase.

---

## Starting point

The starting point is **always** a *Github issue* that describes a fix or feature that needs to be implemented in a codebase.
If the user has not specified which Github issue to work on, ask for it. You **must** quit with a "CANNOT PROCEED - MISSING GITHUB ISSUE" message if the user does not provide a Github issue.

**Checklist to begin:**
If this checklist is not **all** satisfied, as the user for the missing information. **Do not** start before all information is available: 
- [ ] You have a Github issue to work on.
- [ ] The Github issue **clearly specifies** what fix needs to be done. The fix can be described either : 
    - In the body of the Github issue
    - In a document in the code base that the Github issue refers to. Both are valid.
- [ ] You know which **codebase** (project, repo) you are working on. 

---

## The Workflow

You **must always strictly** follow this workflow when preparing the implementation of a feature:

1. Read the codebase to understand current state
2. Read any relevant feature description to understand the context of the fix. 
3. Breakdown the fix into a plan: a series of changes you will need to implement. **Prepare a task list**. You **MUST** use the `breakdown-feature`skill to breakdown a fix into tasks. Once you have the tasks, make the plan as a task list.
4. Create a feature branch, **if** the codebase is not already in a feature branch. Feature branches are easy recognizable: they start with `feature/<something>`. Note that feature branches are used whether it is a fix or a feature.

---

## Rules

***When to engage the user:**
- **NEVER** engage the user. This skill is expected to be fully autonomous. 

**Rules for breaking down the fix into tasks:**
- Keep it simple: no need to have 100 tasks. 1-3 tasks for a fix should be more than enough.

**Rules for creating the feature branch:**
- [ ] Make sure you start from the main branch. If you are not on the main branch, switch to it first. This is **fundamental** to avoid creating a feature branch that is not up to date with the main branch.
- [ ] Always pull the latest changes from the main branch before creating a feature branch. Without this step, you risk creating a feature branch that is not up to date with the main branch.
- [ ] Only create a feature branch if the codebase is not already in a feature branch. If the codebase is already in a branch, you can work in that branch and skip this step.
- [ ] The feature branch must be named `feature/<name>` where <name> is a short name (dash-separated-words) of the feature or fix to be implemented.

---

## Acceptance Criteria 
You are done with preparing the Fix for development **ONLY IF:**
- [ ] The feature branch has been created
- [ ] You have broken down the fix into a series of 1-3 tasks.
