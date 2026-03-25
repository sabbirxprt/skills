---
name: wp-plugin-readme
description: >
  Generates fully compliant WordPress.org plugin readme.txt files and reviews
  existing ones for violations. Use this skill whenever the user wants to write,
  update, audit, or fix a WordPress plugin readme, plugin name, plugin description,
  or any WordPress.org submission content. Also trigger when the user mentions
  WordPress.org compliance, plugin directory, readme.txt, plugin listing,
  banner/icon guidelines, trademark issues, keyword stuffing, third-party service
  disclosure, or source code requirements. If the user is preparing to submit or
  resubmit a plugin to WordPress.org, always use this skill — do not rely on
  general knowledge alone.
---

# WordPress Plugin README Skill

This skill helps you write and audit WordPress plugin `readme.txt` files that are
fully compliant with WordPress.org guidelines, covering all known violation patterns.

---

## What This Skill Does

1. **Generates** a complete, compliant `readme.txt` from scratch
2. **Audits** existing readme files or plugin metadata for violations
3. **Fixes** specific sections that were flagged by WordPress.org reviewers

---

## Known Violation Categories (Always Check These)

### 1. Trademark Abuse ⚠️ (Most Common / Most Severe)

Never use another company's trademark in:
- Plugin **slug** (the folder name / URL)
- Plugin **display name**
- Banner or icon images
- Screenshots

**Banned patterns:**
- Plugin names like `speed-booster-for-elementor` → uses "Elementor" trademark
- Plugin names starting with `cloudflare-`, `turnstile-`, `google-sheets-` → implies official affiliation
- Using the WordPress logo (W mark) in plugin icons
- Icons visually similar to Google Sheets, Google Drive, Slack, etc.

**Compliant pattern:**
- Use a unique, brandable name: `FlexTable`, `FlexOrder`, `WP Dark Mode`
- Generic descriptors are OK; brand names are NOT
- If integration is needed in the name: `[YourBrand] for [Service]` — trademarked term must NOT be first

---

### 2. Keyword Stuffing ⚠️

The plugin **name** field must be short, factual, and non-promotional.

**Violation example:**
```
=== Bulk Order Sync for WooCommerce with Google Sheets | Bulk Edit WooCommerce Orders, Manage Orders, Sync Order Details & More – FlexOrder ===
```

**Compliant example:**
```
=== FlexOrder – WooCommerce Order Sync for Google Sheets ===
```

**Rules:**
- No pipe `|` separated keyword lists in the name
- No superlative claims: "best", "easiest", "#1", "most powerful", "the only"
- Short description should be one factual sentence, max ~150 chars
- Tags section: max 5 relevant tags, no repetition of the plugin name

---

### 3. Support Forum Redirects ⚠️

The `== Support ==` section must NOT redirect free users away from the
WordPress.org forum as the first option.

**Violation:**
```
For support, please contact us at https://yoursite.com/support
```

**Compliant pattern:**
```
== Support ==

For free version support, please use the [WordPress.org support forum](https://wordpress.org/support/plugin/your-plugin/).

Check the [FAQ section](#faq) first — your question may already be answered there.

For the **premium version**, contact us at https://yoursite.com/support
```

---

### 4. Third-Party Service Disclosure ⚠️ (Required)

If your plugin uses **any** external library, API, or service, you MUST disclose it.

**Required section in readme.txt:**
```
== Third-Party Services & Libraries ==

This plugin uses the following external services:

* **Jitsi Meet** – Used for video call functionality.
  - Service URL: https://jitsi.org
  - Terms of Service: https://jitsi.org/terms-of-service/
  - Privacy Policy: https://jitsi.org/privacy/

* **[Library Name]** – [What it does in this plugin]
  - Source: https://example.com
  - License: MIT – https://opensource.org/licenses/MIT
```

Failure to include this section is a common reason for plugin rejection.

---

### 5. Source Code Requirement

Your deployed plugin must include full source code, not just compiled/minified assets.

**In readme.txt**, make clear to contributors:
```
== Development ==

The source code for this plugin is available on [GitHub/GitLab](https://link-to-repo).

To build from source:
1. Run `npm install`
2. Run `npm run build`

The `src/` directory contains all unminified source files.
```

---

## Full Compliant readme.txt Template

```
=== [Plugin Display Name] – [Short Factual Tagline] ===
Contributors: yourwporgusername
Donate link: https://yoursite.com/donate
Tags: tag1, tag2, tag3, tag4, tag5
Requires at least: 5.0
Tested up to: 6.6
Stable tag: 1.0.0
Requires PHP: 7.4
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

One-sentence description of what the plugin does. Keep it factual and under 150 characters.

== Description ==

[Explain what the plugin does. Be factual. No superlatives. No keyword stuffing.]

Key features:
* Feature one
* Feature two
* Feature three

== Installation ==

1. Upload the plugin folder to `/wp-content/plugins/`
2. Activate the plugin through the 'Plugins' screen in WordPress
3. Go to Settings → [Plugin Name] to configure

== Frequently Asked Questions ==

= How do I do X? =
Answer here.

= Is this compatible with Y? =
Answer here.

== Screenshots ==

1. Description of screenshot 1
2. Description of screenshot 2

== Changelog ==

= 1.0.0 =
* Initial release

== Upgrade Notice ==

= 1.0.0 =
Initial release.

== Support ==

For free version support, please use the [WordPress.org support forum](https://wordpress.org/support/plugin/your-plugin-slug/).

Please check the FAQ above before posting — your question may already be answered.

For **premium version** support, visit https://yoursite.com/support

== Third-Party Services & Libraries ==

This plugin uses the following external services or libraries:

* **[Service/Library Name]** – [What it does]
  - URL: https://example.com
  - Terms of Service: https://example.com/tos
  - Privacy Policy: https://example.com/privacy

== Development ==

Source code is available at: https://github.com/yourorg/your-plugin

To build from source:
1. `npm install`
2. `npm run build`

The `src/` directory contains all uncompiled source files.
```

---

## Audit Checklist

When auditing an existing readme or plugin submission, check every item:

### Name & Metadata
- [ ] Plugin name contains no third-party trademarks
- [ ] Plugin name is not keyword-stuffed (no `|` lists, no superlatives)
- [ ] Short description is under 150 chars and factual
- [ ] Tags: 5 or fewer, relevant, not repeating the plugin name
- [ ] Single WordPress.org account owns this plugin (not multiple org accounts)

### Icon & Banner
- [ ] No WordPress logo (W mark) used
- [ ] No other company's logo/color scheme replicated
- [ ] Icon is original artwork

### Support Section
- [ ] Free support links to WordPress.org forum FIRST
- [ ] Premium support link is clearly labeled as premium-only

### Technical Sections
- [ ] All third-party services/libraries disclosed with ToS & Privacy links
- [ ] Source code / build instructions referenced
- [ ] No duplicate of an existing plugin in the directory

### Prohibited Claims
- [ ] No "best", "#1", "most powerful", "easiest", "only" claims
- [ ] No fake reviews or sockpuppet accounts referenced
- [ ] No admin access requested in support forums

---

## Step-by-Step: How to Use This Skill

### To GENERATE a new readme.txt:
1. Ask the user for: plugin name, description, features, WP.org username, external APIs/libraries used
2. Apply the full compliant template above
3. Fill in all sections with user-provided content
4. Run the audit checklist before delivering

### To AUDIT an existing readme.txt:
1. Read the user's current readme content
2. Go through every item in the Audit Checklist
3. Flag all violations with ⚠️ and explain why it's a problem
4. Offer a corrected version of each violating section

### To FIX a flagged section:
1. Identify which of the 5 violation categories applies
2. Rewrite only the flagged section using the compliant pattern shown above
3. Confirm the fix passes the checklist before returning it

---

## Final Warning Triggers (Avoid At All Costs)

WordPress.org can revoke developer rights permanently for:

1. **Plugin duplication** – submitting a copy of another existing plugin
2. **Multiple accounts** – different WP.org accounts for the same organization
3. **Sockpuppeting / fake reviews** – artificial ratings or reviews
4. **Repeated trademark abuse** – continuing after receiving a warning
5. **Repeated support forum violations** – consistently redirecting free users

> ⚠️ If the user's plugin has already received a warning from WordPress.org,
> flag this prominently and recommend strict compliance on every single point
> before resubmission. One more violation could result in permanent removal.
```