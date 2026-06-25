# Regulate — Privacy Policy

**Effective date:** june 25th, 2026
**Last updated:** june 25th, 2026

## About this policy

Regulate is a wellness app made by Lukas Padvelskis ("we", "us", "our"). This policy explains what personal data we collect when you use the Regulate iOS app, why we collect it, who we share it with, and what choices you have. We've written it in plain English; defined terms are limited to the few cases where precision matters.

Regulate is a wellness and lifestyle tool. **It is not a medical device, and nothing in the app is medical advice, diagnosis, or treatment.** See our Terms of Service for the full disclaimer.

## Quick summary

- We collect what you tell us in onboarding and check-ins (name, age, gender, time zone, self-reported symptoms, habits, daily notes), and what we compute from those answers (your Cortisol Score, archetype, streaks).
- We store this in our backend at Supabase. We use PostHog for first-party product analytics and Sentry for crash reporting.
- We do **not** track you across other apps or websites, do **not** use advertising IDs, and do **not** sell your data.
- You can export everything we hold about you, and you can delete your account from inside the app at any time.
- Regulate is for users aged 13 and older.

## Who controls your data

The data controller is Lukas Padvelskis, an individual based in England and Wales. Address available on request via our support email. You can contact us at lukas160@icloud.com.

## What we collect, why, and where it lives

### Information you give us

| What | When | Why | Where it's stored |
|---|---|---|---|
| Email address | When you sign in with Apple | Identifies your account and lets us contact you about service issues. | Supabase Auth (server). |
| First name | Onboarding profile screen | Personalises the app (greeting, narrative). | Supabase, `users` table. |
| Age | Onboarding profile screen (13+ enforced) | Confirms you meet our minimum age and shapes the score model. | Supabase, `users` table. |
| Gender (female, male, non-binary, or prefer-not-to-say) | Onboarding profile screen | Used in the Cortisol Score model. | Supabase, `users` table. |
| Time zone | Detected automatically at sign-in | Anchors your daily check-in to the right local day. | Supabase, `users` table. |
| Symptom selections | Onboarding (body, sleep, mental, emotional categories) | Builds your initial Cortisol Score and archetype. | Supabase, `onboarding_symptoms`. |
| Habit answers | Onboarding (18 yes/no questions about cortisol-related routines) | Identifies flagged habits to include in your plan. | Supabase, `onboarding_habits`. |
| Daily check-ins (which habits you logged today, optional free-text note) | Each time you complete a check-in | Updates your score, streaks, and recommendations. | Supabase, `check_ins` and `check_in_habit_logs`. |
| Regulate Button taps | Each time you use the in-app breathing/regulation moment | Tracks completion for your progress view. | Supabase, `regulate_events`. |
| Notification preferences | When you toggle them in Settings | Remembers your choices on this device. | Stored locally in the iOS Keychain (via expo-secure-store). |

### Information generated from your inputs

- **Cortisol Score** (0–100), **archetype label**, daily score deltas, and streaks. Computed by our server from the inputs above and stored in Supabase (`users`, `score_events`).
- **Personalised insights** generated periodically from your activity, stored in Supabase (`user_insights`).

### Information generated automatically

- **Anonymous analytics identifier** assigned by PostHog when the app first runs, later linked to your account once you sign up.
- **Crash and error reports** captured by Sentry when something goes wrong in the app, including the error stack, app version, OS version, device model, and a Sentry session identifier.
- **IP address** is visible to every server we connect to (Supabase, PostHog, Sentry, Apple, RevenueCat) as a property of the HTTPS request. We do not store IP addresses as fields in our database.
### Stress scan (optional)

Regulate includes an optional **stress scan**. You can take a photo with your camera or choose one from your photo library, and our server sends it to an AI vision provider (Anthropic) for a brief, **non-medical impression of how rested or tense you appear** — an overall 0–100 score plus five appearance facets (for example, how tired the eye area looks).

- **The photo is not stored.** It is transmitted for analysis at the moment you scan and is not kept by us — there is no image field in our database and no file storage. We send it to Anthropic only to produce the result.
- **The result is stored, linked to your account.** The overall score and the five appearance facets are saved so you can see how the impression changes over time.
- This result is **wellness/appearance information, not a medical or diagnostic measurement** — it reflects how you *look*, not a reading of any bodily or physiological state, and it diagnoses nothing.
- It is **never** used for advertising and is **never** sold.
- Like the rest of your data, your stress-scan results are **deleted when you delete your account**.


  
 Information related to your subscription

When you subscribe through the App Store, Apple processes the payment. We use **RevenueCat** to receive subscription status updates (start date, renewal, cancellation, product purchased) and store these in Supabase (`subscriptions`). We never see your card details.

## What we don't collect

- We don't read or write Apple HealthKit.
- We don't use the microphone, location, contacts, or motion sensors. (We **do** use the camera and photo library — only for the optional stress scan described below, and only when you choose to scan.)
- We don't use the iOS advertising identifier (IDFA) and we don't show the App Tracking Transparency prompt because we have nothing to track across other apps.
- We don't use any advertising SDK, social SDK, or data broker.
- We don't send you push notifications today (the Settings toggles save your preference but no notifications are scheduled yet).

## Health and wellness data

Some of what you tell us — your self-reported symptoms (for example, "trouble falling asleep", "heart palpitations", "low mood"), your habits, and the Cortisol Score we compute from them — is health-and-wellness information. We treat it that way:

- It's encrypted in transit (HTTPS/TLS) and at rest (Supabase Postgres encryption).
- It's only accessible to your own account through our backend's row-level security.
- It's never used for advertising and is never sold.
- It's not derived from any medical device or sensor. It's based on what you tell us about how you feel and what you do.

Regulate does not provide medical advice. The Cortisol Score is not a clinical measurement of cortisol. If you're concerned about your health, talk to a qualified healthcare professional.

## Who we share data with

We share data with the service providers that make the app run, listed below. We do not sell your data and we do not share it with advertisers.

| Provider | Role | What it receives |
|---|---|---|
| Supabase (Supabase Inc., USA) | Backend hosting, database, authentication | Everything in the tables above. |
| PostHog (PostHog Inc., USA — US cloud) | First-party product analytics | Anonymous and (once you sign up) account-linked event records: which screens you opened, which actions you took. Event properties may include your archetype and score tier. |
| Sentry (Functional Software Inc., USA) | Crash and error reporting | Errors, stack traces, OS/app/device version, Sentry session identifier. |
| Apple (Apple Inc., USA) | Sign in with Apple; App Store payment processing | Your Apple ID identity token at sign-in; purchase and subscription events. |
| RevenueCat (RevenueCat Inc., USA) | Subscription management on top of the App Store | Your account identifier, product purchased, transaction identifier, subscription status. |

Each provider acts as a processor on our behalf and is bound by its own privacy commitments. Their privacy notices are publicly available.

## International transfers

Our service providers are based in the United States. If you use Regulate from the UK, EU, or another country, your data will be transferred to and processed in the US. We rely on the providers' standard contractual clauses and equivalent protections for these transfers.

## How long we keep your data

We keep your data for as long as your account exists. **When you delete your account in Settings, every row tied to your account is permanently removed from our database** (Supabase cascades the deletion through every related table). Backups are retained by Supabase for a rolling window per their standard policy and expire on their own schedule.

Errors and analytics events held by Sentry and PostHog are retained according to those providers' standard retention windows. The windows are set per provider, not per user.

## Your rights

Wherever you are, you can:

- **Export your data.** Open Settings → Export my data. We'll generate a JSON file with every row tied to your account.
- **Delete your account.** Open Settings → Delete account, type the confirmation phrase, and your account, subscription, and data are removed.
- **Contact us** at lukas160@icloud.com for any other request.

If you're in the UK or EU, you also have rights under UK GDPR / EU GDPR to access, correct, restrict, or object to processing, and to lodge a complaint with your local data protection authority (in the UK, the ICO at ico.org.uk). If you're in California, you have rights under the CCPA/CPRA, including the right to know and the right to delete; the in-app export and delete tools satisfy those rights for our service.

## Age

Regulate is for users **13 and older**. We block sign-up below that age. We do not knowingly collect data from anyone under 13. If you believe a child under 13 has signed up, contact us and we'll delete the account.

## Security

- All connections use HTTPS/TLS.
- Your sign-in session is stored on your device in the iOS Keychain (via expo-secure-store), which is hardware-backed.
- The backend enforces row-level security: a signed-in account can only ever read or write its own data.
- We use Sentry to monitor errors so we can spot and fix problems quickly.

No system is perfectly secure. If we discover a breach that affects you, we'll notify you and, where required, the appropriate regulator.

## Changes to this policy

If we change this policy in a material way, we'll update the "Effective date" above and surface a notice in the app. Continuing to use Regulate after a change means you accept the updated policy.

## Contact

Questions, requests, or complaints: lukas160@icloud.com.
Lukas Padvelskis. Address available on request via our support email.
