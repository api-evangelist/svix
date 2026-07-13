---
title: "US region: delay in delivery of some messages + a small amount of API endpoints had higher latency"
url: "https://status.svix.com/incidents/h8dxztpb8byx"
date: "2023-07-20"
feed_url: "https://status.svix.com/history.atom"
---
Jul 20 , 20:00 UTC Resolved - There was delay in sending messages in the US region and higher latency in some API endpoints. As for the latency: around 0.003% of the requests during this period had a "client disconnect" (which means that the client was disconnected before the server responded which usually means a client timeout or a networking issue), and a total of 2 "create message" calls took more than 5 seconds (across all customers, so a very tiny fraction of the requests).
