<wizard-report>
# PostHog post-wizard report

The wizard has completed a deep integration of PostHog analytics into the DevEvent Next.js App Router project. The following changes were made:

- **`instrumentation-client.ts`** (new): Initializes PostHog on the client side using the Next.js 15.3+ instrumentation approach. Includes exception capture for error tracking and debug mode in development.
- **`next.config.ts`** (updated): Added PostHog reverse proxy rewrites (`/ingest/*`) to route analytics requests through the Next.js server, improving ad-blocker resistance and data accuracy.
- **`components/ExploreBtn.tsx`** (updated): Added `explore_events_clicked` capture when users click the "Explore events" hero button.
- **`components/EventCard.tsx`** (updated): Added `"use client"` directive and `event_card_clicked` capture (with `title`, `slug`, `location`, and `date` properties) when users click on an event card.
- **`.env.local`** (created): Added `NEXT_PUBLIC_POSTHOG_PROJECT_TOKEN` and `NEXT_PUBLIC_POSTHOG_HOST` environment variables.

| Event | Description | File |
|---|---|---|
| `explore_events_clicked` | User clicked the 'Explore events' button on the homepage hero section | `components/ExploreBtn.tsx` |
| `event_card_clicked` | User clicked on an event card to view event details | `components/EventCard.tsx` |

## Next steps

We've built some insights and a dashboard for you to keep an eye on user behavior, based on the events we just instrumented:

- **Dashboard — Analytics basics**: https://us.posthog.com/project/348037/dashboard/1375341
- **Insight — Event engagement over time**: https://us.posthog.com/project/348037/insights/gDPy3BQw
- **Insight — Discovery funnel: Explore to Event Click**: https://us.posthog.com/project/348037/insights/ZJYTnPwI
- **Insight — Unique users clicking event cards**: https://us.posthog.com/project/348037/insights/v4GwaOXs
- **Insight — Top events by title**: https://us.posthog.com/project/348037/insights/ix4Bnj9u

### Agent skill

We've left an agent skill folder in your project. You can use this context for further agent development when using Claude Code. This will help ensure the model provides the most up-to-date approaches for integrating PostHog.

</wizard-report>
