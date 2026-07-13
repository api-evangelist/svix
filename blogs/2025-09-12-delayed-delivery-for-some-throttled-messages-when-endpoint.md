---
title: "Delayed delivery for some throttled messages (when endpoint throttling is configured) - normal delivery unaffected."
url: "https://status.svix.com/incidents/zqxv36p4w10w"
date: "2025-09-12"
feed_url: "https://status.svix.com/history.atom"
---
Sep 12 , 21:09 UTC Resolved - Due to a race condition in the throttling code, some message may have been throttled for a much longer time than they were supposed to. The issue has been fixed and everything should be back in order. No action needed.
