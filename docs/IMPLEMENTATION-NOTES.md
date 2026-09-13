# Implementation Notes

This file is intentionally lightweight. Implementation decisions that change project boundaries or long-lived contracts should graduate into an ADR.

## R0.1 extraction posture

The first implementation pass should extract behavior, not copy an existing application wholesale.

Start with the smallest deterministic vertical slice:

`text/URL payload -> encode -> matrix -> SVG -> validation -> export`

Preserve provenance in the implementing pull request, remove product-specific assumptions, and establish behavioral tests before expanding into structured payloads or styling.
