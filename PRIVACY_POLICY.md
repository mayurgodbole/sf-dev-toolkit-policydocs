# Privacy Policy — SF Dev Toolkit

**Effective date:** October 21, 2026
**Contact:** mayurgodbole92@gmail.com

SF Dev Toolkit ("the extension") is a browser extension that provides developer,
admin, Agentforce, and QA tooling for Salesforce. This policy explains what
data the extension accesses, what it does with it, and what it never does.

## What the extension accesses, and why

- **Your existing Salesforce session.** The extension reads the session
  cookie for whichever Salesforce org tab is active, so it can call that
  org's own REST and Tooling APIs as you, using the session you're already
  logged into. This is how the extension avoids a separate OAuth login flow.
  The extension never sees, stores, or transmits your Salesforce username or
  password — only the existing session token, and only to that same org's
  own API host.
- **The active tab's URL.** Used to detect which Salesforce org and, where
  relevant, which record you're currently viewing, so tools can default to
  the right context.
- **Salesforce data you choose to query or view.** Records, metadata,
  debug logs, permissions, and similar data are fetched directly from your
  org's API and displayed in the extension's interface. This data is not
  copied anywhere else by the extension itself.

## What the extension stores locally

Saved queries, snapshots (for diff/compare features), and your feature
preferences are stored using Chrome's local extension storage
(`chrome.storage.local`), on your own device only. This data is never
synced to any server we operate, because we don't operate one.

## Optional AI features (bring-your-own-key)

A small number of features (for example, formula generation and test
utterance generation) can optionally use a large language model. These
features are **off by default** and only activate if you provide your own
Anthropic or OpenAI API key in Settings. If you do:

- Only the specific text needed for that feature (e.g., field names for a
  formula request) is sent, directly from your browser, to the API host of
  the provider you chose (`api.anthropic.com` or `api.openai.com`).
- Your API key is stored locally in `chrome.storage.local` and is never
  sent anywhere except as an authentication header on your own requests to
  your chosen provider.
- If you never configure a key, no data is ever sent to any AI provider by
  this extension.

## What we do not do

- We do not operate any backend server. There is no infrastructure of ours
  that your data passes through.
- We do not sell, rent, or share your data with any third party.
- We do not use your data for advertising, and this extension does not
  serve ads.
- We do not use your data to make credit, employment, insurance, or other
  eligibility decisions.
- We do not track you across other websites or other extensions.
- We do not collect analytics or telemetry about your usage of the
  extension.

## Permissions, in plain language

| Permission | Why it's needed |
|---|---|
| `cookies` | To read the session cookie for the Salesforce org tab you're using, so the extension can call that org's APIs as you. |
| `storage` | To save your preferences, saved queries, and snapshots locally on your device. |
| `sidePanel` | To display the extension's interface as a Chrome side panel. |
| `activeTab` | To detect which Salesforce org/record you're currently viewing. |
| Host access to `*.salesforce.com`, `*.force.com`, `*.visualforce.com`, `*.salesforce-setup.com` | To call your org's REST/Tooling APIs directly and to show an environment indicator on Salesforce pages. |
| Optional host access to `api.anthropic.com`, `api.openai.com` | Only requested if and when you enable an optional AI feature with your own API key. |

## Your choices

- You can remove the extension at any time, which deletes all locally
  stored data (saved queries, snapshots, settings, and any configured API
  key) along with it.
- You can use the entire extension without ever configuring an AI provider
  key, in which case no data is ever sent to any AI provider.

## Changes to this policy

If this policy changes, the updated version will be posted at this same
URL with a new effective date.

## Contact

Questions about this policy or the extension's data practices:
mayurgodbole92@gmail.com
