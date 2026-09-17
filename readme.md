# Teams Context Debug

Small diagnostic page for troubleshooting Microsoft Teams tab context and Teams SSO behaviour.

## Repository Status

| Field | Value |
|---|---|
| Classification | **Archived utility** |
| Production deployment | **No** |
| Platform | Static HTML / JavaScript |
| Production branch | N/A |
| Purpose | Inspect Teams SDK context, tab URL/query parameters, and test `getAuthToken()` / decoded SSO token claims |
| Canonical repository | This repository |
| Operational warning | No known production dependency. Retained only because it is useful for future Teams SSO/tab troubleshooting. |
| Last verified | 2026-09-17 |

## What it does

When opened inside a Teams tab, the page displays:

- current browser location, origin, referrer and user agent;
- URL query parameters;
- the context returned by `microsoftTeams.app.getContext()`;
- the result of `microsoftTeams.authentication.getAuthToken()`; and
- the decoded JWT payload when token acquisition succeeds.

It is intentionally a simple diagnostic utility rather than an application.

## Expected failures

If Teams SDK initialization fails, the page reports that it is probably not running inside Teams or the tab domain is blocked.

If SSO token acquisition fails, check the Teams app manifest, Entra app registration, `webApplicationInfo`, allowed domains and Teams SSO configuration.

## Lifecycle

This repository is not under active development and should be archived rather than deleted so the diagnostic page remains available if Teams tab/SSO troubleshooting is needed again.
