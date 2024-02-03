# Hlint Rules Aiming To Promote Stability

## Wishlist Of Hlint Features

There are some features we do not have access to from hlint, but that would help us write more
rules.

1. A default typeclass method is overridden.

For example, the `Eq` typeclass has a method, `(/=)`, that is being considered for removal from the
class. To promote stability, we would like to be able to write a rule that would trigger a warning
when this method is manually defined. However we cannot, as of this writing, construct such a rule.
