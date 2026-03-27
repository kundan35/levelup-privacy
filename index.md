---
layout: default
title: Privacy Policy
nav_order: 1
---

# Kindred Sanctuary — Privacy Policy

**Effective Date:** March 9, 2026
**Last Updated:** March 9, 2026

---

## 1. Who We Are

Kindred is an independent application developed and operated by **Kundan** ("I," "me," or "my"), an individual developer. Kindred is a parental-control and digital-wellness application designed to help families establish healthy screen habits. The app is installed on a child's Android device and managed by a parent or legal guardian ("Parent") through a paired account.

**Contact:**
Developer: Kundan
Email: kundan06335@gmail.com
Country of residence: [Your country]

---

## 2. Scope of This Policy

This policy applies to:

- The Kindred Android application installed on a child's device
- The Kindred parent dashboard (Android / iOS / Desktop)
- All data processed through our backend (Supabase) and cloud services

This policy covers all users globally. Sections 10 and 11 provide additional disclosures required by the **Children's Online Privacy Protection Act (COPPA)** and **General Data Protection Regulation (GDPR)**, respectively.

---

## 3. Who We Collect Data About

Kindred processes data about two categories of people:

| Role | Description |
|------|-------------|
| **Parent / Guardian** | The adult who creates an account, configures controls, and receives reports |
| **Child** | The minor whose device is monitored, identified only via a Parent-created child profile |

Children's accounts are **not created directly by the child.** All child profiles are created and controlled by the Parent.

---

## 4. Data We Collect

### 4.1 Parent Account Data

| Data | Purpose | Legal Basis (GDPR) |
|------|---------|-------------------|
| Email address | Account creation, authentication, notifications | Contract performance |
| Encrypted password (via Supabase Auth) | Authentication | Contract performance |
| FCM push token | Delivering real-time alerts to the parent's device | Legitimate interest |
| Profile role ("parent") | Access control | Contract performance |

### 4.2 Child Profile Data

Child profiles are created by the Parent. We collect:

| Data | Purpose | Legal Basis (GDPR) |
|------|---------|-------------------|
| Child's first name (provided by Parent) | Display in dashboard | Parental consent |
| Numeric PIN (hashed) | Child self-login on their device | Parental consent |
| Level (1–4) and gamification progress (XP, coins, achievements) | Digital-wellness reward system | Parental consent |
| Child profile ID (internal UUID) | Linking all child data records | Parental consent |

### 4.3 App Usage Monitoring

Collected on the child's device via the Android **UsageStatsManager** API:

| Data | Retention |
|------|-----------|
| Package name of installed apps | Duration of account |
| Daily usage duration per app (minutes) | 90 days |
| App open count per day | 90 days |
| Time-limit and allow/block status per app | Duration of account |
| Screen time reports (daily and weekly summaries) | 1 year |

### 4.4 Location Data

Collected only when the Parent explicitly enables location tracking:

| Data | Retention |
|------|-----------|
| GPS coordinates (latitude, longitude, accuracy, altitude, speed) | 30 days |
| Geofence zone definitions (name, center, radius) | Duration of account |
| Geofence entry / exit / dwell events | 90 days |

Location data is transmitted to our servers only when a network connection is available. Background location access (`ACCESS_BACKGROUND_LOCATION`) is used exclusively to detect geofence transitions while the app is not in the foreground.

### 4.5 Communication Monitoring

Kindred monitors on-device communications to detect contact with unapproved parties:

| Data | How Collected | Retention |
|------|--------------|-----------|
| Phone call metadata (number, duration, direction) | `READ_CALL_LOG` permission | 30 days |
| SMS metadata (sender number, message excerpt up to 160 chars) | `READ_SMS` permission | 30 days |
| WhatsApp call metadata (direction, type: voice/video, missed flag) | Notification Listener Service | 30 days |
| WhatsApp message metadata (sender contact name, preview up to 50 chars) | Notification Listener Service | 30 days |

> **We do not record the full content of phone calls or SMS/WhatsApp messages.** Only metadata (who, when, whether the contact is approved) is stored.

### 4.6 YouTube Activity

Collected via the Android **Accessibility Service** API while YouTube is in the foreground:

| Data | Retention |
|------|-----------|
| Video titles and channel names viewed | 30 days |
| YouTube search queries typed | 30 days |
| Whether content was a YouTube Short | 30 days |

### 4.7 Device and Technical Data

| Data | Purpose | Retention |
|------|---------|-----------|
| Crash reports and stack traces (Firebase Crashlytics) | Bug fixing and stability | 90 days |
| Device admin activation / deactivation events | Security audit log | 90 days |
| App version, Android OS version (in crash reports) | Bug fixing | 90 days |

We do **not** collect: device serial numbers, advertising identifiers (GAID/IDFA), contact lists beyond call/SMS metadata, photos or camera content, microphone recordings, or browsing history outside of YouTube.

---

## 5. How We Use the Data

1. **Providing parental controls** — enforcing app blocks, time limits, bedtime schedules, exam mode, and web content filters.
2. **Safety monitoring** — alerting Parents in real time when the child communicates with an unapproved contact.
3. **Location safety** — showing the child's current location and notifying Parents of geofence entries/exits.
4. **Wellness reporting** — generating screen time and activity reports for Parent review.
5. **Gamification** — rewarding the child for healthy device habits (XP, coins, pet interactions, achievements).
6. **Service security and fraud prevention** — detecting device-admin deactivation attempts, diagnosing crashes.
7. **Push notifications** — delivering real-time alerts to the Parent's device via Firebase Cloud Messaging.

We do **not** use collected data for advertising, sell it to third parties, or use it to build behavioral profiles for commercial purposes.

---

## 6. Data Sharing

| Recipient | What Is Shared | Reason |
|-----------|----------------|--------|
| **Supabase Inc.** (USA, EU region available) | All user and monitoring data stored in PostgreSQL | Primary database and auth provider |
| **Google Firebase** (Google LLC, USA) | Crash reports, push notification tokens | Crashlytics and Cloud Messaging |
| **Google Play Services** (on-device) | FCM token | Push delivery infrastructure |

All third-party processors are bound by Data Processing Agreements. No data is shared with any other parties except when required by law.

---

## 7. Data Storage and Security

- All data in transit is protected by **TLS 1.2 or higher**.
- The Android app enforces **certificate pinning** for all connections to the backend.
- Cleartext (HTTP) traffic is blocked at the OS level via Android Network Security Config.
- Database access is restricted via **Row-Level Security (RLS)** in Supabase — a parent can only access their own children's data.
- Passwords are never stored in plaintext; authentication is delegated entirely to Supabase Auth (bcrypt-hashed).
- The child PIN is stored as a one-way hash.

---

## 8. Data Retention

| Category | Retention Period |
|----------|-----------------|
| Parent account | Until account deletion |
| Child profile | Until Parent deletes the profile or account |
| App usage data | 90 days rolling |
| Location points | 30 days rolling |
| Communication metadata | 30 days rolling |
| YouTube activity | 30 days rolling |
| Screen time reports | 1 year |
| Crash reports | 90 days |

Upon account deletion all associated data is permanently deleted from our servers within **30 days**.

---

## 9. Your Rights

Regardless of your location, you may at any time:

- **Access** the personal data we hold about you or your child
- **Correct** inaccurate data
- **Delete** your account and all associated data
- **Export** your data in a portable format
- **Withdraw consent** for any optional data collection

To exercise these rights, email **kundan06335@gmail.com** with the subject line "Privacy Request." We will respond within **30 days**.

---

## 10. COPPA Disclosure (United States)

Kindred is designed to be installed **by parents on children's devices**. We take our obligations under the **Children's Online Privacy Protection Act (COPPA), 15 U.S.C. § 6501 et seq.,** and the COPPA Rule (16 C.F.R. Part 312) seriously.

### 10.1 Verifiable Parental Consent

- Children under 13 **do not create accounts**. All accounts are created by the Parent.
- The Parent provides **verifiable consent** to the collection of their child's data at the time they set up the child profile.
- The Parent may review all data collected about their child through the parent dashboard at any time.

### 10.2 What We Collect from Children Under 13

| Category | Is It Collected? | Notes |
|----------|-----------------|-------|
| Name | First name only, entered by Parent | Not collected directly from child |
| Location | Yes, if enabled by Parent | Parent-controlled; see §4.4 |
| Device usage | Yes | Core service functionality |
| Communications metadata | Yes | Core safety feature; see §4.5 |
| Photos / audio / video | No | Not collected |
| Persistent identifiers | Internal UUID only | Not linked to advertising |

### 10.3 Parental Rights under COPPA

Parents may at any time:
1. **Review** personal information collected from their child.
2. **Request deletion** of all data collected from their child by contacting **kundan06335@gmail.com**.
3. **Refuse further collection** by deleting the child profile, which immediately stops all monitoring.

We will not condition a child's participation in the app on disclosure of more personal information than is reasonably necessary to provide the service.

### 10.4 We Do Not

- Disclose children's personal information to third parties for commercial purposes.
- Allow children to publicly post personal information.
- Use children's data to serve behavioral advertising.
- Retain children's data longer than necessary (see §8).

---

## 11. GDPR Disclosure (European Economic Area, UK, Switzerland)

### 11.1 Data Controller

For users in the EEA, UK, and Switzerland, the data controller is:
**Kundan** (individual developer) · kundan06335@gmail.com

### 11.2 Legal Bases for Processing

| Processing Activity | Legal Basis (Art. 6 GDPR) |
|--------------------|--------------------------|
| Parent account creation and authentication | Art. 6(1)(b) — Contract performance |
| Child profile and monitoring data | Art. 6(1)(a) — Explicit consent of the parent / holder of parental responsibility |
| Crash reporting and security logging | Art. 6(1)(f) — Legitimate interest (service security) |
| Compliance with legal obligations | Art. 6(1)(c) — Legal obligation |

For processing special-category data (which may arise incidentally in communication metadata), we rely on **Art. 9(2)(a) GDPR** — explicit consent.

### 11.3 Data Subject Rights (Arts. 15–22 GDPR)

| Right | How to Exercise |
|-------|----------------|
| **Access** (Art. 15) | Email kundan06335@gmail.com |
| **Rectification** (Art. 16) | Edit in app settings or email us |
| **Erasure / Right to be Forgotten** (Art. 17) | Delete account in app or email us |
| **Restriction of Processing** (Art. 18) | Email us |
| **Data Portability** (Art. 20) | Email us; we provide JSON export |
| **Objection** (Art. 21) | Email us |
| **Withdraw Consent** (Art. 7(3)) | Delete child profile in app |

We will respond to all requests within **30 days** (extendable to 90 days for complex requests with notice).

### 11.4 International Transfers

Our primary data processor (Supabase) offers an EU-region deployment. Where data is transferred outside the EEA, we rely on **Standard Contractual Clauses (SCCs)** approved by the European Commission.

### 11.5 Right to Lodge a Complaint

You have the right to lodge a complaint with your national supervisory authority. A list of EU supervisory authorities is available at [edpb.europa.eu](https://edpb.europa.eu/).

---

## 12. Android Permissions — Plain-Language Explanation

| Permission | Why We Need It |
|------------|---------------|
| `ACCESS_FINE_LOCATION` / `ACCESS_BACKGROUND_LOCATION` | Real-time GPS tracking and geofence detection (Parent-enabled feature) |
| `PACKAGE_USAGE_STATS` | Reading which apps are in the foreground to enforce time limits and blocks |
| `SYSTEM_ALERT_WINDOW` | Displaying the "app blocked" overlay on top of blocked apps |
| `READ_CALL_LOG` | Detecting calls to/from unapproved contacts |
| `READ_SMS` | Detecting SMS from unapproved contacts |
| `READ_PHONE_STATE` | Identifying incoming/outgoing call state |
| `BIND_NOTIFICATION_LISTENER_SERVICE` | Reading WhatsApp notification metadata (sender, preview) |
| `BIND_ACCESSIBILITY_SERVICE` | Detecting YouTube video titles and search queries |
| `CAMERA` | Optional photo capture feature for child activity (Parent-reviewed) |
| `POST_NOTIFICATIONS` | Sending real-time alerts to the parent |
| `RECEIVE_BOOT_COMPLETED` | Restarting monitoring services after device reboot |
| `REQUEST_IGNORE_BATTERY_OPTIMIZATIONS` | Keeping monitoring services running on OEM devices with aggressive battery management |

---

## 13. Children's Data — Additional Safeguards

Beyond legal minimums, we apply the following safeguards voluntarily:

1. **Minimum data principle** — we collect only what is necessary for the specific monitoring feature. Each feature can be disabled independently by the Parent.
2. **No advertising** — children's data is never used for targeted advertising, and we carry no third-party advertising SDKs.
3. **No social features for children** — children cannot share profiles, post content, or communicate with users outside their approved contact list.
4. **Transparent to the child** — the app displays a visible notification on the child's device when monitoring is active, so the child is aware they are being monitored.
5. **Parent-only access** — the parent dashboard is protected by password authentication; children cannot access monitoring reports.
6. **Data minimisation on communication monitoring** — message content beyond a 50-character preview is never stored; full message bodies are never uploaded.

---

## 14. Data Breaches

In the event of a personal data breach affecting users in the EEA, I will notify the relevant supervisory authority within **72 hours** of becoming aware of it (Art. 33 GDPR) and affected users without undue delay where the breach is likely to result in high risk (Art. 34 GDPR).

---

## 15. Changes to This Policy

Registered Parents will be notified by email and in-app notification at least **30 days** before any material changes take effect. Continued use of the service after the effective date constitutes acceptance of the revised policy. For changes that affect how we use children's data, fresh parental consent will be sought where required by law.

---

## 16. Contact

**Developer:** Kundan
**Email:** kundan06335@gmail.com
**Response time:** 5 business days for acknowledgement; 30 days for resolution

If you believe your data has not been handled appropriately, you may also contact your local data-protection authority.

---

## 17. Note on Solo Developer Status

Kindred is built and maintained by a single independent developer. There is no company, employees, or investors. All data handling described in this policy is performed solely by the developer and the third-party processors named in §6 (Supabase, Firebase). Your privacy rights are exercised directly with me at the contact address above.

---

*This document was last updated on March 9, 2026.*
