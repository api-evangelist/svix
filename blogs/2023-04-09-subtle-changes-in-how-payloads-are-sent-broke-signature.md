---
title: "Subtle changes in how payloads are sent broke signature verification for consumers verifying incorrectly"
url: "https://status.svix.com/incidents/ghfj7w6svrsq"
date: "2023-04-09"
feed_url: "https://status.svix.com/history.atom"
---
Apr 9 , 11:00 UTC Resolved - We changed the code to send the payload exactly the same way as it's sent to us (before, we were compacting it before sending). This meant that people that relied on the payload to be compact in order to verify webhooks (i.e they were verifying incorrectly) had verification failing. We reverted this immediately once it was reported signatures were failing for customers.
