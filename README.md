# AI Email Assistant (MindsDB)

An automated email-reply system built with MindsDB that reads incoming emails, uses an AI model to detect sponsorship inquiries, and automatically drafts and sends personalized replies on a daily schedule.

## What It Does

This project connects an email inbox directly to MindsDB so it can be queried and managed with SQL. An AI model (powered by OpenAI) reviews each email to determine whether it's related to a sponsorship request. If it is, the model drafts a polite, professional reply that includes sponsorship rates. If it isn't, the email is simply skipped. A scheduled job ties everything together, automatically checking for new matching emails and sending AI-generated replies without any manual work.

## Key Features

- **Email as a database** — Read and send emails using simple queries instead of a traditional inbox interface.
- **AI-powered classification** — Automatically detects whether an email is sponsorship-related.
- **Personalized auto-replies** — Generates polite, on-brand responses that include current sponsorship rates.
- **Scheduled automation** — Runs daily to catch new emails and respond without manual intervention.

## How It Works (High Level)

1. The system connects to an email account and treats it as a queryable data source.
2. Incoming emails can be filtered and reviewed using standard search criteria (like subject line).
3. An AI model is created to evaluate each email and generate an appropriate reply.
4. Matching emails are passed through the model to produce draft responses.
5. A recurring job automates the entire process — checking for new emails, generating replies, and sending them out on a set schedule (currently daily).

## Use Case

This is ideal for content creators, YouTubers, or small teams who regularly receive sponsorship inquiries and want a fast, consistent way to respond with accurate rate information — without manually replying to every email.

## Things to Keep in Mind

- **Matching is currently strict** — the system looks for exact subject line matches, so slightly different subjects (typos, reply threads, forwarded emails) may not be caught.
- **No review step before sending** — replies go out automatically. For higher-stakes use, consider adding a manual approval step before any AI-drafted reply is sent.
- **Keep credentials secure** — email and API credentials should never be committed to a public repository; use environment variables or a secrets manager instead.
