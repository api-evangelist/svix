---
title: "EU: some requests were timing out due to increased latency."
url: "https://status.svix.com/incidents/8j5tf01l0lbh"
date: "2025-01-19"
feed_url: "https://status.svix.com/history.atom"
---
Jan 19 , 13:15 UTC Resolved - Sorry also for not updating the status page before, it looked ephemeral when it first surfaced. The issue was one API node that was having networking issues and was failing to connect to the rest of the systems and was timing out while at it. Only requests routed to this API node were affected, so retries would succeed.
