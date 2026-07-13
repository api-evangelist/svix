---
title: "US region: create message API failures [ephemeral, resolved]"
url: "https://status.svix.com/incidents/l0t1zz7wp4zx"
date: "2025-11-24"
feed_url: "https://status.svix.com/history.atom"
---
Nov 24 , 21:30 UTC Resolved - Load balancing misconfiguration caused ~90% of "create message" API calls to fail in the US region. The configuration was immediately reverted which returned to full functionality. Affected time: 2025-11-24 at ~21:23:00 UTC Svix SDKs have retries baked in and would in most cases transparently recover.
