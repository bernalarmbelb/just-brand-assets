# Shipment Email Templates

Permanent, standardized HTML templates for The Just Brand's client shipment/order emails. All six share one structure (navy header with seagull logo, color-coded boxes, items table, sign-off, footer) so wording and layout stay consistent no matter who sends the email.

Live mockup of all six (with sample data filled in), reviewed and approved 2026-09-29: https://claude.ai/artifact/TCMb1qp5Nb7Tsb4xHwEmmK

## Files

**Status updates** (sent in order as a shipment progresses):
- `01-on-production.html` — order is in production
- `02-label-created.html` — shipping label created, awaiting carrier pickup
- `03-on-the-way.html` — in transit; ETA is always included (folded into the Current Status box, not a separate box)
- `04-delivered.html` — delivered; asks for a quick confirmation of receipt

**Client requests**:
- `05-shipment-confirmation.html` — standalone follow-up asking the client to confirm a shipment already marked delivered actually arrived okay (use when a reply to `04-delivered.html` wasn't received)
- `06-how-to-ship.html` — asks the client to choose sea vs. air freight and to confirm the delivery address/phone before the order ships

## Color coding (consistent across every template)

| Color | Meaning |
|---|---|
| Blue | Status / tracking info |
| Amber | Details, or action needed from The Just Brand's side |
| Green | Needs a reply from the client |

## Using a template

1. Open the file, find/replace every `{{PLACEHOLDER}}` with the real order details (see table below).
2. Leave the logo `src` pointing at the CDN link — never swap in a local or base64 copy; it must stay `https://cdn.jsdelivr.net/gh/bernalarmbelb/just-brand-assets@main/logos/justbrand-seagull-white@2x.png`.
3. Paste the full HTML into the outgoing email client. Do not create a Gmail draft automatically — output/paste only, sending is handled manually.
4. For multiple line items, duplicate the single `<tr>` row inside the items table (the row with `border-top:none` on the first item) once per additional item, and set `border-top:1px solid #e8e8e8` on the added rows.

### Common placeholders

| Placeholder | Used in |
|---|---|
| `{{RECIPIENT_NAME}}` | all |
| `{{ORDER_REF}}` | all |
| `{{ITEM_NAME}}`, `{{ITEM_VARIANT}}`, `{{QTY}}` | all |
| `{{CARRIER}}` | 02, 03, 04, 05 |
| `{{TRACKING_NUMBER}}`, `{{TRACKING_URL}}` | 02, 03, 04, 05 |
| `{{FREIGHT_METHOD}}`, `{{BOX_COUNT}}` | 02, 03, 04, 05 |
| `{{EST_COMPLETION_DATE}}` | 01 |
| `{{ETA_DATE}}` | 03 |
| `{{DELIVERY_DATE}}` | 04, 05 |
| `{{SEA_TRANSIT_ESTIMATE}}`, `{{AIR_TRANSIT_ESTIMATE}}` | 06 |
| `{{SHIP_TO_ADDRESS_LINE_1}}`, `{{SHIP_TO_ADDRESS_LINE_2}}`, `{{SHIP_TO_PHONE}}` | 06 |

If `{{TRACKING_URL}}` isn't known for the carrier, drop the "TRACK PACKAGE →" button and show the tracking number as plain text instead of guessing a link.

Default sign-off: Armbel Bernal, Production Operations Coordinator — change only if told otherwise.
