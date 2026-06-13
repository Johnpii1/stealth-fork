# Receipts Contract

Creates authenticated delivery and read-receipt state for a message hash.

The sender authorizes the delivery record. Only the recipient can add the
read timestamp. Both transitions emit events for relays and clients.

## Interface

- `delivered(message_id, sender, recipient)` creates a delivery receipt.
- `read(message_id)` adds the recipient-authorized read timestamp.
- `get(message_id)` reads the receipt.
