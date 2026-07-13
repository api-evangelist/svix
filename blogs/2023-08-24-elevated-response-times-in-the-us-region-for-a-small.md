---
title: "Elevated response times in the US region for a small percentage of the requests"
url: "https://status.svix.com/incidents/pyt8jbp6l10r"
date: "2023-08-24"
feed_url: "https://status.svix.com/history.atom"
---
Aug 24 , 16:00 UTC Resolved - There were elevated response times in the US region for a small percentage of the requests. The issue was due to a memory leak in a new third party library we integrated with, which caused some nodes to operate with constrained resources (heavy CPU/MEM usage). This fixed itself automatically by killing the affected nodes (each one as it exhausted its resources over the span of a few minutes) and starting new ones instead.
