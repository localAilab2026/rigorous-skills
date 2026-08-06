# Persistence Failure Injection

Test failure:
1. before transaction begins,
2. after each insert/update/delete,
3. before commit,
4. after commit but before acknowledgement,
5. during retry,
6. after restart with partially processed durable work.

Verify durable state, side effects, retry behavior, and reconciliation after each point.
