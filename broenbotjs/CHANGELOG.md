# Changelog

## Unreleased
- add `stripVerbatimBlocks` so `<verbatim>` … `</verbatim>` segments are removed before parsing webhook responses, guarding the renderer from injected fragments.
- add `sanitizeInputTextForWebhook` so newline sequences convert to single spaces before we send them to the webhook, preventing empty/multiline payloads that trigger backend failures.
