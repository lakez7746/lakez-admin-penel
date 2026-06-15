# FIREBASE AUTHENTICATION FLOW

=================================================

AUTHENTICATION METHOD

Firebase Authentication

Login Type:

- Email & Password
- Two Factor Authentication (2FA)

=================================================

USER ROLE

1. Super Admin
2. Admin

Note:

Seller Login → Seller Panel
Customer Login → Customer App

Admin Panel শুধুমাত্র Admin-এর জন্য।

=================================================

LOGIN FLOW

Admin Opens Panel

↓

Enter Email

↓

Enter Password

↓

Firebase Authentication Verify

↓

Check Account Status

↓

Check Role

↓

Send OTP / 2FA

↓

Verify OTP

↓

Create Session

↓

Open Dashboard

=================================================

ACCOUNT STATUS CHECK

Values:

- active
- inactive
- blocked

Rules:

active
    → Login Allowed

inactive
    → Login Denied

blocked
    → Security Alert

=================================================

ROLE CHECK

super_admin

    Full Access


finance_admin

    Settlement
    Wallet
    Withdraw
    Transaction


order_admin

    Orders
    Delivery
    Pickup


courier_admin

    Courier
    Tracking


support_admin

    Chat
    Tickets

=================================================

DEVICE VERIFICATION

System Stores:

- Device ID
- Browser
- Operating System
- IP Address
- Login Time

If New Device:

    Send OTP

=================================================

SESSION MANAGEMENT

sessionId

accessToken

refreshToken

createdAt

expiresAt

sessionStatus

Values:

- active
- expired
- revoked

=================================================

FAILED LOGIN PROTECTION

Rules:

1st Failed Login
    Warning

3 Failed Login
    Temporary Lock

5 Failed Login
    Account Locked

Admin Alert Generated

=================================================

OTP FLOW

Login

↓

Generate OTP

↓

Send Email

↓

Verify OTP

↓

Dashboard Access

OTP Expiry:

5 Minutes

=================================================

FORCE LOGOUT

Super Admin Can:

- Logout Admin
- Revoke Session
- Block Device
- Block IP

=================================================

AUDIT LOG

Record:

- Login
- Logout
- Failed Login
- Password Change
- Permission Change
- Device Change

=================================================

FIREBASE COLLECTIONS USED

admins

security_logs

audit_logs

sessions

device_logs

notifications

=================================================

SECURITY FEATURES

✓ Password Hash

✓ Two Factor Authentication

✓ Device Tracking

✓ IP Tracking

✓ Session Timeout

✓ Force Logout

✓ Audit Logging

✓ Suspicious Activity Detection
