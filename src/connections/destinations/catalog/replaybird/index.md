---
title: ReplayBird Destination
rewrite: true
---
Discover how users engage with your product through session replays with [ReplayBird](https://www.replaybird.com/). Identify issues in the website or product's frontend, xhr calls, and performance. Gain insights into user frustrations and understand precisely why issues are occurring.

The Segment integration for ReplayBird helps accurately identify your customers' behaviour within the ReplayBird dashboard.

## Getting Started
1. Navigate to the **Catalog** in the Segment web app.
2. Search for **ReplayBird** in the Catalog, choose it, and select the source you want to connect to the ReplayBird destination. Ensure that the source is sending events through our JavaScript library Analytics.js.
3. Include your ReplayBird API Key in the destination settings. Copy the ReplayBird **Site Key (alias API KEY)** from the Site Settings and paste it in the destination settings.

After about 30 minutes, the changes you make will be active on the Segment CDN. Analytics.js will then start loading ReplayBird's snippet on your page, sending data in an asynchronous manner.

## Identify

ReplayBird's destination seamlessly captures a User ID and any values sent through your identify call.

It's important to note that identify calls lacking a User ID value won't be sent to ReplayBird.

```javascript
analytics.identify();
analytics.identify("USER_ID");
```

Additionally, any traits specified in the identify call will be forwarded by Segment. For instance, the following call includes traits such as `name`, `email` and `plan`.

```
analytics.identify("user_27", {
  name: "Mathew",
  email: "mathew@acme.com",
  plan: "Premium",
});
```

## Track

ReplayBird's destination automatically ingests user actions when track action is called.

```javascript
analytics.track("EVENT_NAME");
```

An example call would look like:

```
analytics.track("Plan Purchased", {
    planId: "plan_2969302398",
    planAmount: 100
});
```