# Privacy Policy — CoStar → Salesforce Property Sync

**Last updated:** June 16, 2026

## Overview
The CoStar → Salesforce Property Sync Chrome extension ("the Extension") is an
internal productivity tool used by Rein & Grossoehme (RGCRE) staff to copy property
details from a CoStar property page into a matching Salesforce Property record
(creating a new record or updating an existing one).

## Data the Extension reads
- **From CoStar (`*.costar.com`):** the property's address, building size, land area,
  submarket, and the CoStar property ID (from the page URL) shown on the CoStar tab
  you are actively viewing. Read only when you open the extension popup, and only from
  the rendered page already on your screen. The Extension makes no network calls to
  CoStar and does not access CoStar's APIs.
- **From Salesforce (your org's `*.salesforce.com` domain):** existing Property records
  (to match the property you're viewing), and the values of the record you choose to
  update — used to match, avoid duplicates, and show you what will change before any write.

## Data the Extension stores
- **Locally in Chrome (`chrome.storage.local`) only:**
  - Your Salesforce OAuth access token and refresh token (to call the Salesforce REST API on your behalf)
  - Your Salesforce instance URL
- No data is stored on any server operated by the developer.

## Data the Extension sends
- Property fields are written to **your own Salesforce org** via the official Salesforce
  REST API, using the OAuth token you authorized, and only after you review and approve
  the change.
- **No data is transmitted to the developer or any third party.** There is no analytics,
  telemetry, or external server.

## Authentication
- Authentication uses Salesforce OAuth 2.0 via Chrome's `chrome.identity.launchWebAuthFlow`.
  You sign in directly to Salesforce; the Extension never sees your password.

## Permissions justification
- `storage` — store the Salesforce OAuth tokens locally
- `identity` — perform the Salesforce OAuth flow
- `tabs` — detect the active CoStar / Salesforce tab
- `scripting` — read the rendered CoStar page DOM when you open the popup
- Host permissions for `*.costar.com`, `*.salesforce.com`, `*.force.com`,
  `login.salesforce.com` — required to read the CoStar page and call Salesforce APIs

## Data retention & deletion
- Tokens persist locally until you click "Disconnect" in the popup, uninstall the
  Extension, or clear Chrome's extension storage.
- To revoke access on the Salesforce side: Salesforce Setup → Personal Information →
  Connected Apps OAuth Usage → Revoke.

## Third parties
- None. The Extension reads the rendered CoStar page (read-only DOM, no CoStar API calls)
  and communicates only with your Salesforce org via REST API.

## Contact
For questions about this policy, contact: **max@rgcre.com**
