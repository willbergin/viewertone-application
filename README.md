# ViewerTone

**Understand what viewers are saying and decide what to try next.**

[Example audience report](USER_GUIDE.md#example-tpd-tv-weekly-report) · [User guide](USER_GUIDE.md)

## What it is

ViewerTone is an audience research prototype for YouTube creators. It groups comments by sentiment, topic and feedback type, then connects suggested actions to the comments that support them.

I built it to explore a question. After an upload attracts hundreds of comments, can a creator quickly decide what to change in the next video?

## Key features

- **Audience overview** with sentiment, recurring themes, recent uploads and analysis coverage.
- **Content analysis** with video-level sentiment and example comments.
- **Audience insights** with filters for time period, topic, video and feedback type.
- **Opportunities** with suggested actions and supporting comments.
- **Weekly report** with a fixed scope and a short list of actions an editor can review.
- **Creator accounts** with sign-in, password recovery and a saved YouTube handle.

## Current status

ViewerTone is a deployed prototype awaiting creator validation. The dashboard and weekly report use a synthetic TPD TV sample. The account flow saves a channel handle. Live channel analysis is pending.

I also prepared a separate, manual pilot using 151 top-level comments from one real festival vlog. The next step is to validate the report with a creator and learn which recommendations they would use. Invite-only access is the likely next stage after validation.

This public repository contains the project overview and user guide. Application source is maintained in a separate private repository.

## Tech stack

| Area | Technology |
| --- | --- |
| Interface | HTML, CSS and TypeScript with Instrument Sans |
| Build and hosting | Node.js, esbuild and Vercel |
| Accounts and database | Supabase Auth and PostgreSQL |
| Data preparation | Python scripts for YouTube collection, snapshots and offline classification experiments |
| Testing | Node.js, PGlite, Python unittest, Playwright and GitHub Actions |
| Diagnostics | Opt-in Sentry browser error reporting |

## Technical decisions and trade-offs

| Decision | Reason | Trade-off |
| --- | --- | --- |
| Keep comments alongside recommendations | An editor can see the evidence behind an action. | The strength of a suggestion depends on the comments in scope. |
| Keep the dashboard interactive and the weekly report fixed | The dashboard supports investigation. The report gives the team a shared set of actions to discuss. | A fixed report reflects its stated period and sample. |
| Use synthetic data for the application demo | The experience can be shown while creator validation is underway. | Synthetic findings demonstrate the workflow. A real pilot is needed to judge the value to a creator. |

## Privacy and sources

The example data, comment quotes and upload titles are simulated. TPD TV is the example workspace. The sample does not imply endorsement or participation. The real-comment pilot is separate from the example.

Browser error reporting is optional. The app asks for consent before sending scrubbed error diagnostics. See the [user guide](USER_GUIDE.md) for details.
