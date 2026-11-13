SUBSCRIPTION LOCK UPDATE
========================

This update adds a client-side subscription gate to the Principal HomePage:
- Dashboard remains visible when subscription is not active.
- Navigation drawer and bottom navigation block non-dashboard modules.
- Subscription page remains accessible.
- Active subscription requires subscriptionStatus == "active" and a missing/null or future subscriptionExpiresAt.
- If Firestore cannot be checked, modules remain locked (fail-closed).

IMPORTANT LIMITATIONS:
- This is a client-side UI gate, not tamper-proof security. Production enforcement for every role/device requires trusted server-side authorization and role-specific routing.
- This change gates the HomePage only. The separate Staff/Parent portal flows still need subscription checks before their own screens are opened.
- Offline use will keep modules locked if the app cannot verify the subscription from Firestore.
- Flutter build was not run in this environment; run `flutter pub get` and `flutter build apk --release` and share any compiler error.
- Ensure the published Firestore rules permit the subscription fields written by the current Admin approval code.
