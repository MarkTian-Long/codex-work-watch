# Lifecycle State Machine

## Reset

unknown → teaser → announcement → rollout-start → completion

Rules:
- A promise is not completion.
- Loading is not propagated.
- Third-party completion labels require official confirmation.

## Model availability

unverified → unofficial evidence → official announcement → service shipped → client shipped → broad availability

## Regression

single report → investigation → B+B confirmation → official acknowledgement/fix

Only stage transitions or scope changes trigger notification.
