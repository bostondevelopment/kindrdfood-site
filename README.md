# Kindrdfood — telehealth nutrition care for families

A video-first telehealth nutrition platform connecting families with registered dietitians — scheduling, live video visits, clinical charting, payments, and dietitian-reviewed recipes.

→ **[The product + what it does](https://bostondevelopment.github.io/kindrdfood-site/)**
→ **[Engineering deep-dive](https://bostondevelopment.github.io/kindrdfood-site/engineering.html)** — Rails platform, scheduling engine, live video, Stripe billing, survey engine, audit versioning
→ **[Design](https://bostondevelopment.github.io/kindrdfood-site/design.html)** — brand, palette, components

---

## About this repo

This repository hosts the public-facing site for Kindrdfood — landing page, engineering write-up, design page, privacy policy. The Kindrdfood platform itself (a Ruby on Rails application) lived in a separate, private repository.

## About the app

Kindrdfood was a real, production telehealth platform. A physician refers a child into Kindrdfood; the family is matched with a registered dietitian, builds a household clinical profile, books and pays for a video consultation, completes a pre-appointment intake, meets the dietitian in a live in-browser video room, and afterward receives a clinical assessment plus dietitian-reviewed, allergen-safe recipes. Not a directory or a booking widget bolted onto a calendar — a complete software clinic: scheduling, live video, clinical charting, billing, content, and audit in one product.

## How it was built

I built Kindrdfood end to end as its **technical cofounder and sole engineer**, designing and shipping the platform on Ruby on Rails over roughly three years — data model through AWS deployment.

- **43 database tables** across a genuine clinical + scheduling domain — ~40 ActiveRecord models, 41 controllers, ~9,400 lines of Ruby, and **233 migrations** of continuous schema evolution.
- A **bespoke scheduling engine** that turns each dietitian's availability into overlapping 30- and 60-minute bookable slots, with cascading conflict resolution when a booking changes.
- **Three Stripe billing models** — pay-per-visit, prepaid packages, and recurring subscriptions, with saved cards, coupons, and partner-comped sessions.
- **Live in-browser video** (OpenTok) provisioned per appointment with role-scoped tokens.
- A **lifecycle survey engine** that threads answers forward across intake → session notes → assessment, plus pediatric growth-chart percentiles and z-scores.
- A **recipe allergen-review pipeline** — an in-house chef authors recipes, dietitians tag them at the ingredient level and sign off before any family sees them.
- **IP-tracked, field-level audit versioning** with visual diffs and rollback — compliance-minded history for a HIPAA-adjacent product.

The **[engineering page](https://bostondevelopment.github.io/kindrdfood-site/engineering.html)** walks through all of it.

---

## Author

Built by **Michael Finneran** — Boston, MA
[linkedin.com/in/michaelfinneran](https://linkedin.com/in/michaelfinneran) · [bostondevelopmentco@gmail.com](mailto:bostondevelopmentco@gmail.com)
