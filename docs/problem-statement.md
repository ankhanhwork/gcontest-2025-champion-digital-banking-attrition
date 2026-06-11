# Problem Statement

## Context

A bank had introduced a fully digital account-opening journey. During the
first quarter of 2024, the onboarding system recorded more than 26,000
application attempts from 9,148 customers.

Although the overall completion rate was high, hundreds of customers still
left without successfully opening an account. Each failed journey represented
both a poor first experience and potentially wasted customer acquisition
spend.

## Available Evidence

The private competition dataset described each onboarding attempt through
information such as:

- start and end timestamps;
- final attempt status;
- anonymized customer identifier;
- demographic attributes;
- phone manufacturer and operating system;
- onboarding stop point;
- device system and OS version;
- rejection reason.

The same customer could appear in multiple rows because an unsuccessful
customer might retry the journey.

## Analytical Objective

The project aimed to build an end-to-end view of the onboarding funnel and
answer the following questions:

1. How effective was the onboarding process?
2. Where were its most important friction points?
3. Which customers and contexts were associated with repeated failures or
   permanent abandonment?
4. Could machine learning identify customers at risk of dropping off?
5. What product, operational, and marketing actions could reduce rejection
   and improve completion?

The final extension of the case placed additional emphasis on device-level
factors, including operating system, OS version, and detailed rejection
reasons.

## Required Outcome

The solution needed to combine analysis and decision-making rather than stop
at descriptive charts. A successful proposal would:

- clean and validate the event-level data;
- describe the customer journey and failure funnel;
- identify the strongest drop-off patterns;
- evaluate predictive approaches;
- distinguish reliable evidence from weak model signals;
- recommend at least three practical actions;
- explain how the bank should measure the impact of those actions.

## Public Portfolio Boundary

This document is an original summary written for the portfolio. It is not a
copy of the organizer's brief. The original PDFs and raw dataset remain
private and are not distributed through this repository.
