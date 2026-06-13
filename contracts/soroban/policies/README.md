# Policies Contract

Gives each mailbox owner explicit control over who can mail them.

Owners can allow or block individual senders, decide whether unknown senders
are accepted, require sender verification, and set minimum postage. Explicit
sender rules always take precedence over the mailbox default.

## Interface

- `set_policy(owner, policy)` writes mailbox defaults.
- `get_policy(owner)` reads mailbox defaults.
- `set_sender_rule(owner, sender, rule)` allows, blocks, or resets a sender.
- `sender_rule(owner, sender)` reads the current sender override.
- `can_mail(...)` evaluates the complete policy.
