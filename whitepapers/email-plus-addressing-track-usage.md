# Email Plus Addressing: How to Track Who's Sharing Your Email

Ever wonder which companies are selling or sharing your email address? There's a simple trick built into most email systems that lets you find out — and it's been part of the email standard for years.

## What Is Plus Addressing?

Plus addressing (also called sub-addressing or tagged addressing) lets you append `+anything` to the local part of your email address, and messages will still arrive in your inbox. For example, if your email is `jane@gmail.com`, you can sign up for a service using `jane+netflix@gmail.com` or `jane+bankofamerica@gmail.com`. All of those messages land in the same inbox, but now you know exactly who gave out your address if spam starts showing up.

This feature is formally defined in **RFC 5233**, making it a recognized internet standard rather than a proprietary trick.

## Which Email Providers Support It?

The good news is that plus addressing is supported far more widely than most people realize.

### Major Consumer Providers

All of the following support the `+` delimiter out of the box:

- **Gmail** (`you+tag@gmail.com`)
- **Outlook / Hotmail / Live.com** (`you+tag@outlook.com`)
- **Yahoo Mail** (`you+tag@yahoo.com`)
- **Apple iCloud Mail** (`you+tag@icloud.com`, `you+tag@me.com`)
- **Proton Mail** (`you+tag@protonmail.com`)
- **Fastmail** (`you+tag@fastmail.com`)
- **Zoho Mail**
- **Hey.com** (Basecamp's email service)
- **Tutanota / Tuta**

### Business and Enterprise

- **Microsoft 365 / Exchange Online** — enabled by default since approximately 2020
- **Google Workspace** — works the same as consumer Gmail

### Self-Hosted and On-Premise Mail Servers

If you run your own mail infrastructure, most modern mail server software supports plus addressing either by default or with minimal configuration:

- **Postfix** — supports the `+` delimiter by default (configurable via the `recipient_delimiter` setting)
- **Sendmail** — supports it with configuration
- **Dovecot** — native support
- **Zimbra** — supported
- **Exim** (commonly used with cPanel/WHM) — supported

In general, any standards-compliant mail server can support this feature. It's the server software configuration, not the email protocol itself, that determines whether it works.

## Variations on the Format

Not every provider uses the `+` character. Some notable differences:

- **Yahoo** historically used `-` as its delimiter (e.g., `you-tag@yahoo.com`), though `+` now works as well.
- **Fastmail** offers subdomain addressing in addition to plus addressing, allowing formats like `anything@you.fastmail.com`.
- **Postfix** administrators can configure any character as the delimiter — some choose `-` or `=` instead of `+`.
- **Proton Mail** supports both `+` tagging and the creation of fully separate aliases.

## The Catch: Not Every Website Accepts It

The biggest practical limitation of plus addressing has nothing to do with your email provider. Many websites and online services **reject email addresses containing a `+` character**, either because their validation logic incorrectly treats it as invalid or because they intentionally block it to prevent users from creating multiple accounts or tracking data sharing.

This is frustrating because the `+` is perfectly valid according to the email RFCs, but it remains a common issue.

## Workarounds When Plus Addressing Is Blocked

If a website won't accept your plus-addressed email, there are several alternatives.

### The Gmail Dot Trick

Gmail ignores dots in the local part of an address. That means `j.ane@gmail.com`, `ja.ne@gmail.com`, and `jane@gmail.com` all deliver to the same inbox. You can use different dot placements for different services to achieve a similar tracking effect. Note that this is a Gmail-specific behavior and not an email standard.

### Email Alias and Relay Services

These services generate unique, random email addresses that forward to your real inbox. Because each alias is a completely separate address, the recipient has no way to derive your actual email — making them more private than plus addressing.

- **Apple Hide My Email** — built into iCloud+ and Safari, generates random addresses on the fly
- **Firefox Relay** — Mozilla's email aliasing service
- **DuckDuckGo Email Protection** — strips trackers and forwards to your real address
- **SimpleLogin** (now owned by Proton) — a dedicated open-source email aliasing service
- **addy.io** (formerly AnonAddy) — open-source email forwarding and aliasing

### Provider-Native Aliases

Some email providers let you create fully separate alias addresses within your account:

- **Fastmail** — create custom aliases that route to your inbox
- **Proton Mail** — supports multiple aliases depending on your plan
- **iCloud+** — Hide My Email aliases integrated into Apple's ecosystem

## Which Approach Is Best for Tracking?

If your primary goal is identifying which companies share or sell your email address, **alias services are more robust than plus addressing**. Here's why: any company or data broker that receives `jane+someservice@gmail.com` can trivially strip the `+someservice` portion to recover your real address. A fully separate alias like `x7k9m2@relay.example.com` reveals nothing about your actual inbox.

That said, plus addressing remains extremely useful for **email filtering and organization**. Most email clients let you create rules based on the "To" address, so you can automatically sort messages sent to `jane+shopping@gmail.com` into a Shopping folder, `jane+work@gmail.com` into a Work folder, and so on.

## Quick Reference

| Method | Privacy Level | Ease of Use | Works Everywhere |
|---|---|---|---|
| Plus addressing (`+tag`) | Low — real address is visible | Very easy | No — some sites block it |
| Gmail dot trick | Low — real address is visible | Easy | Gmail only |
| Email aliases (provider) | Medium — linked to your account | Moderate | Yes |
| Relay services (SimpleLogin, etc.) | High — fully anonymous | Moderate | Yes |

## Getting Started

The simplest way to start is to use plus addressing wherever it's accepted. The next time you sign up for a service, try `youremail+servicename@provider.com`. If spam later arrives at that tagged address, you'll know exactly who shared it.

For higher-stakes privacy needs or services that block the `+` character, set up an alias service. Most offer free tiers that are more than sufficient for personal use.
