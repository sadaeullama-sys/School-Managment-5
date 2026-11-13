Manual Subscription Payment (Spark Free)

Plans:
Weekly Rs 350, Monthly Rs 1,000, Yearly Rs 8,000, Lifetime Rs 16,000.
Principal opens School Subscription from the dashboard, chooses JazzCash/Easypaisa/Bank Transfer,
and submits the transaction/reference ID. The request is stored as pending under:
schools/{schoolId}/paymentRequests/{requestId}.

IMPORTANT:
- This update only submits requests. It does NOT yet provide the System Admin approval screen,
  payment-account number display, proof-image upload, or automatic subscription activation.
- Admin approval must be implemented and tested before production use.
- Do not paste private payment credentials into the app.
- Replace Firestore Rules in Firebase Console only after reviewing them and keeping a backup.
- The existing school status approval and school data access behavior is retained.

ADMIN PAYMENT DETAILS:
System Admin Panel now has editable JazzCash, Easypaisa and Bank account title/number fields.
Save these values in appSettings/paymentAccounts; schools see the details for their selected method.
Subscription expiry is checked when the signed-in principal loads the dashboard. Weekly/Monthly/Yearly
approval writes an expiry timestamp; Lifetime writes no expiry. Expired schools are shown a renewal
screen. This client-side expiry check is not tamper-proof; production enforcement across all roles
requires server-side verification/expiry enforcement. Test Admin settings and Firestore rules before
using with real payments.
