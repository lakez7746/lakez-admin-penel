# FIRESTORE SECURITY RULES DESIGN

=================================================

RULE 1: DEFAULT DENY POLICY

allow read, write: if false;

ব্যাখ্যা:

ডিফল্টভাবে কেউ কোনো Data Access করতে পারবে না।

=================================================

RULE 2: ADMIN ACCESS

Condition:

User must be authenticated

AND

role == admin OR super_admin


Permissions:

Read: Yes

Write: Yes

Update: Yes

Delete: Yes


Collections:

admins
sellers
customers
products
orders
transactions
wallets
settlements
withdraw_requests
audit_logs
security_logs


=================================================

RULE 3: SELLER ACCESS

Seller শুধুমাত্র নিজের Data দেখতে পারবে।

Condition:

request.auth.uid == resource.data.sellerId


Allowed Collections:

products
orders
wallets
withdraw_requests
notifications
reviews
conversations
messages


Restrictions:

Seller অন্য Seller-এর Data দেখতে পারবে না।

=================================================

RULE 4: CUSTOMER ACCESS

Customer শুধুমাত্র নিজের Data দেখতে পারবে।

Condition:

request.auth.uid == resource.data.customerId


Allowed Collections:

orders
notifications
reviews
conversations
messages
tickets


Restrictions:

Customer অন্য Customer-এর Data দেখতে পারবে না।

=================================================

RULE 5: CHAT SECURITY

Conversation Access:

Customer OR Seller


Condition:

request.auth.uid in [
    resource.data.customerId,
    resource.data.sellerId
]


Admin:

Full Access


=================================================

RULE 6: TRANSACTION SECURITY

Only Admin Access

Collections:

transactions
settlements
wallets
audit_logs


Seller:

Read Only (own records)


Customer:

No Access


=================================================

RULE 7: SETTINGS SECURITY

Only Super Admin

Collections:

settings


Permissions:

Read: Yes

Write: Yes

Delete: Yes


Others:

No Access


=================================================

RULE 8: SECURITY LOGS

Only Super Admin Access


Collections:

security_logs
audit_logs


Others:

No Access


=================================================

RULE 9: WITHDRAW SECURITY

Seller:

Create own withdraw request

Read own withdraw request


Admin:

Approve
Reject
Process Payment


=================================================

RULE 10: REVIEW SECURITY

Customer:

Create Review

Only if order delivered


Seller:

Read Review

Reply Review


Admin:

Approve
Hide
Delete


=================================================

RULE 11: FRAUD DETECTION DATA

Collections:

messages
security_logs
audit_logs


Only Admin Access


=================================================

RULE 12: NOTIFICATION SECURITY

Users only access own notification


Condition:

request.auth.uid ==
resource.data.receiverId


Admin:

Full Access


=================================================

RULE 13: ADMIN PERMISSION CHECK

Example:

Finance Admin:

Allowed:

wallets
transactions
withdraw_requests


Not Allowed:

settings
security_logs


=================================================

RULE 14: API SECURITY

Only Backend Service Account

Allowed:

Courier API
Payment Gateway
Firebase Functions


Direct Client Access:

Denied


=================================================

RULE 15: FORCE DELETE PROTECTION

Audit Logs:

No Delete


Transactions:

No Delete


Security Logs:

No Delete


=================================================

SECURITY PRINCIPLES

1. Least Privilege Access

2. Role Based Access Control

3. Authentication Required

4. Sensitive Data Protected

5. Audit Logging Enabled

6. Backend Validation Required
