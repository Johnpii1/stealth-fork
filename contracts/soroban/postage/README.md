# Postage Contract

Records authenticated postage proofs for Stealth messages and tracks whether
the recipient settled or refunded each proof.

This first version is intentionally non-custodial. The relay must verify that
`payment_hash` points to a valid Stellar payment before accepting `submit`.
Token custody, transfer authorization, expiry, and dispute handling remain
separate audited milestones.

## Interface

- `initialize(minimum)` sets the global minimum postage once.
- `quote(sender_trusted)` returns zero for trusted senders or the minimum.
- `submit(...)` records a sender-authorized payment proof.
- `settle(message_id)` lets the recipient accept the postage.
- `refund(message_id)` lets the recipient mark it for refund.
- `get(message_id)` reads the current record.
