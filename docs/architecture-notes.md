# Architecture Notes

## Workflow Shape

Most production automation problems in commerce start with an event:

- an order changes state;
- a customer enters a follow-up segment;
- a product sheet is uploaded;
- a manager needs a report;
- a provider callback arrives;
- an exception needs staff review.

The safe pattern is to classify the event, normalize the payload, decide whether the action is read-only or mutating, and route the result through a bounded owner or approval step.

## Data Flow

1. Capture the event from WooCommerce, CRM, Google Sheets, Telegram, email, or a scheduled trigger.
2. Normalize the payload into a small internal shape with identifiers, timestamps, owner, and risk level.
3. Branch into read-only reporting, staff notification, or controlled mutation.
4. Add human review for customer messaging, price/stock edits, refund-like actions, or operational exceptions.
5. Record the outcome in a report, queue, or audit note.

## Safety Boundaries

- Workflow exports are private because they can expose tokens, webhook URLs, account IDs, and business rules.
- Public documentation uses generalized event names and sanitized examples only.
- Provider-specific integrations are replaceable boundaries, not hard-coded business logic.
- Failed automations should produce visible tasks rather than silently retry forever.

## Example Public-Safe Workflow Map

```text
Commerce event
  -> classify event type
  -> normalize customer/order/product identifiers
  -> check risk level
  -> route to report, staff task, or approval queue
  -> execute approved action
  -> write outcome note
```
