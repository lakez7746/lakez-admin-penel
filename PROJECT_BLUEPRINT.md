# LAKEZ Marketplace Admin Control Panel

## Project Information

Project Name: LAKEZ Marketplace

Platform: Flutter Web

Backend: Firebase

Courier: Steadfast

Payments:

* bKash
* Nagad
* Cash On Delivery (COD)

Repository:

* lakez_admin_panel

---

## Core Modules

1. Dashboard
2. Seller Management
3. Seller Commission Management
4. Seller Wallet Management
5. Withdrawal Management
6. Customer Management
7. Product Management
8. Category Management
9. Brand Management
10. Review Management
11. Order Management
12. Pickup Management
13. Courier Management
14. Delivery Charge Management
15. Delivery Zone Management
16. Coupon Management
17. Free Delivery Management
18. Campaign Management
19. Banner Management
20. Notification Management
21. Complaint Management
22. Return Management
23. Refund Management
24. Financial Management
25. Transaction Management
26. Seller KYC Management
27. Settlement Management

---

## ID Format

Seller ID:
SLR-0000000001

Customer ID:
CUS-0000000001

Product ID:
PRD-0000000001

Order ID:
ORD-0000000001

Transaction ID:
TRX-0000000001

Withdraw ID:
WDR-0000000001

Pickup ID:
PCK-0000000001

Complaint ID:
CMP-0000000001

Refund ID:
RFD-0000000001

Return ID:
RTN-0000000001
# Seller Collection Design

Collection Name: sellers

## Basic Information

sellerId:
Example: SLR-0000000001

shopId:
Example: SHP-0000000001

shopName

ownerName

email

phone

passwordManagedByFirebase:
true

---

## Identity Verification (KYC)

nidNumber

nidFrontImage

nidBackImage

tradeLicenseNumber

tradeLicenseImage

verificationStatus

Values:

* pending
* approved
* rejected

---

## Shop Information

shopLogo

shopBanner

shopDescription

shopAddress

district

upazila

postalCode

---

## Pickup Information

pickupContactName

pickupPhone

pickupDistrict

pickupUpazila

pickupAddress

---

## Commission Information

commissionType

Values:

* percentage

commissionRate

Example:
5
8
10
12
14
16
18
20

---

## Wallet Information

totalEarnings

pendingBalance

availableBalance

withdrawnBalance

totalCommissionPaid

---

## Payment Information

bkashNumber

nagadNumber

bankAccountName

bankAccountNumber

bankName

branchName

---

## Seller Statistics

totalProducts

totalOrders

completedOrders

cancelledOrders

returnOrders

totalSalesAmount

---

## Seller Status

status

Values:

* active
* inactive
* suspended
* banned

---

## Dates

createdAt

updatedAt

lastLoginAt
# SELLER MANAGEMENT DATABASE DESIGN

## Seller Basic Information

sellerId:
SLR-0000000001

shopId:
SHP-0000000001

shopName

ownerName

phoneNumber

email

passwordManagedByFirebase

profileImage

shopLogo

joinDate

lastLogin

---

## Seller Status

status

Available Values:

* active
* inactive
* suspended
* banned

---

## Seller Verification (KYC)

nidFrontImage

nidBackImage

nidNumber

verificationStatus

Available Values:

* pending
* approved
* rejected

verificationDate

verifiedBy

---

## Seller Commission

commissionType

Available Values:

* percentage
* fixed

commissionRate

Examples:

5
8
10
12
14
16
18
20ses

---

## Seller Wallet

totalEarnings

availableBalance

pendingBalance

withdrawnBalance

totalCommissionPaid

lastSettlementDate

---

## Seller Payment Information

bkashNumber

nagadNumber

bankAccountName

bankAccountNumber

bankName

branchName

---

## Pickup Information

pickupContactName

pickupPhone

pickupDistrict

pickupArea

pickupAddress

pickupLatitude

pickupLongitude

---

## Business Statistics

totalProducts

totalOrders

totalDeliveredOrders

totalCancelledOrders

totalReturnedOrders

totalSalesAmount

averageRating

---

## Account Control

canAddProduct

canWithdraw

canReceiveOrders

adminNotes
# CUSTOMER MANAGEMENT DATABASE DESIGN

## Customer Basic Information

customerId:
CUS-0000000001

fullName

phoneNumber

email

passwordManagedByFirebase

profileImage

joinDate

lastLogin

---

## Customer Status

status

Available Values:

* active
* blocked
* banned

banReason

---

## Customer Address Book

defaultAddress

district

area

fullAddress

postalCode

latitude

longitude

---

## Customer Statistics

totalOrders

totalCompletedOrders

totalCancelledOrders

totalReturnedOrders

totalSpentAmount

---

## Customer Wallet

walletBalance

refundBalance

totalRefundReceived

---

## Customer Preferences

wishlistCount

favoriteCategories

---

## Customer Account Control

canPlaceOrder

canUseCoupon

canRequestReturn

adminNotes
# CUSTOMER MANAGEMENT DATABASE DESIGN

## Customer Basic Information

customerId:
CUS-0000000001

fullName

phoneNumber

email

passwordManagedByFirebase

profileImage

gender

dateOfBirth

joinDate

lastLogin

---

## Customer Status

status

Available Values:

* active
* blocked
* banned

statusReason

statusUpdatedDate

statusUpdatedBy

---

## Customer Address Information

defaultAddress

district

area

fullAddress

postalCode

latitude

longitude

---

## Multiple Delivery Addresses

addressBook

Each Address Contains:

addressId

receiverName

receiverPhone

district

area

fullAddress

postalCode

latitude

longitude

isDefault

---

## Customer Statistics

totalOrders

completedOrders

cancelledOrders

returnedOrders

totalSpent

averageOrderValue

lastOrderDate

---

## Customer Wallet

walletBalance

refundBalance

couponBalance

totalRefundReceived

---

## Customer Coupons

usedCoupons

activeCoupons

expiredCoupons

---

## Customer Activity

lastOrderId

lastLoginIp

deviceInfo

accountCreatedFrom

Available Values:

* android
* ios
* web

---

## Customer Complaints

totalComplaints

openComplaints

resolvedComplaints

---

## Customer Reviews

totalReviews

averageReviewRating

---

## Customer Security

emailVerified

phoneVerified

twoFactorEnabled

---

## Customer Account Control

canPlaceOrder

canWriteReview

canUseCoupon

canReceiveNotifications

adminNotes
# PRODUCT MANAGEMENT DATABASE DESIGN

## Product Basic Information

productId:
PRD-0000000001

sellerId

shopId

categoryId

subCategoryId

brandId

productName

shortDescription

fullDescription

productStatus

Available Values:

* pending
* approved
* rejected
* hidden
* blocked

approvalDate

approvedBy

rejectionReason

createdAt

updatedAt

---

## Product Pricing

regularPrice

salePrice

costPrice

taxAmount

discountAmount

discountType

Available Values:

* percentage
* fixed

---

## Product Inventory

sku

barcode

stockQuantity

minimumStockAlert

soldQuantity

reservedQuantity

stockStatus

Available Values:

* in_stock
* low_stock
* out_of_stock

---

## Product Images

thumbnailImage

galleryImages

imageCount

---

## Product Variants

hasVariant

variantType

Examples:

* size
* color
* size_color

---

## Size Options

sizes

Examples:

S
M
L
XL
XXL

---

## Color Options

colors

Examples:

Black
White
Blue
Red

---

## Variant Stock

variantStock

Example:

Black + XL = 20 pcs

White + L = 15 pcs

---

## Product Shipping

weight

length

width

height

shippingClass

pickupRequired

---

## Product Review Information

totalReviews

averageRating

fiveStarCount

fourStarCount

threeStarCount

twoStarCount

oneStarCount

---

## Product Sales Statistics

totalViews

totalWishlist

totalOrders

totalDeliveredOrders

totalReturnedOrders

totalRevenue

---

## Product Visibility

isFeatured

isTrending

isBestSelling

isRecommended

showOnHomepage

---

## Product SEO

slug

metaTitle

metaDescription

searchKeywords

---

## Product Control

canPurchase

canReview

adminNotes

sellerNotes
# ORDER MANAGEMENT DATABASE DESIGN (FINAL)

## System Rule

- Merchant Account শুধুমাত্র ১টি থাকবে।
- Merchant Account হবে Admin-এর নিজস্ব।
- সকল Seller-এর Pickup Request এই একটি Merchant Account থেকে Courier API-এর মাধ্যমে যাবে।
- Seller-এর নিজস্ব Merchant Account থাকবে না।
- Seller-এর Pickup Location থেকে Parcel Pickup হবে।
- Customer Delivery Location অনুযায়ী Delivery Charge নির্ধারণ হবে।
- Delivery Complete হওয়ার পর Commission Calculation এবং Settlement Process শুরু হবে।


# 1. Order Basic Information

orderId

orderDate

orderTime

orderSource

Values:
- android
- ios
- web


orderStatus

Values:
- pending
- confirmed
- processing
- pickup_requested
- picked_up
- in_transit
- out_for_delivery
- delivered
- cancelled
- returned
- refunded


Purpose:

Order বর্তমানে কোন অবস্থায় আছে তা সংরক্ষণ করবে।


# 2. Customer Information

customerId

customerName

customerPhone

customerEmail


## Customer Delivery Address

deliveryDistrict

deliveryUpazilaOrCity

deliveryArea

deliveryAddress


Purpose:

Customer কোথায় Parcel গ্রহণ করবে তার তথ্য।


# 3. Seller Information

sellerId

shopId

sellerName

shopName

sellerPhone


Purpose:

কোন Seller-এর Product থেকে Order এসেছে তা সংরক্ষণ করবে।


# 4. Seller Pickup Location Information

locationId

pickupContactName

pickupContactPhone

pickupDistrict

pickupUpazilaOrCity

pickupArea

pickupAddress


Purpose:

Courier Rider যে স্থান থেকে Parcel Pickup করবে সেই তথ্য।


# 5. Product Order Information

productId

productName

sku

category

brand

variant

size

color

quantity

unitPrice

subtotal


Purpose:

Order-এর Product Details সংরক্ষণ করবে।


# 6. Merchant Information

merchantId


Purpose:

একটি Main Merchant Account ব্যবহার হবে।

এই Merchant Account ব্যবহার করে:

- Courier API Connection
- Parcel Create
- Pickup Request
- Tracking Update

করা হবে।


# 7. Courier Information

courierId

courierName

trackingCode


Example:

Steadfast


Purpose:

Courier Service এবং Tracking Number সংরক্ষণ।


# 8. Pickup Information

pickupRequestId

pickupStatus

pickupRequestDate

pickupRequestTime

pickupDate


pickupStatus Values:

- pending
- requested
- accepted
- rider_assigned
- picked_up
- failed
- cancelled


Purpose:

Seller Location থেকে Parcel Pickup Management।


# 9. Pickup Rider Information

pickupRiderId

pickupRiderName

pickupRiderPhone

pickupAssignedDate

pickupCompletedDate


Seller Permission:

Seller দেখতে পারবে:

- Pickup Rider Name
- Pickup Rider Phone
- Pickup Status


Purpose:

Seller যেন জানতে পারে কে Parcel নিতে আসবে।


# 10. Delivery Rider Information

deliveryRiderId

deliveryRiderName

deliveryRiderPhone

deliveryAssignedDate

deliveryCompletedDate


Permission:

Admin:
- Full Access


Seller:
- No Access


Purpose:

Customer Delivery Rider Information নিরাপদ রাখা।


# 11. Delivery Charge Information

deliveryZoneType

deliveryCharge


deliveryZoneType Values:

- inside_district
- outside_district


Delivery Logic:


যদি:

Seller Pickup District = Customer Delivery District


তাহলে:

inside_district_charge


যদি:

Seller Pickup District ≠ Customer Delivery District


তাহলে:

outside_district_charge


Purpose:

Admin Control Panel থেকে Delivery Charge নিয়ন্ত্রণ।


# 12. Payment Information

paymentMethod

Values:

- COD
- bKash
- Nagad


paymentStatus

Values:

- pending
- paid
- failed
- refunded


paymentTransactionId


Purpose:

Customer Payment Information।


# 13. Order Amount Information

productAmount

deliveryCharge

discountAmount

couponDiscount

finalAmount


Purpose:

Order-এর সম্পূর্ণ Financial Calculation।


# 14. Commission Information

commissionType

commissionRate

commissionAmount

adminCommissionAmount

sellerReceivableAmount


Calculation:


Total Product Amount

-

Admin Commission

=

Seller Receive Amount


Purpose:

প্রতিটি Seller-এর Commission হিসাব।


# 15. Settlement Information

settlementEligible

Values:

- yes
- no


settlementStatus

Values:

- pending
- ready
- completed


settlementDate


Purpose:

Delivery Complete হওয়ার পরে Seller Payment Process।


# 16. Return Information

returnRequested

returnReason

returnDate

returnStatus


returnStatus Values:

- none
- requested
- approved
- returned
- rejected


Purpose:

Product Return Management।


# 17. Cancellation Information

cancelReason

cancelDate

cancelledBy


Purpose:

Order Cancellation Record।


# 18. Admin Control Information

adminNotes

sellerNotes

systemNotes

fraudFlag

manualReviewRequired


Purpose:

Admin Monitoring এবং Security Control।


# COMPLETE ORDER FLOW


Customer Order Place

↓

Seller Order Receive

↓

Seller Pickup Location Detect

↓

Single Merchant Account Select

↓

Courier API Request

↓

Pickup Request Create

↓

Pickup Rider Assigned

↓

Seller Pickup

↓

Pickup Completed

↓

Delivery Rider Assigned

↓

Customer Delivery

↓

Delivery Completed

↓

Commission Calculate

↓

Settlement Ready

↓

Seller Wallet Update


# ORDER RELATION


Order

|

|---- Customer

|

|---- Seller

|

|---- Seller Pickup Location

|

|---- Merchant Account

|

|---- Courier

|

|---- Product

|

|---- Settlement

|

|---- Transaction
# MERCHANT MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose

Merchant Management Module-এর কাজ:

- একটি Main Merchant Account পরিচালনা করা।
- এই Merchant Account শুধুমাত্র Admin-এর নিজস্ব হবে।
- সকল Seller-এর Pickup Request এই একটি Merchant Account থেকে যাবে।
- Steadfast API Connection পরিচালনা করা।
- Courier Communication এবং Security Control করা।


# System Rule

- Merchant Account সংখ্যা = ১টি
- Merchant Account Owner = Admin
- Seller-এর আলাদা Merchant Account থাকবে না।
- সকল Seller Order একই Merchant API ব্যবহার করবে।
- Seller Pickup Location আলাদা থাকবে।


==================================================


# 1. MERCHANT BASIC INFORMATION


## merchantId

Data Type:

VARCHAR(50)


Example:

LAKEZ_MAIN_MERCHANT


ব্যাখ্যা:

এটি Main Merchant Account-এর ইউনিক ID।

এই ID পুরো System-এ Merchant Account শনাক্ত করার জন্য ব্যবহার হবে।


--------------------------------------------------


## companyName

Data Type:

VARCHAR(150)


ব্যাখ্যা:

Merchant Account-এর কোম্পানি বা ব্যবসার নাম সংরক্ষণ করবে।


--------------------------------------------------


## merchantEmail

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Merchant Account-এর Email Address।

API Notification এবং গুরুত্বপূর্ণ যোগাযোগের জন্য ব্যবহার হবে।


--------------------------------------------------


## merchantPhone

Data Type:

VARCHAR(20)


ব্যাখ্যা:

Merchant Account-এর মোবাইল নাম্বার।


==================================================


# 2. COURIER API CONFIGURATION


## apiKey

Data Type:

TEXT


ব্যাখ্যা:

Steadfast API Authentication Key।

এই Key ব্যবহার করে Admin Panel Courier Server-এর সাথে যোগাযোগ করবে।


--------------------------------------------------


## secretKey

Data Type:

TEXT


ব্যাখ্যা:

API Security Secret Key।

API Request Verify করার জন্য ব্যবহার হবে।


--------------------------------------------------


## baseUrl

Data Type:

VARCHAR(255)


ব্যাখ্যা:

Courier API Server Address।

যেখানে Parcel Create এবং Tracking Request পাঠানো হবে।


--------------------------------------------------


## sandboxMode

Data Type:

ENUM


Values:

- yes
- no


ব্যাখ্যা:

API Test Mode অথবা Live Mode নিয়ন্ত্রণ করবে।


yes = Testing Environment

no = Real Order Processing


==================================================


# 3. COURIER CONNECTION MANAGEMENT


## connectionStatus

Data Type:

ENUM


Values:

- connected
- disconnected


ব্যাখ্যা:

Courier API বর্তমানে Connected নাকি Disconnected তা দেখাবে।


--------------------------------------------------


## lastConnectionCheck

Data Type:

DATETIME


ব্যাখ্যা:

সর্বশেষ কখন API Connection Check করা হয়েছে তা সংরক্ষণ করবে।


==================================================


# 4. COURIER SERVICE INFORMATION


## courierId

Data Type:

VARCHAR(50)


Example:

CUR-STEADFAST


ব্যাখ্যা:

ব্যবহৃত Courier Service-এর ইউনিক ID।


--------------------------------------------------


## courierName

Data Type:

VARCHAR(100)


Example:

Steadfast


ব্যাখ্যা:

Courier Company-এর নাম সংরক্ষণ করবে।


--------------------------------------------------


## courierStatus

Data Type:

ENUM


Values:

- active
- inactive


ব্যাখ্যা:

Courier Service চালু অথবা বন্ধ করার জন্য ব্যবহার হবে।


==================================================


# 5. WEBHOOK CONFIGURATION


## webhookUrl

Data Type:

VARCHAR(255)


ব্যাখ্যা:

Courier Server থেকে Automatic Status Update গ্রহণ করার URL।


যেমন:

- Delivered
- Returned
- Cancelled


--------------------------------------------------


## webhookStatus

Data Type:

ENUM


Values:

- active
- inactive


ব্যাখ্যা:

Webhook System চালু আছে কিনা নিয়ন্ত্রণ করবে।


==================================================


# 6. API REQUEST MANAGEMENT


## totalApiRequest

Data Type:

INT


ব্যাখ্যা:

মোট কতগুলো API Request পাঠানো হয়েছে তা সংরক্ষণ করবে।


--------------------------------------------------


## successfulApiRequest

Data Type:

INT


ব্যাখ্যা:

কতগুলো API Request সফল হয়েছে তা সংরক্ষণ করবে।


--------------------------------------------------


## failedApiRequest

Data Type:

INT


ব্যাখ্যা:

কতগুলো API Request ব্যর্থ হয়েছে তা সংরক্ষণ করবে।


==================================================


# 7. SECURITY MANAGEMENT


## encryptionStatus

Data Type:

ENUM


Values:

- enabled
- disabled


ব্যাখ্যা:

API Sensitive Data Encryption চালু আছে কিনা।


--------------------------------------------------


## lastSecurityCheck

Data Type:

DATETIME


ব্যাখ্যা:

সর্বশেষ Security Verification সময়।


==================================================


# 8. ADMIN CONTROL SETTINGS


## canCreateParcel

Data Type:

BOOLEAN


Values:

- true
- false


ব্যাখ্যা:

Admin এই Merchant Account ব্যবহার করে Parcel Create করতে পারবে কিনা।


--------------------------------------------------


## canCancelParcel

Data Type:

BOOLEAN


ব্যাখ্যা:

Admin Parcel Cancel করতে পারবে কিনা।


--------------------------------------------------


## canSyncTracking

Data Type:

BOOLEAN


ব্যাখ্যা:

Courier Tracking Automatic Sync হবে কিনা।


==================================================


# 9. MERCHANT ACCOUNT STATUS


## accountStatus

Data Type:

ENUM


Values:

- active
- inactive
- suspended


ব্যাখ্যা:

Merchant Account-এর বর্তমান অবস্থা।


--------------------------------------------------


## createdAt

Data Type:

TIMESTAMP


ব্যাখ্যা:

Merchant Account তৈরি হওয়ার সময়।


--------------------------------------------------


## updatedAt

Data Type:

TIMESTAMP


ব্যাখ্যা:

সর্বশেষ পরিবর্তনের সময়।


==================================================


# COMPLETE MERCHANT FLOW


Admin Control Panel

↓

Main Merchant Account

↓

Steadfast API Connection

↓

Seller Order Receive

↓

Parcel Create

↓

Pickup Request Send

↓

Tracking Receive

↓

Delivery Complete

↓

Settlement Process


==================================================


# DATABASE RELATION


Merchant

|

|---- Seller Pickup Location

|

|---- Order

|

|---- Parcel

|

|---- Courier Tracking

|

|---- Settlement
                                          
# SELLER PICKUP LOCATION MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose

Seller Pickup Location Management Module-এর কাজ:

- Seller-এর Parcel কোথা থেকে Pickup হবে তা সংরক্ষণ করা।
- একজন Seller-এর একাধিক Pickup Location পরিচালনা করা।
- Courier Rider-এর জন্য সঠিক Pickup Address প্রদান করা।
- Merchant Account-এর মাধ্যমে Courier Pickup Request তৈরি করা।
- Admin Panel থেকে সব Pickup Location Control করা।


# System Rule

- একটি Seller-এর একাধিক Pickup Location থাকতে পারে।
- প্রতিটি Pickup Location-এর আলাদা ID থাকবে।
- সব Pickup Location একটি Main Merchant Account-এর অধীনে কাজ করবে।
- Seller নিজের Pickup Location Manage করতে পারবে।
- Admin সব Seller-এর Pickup Location দেখতে ও নিয়ন্ত্রণ করতে পারবে।


==================================================


# 1. PICKUP LOCATION BASIC INFORMATION


## locationId

Data Type:

VARCHAR(50)


Example:

LOC-0000000001


ব্যাখ্যা:

প্রতিটি Seller Pickup Location-এর ইউনিক ID।

যে Location থেকে Parcel Pickup হবে সেটি শনাক্ত করার জন্য ব্যবহার হবে।


--------------------------------------------------


## merchantId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

এই Pickup Location কোন Main Merchant Account-এর অধীনে কাজ করছে তা নির্দেশ করবে।

সব Seller-এর Location একই Merchant Account-এর সাথে যুক্ত থাকবে।


--------------------------------------------------


## sellerId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Seller-এর Pickup Location সেটি সংরক্ষণ করবে।


--------------------------------------------------


## shopId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

Seller Shop-এর ইউনিক ID।


--------------------------------------------------


## shopName

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Seller-এর দোকানের নাম।


--------------------------------------------------


## sellerName

Data Type:

VARCHAR(100)


ব্যাখ্যা:

যার কাছ থেকে Courier Parcel সংগ্রহ করবে তার নাম।


==================================================


# 2. PICKUP CONTACT INFORMATION


## pickupContactName

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Courier Rider যাকে কল করবে সেই ব্যক্তির নাম।


--------------------------------------------------


## pickupContactPhone

Data Type:

VARCHAR(20)


ব্যাখ্যা:

Courier Rider Pickup-এর আগে এই নাম্বারে যোগাযোগ করবে।


==================================================


# 3. PICKUP ADDRESS INFORMATION


## pickupDistrict

Data Type:

VARCHAR(50)


ব্যাখ্যা:

Seller-এর Pickup District।

Delivery Charge Calculation-এর জন্যও ব্যবহার হবে।


--------------------------------------------------


## pickupUpazilaOrCity

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Pickup Location-এর উপজেলা বা City।


--------------------------------------------------


## pickupArea

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Pickup Area বা Local Area।


--------------------------------------------------


## pickupAddress

Data Type:

TEXT


ব্যাখ্যা:

সম্পূর্ণ Pickup Address।

Courier Rider এই Address ব্যবহার করে Parcel সংগ্রহ করবে।


==================================================


# 4. LOCATION TYPE MANAGEMENT


## locationType

Data Type:

ENUM


Values:

- shop
- warehouse
- branch
- home


ব্যাখ্যা:

Pickup Location-এর ধরন নির্ধারণ করবে।


Example:

Shop

Warehouse


==================================================


# 5. LOCATION STATUS MANAGEMENT


## locationStatus

Data Type:

ENUM


Values:

- active
- inactive
- pending
- suspended


ব্যাখ্যা:

Pickup Location চালু, বন্ধ বা যাচাইয়ের অবস্থায় আছে কিনা।


--------------------------------------------------


## isDefaultLocation

Data Type:

BOOLEAN


Values:

- true
- false


ব্যাখ্যা:

Seller-এর Default Pickup Location কোনটি তা নির্ধারণ করবে।


একজন Seller-এর একাধিক Location থাকলে একটি Default থাকবে।


==================================================


# 6. PICKUP TIME MANAGEMENT


## pickupAvailableTime

Data Type:

VARCHAR(100)


ব্যাখ্যা:

কোন সময় Courier Rider Pickup করতে পারবে।


Example:

10 AM - 6 PM


--------------------------------------------------


## pickupInstruction

Data Type:

TEXT


ব্যাখ্যা:

Seller-এর বিশেষ Pickup নির্দেশনা।


Example:

"Shop এর সামনে এসে কল করবেন"


==================================================


# 7. LOCATION VERIFICATION


## verificationStatus

Data Type:

ENUM


Values:

- pending
- verified
- rejected


ব্যাখ্যা:

Admin Location যাচাই করেছে কিনা।


--------------------------------------------------


## verifiedBy

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Admin Location Verify করেছে।


--------------------------------------------------


## verifiedDate

Data Type:

DATETIME


ব্যাখ্যা:

কখন Location Verify হয়েছে।


==================================================


# 8. ADMIN CONTROL


## adminNote

Data Type:

TEXT


ব্যাখ্যা:

Admin-এর অভ্যন্তরীণ Note।


--------------------------------------------------


## createdAt

Data Type:

TIMESTAMP


ব্যাখ্যা:

Location তৈরি হওয়ার সময়।


--------------------------------------------------


## updatedAt

Data Type:

TIMESTAMP


ব্যাখ্যা:

সর্বশেষ পরিবর্তনের সময়।


==================================================


# PICKUP LOCATION FLOW


Seller Registration

↓

Seller Adds Pickup Location

↓

Admin Verification

↓

Location Active

↓

Customer Order Place

↓

System Seller Location Select

↓

Merchant Account ব্যবহার

↓

Courier Pickup Request

↓

Rider Pickup From Location


==================================================


# PERMISSION CONTROL


## Seller Panel


Seller দেখতে পারবে:

- নিজের Pickup Location
- Pickup Address
- Pickup Contact
- Pickup Status


Seller করতে পারবে:

- নতুন Location Add
- Location Update


Seller পারবে না:

- অন্য Seller Location দেখতে


--------------------------------------------------


## Admin Control Panel


Admin দেখতে পারবে:

- সকল Seller Location
- সকল Pickup Address
- Location Status
- Verification Status


Admin করতে পারবে:

- Approve
- Reject
- Active
- Inactive


==================================================


# DATABASE RELATION


Seller

|

|---- Seller Pickup Location

|

|---- Order

|

|---- Parcel

|

|---- Courier Pickup Request

|

|---- Merchant Account
# COURIER & PICKUP MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose

Courier & Pickup Management Module-এর কাজ:

- Courier API-এর মাধ্যমে Parcel Create করা।
- Seller Location থেকে Pickup Request পাঠানো।
- Pickup Rider Assign করা।
- Delivery Rider Assign করা।
- Parcel Tracking পরিচালনা করা।
- Delivery Status Update রাখা।
- Return Management করা।


# System Rule

- Courier Service হিসেবে Steadfast ব্যবহার হবে।
- Merchant Account শুধুমাত্র ১টি থাকবে।
- সব Seller-এর Parcel একই Merchant API ব্যবহার করবে।
- Pickup Rider এবং Delivery Rider আলাদা হতে পারে।
- Seller শুধু Pickup Rider দেখতে পারবে।
- Delivery Rider Information শুধুমাত্র Admin দেখতে পারবে।


==================================================


# 1. COURIER INFORMATION


## courierId

Data Type:

VARCHAR(50)


Example:

CUR-STEADFAST


ব্যাখ্যা:

Courier Service-এর ইউনিক ID।


--------------------------------------------------


## courierName

Data Type:

VARCHAR(100)


Example:

Steadfast


ব্যাখ্যা:

Courier Company-এর নাম।


--------------------------------------------------


## courierStatus

Data Type:

ENUM


Values:

- active
- inactive


ব্যাখ্যা:

Courier Service চালু বা বন্ধ করার জন্য।


==================================================


# 2. PARCEL COURIER INFORMATION


## parcelId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Parcel-এর Courier Process চলছে তা শনাক্ত করবে।


--------------------------------------------------


## orderId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

এই Parcel কোন Order থেকে এসেছে তা সংযুক্ত করবে।


--------------------------------------------------


## merchantId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Merchant Account ব্যবহার করে Courier Request পাঠানো হয়েছে।


--------------------------------------------------


## locationId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Seller Pickup Location থেকে Parcel সংগ্রহ হবে।


--------------------------------------------------


## customerId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Customer-এর কাছে Parcel যাবে।


==================================================


# 3. COURIER API PARCEL CREATION


## courierRequestId

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Courier API-তে Parcel Create করার Request ID।


--------------------------------------------------


## trackingCode

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Courier Tracking Number।

Customer এবং Admin Parcel Track করার জন্য ব্যবহার করবে।


--------------------------------------------------


## apiResponseStatus

Data Type:

ENUM


Values:

- success
- failed
- pending


ব্যাখ্যা:

Courier API Request সফল হয়েছে কিনা।


==================================================


# 4. PICKUP MANAGEMENT


## pickupId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

Pickup Operation-এর ইউনিক ID।


--------------------------------------------------


## pickupRequestId

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Courier-এর কাছে পাঠানো Pickup Request ID।


--------------------------------------------------


## pickupStatus

Data Type:

ENUM


Values:


- pending
- requested
- accepted
- rider_assigned
- picked_up
- failed
- cancelled


ব্যাখ্যা:

Parcel Pickup-এর বর্তমান অবস্থা।


--------------------------------------------------


## pickupRequestDate

Data Type:

DATE


ব্যাখ্যা:

কখন Pickup Request পাঠানো হয়েছে।


--------------------------------------------------


## pickupDate

Data Type:

DATE


ব্যাখ্যা:

কখন Parcel Pickup হয়েছে।


==================================================


# 5. PICKUP RIDER INFORMATION


## pickupRiderId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

Pickup Rider-এর ID।


--------------------------------------------------


## pickupRiderName

Data Type:

VARCHAR(100)


ব্যাখ্যা:

যে Rider Seller Location থেকে Parcel সংগ্রহ করবে।


--------------------------------------------------


## pickupRiderPhone

Data Type:

VARCHAR(20)


ব্যাখ্যা:

Seller Rider-এর সাথে যোগাযোগ করতে পারবে।


--------------------------------------------------


## pickupAssignedDate

Data Type:

DATETIME


ব্যাখ্যা:

কখন Pickup Rider Assign হয়েছে।


--------------------------------------------------


## pickupCompletedDate

Data Type:

DATETIME


ব্যাখ্যা:

কখন Pickup সম্পন্ন হয়েছে।


==================================================


# 6. DELIVERY MANAGEMENT


## deliveryStatus

Data Type:

ENUM


Values:


- pending
- assigned
- picked_from_hub
- out_for_delivery
- delivered
- failed
- returned


ব্যাখ্যা:

Customer Delivery-এর বর্তমান অবস্থা।


==================================================


# 7. DELIVERY RIDER INFORMATION


## deliveryRiderId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

Delivery Rider-এর ID।


--------------------------------------------------


## deliveryRiderName

Data Type:

VARCHAR(100)


ব্যাখ্যা:

যে Rider Customer-এর কাছে Parcel পৌঁছাবে।


--------------------------------------------------


## deliveryRiderPhone

Data Type:

VARCHAR(20)


ব্যাখ্যা:

Admin Delivery Rider-এর সাথে যোগাযোগ করতে পারবে।


--------------------------------------------------


## deliveryAssignedDate

Data Type:

DATETIME


ব্যাখ্যা:

Delivery Rider Assign হওয়ার সময়।


--------------------------------------------------


## deliveryCompletedDate

Data Type:

DATETIME


ব্যাখ্যা:

Delivery শেষ হওয়ার সময়।


==================================================


# 8. DELIVERY CONFIRMATION


## deliveryDate

Data Type:

DATE


ব্যাখ্যা:

Parcel Delivered হওয়ার তারিখ।


--------------------------------------------------


## deliveryTime

Data Type:

TIME


ব্যাখ্যা:

Delivery হওয়ার সময়।


--------------------------------------------------


## deliveryVerified

Data Type:

ENUM


Values:

- yes
- no


ব্যাখ্যা:

Delivery সফলভাবে Confirm হয়েছে কিনা।


--------------------------------------------------


## receiverName

Data Type:

VARCHAR(100)


ব্যাখ্যা:

যে ব্যক্তি Parcel গ্রহণ করেছে তার নাম।


--------------------------------------------------


## receiverPhone

Data Type:

VARCHAR(20)


ব্যাখ্যা:

Receiver-এর Contact Number।


==================================================


# 9. RETURN MANAGEMENT


## returnStatus

Data Type:

ENUM


Values:

- no_return
- return_requested
- returned


ব্যাখ্যা:

Parcel Return-এর অবস্থা।


--------------------------------------------------


## returnDate

Data Type:

DATE


ব্যাখ্যা:

কখন Return হয়েছে।


--------------------------------------------------


## returnReason

Data Type:

TEXT


ব্যাখ্যা:

Return করার কারণ।


==================================================


# 10. TRACKING HISTORY


## trackingId

Data Type:

INT


ব্যাখ্যা:

প্রতিটি Tracking Update-এর ID।


--------------------------------------------------


## trackingStatus

Data Type:

ENUM


Values:


- pickup_requested
- picked_up
- in_hub
- in_transit
- out_for_delivery
- delivered
- returned
- cancelled


ব্যাখ্যা:

Parcel-এর সম্পূর্ণ Journey History।


--------------------------------------------------


## trackingDate

Data Type:

DATE


ব্যাখ্যা:

Tracking Update-এর তারিখ।


--------------------------------------------------


## trackingTime

Data Type:

TIME


ব্যাখ্যা:

Tracking Update-এর সময়।


--------------------------------------------------


## currentLocation

Data Type:

VARCHAR(150)


ব্যাখ্যা:

বর্তমানে Parcel কোন Hub বা Location-এ আছে।


--------------------------------------------------


## remarks

Data Type:

TEXT


ব্যাখ্যা:

অতিরিক্ত Tracking Note।


==================================================


# 11. SELLER PERMISSION


Seller দেখতে পারবে:

- Pickup Rider Name
- Pickup Rider Phone
- Pickup Status
- Pickup Completed Status


Seller দেখতে পারবে না:

- Delivery Rider Name
- Delivery Rider Phone
- Customer Delivery Route


==================================================


# 12. ADMIN PERMISSION


Admin দেখতে পারবে:


- Pickup Rider Information
- Delivery Rider Information
- Tracking History
- Courier Status
- API Status
- Parcel Status


Admin করতে পারবে:

- Retry Pickup
- Cancel Request
- Update Status
- View Logs


==================================================


# COMPLETE COURIER FLOW


Customer Order

↓

Seller Pickup Location Select

↓

Merchant Account Select

↓

Courier API Request

↓

Pickup Request Create

↓

Pickup Rider Assigned

↓

Seller Pickup

↓

Courier Hub

↓

Delivery Rider Assigned

↓

Customer Delivery

↓

Delivery Confirm

↓

Settlement Process


==================================================


# DATABASE RELATION


Courier

|

|---- Merchant

|

|---- Parcel

|

|---- Pickup Operation

|

|---- Pickup Rider

|

|---- Delivery Rider

|

|---- Tracking History

|

|---- Return Management
# SETTLEMENT MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose

Settlement Management Module-এর কাজ:

- Delivered Parcel-এর Payment Calculation করা।
- Seller Commission Deduction করা।
- Delivery Charge Deduction করা।
- Seller-এর পাওনা টাকা হিসাব করা।
- Seller Payment Request পরিচালনা করা।
- Admin Settlement Control করা।


# System Rule

- Settlement শুধুমাত্র Delivered Order-এর জন্য হবে।
- Parcel Delivered হওয়ার আগে Settlement তৈরি হবে না।
- Commission এবং Delivery Charge Automatic Calculate হবে।
- Seller নিজের Settlement Details দেখতে পারবে।
- Admin সব Settlement Control করতে পারবে।


==================================================


# 1. SETTLEMENT BASIC INFORMATION


## settlementId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

প্রতিটি Settlement-এর ইউনিক ID।

একটি Delivered Parcel-এর জন্য একটি Settlement Record থাকবে।


--------------------------------------------------


## orderId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Order-এর Settlement হচ্ছে তা শনাক্ত করবে।


--------------------------------------------------


## parcelId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Parcel Delivered হওয়ার পরে Settlement তৈরি হয়েছে তা সংরক্ষণ করবে।


--------------------------------------------------


## sellerId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Seller-এর টাকা হিসাব হচ্ছে তা নির্দেশ করবে।


==================================================


# 2. DELIVERY COMPLETE INFORMATION


## deliveryStatus

Data Type:

ENUM


Values:

- delivered
- pending


ব্যাখ্যা:

Parcel Delivered হয়েছে কিনা যাচাই করবে।


--------------------------------------------------


## deliveredDate

Data Type:

DATETIME


ব্যাখ্যা:

কখন Parcel Delivered হয়েছে তা সংরক্ষণ করবে।


--------------------------------------------------


## settlementCreatedDate

Data Type:

DATETIME


ব্যাখ্যা:

কখন Settlement তৈরি হয়েছে।


==================================================


# 3. PRODUCT AMOUNT INFORMATION


## productAmount

Data Type:

DECIMAL


ব্যাখ্যা:

Customer Product-এর জন্য মোট কত টাকা দিয়েছে।


Example:

Product Price = 2000 টাকা


==================================================


# 4. COMMISSION CALCULATION


## commissionType

Data Type:

ENUM


Values:

- percentage
- fixed


ব্যাখ্যা:

Commission Percentage অথবা Fixed Amount হবে কিনা।


--------------------------------------------------


## commissionRate

Data Type:

DECIMAL


ব্যাখ্যা:

Seller অনুযায়ী Commission Rate।

প্রতিটি Seller-এর জন্য আলাদা হতে পারে।


Example:

Seller A = 10%

Seller B = 15%


--------------------------------------------------


## commissionAmount

Data Type:

DECIMAL


ব্যাখ্যা:

Seller-এর কাছ থেকে কাটা Commission Amount।


Example:

2000 টাকার 10%

Commission = 200 টাকা


==================================================


# 5. DELIVERY CHARGE CALCULATION


## deliveryZoneType

Data Type:

ENUM


Values:

- inside_district
- outside_district


ব্যাখ্যা:

Seller এবং Customer একই জেলার কিনা তা নির্ধারণ করবে।


--------------------------------------------------


## deliveryCharge

Data Type:

DECIMAL


ব্যাখ্যা:

Customer-এর Parcel Delivery-এর চার্জ।


Example:


Same District:

60 টাকা


Different District:

120 টাকা


--------------------------------------------------


## deliveryChargeDeducted

Data Type:

DECIMAL


ব্যাখ্যা:

Seller Payment থেকে কত Delivery Charge কাটা হয়েছে।


==================================================


# 6. SELLER PAYMENT CALCULATION


## grossAmount

Data Type:

DECIMAL


ব্যাখ্যা:

কোনো Deduction-এর আগে Seller-এর মোট Amount।


--------------------------------------------------


## totalDeduction

Data Type:

DECIMAL


ব্যাখ্যা:

মোট কত টাকা কাটা হয়েছে।


Calculation:


Commission

+

Delivery Charge


--------------------------------------------------


## sellerPayableAmount

Data Type:

DECIMAL


ব্যাখ্যা:

সব Deduction-এর পরে Seller যে টাকা পাবে।


Calculation:


Product Amount

-

Commission

-

Delivery Charge

=

Seller Payable Amount


==================================================


# 7. SELLER SETTLEMENT STATUS


## settlementStatus

Data Type:

ENUM


Values:

- pending
- approved
- paid
- rejected


ব্যাখ্যা:

Seller Payment-এর বর্তমান অবস্থা।


--------------------------------------------------


## paymentRequestStatus

Data Type:

ENUM


Values:

- not_requested
- requested
- processing
- completed


ব্যাখ্যা:

Seller টাকা তোলার Request করেছে কিনা।


==================================================


# 8. SELLER VIEW INFORMATION


Seller দেখতে পারবে:


- Order ID

- Parcel ID

- Product Amount

- Commission Rate

- Commission Amount

- Delivery Charge

- Total Deduction

- Seller Payable Amount

- Settlement Status


Seller দেখতে পারবে না:


- অন্য Seller-এর Settlement

- Admin Internal Notes


==================================================


# 9. ADMIN CONTROL INFORMATION


## adminNote

Data Type:

TEXT


ব্যাখ্যা:

Admin-এর Internal Note।


--------------------------------------------------


## processedBy

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Admin Settlement Process করেছে।


--------------------------------------------------


## processedDate

Data Type:

DATETIME


ব্যাখ্যা:

কখন Settlement Process হয়েছে।


==================================================


# COMPLETE SETTLEMENT FLOW


Customer Order

↓

Seller Pickup

↓

Customer Delivery Complete

↓

System Settlement Create

↓

Commission Calculate

↓

Delivery Charge Deduct

↓

Seller Payable Amount Calculate

↓

Seller Pending Payment

↓

Seller Payment Request

↓

Admin Approval

↓

Payment Complete


==================================================


# DATABASE RELATION


Settlement

|

|---- Order

|

|---- Parcel

|

|---- Seller

|

|---- Transaction

|

|---- Wallet
 # SELLER WALLET MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose

Seller Wallet Management Module-এর কাজ:

- Seller-এর আয় সংরক্ষণ করা।
- Delivered Order থেকে Seller Payable Amount Wallet-এ যোগ করা।
- Seller Payment Request-এর আগে Balance Management করা।
- Admin থেকে Wallet Monitoring করা।
- সম্পূর্ণ Financial History রাখা।


# System Rule

- প্রতিটি Seller-এর একটি Wallet থাকবে।
- Wallet Balance শুধুমাত্র System Update করবে।
- Seller নিজের Wallet Balance দেখতে পারবে।
- Admin সব Seller Wallet দেখতে পারবে।
- Manual Balance Edit শুধুমাত্র Admin Permission-এর মাধ্যমে হবে।


==================================================


# 1. WALLET BASIC INFORMATION


## walletId

Data Type:

VARCHAR(50)


Example:

WALLET-000000001


ব্যাখ্যা:

প্রতিটি Seller Wallet-এর ইউনিক ID।


--------------------------------------------------


## sellerId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Seller-এর Wallet সেটি সংরক্ষণ করবে।


--------------------------------------------------


## shopId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

Seller Shop-এর সাথে Wallet সংযুক্ত করবে।


==================================================


# 2. BALANCE INFORMATION


## currentBalance

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Seller বর্তমানে কত টাকা Withdraw করতে পারবে তা দেখাবে।


Example:

5000 টাকা


--------------------------------------------------


## pendingBalance

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Delivered Order থেকে আসা কিন্তু এখনো Release না হওয়া টাকা।


Example:

আজ Delivery হয়েছে, Settlement Processing চলছে।


--------------------------------------------------


## totalEarning

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Seller শুরু থেকে মোট কত টাকা আয় করেছে।


--------------------------------------------------


## totalWithdraw

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Seller এখন পর্যন্ত মোট কত টাকা উত্তোলন করেছে।


==================================================


# 3. ORDER SETTLEMENT WALLET ENTRY


## settlementId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Settlement থেকে Wallet Amount এসেছে তা সংযুক্ত করবে।


--------------------------------------------------


## orderId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Order-এর Payment Seller Wallet-এ যোগ হয়েছে।


--------------------------------------------------


## parcelId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Parcel Delivery Complete হওয়ার পরে টাকা যোগ হয়েছে।


--------------------------------------------------


## amountAdded

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

এই Order থেকে Seller Wallet-এ কত টাকা যোগ হয়েছে।


==================================================


# 4. WALLET TRANSACTION TYPE


## transactionType

Data Type:

ENUM


Values:


- order_income
- withdraw
- refund
- adjustment


ব্যাখ্যা:

Wallet-এ টাকা কেন যোগ বা কম হয়েছে তা নির্দেশ করবে।


Example:


order_income:

Order থেকে আয়


withdraw:

টাকা উত্তোলন


==================================================


# 5. WALLET TRANSACTION STATUS


## transactionStatus

Data Type:

ENUM


Values:


- pending
- completed
- cancelled


ব্যাখ্যা:

Wallet Transaction সফল হয়েছে কিনা।


==================================================


# 6. WITHDRAW CONTROL


## withdrawAvailable

Data Type:

BOOLEAN


Values:

- true
- false


ব্যাখ্যা:

Seller বর্তমানে Withdraw করতে পারবে কিনা।


--------------------------------------------------


## minimumWithdrawAmount

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

সর্বনিম্ন কত টাকা হলে Seller Withdraw Request করতে পারবে।


Example:

1000 টাকা


==================================================


# 7. ADMIN CONTROL


## walletStatus

Data Type:

ENUM


Values:


- active
- inactive
- blocked


ব্যাখ্যা:

Admin Seller Wallet চালু বা বন্ধ করতে পারবে।


--------------------------------------------------


## adminNote

Data Type:

TEXT


ব্যাখ্যা:

Admin-এর Internal Note।


==================================================


# 8. DATE INFORMATION


## createdAt

Data Type:

TIMESTAMP


ব্যাখ্যা:

Wallet তৈরি হওয়ার সময়।


--------------------------------------------------


## updatedAt

Data Type:

TIMESTAMP


ব্যাখ্যা:

Wallet সর্বশেষ Update হওয়ার সময়।


==================================================


# WALLET AUTOMATIC FLOW


Customer Order

↓

Product Delivered

↓

Settlement Created

↓

Commission Deduct

↓

Delivery Charge Deduct

↓

Seller Payable Amount Calculate

↓

Seller Wallet Pending Balance

↓

Release To Available Balance

↓

Seller Withdraw Request


==================================================


# SELLER PANEL VIEW


Seller দেখতে পারবে:


- Current Balance

- Pending Balance

- Total Earnings

- Total Withdraw

- Order Wise Income

- Transaction History


Seller করতে পারবে:


- Withdraw Request


Seller করতে পারবে না:


- Balance Edit

- Transaction Delete


==================================================


# ADMIN CONTROL PANEL VIEW


Admin দেখতে পারবে:


- All Seller Wallet

- Balance

- Transaction History

- Withdraw Request

- Wallet Status


Admin করতে পারবে:


- Approve Withdraw

- Reject Withdraw

- Block Wallet


==================================================


# DATABASE RELATION


Seller Wallet

|

|---- Seller

|

|---- Settlement

|

|---- Order

|

|---- Transaction

|

|---- Withdraw Request
# WITHDRAW MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose

Withdraw Management Module-এর কাজ:

- Seller-এর Payment Request গ্রহণ করা।
- Seller Wallet থেকে Withdraw Amount যাচাই করা।
- Admin Approval Process পরিচালনা করা।
- Seller-কে bKash, Nagad অথবা Bank-এর মাধ্যমে Payment করা।
- সকল Withdraw History সংরক্ষণ করা।


# System Rule

- Seller শুধুমাত্র নিজের Wallet Balance থেকে Withdraw Request করতে পারবে।
- Available Balance ছাড়া Withdraw Request করা যাবে না।
- Admin সব Withdraw Request দেখতে পারবে।
- Payment Complete হওয়ার আগে Wallet Balance থেকে টাকা Final Deduct হবে না।
- প্রতিটি Withdraw-এর একটি আলাদা ID থাকবে।


==================================================


# 1. WITHDRAW BASIC INFORMATION


## withdrawId

Data Type:

VARCHAR(50)


Example:

WITHDRAW-000000001


ব্যাখ্যা:

প্রতিটি Withdraw Request-এর ইউনিক ID।

একটি Payment Request শনাক্ত করার জন্য ব্যবহার হবে।


--------------------------------------------------


## sellerId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Seller টাকা Withdraw Request করেছে তা সংরক্ষণ করবে।


--------------------------------------------------


## walletId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Seller Wallet থেকে টাকা নেওয়া হচ্ছে তা সংযুক্ত করবে।


--------------------------------------------------


## requestDate

Data Type:

DATETIME


ব্যাখ্যা:

Seller কখন Withdraw Request করেছে তা সংরক্ষণ করবে।


==================================================


# 2. WITHDRAW AMOUNT INFORMATION


## requestedAmount

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Seller কত টাকা Withdraw Request করেছে।


Example:

5000 টাকা


--------------------------------------------------


## availableBalanceBefore

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Withdraw Request করার আগে Seller Wallet-এ কত টাকা ছিল।


--------------------------------------------------


## availableBalanceAfter

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Withdraw Complete হওয়ার পরে Wallet-এ কত টাকা থাকবে।


==================================================


# 3. PAYMENT METHOD INFORMATION


## paymentMethod

Data Type:

ENUM


Values:


- bKash
- Nagad
- Bank


ব্যাখ্যা:

Seller কোন মাধ্যমে টাকা নিতে চায়।


--------------------------------------------------


## accountName

Data Type:

VARCHAR(100)


ব্যাখ্যা:

যে ব্যক্তির Account-এ টাকা যাবে তার নাম।


--------------------------------------------------


## accountNumber

Data Type:

VARCHAR(50)


ব্যাখ্যা:

bKash/Nagad Number অথবা Bank Account Number।


--------------------------------------------------


## bankName

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Bank Payment হলে Bank-এর নাম।


--------------------------------------------------


## branchName

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Bank Branch-এর নাম।


==================================================


# 4. WITHDRAW STATUS MANAGEMENT


## withdrawStatus

Data Type:

ENUM


Values:


- pending
- approved
- processing
- completed
- rejected
- cancelled


ব্যাখ্যা:

Withdraw Request-এর বর্তমান অবস্থা।


--------------------------------------------------


## rejectionReason

Data Type:

TEXT


ব্যাখ্যা:

Admin Reject করলে কেন Reject করা হয়েছে তার কারণ।


==================================================


# 5. ADMIN PAYMENT PROCESS


## approvedBy

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Admin Withdraw Approve করেছে।


--------------------------------------------------


## approvedDate

Data Type:

DATETIME


ব্যাখ্যা:

কখন Withdraw Approve হয়েছে।


--------------------------------------------------


## processedBy

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Admin Payment Process করেছে।


--------------------------------------------------


## processedDate

Data Type:

DATETIME


ব্যাখ্যা:

কখন Payment সম্পন্ন হয়েছে।


==================================================


# 6. PAYMENT TRANSACTION INFORMATION


## paymentTransactionId

Data Type:

VARCHAR(100)


ব্যাখ্যা:

bKash/Nagad/Bank Transaction ID সংরক্ষণ করবে।


--------------------------------------------------


## paymentProof

Data Type:

TEXT


ব্যাখ্যা:

Admin Payment Proof বা Screenshot Reference সংরক্ষণ করা যাবে।


==================================================


# 7. SECURITY CONTROL


## verificationStatus

Data Type:

ENUM


Values:


- verified
- unverified


ব্যাখ্যা:

Payment Account যাচাই করা হয়েছে কিনা।


--------------------------------------------------


## adminNote

Data Type:

TEXT


ব্যাখ্যা:

Admin-এর Internal Note।


==================================================


# 8. SELLER PANEL VIEW


Seller দেখতে পারবে:


- Withdraw Request History

- Request Amount

- Payment Method

- Withdraw Status

- Payment Date

- Transaction ID


Seller করতে পারবে:


- New Withdraw Request


Seller করতে পারবে না:


- Withdraw Status Change

- Transaction Edit


==================================================


# 9. ADMIN CONTROL PANEL VIEW


Admin দেখতে পারবে:


- All Seller Withdraw Request

- Seller Information

- Wallet Balance

- Payment Method

- Payment History


Admin করতে পারবে:


- Approve

- Reject

- Process Payment

- Add Transaction ID


==================================================


# COMPLETE WITHDRAW FLOW


Seller Wallet

↓

Available Balance

↓

Seller Withdraw Request

↓

Admin Review

↓

Approve

↓

Payment Processing

↓

Payment Complete

↓

Wallet Balance Update

↓

Transaction History Save


==================================================


# DATABASE RELATION


Withdraw

|

|---- Seller

|

|---- Wallet

|

|---- Settlement

|

|---- Transaction

|

|---- Admin
  # TRANSACTION MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose

Transaction Management Module-এর কাজ:

- System-এর সকল আর্থিক লেনদেন সংরক্ষণ করা।
- Order থেকে শুরু করে Seller Payment পর্যন্ত সম্পূর্ণ হিসাব রাখা।
- Commission, Delivery Charge, Settlement এবং Withdraw Track করা।
- Admin Financial Report তৈরি করা।
- প্রতিটি Transaction-এর History সংরক্ষণ করা।


# System Rule

- প্রতিটি Transaction-এর আলাদা Transaction ID থাকবে।
- Transaction Delete করা যাবে না।
- ভুল Transaction হলে Adjustment করা হবে।
- Seller শুধুমাত্র নিজের Transaction দেখতে পারবে।
- Admin সব Transaction দেখতে পারবে।
- সকল Financial Activity এই Module-এ Record হবে।


==================================================


# 1. TRANSACTION BASIC INFORMATION


## transactionId

Data Type:

VARCHAR(50)


Example:

TXN-0000000001


ব্যাখ্যা:

প্রতিটি Financial Transaction-এর ইউনিক ID।

Transaction শনাক্ত করার জন্য ব্যবহার হবে।


--------------------------------------------------


## transactionDate

Data Type:

DATETIME


ব্যাখ্যা:

Transaction কখন তৈরি হয়েছে তা সংরক্ষণ করবে।


--------------------------------------------------


## transactionType

Data Type:

ENUM


Values:


- order_payment
- commission
- delivery_charge
- seller_wallet_credit
- withdraw
- refund
- adjustment


ব্যাখ্যা:

কোন ধরনের টাকা লেনদেন হয়েছে তা নির্দেশ করবে।


==================================================


# 2. ORDER PAYMENT INFORMATION


## orderId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Order-এর জন্য Transaction তৈরি হয়েছে।


--------------------------------------------------


## parcelId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Parcel-এর সাথে Transaction যুক্ত।


--------------------------------------------------


## customerId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Customer Payment করেছে।


--------------------------------------------------


## paymentMethod

Data Type:

ENUM


Values:


- COD
- bKash
- Nagad


ব্যাখ্যা:

Customer কোন মাধ্যমে Payment করেছে।


==================================================


# 3. SELLER INFORMATION


## sellerId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Seller-এর সাথে Transaction সম্পর্কিত।


--------------------------------------------------


## shopId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

Seller Shop-এর ID।


==================================================


# 4. AMOUNT INFORMATION


## transactionAmount

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

এই Transaction-এ কত টাকা লেনদেন হয়েছে।


--------------------------------------------------


## previousBalance

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Transaction হওয়ার আগে Wallet Balance কত ছিল।


--------------------------------------------------


## currentBalance

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Transaction হওয়ার পরে Wallet Balance কত হয়েছে।


==================================================


# 5. COMMISSION TRANSACTION


## commissionRate

Data Type:

DECIMAL(5,2)


ব্যাখ্যা:

Seller-এর জন্য নির্ধারিত Commission Rate।


Example:

10%


--------------------------------------------------


## commissionAmount

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Admin যে Commission কেটেছে তার Amount।


Example:

200 টাকা


==================================================


# 6. DELIVERY CHARGE TRANSACTION


## deliveryZoneType

Data Type:

ENUM


Values:


- inside_district
- outside_district


ব্যাখ্যা:

Seller এবং Customer একই জেলা নাকি আলাদা জেলা তা নির্দেশ করবে।


--------------------------------------------------


## deliveryChargeAmount

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Delivery Charge হিসেবে কাটা Amount।


==================================================


# 7. WALLET TRANSACTION INFORMATION


## walletId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Seller Wallet-এ টাকা যোগ বা কম হয়েছে।


--------------------------------------------------


## walletAction

Data Type:

ENUM


Values:


- credit
- debit


ব্যাখ্যা:

Wallet-এ টাকা যোগ হয়েছে নাকি কমেছে।


--------------------------------------------------


## referenceId

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Transaction কোন Module থেকে এসেছে তা সংযুক্ত করবে।


Example:


Settlement ID

Withdraw ID


==================================================


# 8. WITHDRAW TRANSACTION INFORMATION


## withdrawId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Withdraw Request-এর Payment এটি।


--------------------------------------------------


## paymentTransactionId

Data Type:

VARCHAR(100)


ব্যাখ্যা:

bKash/Nagad/Bank Payment Reference Number।


--------------------------------------------------


## paymentStatus

Data Type:

ENUM


Values:


- pending
- completed
- failed


ব্যাখ্যা:

Payment সফল হয়েছে কিনা।


==================================================


# 9. REFUND TRANSACTION


## refundAmount

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Customer-কে কত টাকা Refund করা হয়েছে।


--------------------------------------------------


## refundReason

Data Type:

TEXT


ব্যাখ্যা:

Refund করার কারণ।


==================================================


# 10. ADMIN ADJUSTMENT


## adjustmentType

Data Type:

ENUM


Values:


- add
- subtract


ব্যাখ্যা:

Admin Manual Balance Adjustment করেছে কিনা।


--------------------------------------------------


## adjustmentReason

Data Type:

TEXT


ব্যাখ্যা:

কেন Adjustment করা হয়েছে।


==================================================


# 11. TRANSACTION STATUS


## transactionStatus

Data Type:

ENUM


Values:


- pending
- completed
- failed
- cancelled


ব্যাখ্যা:

Transaction-এর বর্তমান অবস্থা।


==================================================


# 12. ADMIN CONTROL


## createdBy

Data Type:

VARCHAR(50)


ব্যাখ্যা:

Transaction কে তৈরি করেছে।


--------------------------------------------------


## adminNote

Data Type:

TEXT


ব্যাখ্যা:

Admin-এর Internal Note।


==================================================


# SELLER PANEL VIEW


Seller দেখতে পারবে:


- নিজের Transaction History
- Order Income
- Commission Deduction
- Delivery Charge Deduction
- Wallet Credit
- Withdraw History


Seller দেখতে পারবে না:


- অন্য Seller Transaction
- Admin Internal Adjustment


==================================================


# ADMIN CONTROL PANEL VIEW


Admin দেখতে পারবে:


- সব Transaction
- সব Seller Financial History
- Commission Report
- Delivery Charge Report
- Withdraw Report
- Refund Report


Admin করতে পারবে:


- Transaction Review
- Adjustment Create
- Report Generate


==================================================


# COMPLETE TRANSACTION FLOW


Customer Order

↓

Payment Received

↓

Order Delivered

↓

Commission Calculate

↓

Delivery Charge Deduct

↓

Seller Wallet Credit

↓

Seller Withdraw Request

↓

Admin Payment

↓

Transaction History Save


==================================================


# DATABASE RELATION


Transaction

|

|---- Order

|

|---- Parcel

|

|---- Seller

|

|---- Wallet

|

|---- Settlement

|

|---- Withdraw

|

|---- Refund
 # DELIVERY CHARGE MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose

Delivery Charge Management Module-এর কাজ:

- Customer Delivery অনুযায়ী Delivery Charge নির্ধারণ করা।
- Seller Location এবং Customer Location Compare করা।
- Same District এবং Different District Charge Manage করা।
- Admin Panel থেকে Delivery Charge Control করা।
- Automatic Order Calculation করা।


# System Rule

- Delivery Charge Admin Control করবে।
- Seller Delivery Charge পরিবর্তন করতে পারবে না।
- Customer Order করার সময় Charge Automatically Calculate হবে।
- Delivery Charge Settlement-এর সময় Deduct হবে।
- Future Expansion-এর জন্য Weight Based Charge Support থাকবে।


==================================================


# 1. DELIVERY CHARGE BASIC INFORMATION


## deliveryChargeId

Data Type:

VARCHAR(50)


Example:

DC-000000001


ব্যাখ্যা:

প্রতিটি Delivery Charge Rule-এর ইউনিক ID।


--------------------------------------------------


## courierId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Courier Service-এর জন্য Charge নির্ধারণ করা হয়েছে।


Example:

Steadfast


--------------------------------------------------


## courierName

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Courier Company-এর নাম।


==================================================


# 2. LOCATION BASED CHARGE


## chargeZoneType

Data Type:

ENUM


Values:

- inside_district
- outside_district


ব্যাখ্যা:

Seller এবং Customer Location একই জেলা নাকি ভিন্ন জেলা তা নির্দেশ করবে।


--------------------------------------------------


## pickupDistrict

Data Type:

VARCHAR(50)


ব্যাখ্যা:

Seller যে জেলা থেকে Parcel Pickup হবে।


--------------------------------------------------


## deliveryDistrict

Data Type:

VARCHAR(50)


ব্যাখ্যা:

Customer যে জেলায় Delivery হবে।


--------------------------------------------------


## sameDistrictRule

Data Type:

BOOLEAN


Values:

- true
- false


ব্যাখ্যা:

Seller এবং Customer একই জেলার হলে এই Rule ব্যবহার হবে।


==================================================


# 3. DELIVERY CHARGE AMOUNT


## deliveryChargeAmount

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

এই Rule অনুযায়ী Delivery Charge Amount।


Example:


Same District:

60 টাকা


Different District:

120 টাকা


--------------------------------------------------


## returnChargeAmount

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Parcel Return হলে কত Charge হবে।


==================================================


# 4. WEIGHT BASED CHARGE (Future Support)


## minimumWeight

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

এই Charge Rule কোন Minimum Weight থেকে শুরু হবে।


Example:

0.5 KG


--------------------------------------------------


## maximumWeight

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

এই Rule সর্বোচ্চ কত Weight পর্যন্ত প্রযোজ্য।


--------------------------------------------------


## extraWeightCharge

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

অতিরিক্ত Weight হলে প্রতি KG অতিরিক্ত Charge।


==================================================


# 5. AREA BASED CHARGE (Future Support)


## areaType

Data Type:

ENUM


Values:

- city
- outside_city
- rural


ব্যাখ্যা:

Delivery Area-এর ধরন।


--------------------------------------------------


## areaName

Data Type:

VARCHAR(100)


ব্যাখ্যা:

নির্দিষ্ট Area-এর নাম।


==================================================


# 6. CHARGE STATUS MANAGEMENT


## status

Data Type:

ENUM


Values:

- active
- inactive


ব্যাখ্যা:

Delivery Charge Rule বর্তমানে চালু আছে কিনা।


--------------------------------------------------


## priority

Data Type:

INT


ব্যাখ্যা:

একাধিক Rule থাকলে কোন Rule আগে Apply হবে তা নির্ধারণ করবে।


==================================================


# 7. ADMIN CONTROL INFORMATION


## createdBy

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Admin এই Charge Rule তৈরি করেছে।


--------------------------------------------------


## updatedBy

Data Type:

VARCHAR(50)


ব্যাখ্যা:

সর্বশেষ কোন Admin পরিবর্তন করেছে।


--------------------------------------------------


## adminNote

Data Type:

TEXT


ব্যাখ্যা:

Admin-এর Internal Note।


==================================================


# 8. DATE INFORMATION


## createdAt

Data Type:

TIMESTAMP


ব্যাখ্যা:

Charge Rule তৈরি হওয়ার সময়।


--------------------------------------------------


## updatedAt

Data Type:

TIMESTAMP


ব্যাখ্যা:

সর্বশেষ Update হওয়ার সময়।


==================================================


# AUTOMATIC DELIVERY CHARGE FLOW


Customer Order Place

↓

Customer Delivery Location Check

↓

Seller Pickup Location Check

↓

District Compare

↓

Same District?

↓

YES

↓

Inside District Charge Apply


NO

↓

Outside District Charge Apply


↓

Order Total Update

↓

Settlement-এর সময় Deduct


==================================================


# EXAMPLE LOGIC


Seller Location:

Sylhet


Customer Location:

Sylhet


Result:

Inside District Charge


------------------------------


Seller Location:

Sylhet


Customer Location:

Dhaka


Result:

Outside District Charge


==================================================


# SELLER PANEL VIEW


Seller দেখতে পারবে:


- Order Delivery Charge
- Deducted Delivery Charge
- Settlement Report


Seller পরিবর্তন করতে পারবে না:


- Delivery Charge Rule


==================================================


# ADMIN CONTROL PANEL VIEW


Admin দেখতে পারবে:


- All Delivery Rules
- Courier Wise Charge
- District Wise Charge


Admin করতে পারবে:


- Add Rule
- Edit Rule
- Active/Inactive Rule


==================================================


# DATABASE RELATION


Delivery Charge

|

|---- Courier

|

|---- Order

|

|---- Seller Pickup Location

|

|---- Customer Location

|

|---- Settlement

|

|---- Transaction
step                                                                                              # COUPON & VOUCHER MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose

Coupon & Voucher Management Module-এর কাজ:

- Customer Discount System পরিচালনা করা।
- Free Delivery Offer তৈরি করা।
- Admin Control Panel থেকে Voucher তৈরি ও নিয়ন্ত্রণ করা।
- নির্দিষ্ট Product, Category বা Seller-এর জন্য Discount দেওয়া।
- Coupon Usage Tracking করা।


# System Rule

- Coupon শুধুমাত্র Admin তৈরি করবে।
- Customer Checkout-এর সময় Coupon ব্যবহার করবে।
- Expiry Date শেষ হলে Coupon কাজ করবে না।
- Usage Limit শেষ হলে Coupon ব্যবহার করা যাবে না।
- Admin যেকোনো সময় Coupon Active বা Inactive করতে পারবে।


==================================================


# 1. COUPON BASIC INFORMATION


## couponId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

প্রতিটি Coupon-এর ইউনিক ID।


--------------------------------------------------


## couponCode

Data Type:

VARCHAR(50)


Example:

LAKEZ100


ব্যাখ্যা:

Customer যে Code ব্যবহার করবে।


--------------------------------------------------


## couponName

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Coupon-এর নাম।


Example:

New Year Offer


==================================================


# 2. DISCOUNT INFORMATION


## discountType

Data Type:

ENUM


Values:

- percentage
- fixed_amount
- free_delivery


ব্যাখ্যা:

Discount কী ধরনের হবে তা নির্ধারণ করবে।


--------------------------------------------------


## discountValue

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

কত Discount দেওয়া হবে।


Example:

10%

অথবা

100 টাকা


==================================================


# 3. ELIGIBILITY CONTROL


## minimumOrderAmount

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

কত টাকার Order হলে Coupon ব্যবহার করা যাবে।


Example:

Minimum Order 1000 টাকা


--------------------------------------------------


## maximumDiscountAmount

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Percentage Discount-এর সর্বোচ্চ সীমা।


==================================================


# 4. TARGET CONTROL


## targetType

Data Type:

ENUM


Values:


- all_customer
- specific_customer
- specific_seller
- specific_product
- specific_category


ব্যাখ্যা:

Coupon কার জন্য প্রযোজ্য হবে।


--------------------------------------------------


## sellerId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

নির্দিষ্ট Seller-এর জন্য Coupon হলে Seller ID।


--------------------------------------------------


## productId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

নির্দিষ্ট Product-এর জন্য Coupon হলে Product ID।


--------------------------------------------------


## categoryId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

নির্দিষ্ট Category-এর জন্য Coupon হলে Category ID।


==================================================


# 5. FREE DELIVERY CONTROL


## freeDelivery

Data Type:

BOOLEAN


ব্যাখ্যা:

Coupon Delivery Charge সম্পূর্ণ Free করবে কিনা।


--------------------------------------------------


## deliveryZone

Data Type:

ENUM


Values:


- inside_district
- outside_district
- all


ব্যাখ্যা:

কোন Delivery Zone-এর জন্য Free Delivery প্রযোজ্য হবে।


==================================================


# 6. DATE CONTROL


## startDate

Data Type:

DATETIME


ব্যাখ্যা:

Coupon কখন থেকে চালু হবে।


--------------------------------------------------


## expiryDate

Data Type:

DATETIME


ব্যাখ্যা:

Coupon কখন শেষ হবে।


==================================================


# 7. USAGE CONTROL


## usageLimit

Data Type:

INT


ব্যাখ্যা:

মোট কতবার Coupon ব্যবহার করা যাবে।


--------------------------------------------------


## usedCount

Data Type:

INT


ব্যাখ্যা:

কতবার ব্যবহার হয়েছে।


--------------------------------------------------


## userLimit

Data Type:

INT


ব্যাখ্যা:

একজন Customer কতবার ব্যবহার করতে পারবে।


==================================================


# 8. STATUS MANAGEMENT


## couponStatus

Data Type:

ENUM


Values:


- active
- inactive
- expired


ব্যাখ্যা:

Coupon-এর বর্তমান অবস্থা।


==================================================


# 9. COUPON USAGE HISTORY


## usageId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

প্রতিটি Coupon ব্যবহারের আলাদা ID।


--------------------------------------------------


## customerId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কে Coupon ব্যবহার করেছে।


--------------------------------------------------


## orderId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Order-এ Coupon ব্যবহার হয়েছে।


--------------------------------------------------


## discountAmount

Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

কত টাকা Discount হয়েছে।


==================================================


# ADMIN CONTROL


Admin দেখতে পারবে:

- সব Coupon
- Usage History
- Discount Report


Admin করতে পারবে:

- Create Coupon
- Edit Coupon
- Active/Inactive
- Delete/Disable


==================================================


# DATABASE RELATION


Coupon

|

|---- Customer

|

|---- Order

|

|---- Product

|

|---- Seller

|

|---- Transaction
# ADMIN PERMISSION MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose

Admin Permission Management Module-এর কাজ:

- Control Panel Access Control করা।
- বিভিন্ন Admin User তৈরি করা।
- Role অনুযায়ী Permission দেওয়া।
- নির্দিষ্ট Module Access নিয়ন্ত্রণ করা।
- Admin Activity Track করা।


# System Rule

- একজন Super Admin থাকবে (Owner Account)।
- Super Admin সকল Permission নিয়ন্ত্রণ করবে।
- অন্যান্য Admin প্রয়োজন অনুযায়ী Permission পাবে।
- Permission ছাড়া কোনো Admin কোনো Module Access করতে পারবে না।
- সকল Admin Activity Log হবে।


==================================================


# 1. ADMIN USER INFORMATION


## adminId

Data Type:

VARCHAR(50)


Example:

ADMIN-000000001


ব্যাখ্যা:

প্রতিটি Admin User-এর ইউনিক ID।


--------------------------------------------------


## adminName

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Admin User-এর নাম।


--------------------------------------------------


## adminEmail

Data Type:

VARCHAR(100)


ব্যাখ্যা:

Admin Login Email।


--------------------------------------------------


## adminPhone

Data Type:

VARCHAR(20)


ব্যাখ্যা:

Admin Contact Number।


--------------------------------------------------


## passwordHash

Data Type:

TEXT


ব্যাখ্যা:

Encrypted Password সংরক্ষণ করবে।

Password সরাসরি Database-এ রাখা হবে না।


==================================================


# 2. ADMIN ROLE MANAGEMENT


## roleId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

Admin Role-এর ইউনিক ID।


--------------------------------------------------


## roleName

Data Type:

VARCHAR(100)


Example:

Super Admin

Finance Admin

Order Manager


ব্যাখ্যা:

Admin-এর দায়িত্বের ধরন।


--------------------------------------------------


## roleDescription

Data Type:

TEXT


ব্যাখ্যা:

Role-এর কাজের বিবরণ।


==================================================


# 3. ADMIN ROLE TYPE


## roleType

Data Type:

ENUM


Values:


- super_admin
- finance_admin
- order_admin
- seller_manager
- courier_manager
- support_admin


ব্যাখ্যা:

Admin-এর Access Level নির্ধারণ করবে।


==================================================


# 4. MODULE PERMISSION MANAGEMENT


## permissionId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

প্রতিটি Permission-এর ID।


--------------------------------------------------


## moduleName

Data Type:

VARCHAR(100)


Values:


- Dashboard
- Seller Management
- Customer Management
- Product Management
- Order Management
- Courier Management
- Settlement
- Wallet
- Withdraw
- Transaction
- Coupon
- Reports
- Settings


ব্যাখ্যা:

কোন Module-এর Permission দেওয়া হচ্ছে।


--------------------------------------------------


## canView

Data Type:

BOOLEAN


ব্যাখ্যা:

Admin Module দেখতে পারবে কিনা।


--------------------------------------------------


## canCreate

Data Type:

BOOLEAN


ব্যাখ্যা:

নতুন Data তৈরি করতে পারবে কিনা।


--------------------------------------------------


## canEdit

Data Type:

BOOLEAN


ব্যাখ্যা:

Data পরিবর্তন করতে পারবে কিনা।


--------------------------------------------------


## canDelete

Data Type:

BOOLEAN


ব্যাখ্যা:

Delete Permission আছে কিনা।


==================================================


# 5. ADMIN ROLE PERMISSION TABLE


## rolePermissionId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

Role এবং Permission-এর সম্পর্ক ID।


--------------------------------------------------


## roleId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Role-এর Permission।


--------------------------------------------------


## permissionId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Permission দেওয়া হয়েছে।


==================================================


# 6. ADMIN ACCOUNT STATUS


## accountStatus

Data Type:

ENUM


Values:


- active
- inactive
- blocked


ব্যাখ্যা:

Admin Account চালু বা বন্ধ করার জন্য।


--------------------------------------------------


## lastLoginDate

Data Type:

DATETIME


ব্যাখ্যা:

শেষ Login সময়।


--------------------------------------------------


## loginAttempt

Data Type:

INT


ব্যাখ্যা:

ভুল Password Attempt সংখ্যা।


==================================================


# 7. SECURITY CONTROL


## twoFactorEnabled

Data Type:

BOOLEAN


ব্যাখ্যা:

Two Factor Authentication চালু আছে কিনা।


--------------------------------------------------


## ipRestriction

Data Type:

TEXT


ব্যাখ্যা:

নির্দিষ্ট IP থেকে Login Allow করা যাবে।


--------------------------------------------------


## sessionToken

Data Type:

TEXT


ব্যাখ্যা:

বর্তমান Login Session সংরক্ষণ করবে।


==================================================


# 8. ADMIN ACTIVITY LOG


## activityId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

প্রতিটি Admin Activity-এর ID।


--------------------------------------------------


## adminId

Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Admin কাজটি করেছে।


--------------------------------------------------


## actionType

Data Type:

ENUM


Values:


- login
- create
- update
- delete
- approve
- reject


ব্যাখ্যা:

Admin কী ধরনের কাজ করেছে।


--------------------------------------------------


## moduleName

Data Type:

VARCHAR(100)


ব্যাখ্যা:

কোন Module-এ কাজ করেছে।


--------------------------------------------------


## description

Data Type:

TEXT


ব্যাখ্যা:

কাজের বিস্তারিত বিবরণ।


--------------------------------------------------


## actionDate

Data Type:

DATETIME


ব্যাখ্যা:

কখন কাজটি হয়েছে।


==================================================


# ADMIN PERMISSION EXAMPLE


## Super Admin


Access:

সব Module


Permission:

View ✅

Create ✅

Edit ✅

Delete ✅



------------------------------


## Finance Admin


Access:

Settlement

Wallet

Withdraw

Transaction


Permission:

View ✅

Approve ✅



------------------------------


## Courier Manager


Access:

Courier

Pickup

Delivery


Permission:

View ✅

Update ✅



==================================================


# DATABASE RELATION


Admin User

|

|---- Role

|

|---- Permission

|

|---- Module Access

|

|---- Activity Log

   # NOTIFICATION MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose


Notification Management Module-এর কাজ:


- Customer, Seller এবং Admin-কে গুরুত্বপূর্ণ Update দেওয়া।
- Order Status Notification পরিচালনা করা।
- Pickup এবং Delivery Alert পাঠানো।
- Payment এবং Settlement Update দেওয়া।
- Firebase Push Notification পরিচালনা করা।
- Notification History সংরক্ষণ করা।



# System Rule


- Notification System Automatic হবে।
- Firebase Cloud Messaging (FCM) ব্যবহার করা হবে।
- User অনুযায়ী Notification আলাদা হবে।
- User Notification Read/Unread Status থাকবে।
- Admin প্রয়োজন হলে Manual Notification পাঠাতে পারবে।



==================================================


# 1. NOTIFICATION BASIC INFORMATION



## notificationId


Data Type:

VARCHAR(50)



ব্যাখ্যা:

প্রতিটি Notification-এর ইউনিক ID।




--------------------------------------------------



## receiverId


Data Type:

VARCHAR(50)



ব্যাখ্যা:

যে User Notification পাবে তার ID।


Example:


Customer ID

Seller ID

Admin ID




--------------------------------------------------



## receiverType


Data Type:

ENUM



Values:


- customer

- seller

- admin




ব্যাখ্যা:

Notification কোন User Type-এর জন্য তা নির্ধারণ করবে।



==================================================


# 2. NOTIFICATION CONTENT INFORMATION



## title


Data Type:

VARCHAR(200)



ব্যাখ্যা:

Notification-এর Title।



Example:


"Your Order Has Been Delivered"




--------------------------------------------------



## message


Data Type:

TEXT



ব্যাখ্যা:

Notification-এর বিস্তারিত লেখা।





--------------------------------------------------



## notificationImage


Data Type:

TEXT



ব্যাখ্যা:

প্রয়োজনে Image URL সংরক্ষণ করবে।





==================================================


# 3. NOTIFICATION TYPE MANAGEMENT



## notificationType


Data Type:

ENUM



Values:



- order

- payment

- settlement

- pickup

- delivery

- withdraw

- promotion

- system




ব্যাখ্যা:

Notification কোন বিষয়ের তা নির্ধারণ করবে।





==================================================


# 4. ORDER RELATED INFORMATION



## orderId


Data Type:

VARCHAR(50)



ব্যাখ্যা:

কোন Order-এর জন্য Notification তৈরি হয়েছে।





--------------------------------------------------



## parcelId


Data Type:

VARCHAR(50)



ব্যাখ্যা:

কোন Parcel-এর সাথে Notification সম্পর্কিত।





--------------------------------------------------



## trackingCode


Data Type:

VARCHAR(100)



ব্যাখ্যা:

Customer Tracking Notification-এর জন্য ব্যবহার হবে।





==================================================


# 5. PUSH NOTIFICATION INFORMATION



## deviceToken


Data Type:

TEXT



ব্যাখ্যা:

Firebase Push Notification পাঠানোর জন্য Device Token।





--------------------------------------------------



## platform


Data Type:

ENUM



Values:


- android

- ios

- web




ব্যাখ্যা:

User কোন Device ব্যবহার করছে।





==================================================


# 6. NOTIFICATION STATUS



## readStatus


Data Type:

ENUM



Values:


- unread

- read




ব্যাখ্যা:

User Notification দেখেছে কিনা।





--------------------------------------------------



## readDate


Data Type:

DATETIME



ব্যাখ্যা:

কখন Notification Read হয়েছে।





==================================================


# 7. NOTIFICATION ACTION



## actionType


Data Type:

ENUM



Values:


- open_order

- open_product

- open_payment

- open_wallet

- open_tracking

- none




ব্যাখ্যা:

Notification Click করলে কোন Page খুলবে।





--------------------------------------------------



## actionId


Data Type:

VARCHAR(50)



ব্যাখ্যা:

যে Page বা Data Open হবে তার ID।





Example:


Order ID

Product ID




==================================================


# 8. SELLER NOTIFICATION FLOW



Seller Notification পাবে:



- New Order Received

- Order Cancelled

- Pickup Request Created

- Rider Assigned

- Parcel Picked Up

- Product Delivered

- Commission Deducted

- Wallet Updated

- Withdraw Approved





==================================================


# 9. CUSTOMER NOTIFICATION FLOW



Customer Notification পাবে:



- Order Confirmed

- Seller Processing

- Pickup Completed

- Parcel In Transit

- Out For Delivery

- Delivered

- Return Status

- Payment Update





==================================================


# 10. ADMIN NOTIFICATION FLOW



Admin Notification পাবে:



- New Seller Registration

- New Withdraw Request

- Payment Request

- Courier Error

- Failed Delivery

- Fraud Alert

- System Warning





==================================================


# 11. ADMIN CONTROL



Admin করতে পারবে:



- Send Manual Notification

- Send Promotion Notification

- View Notification History

- Delete Old Notification





==================================================


# 12. DATE INFORMATION



## createdAt


Data Type:


TIMESTAMP



ব্যাখ্যা:


Notification তৈরি হওয়ার সময়।





--------------------------------------------------



## sentAt


Data Type:


DATETIME



ব্যাখ্যা:


Notification কখন পাঠানো হয়েছে।





==================================================


# DATABASE RELATION



Notification


|


|---- Customer


|


|---- Seller


|


|---- Admin


|


|---- Order


|


|---- Parcel


|


|---- Transaction
# REVIEW & RATING MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose


Review & Rating Management Module-এর কাজ:


- Customer Feedback সংগ্রহ করা।
- Product Quality Rating সংরক্ষণ করা।
- Seller Performance Monitor করা।
- Admin Review Approval পরিচালনা করা।
- Product Ranking তৈরি করতে সাহায্য করা।



# System Rule


- শুধুমাত্র Delivered Order-এর Customer Review দিতে পারবে।
- একজন Customer একই Order Product-এর জন্য একবার Review দিতে পারবে।
- Review Edit করা যাবে নির্দিষ্ট সময়ের মধ্যে।
- Admin Review Approve, Hide অথবা Delete করতে পারবে।
- Seller Review Delete করতে পারবে না।



==================================================


# 1. REVIEW BASIC INFORMATION



## reviewId


Data Type:

VARCHAR(50)



ব্যাখ্যা:

প্রতিটি Review-এর ইউনিক ID।




--------------------------------------------------



## customerId


Data Type:

VARCHAR(50)



ব্যাখ্যা:

যে Customer Review দিয়েছে তার ID।





--------------------------------------------------



## sellerId


Data Type:

VARCHAR(50)



ব্যাখ্যা:

যে Seller-এর Product-এর Review দেওয়া হয়েছে।





--------------------------------------------------



## productId


Data Type:

VARCHAR(50)



ব্যাখ্যা:

কোন Product-এর Review তা সংরক্ষণ করবে।





--------------------------------------------------



## orderId


Data Type:

VARCHAR(50)



ব্যাখ্যা:

কোন Order-এর মাধ্যমে Product কেনা হয়েছে তা সংযুক্ত করবে।





==================================================


# 2. RATING INFORMATION



## productRating


Data Type:

INT



Range:


1 - 5



ব্যাখ্যা:

Customer Product Quality অনুযায়ী Star Rating দেবে।





Example:


★★★★★ = 5





--------------------------------------------------



## sellerRating


Data Type:

INT



Range:


1 - 5



ব্যাখ্যা:

Seller-এর Service অনুযায়ী Rating।





--------------------------------------------------



## deliveryRating


Data Type:

INT



Range:


1 - 5



ব্যাখ্যা:

Delivery Experience-এর Rating।





==================================================


# 3. REVIEW CONTENT



## reviewTitle


Data Type:

VARCHAR(200)



ব্যাখ্যা:

Review-এর ছোট Title।





Example:


"Excellent Product"





--------------------------------------------------



## reviewDescription


Data Type:

TEXT



ব্যাখ্যা:

Customer-এর বিস্তারিত মতামত।





--------------------------------------------------



## reviewImages


Data Type:

TEXT



ব্যাখ্যা:

Customer Product-এর ছবি Upload করলে তার URL সংরক্ষণ করবে।





==================================================


# 4. VERIFIED PURCHASE INFORMATION



## verifiedPurchase


Data Type:

BOOLEAN



Values:


true

false



ব্যাখ্যা:

Customer সত্যিই Product কিনেছে কিনা।





--------------------------------------------------



## deliveredOrderId


Data Type:

VARCHAR(50)



ব্যাখ্যা:

Delivered Order থেকে Review এসেছে কিনা।





==================================================


# 5. REVIEW STATUS MANAGEMENT



## reviewStatus


Data Type:

ENUM



Values:



- pending

- approved

- rejected

- hidden





ব্যাখ্যা:

Review বর্তমানে কোন অবস্থায় আছে।





--------------------------------------------------



## rejectionReason


Data Type:

TEXT



ব্যাখ্যা:

Admin Reject করলে কারণ সংরক্ষণ করবে।





==================================================


# 6. SELLER RESPONSE SYSTEM



## sellerReply


Data Type:

TEXT



ব্যাখ্যা:

Seller Customer Review-এর উত্তর দিতে পারবে।





--------------------------------------------------



## replyDate


Data Type:

DATETIME



ব্যাখ্যা:

Seller কখন Reply দিয়েছে।





==================================================


# 7. REVIEW MODERATION



## moderatedBy


Data Type:

VARCHAR(50)



ব্যাখ্যা:

কোন Admin Review Check করেছে।





--------------------------------------------------



## moderatedDate


Data Type:

DATETIME



ব্যাখ্যা:

কখন Review Approve বা Reject হয়েছে।





==================================================


# 8. REVIEW REPORT SYSTEM



## reportId


Data Type:

VARCHAR(50)



ব্যাখ্যা:

Review Report-এর ID।





--------------------------------------------------



## reportedBy


Data Type:

VARCHAR(50)



ব্যাখ্যা:

কে Review Report করেছে।





--------------------------------------------------



## reportReason


Data Type:

TEXT



ব্যাখ্যা:

কেন Review Report করা হয়েছে।





--------------------------------------------------



## reportStatus


Data Type:

ENUM



Values:


- pending

- reviewed

- resolved





ব্যাখ্যা:

Report-এর বর্তমান অবস্থা।





==================================================


# 9. PRODUCT RATING SUMMARY



## averageRating


Data Type:

DECIMAL(3,2)



ব্যাখ্যা:

Product-এর Average Rating।





Example:


4.75





--------------------------------------------------



## totalReviews


Data Type:

INT



ব্যাখ্যা:

মোট কতটি Review হয়েছে।





--------------------------------------------------



## fiveStarCount


Data Type:

INT



ব্যাখ্যা:

৫ Star Review সংখ্যা।





--------------------------------------------------



## oneStarCount


Data Type:

INT



ব্যাখ্যা:

১ Star Review সংখ্যা।





==================================================


# SELLER PANEL VIEW



Seller দেখতে পারবে:



- নিজের Product Review

- Customer Rating

- Customer Comment

- Seller Reply Option

- Product Average Rating





Seller করতে পারবে:



- Reply দিতে





Seller করতে পারবে না:



- Review Delete

- Rating Change





==================================================


# CUSTOMER PANEL VIEW



Customer দেখতে পারবে:



- Product Rating

- Customer Review

- Verified Purchase Badge

- Seller Reply





Customer করতে পারবে:



- Review Submit

- Review Edit

- Report Review





==================================================


# ADMIN CONTROL PANEL VIEW



Admin দেখতে পারবে:



- All Reviews

- Rating Report

- Reported Reviews

- Fake Review Alert





Admin করতে পারবে:



- Approve Review

- Reject Review

- Hide Review

- Remove Fake Review





==================================================


# COMPLETE REVIEW FLOW



Order Complete


↓

Customer Receives Product


↓

Customer Submit Review


↓

System Verify Purchase


↓

Admin Moderation


↓

Review Published


↓

Product Rating Update





==================================================


# DATABASE RELATION



Review


|


|---- Customer


|


|---- Seller


|


|---- Product


|


|---- Order


|


|---- Admin Moderation

# STEP 17: REPORT & ANALYTICS MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose


Report & Analytics Management Module-এর কাজ:


- Business Performance বিশ্লেষণ করা।
- Sales Report তৈরি করা।
- Seller Performance দেখা।
- Product Performance দেখা।
- Financial হিসাব বিশ্লেষণ করা।
- Courier Performance Monitor করা।
- Customer Growth দেখা।
- Admin Dashboard পরিচালনা করা।



# System Rule


- Report শুধুমাত্র System-এর মূল Database থেকে তৈরি হবে।
- Admin যেকোনো Date Range অনুযায়ী Report দেখতে পারবে।
- Hourly, Daily, Weekly, Monthly, Yearly Report পাওয়া যাবে।
- Seller শুধুমাত্র নিজের Report দেখতে পারবে।
- Customer Report দেখতে পারবে না।
- Report Delete করা যাবে না।



==================================================


# 1. REPORT BASIC INFORMATION


## reportId


Data Type:

VARCHAR(50)


ব্যাখ্যা:

প্রতিটি Report-এর ইউনিক ID।



----------------------------------


## reportType


Data Type:

ENUM


Values:


- sales_report
- order_report
- seller_report
- product_report
- financial_report
- courier_report
- customer_report



ব্যাখ্যা:

কোন ধরনের Report তৈরি হয়েছে।



==================================================


# 2. REPORT PERIOD MANAGEMENT


## reportPeriodId


Data Type:

VARCHAR(50)


ব্যাখ্যা:

প্রতিটি Report Period-এর ইউনিক ID।



----------------------------------


## periodType


Data Type:

ENUM


Values:


- hourly
- daily
- weekly
- monthly
- yearly
- custom



ব্যাখ্যা:

কোন সময় অনুযায়ী Report তৈরি হবে।



----------------------------------


## periodStartTime


Data Type:

DATETIME


ব্যাখ্যা:

Report শুরুর সময়।



----------------------------------


## periodEndTime


Data Type:

DATETIME


ব্যাখ্যা:

Report শেষ হওয়ার সময়।



----------------------------------


## autoGenerate


Data Type:

BOOLEAN


ব্যাখ্যা:

System Automatic Report তৈরি করবে কিনা।



----------------------------------


## lastGeneratedTime


Data Type:

DATETIME


ব্যাখ্যা:

সর্বশেষ কখন Report তৈরি হয়েছে।



==================================================


# 3. SALES REPORT MANAGEMENT


## totalSalesAmount


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

নির্দিষ্ট সময়ে মোট Sales Amount।



----------------------------------


## totalOrders


Data Type:

INT


ব্যাখ্যা:

মোট Order সংখ্যা।



----------------------------------


## completedOrders


Data Type:

INT


ব্যাখ্যা:

Delivered হওয়া Order সংখ্যা।



----------------------------------


## cancelledOrders


Data Type:

INT


ব্যাখ্যা:

Cancel হওয়া Order সংখ্যা।



----------------------------------


## returnedOrders


Data Type:

INT


ব্যাখ্যা:

Return হওয়া Order সংখ্যা।



==================================================


# 4. ORDER ANALYTICS


## pendingOrders


Data Type:

INT


ব্যাখ্যা:

বর্তমান Pending Order সংখ্যা।



----------------------------------


## processingOrders


Data Type:

INT


ব্যাখ্যা:

Processing অবস্থায় থাকা Order।



----------------------------------


## deliveryOrders


Data Type:

INT


ব্যাখ্যা:

Delivery অবস্থায় থাকা Order।



----------------------------------


## averageOrderValue


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

প্রতি Order-এর গড় মূল্য।



==================================================


# 5. SELLER PERFORMANCE REPORT


## sellerId


Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Seller-এর Report।



----------------------------------


## totalSellerSales


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Seller মোট কত টাকার Product বিক্রি করেছে।



----------------------------------


## totalProductsSold


Data Type:

INT


ব্যাখ্যা:

Seller কত Product বিক্রি করেছে।



----------------------------------


## sellerCommissionEarned


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Admin কত Commission পেয়েছে।



----------------------------------


## sellerPayableAmount


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Seller কত টাকা পাওয়ার যোগ্য।



----------------------------------


## sellerRatingAverage


Data Type:

DECIMAL(3,2)


ব্যাখ্যা:

Seller-এর Average Rating।



==================================================


# 6. PRODUCT PERFORMANCE REPORT


## productId


Data Type:

VARCHAR(50)


ব্যাখ্যা:

কোন Product-এর Report।



----------------------------------


## totalSoldQuantity


Data Type:

INT


ব্যাখ্যা:

কত Quantity বিক্রি হয়েছে।



----------------------------------


## productRevenue


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Product থেকে মোট Revenue।



----------------------------------


## remainingStock


Data Type:

INT


ব্যাখ্যা:

বর্তমান Stock।



----------------------------------


## bestSellingRank


Data Type:

INT


ব্যাখ্যা:

Product Ranking।



==================================================


# 7. FINANCIAL REPORT


## grossRevenue


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Customer থেকে মোট Collection।



----------------------------------


## totalCommission


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Admin-এর মোট Commission Income।



----------------------------------


## totalDeliveryCharge


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

মোট Delivery Charge Collection।



----------------------------------


## totalSellerPayment


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Seller-কে দেওয়া মোট Payment।



----------------------------------


## totalWithdraw


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Seller মোট কত টাকা Withdraw করেছে।



----------------------------------


## totalRefund


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Customer Refund Amount।



==================================================


# 8. COURIER PERFORMANCE REPORT


## courierId


Data Type:

VARCHAR(50)


ব্যাখ্যা:

Courier Service ID।



----------------------------------


## totalPickup


Data Type:

INT


ব্যাখ্যা:

মোট Pickup সংখ্যা।



----------------------------------


## successfulDelivery


Data Type:

INT


ব্যাখ্যা:

সফল Delivery সংখ্যা।



----------------------------------


## failedDelivery


Data Type:

INT


ব্যাখ্যা:

Failed Delivery সংখ্যা।



----------------------------------


## returnCount


Data Type:

INT


ব্যাখ্যা:

Return সংখ্যা।



----------------------------------


## averageDeliveryTime


Data Type:

VARCHAR(50)


ব্যাখ্যা:

গড় Delivery Time।



==================================================


# 9. CUSTOMER REPORT


## totalCustomers


Data Type:

INT


ব্যাখ্যা:

মোট Customer সংখ্যা।



----------------------------------


## newCustomers


Data Type:

INT


ব্যাখ্যা:

নতুন Customer সংখ্যা।



----------------------------------


## repeatCustomers


Data Type:

INT


ব্যাখ্যা:

পুনরায় Order করা Customer।



----------------------------------


## customerRetentionRate


Data Type:

DECIMAL(5,2)


ব্যাখ্যা:

Customer ধরে রাখার হার।



==================================================


# 10. DASHBOARD SUMMARY


## todaySales


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

আজকের Sales।



----------------------------------


## todayOrders


Data Type:

INT


ব্যাখ্যা:

আজকের Order সংখ্যা।



----------------------------------


## todayCommission


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

আজকের Commission Income।



----------------------------------


## todayDeliveryCharge


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

আজকের Delivery Charge।



----------------------------------


## pendingWithdrawAmount


Data Type:

DECIMAL(10,2)


ব্যাখ্যা:

Pending Seller Withdraw Amount।



==================================================


# 11. REPORT FILTER SYSTEM


Admin Filter করতে পারবে:


- Today

- Yesterday

- Last 7 Days

- Last 30 Days

- This Month

- Last Month

- This Year

- Custom Date Range



==================================================


# 12. EXPORT SYSTEM


Admin করতে পারবে:


- PDF Export

- Excel Export

- CSV Export



==================================================


# SELLER PANEL VIEW


Seller দেখতে পারবে:


- Own Sales Report

- Product Sales

- Commission Report

- Wallet Report

- Order Performance



Seller দেখতে পারবে না:


- Other Seller Report

- Full Business Report



==================================================


# ADMIN CONTROL PANEL VIEW


Admin দেখতে পারবে:


- Complete Business Report

- Sales Analytics

- Financial Analytics

- Seller Analytics

- Product Analytics

- Courier Analytics

- Customer Analytics



==================================================


# DATABASE RELATION


Report


|


|---- Order


|


|---- Seller


|


|---- Product


|


|---- Transaction


|


|---- Courier


|


|---- Customer


|


|---- Settlement
  # STEP 18: AUDIT LOG MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose


Audit Log Management Module-এর কাজ:


- System-এর সকল গুরুত্বপূর্ণ Activity সংরক্ষণ করা।
- Admin এবং User Action Track করা।
- Security Monitoring করা।
- Data Change History রাখা।
- Fraud বা ভুল পরিবর্তন শনাক্ত করা।



# System Rule


- Audit Log Delete করা যাবে না।
- শুধুমাত্র Super Admin দেখতে পারবে।
- প্রতিটি Action Automatic Record হবে।
- পুরাতন Data পরিবর্তন হলেও Previous Value সংরক্ষণ করা হবে।
- Sensitive Financial Activity অবশ্যই Log হবে।



==================================================


# 1. AUDIT LOG BASIC INFORMATION



## auditId


Data Type:

VARCHAR(50)



ব্যাখ্যা:


প্রতিটি Audit Record-এর ইউনিক ID।





----------------------------------


## createdDate


Data Type:

DATETIME



ব্যাখ্যা:


কখন Activity হয়েছে।





==================================================


# 2. USER INFORMATION



## userId


Data Type:

VARCHAR(50)



ব্যাখ্যা:


যে ব্যক্তি Action করেছে তার ID।





----------------------------------



## userType


Data Type:

ENUM



Values:


- admin

- seller

- customer

- system



ব্যাখ্যা:


কোন ধরনের User Action করেছে।





----------------------------------



## userName


Data Type:

VARCHAR(100)



ব্যাখ্যা:


যে User Action করেছে তার নাম।





==================================================


# 3. ACTION INFORMATION



## actionType


Data Type:

ENUM



Values:


- login

- logout

- create

- update

- delete

- approve

- reject

- payment

- refund

- settlement

- withdraw



ব্যাখ্যা:


কী ধরনের কাজ হয়েছে।





----------------------------------



## moduleName


Data Type:

VARCHAR(100)



Values:


- seller_management

- product_management

- order_management

- transaction

- settlement

- courier

- wallet

- settings



ব্যাখ্যা:


কোন Module-এ Action হয়েছে।





----------------------------------



## actionDescription


Data Type:

TEXT



ব্যাখ্যা:


কী কাজ করা হয়েছে তার বিস্তারিত।





==================================================


# 4. DATA CHANGE HISTORY



## tableName


Data Type:

VARCHAR(100)



ব্যাখ্যা:


কোন Database Table পরিবর্তন হয়েছে।





----------------------------------



## recordId


Data Type:

VARCHAR(50)



ব্যাখ্যা:


কোন Record পরিবর্তন হয়েছে।





Example:


Seller ID

Order ID

Product ID





----------------------------------



## oldValue


Data Type:

JSON



ব্যাখ্যা:


পরিবর্তনের আগের Data সংরক্ষণ করবে।





----------------------------------



## newValue


Data Type:

JSON



ব্যাখ্যা:


পরিবর্তনের পরের Data সংরক্ষণ করবে।





==================================================


# 5. SECURITY INFORMATION



## ipAddress


Data Type:

VARCHAR(50)



ব্যাখ্যা:


কোন IP Address থেকে Action হয়েছে।





----------------------------------



## deviceInformation


Data Type:

TEXT



ব্যাখ্যা:


কোন Device থেকে Access হয়েছে।





----------------------------------



## loginSessionId


Data Type:

VARCHAR(100)



ব্যাখ্যা:


Login Session Track করার জন্য।





==================================================


# 6. FINANCIAL AUDIT TRACKING



## transactionId


Data Type:

VARCHAR(50)



ব্যাখ্যা:


কোন Financial Transaction-এর সাথে সম্পর্কিত।





----------------------------------



## amountChanged


Data Type:

DECIMAL(10,2)



ব্যাখ্যা:


কত টাকার পরিবর্তন হয়েছে।





----------------------------------



## approvalStatus


Data Type:

ENUM



Values:


- pending

- approved

- rejected



ব্যাখ্যা:


Financial Approval Status।





==================================================


# 7. ADMIN ACTIVITY EXAMPLE



Example 1:


Admin Seller Approve করেছে।


Record:


User:

Admin


Module:

Seller Management


Action:

Approve





----------------------------------



Example 2:


Admin Commission Rate পরিবর্তন করেছে।


Record:


Old Value:

10%


New Value:

12%





----------------------------------



Example 3:


Admin Seller Payment Approve করেছে।


Record:


Amount:

5000 টাকা





==================================================


# 8. AUTOMATIC SYSTEM LOG



System Automatically Record করবে:


- Failed Login Attempt

- Successful Login

- Password Change

- Permission Change

- API Error

- Payment Failure

- Order Status Change

- Settlement Update





==================================================


# 9. ADMIN VIEW



Super Admin দেখতে পারবে:


- All Activity History

- Admin Activity

- Financial Activity

- Data Change History

- Security Log





অন্যান্য Admin:


শুধুমাত্র Permission অনুযায়ী দেখতে পারবে।





==================================================


# 10. SEARCH & FILTER



Admin Search করতে পারবে:


- Date

- User

- Module

- Action Type

- Record ID





==================================================


# DATABASE RELATION



Audit Log


|


|---- Admin


|


|---- Seller


|


|---- Customer


|


|---- Order


|


|---- Transaction


|


|---- Settlement


|


|---- Product
# STEP 19: SETTINGS MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose


Settings Management Module-এর কাজ:


- পুরো System Configuration নিয়ন্ত্রণ করা।
- Business Rule পরিবর্তন করা।
- Payment Gateway পরিচালনা করা।
- Delivery System নিয়ন্ত্রণ করা।
- Security Settings পরিচালনা করা।
- Admin থেকে Dynamic Change করা।



# System Rule


- শুধুমাত্র Super Admin Settings পরিবর্তন করতে পারবে।
- গুরুত্বপূর্ণ পরিবর্তন Audit Log-এ সংরক্ষণ হবে।
- Sensitive Information Encrypt করা হবে।
- System Restart ছাড়াই Dynamic Settings Update হবে।



==================================================


# 1. GENERAL APPLICATION SETTINGS



## settingId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


প্রতিটি Setting-এর ইউনিক ID।





----------------------------------


## settingKey


Data Type:


VARCHAR(100)



ব্যাখ্যা:


Setting-এর নাম।





Example:


app_name


company_logo





----------------------------------


## settingValue


Data Type:


TEXT



ব্যাখ্যা:


Setting-এর Value সংরক্ষণ করবে।





Example:


Lakez Fashion





----------------------------------


## settingType


Data Type:


ENUM



Values:


- text

- number

- boolean

- image

- json



ব্যাখ্যা:


Setting-এর Data Type।





==================================================


# 2. BUSINESS INFORMATION SETTINGS



## companyName


Data Type:


VARCHAR(150)



ব্যাখ্যা:


Platform-এর নাম।





----------------------------------


## companyEmail


Data Type:


VARCHAR(100)



ব্যাখ্যা:


Official Email।





----------------------------------


## companyPhone


Data Type:


VARCHAR(20)



ব্যাখ্যা:


Contact Number।





----------------------------------


## companyAddress


Data Type:


TEXT



ব্যাখ্যা:


Business Address।





----------------------------------


## companyLogo


Data Type:


TEXT



ব্যাখ্যা:


Logo Image URL।





==================================================


# 3. COMMISSION SETTINGS



## commissionSettingId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


Commission Configuration ID।





----------------------------------


## defaultCommissionRate


Data Type:


DECIMAL(5,2)



ব্যাখ্যা:


Default Seller Commission Percentage।





Example:


10%





----------------------------------


## categoryWiseCommission


Data Type:


JSON



ব্যাখ্যা:


Category অনুযায়ী আলাদা Commission।





Example:


Watch = 8%

Shoes = 10%

Fashion = 12%





----------------------------------


## sellerSpecificCommission


Data Type:


BOOLEAN



ব্যাখ্যা:


নির্দিষ্ট Seller-এর আলাদা Commission দেওয়া যাবে কিনা।





==================================================


# 4. DELIVERY CHARGE SETTINGS



## deliverySettingId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


Delivery Configuration ID।





----------------------------------


## insideDistrictCharge


Data Type:


DECIMAL(10,2)



ব্যাখ্যা:


Seller এবং Customer একই জেলার হলে Delivery Charge।





----------------------------------


## outsideDistrictCharge


Data Type:


DECIMAL(10,2)



ব্যাখ্যা:


ভিন্ন জেলার হলে Delivery Charge।





----------------------------------


## freeDeliveryStatus


Data Type:


BOOLEAN



ব্যাখ্যা:


Free Delivery চালু আছে কিনা।





----------------------------------


## weightBasedCharge


Data Type:


JSON



ব্যাখ্যা:


Weight অনুযায়ী Delivery Charge Rule।





==================================================


# 5. PAYMENT GATEWAY SETTINGS



## paymentSettingId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


Payment Gateway Configuration ID।





----------------------------------


## bkashEnabled


Data Type:


BOOLEAN



ব্যাখ্যা:


bKash চালু আছে কিনা।





----------------------------------


## nagadEnabled


Data Type:


BOOLEAN



ব্যাখ্যা:


Nagad চালু আছে কিনা।





----------------------------------


## bkashApiKey


Data Type:


TEXT



ব্যাখ্যা:


bKash API Key।





----------------------------------


## nagadApiKey


Data Type:


TEXT



ব্যাখ্যা:


Nagad API Key।





----------------------------------


## paymentMode


Data Type:


ENUM



Values:


- sandbox

- live



ব্যাখ্যা:


Testing অথবা Real Payment Mode।





==================================================


# 6. FIREBASE SETTINGS



## firebaseSettingId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


Firebase Configuration ID।





----------------------------------


## firebaseProjectId


Data Type:


VARCHAR(200)



ব্যাখ্যা:


Firebase Project ID।





----------------------------------


## firebaseServerKey


Data Type:


TEXT



ব্যাখ্যা:


Push Notification-এর জন্য Key।





----------------------------------


## firebaseStatus


Data Type:


BOOLEAN



ব্যাখ্যা:


Firebase Active কিনা।





==================================================


# 7. NOTIFICATION SETTINGS



## notificationSettingId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


Notification Configuration ID।





----------------------------------


## orderNotification


Data Type:


BOOLEAN



ব্যাখ্যা:


Order Notification চালু কিনা।
# STEP 20: SECURITY MANAGEMENT DATABASE DESIGN (FINAL VERSION)


# Module Purpose


Security Management Module-এর কাজ:


- System Security নিয়ন্ত্রণ করা।
- Unauthorized Access বন্ধ করা।
- Admin Account নিরাপদ রাখা।
- Login Activity Monitor করা।
- API এবং Session Security পরিচালনা করা।
- Security Threat Detect করা।



# System Rule


- শুধুমাত্র Authorized User Access করতে পারবে।
- Sensitive Data Encrypt করা হবে।
- Failed Login Attempt Track করা হবে।
- Suspicious Activity হলে Alert তৈরি হবে।
- Security Log Delete করা যাবে না।



==================================================


# 1. SECURITY BASIC INFORMATION



## securityId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


প্রতিটি Security Record-এর ইউনিক ID।





----------------------------------


## userId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


যে User-এর Security Information।





----------------------------------


## userType


Data Type:


ENUM



Values:


- admin

- seller

- customer



ব্যাখ্যা:


কোন ধরনের User-এর Security Data।





==================================================


# 2. LOGIN SECURITY MANAGEMENT



## loginId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


প্রতিটি Login Attempt-এর ID।





----------------------------------


## loginEmail


Data Type:


VARCHAR(100)



ব্যাখ্যা:


যে Email দিয়ে Login করা হয়েছে।





----------------------------------


## loginStatus


Data Type:


ENUM



Values:


- success

- failed

- blocked



ব্যাখ্যা:


Login সফল হয়েছে কিনা।





----------------------------------


## loginDateTime


Data Type:


DATETIME



ব্যাখ্যা:


Login-এর সময়।





----------------------------------


## failureReason


Data Type:


TEXT



ব্যাখ্যা:


Failed Login-এর কারণ।





==================================================


# 3. DEVICE MANAGEMENT



## deviceId


Data Type:


VARCHAR(100)



ব্যাখ্যা:


User Device-এর ইউনিক ID।





----------------------------------


## deviceName


Data Type:


VARCHAR(100)



ব্যাখ্যা:


Device-এর নাম।





Example:


Samsung Mobile

Windows Laptop





----------------------------------


## deviceType


Data Type:


ENUM



Values:


- android

- ios

- windows

- web



ব্যাখ্যা:


কোন Device ব্যবহার হচ্ছে।





----------------------------------


## deviceToken


Data Type:


TEXT



ব্যাখ্যা:


Firebase Push Notification-এর Device Token।





----------------------------------


## trustedDevice


Data Type:


BOOLEAN



ব্যাখ্যা:


Device Trusted কিনা।





==================================================


# 4. TWO FACTOR AUTHENTICATION (2FA)



## twoFactorId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


2FA Record ID।





----------------------------------


## twoFactorStatus


Data Type:


BOOLEAN



ব্যাখ্যা:


2FA চালু আছে কিনা।





----------------------------------


## verificationMethod


Data Type:


ENUM



Values:


- sms

- email

- authenticator_app



ব্যাখ্যা:


কোন মাধ্যমে Verification হবে।





----------------------------------


## secretKey


Data Type:


TEXT



ব্যাখ্যা:


Authenticator Security Key।





==================================================


# 5. OTP VERIFICATION MANAGEMENT



## otpId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


প্রতিটি OTP-এর ID।





----------------------------------


## otpCode


Data Type:


VARCHAR(10)



ব্যাখ্যা:


Verification Code।





----------------------------------


## otpPurpose


Data Type:


ENUM



Values:


- login

- password_reset

- withdraw

- payment_verify



ব্যাখ্যা:


OTP কেন পাঠানো হয়েছে।





----------------------------------


## otpExpiryTime


Data Type:


DATETIME



ব্যাখ্যা:


OTP কতক্ষণ কার্যকর থাকবে।





----------------------------------


## otpStatus


Data Type:


ENUM



Values:


- pending

- verified

- expired



ব্যাখ্যা:


OTP-এর অবস্থা।





==================================================


# 6. SESSION MANAGEMENT



## sessionId


Data Type:


VARCHAR(100)



ব্যাখ্যা:


Login Session ID।





----------------------------------


## accessToken


Data Type:


TEXT



ব্যাখ্যা:


User Authentication Token।





----------------------------------


## refreshToken


Data Type:


TEXT



ব্যাখ্যা:


Long Session Maintain করার Token।





----------------------------------


## sessionExpiry


Data Type:


DATETIME



ব্যাখ্যা:


Session কখন শেষ হবে।





----------------------------------


## sessionStatus


Data Type:


ENUM



Values:


- active

- expired

- revoked



ব্যাখ্যা:


Session-এর অবস্থা।





==================================================


# 7. PASSWORD SECURITY



## passwordHistoryId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


Password Change History ID।





----------------------------------


## passwordHash


Data Type:


TEXT



ব্যাখ্যা:


Encrypted Password।





----------------------------------


## changedDate


Data Type:


DATETIME



ব্যাখ্যা:


Password পরিবর্তনের সময়।





----------------------------------


## changedBy


Data Type:


VARCHAR(50)



ব্যাখ্যা:


কে Password পরিবর্তন করেছে।





==================================================


# 8. ACCOUNT LOCK MANAGEMENT



## lockId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


Account Lock Record ID।





----------------------------------


## failedAttemptCount


Data Type:


INT



ব্যাখ্যা:


কতবার ভুল Login হয়েছে।





----------------------------------


## lockStatus


Data Type:


ENUM



Values:


- unlocked

- temporarily_locked

- permanently_locked



ব্যাখ্যা:


Account-এর অবস্থা।





----------------------------------


## unlockDate


Data Type:


DATETIME



ব্যাখ্যা:


কখন Account Unlock হবে।





==================================================


# 9. IP SECURITY MANAGEMENT



## ipId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


IP Record ID।





----------------------------------


## ipAddress


Data Type:


VARCHAR(50)



ব্যাখ্যা:


Login করা IP Address।





----------------------------------


## ipStatus


Data Type:


ENUM



Values:


- allowed

- blocked



ব্যাখ্যা:


IP Allow বা Block।





----------------------------------


## locationInfo


Data Type:


TEXT



ব্যাখ্যা:


IP Location Information।





==================================================


# 10. API SECURITY MANAGEMENT



## apiSecurityId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


API Security Record ID।





----------------------------------


## apiName


Data Type:


VARCHAR(100)



ব্যাখ্যা:


কোন API ব্যবহার হচ্ছে।





----------------------------------


## apiKey


Data Type:


TEXT



ব্যাখ্যা:


API Authentication Key।





----------------------------------


## apiStatus


Data Type:


ENUM



Values:


- active

- inactive

- expired



ব্যাখ্যা:


API-এর অবস্থা।





==================================================


# 11. SECURITY ALERT SYSTEM



## alertId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


Security Alert ID।





----------------------------------


## alertType


Data Type:


ENUM



Values:


- suspicious_login

- multiple_failed_login

- unknown_device

- api_attack

- unauthorized_access



ব্যাখ্যা:


কোন ধরনের Security Alert।





----------------------------------


## alertStatus


Data Type:


ENUM



Values:


- pending

- resolved



ব্যাখ্যা:


Alert সমাধান হয়েছে কিনা।





==================================================


# ADMIN CONTROL


Super Admin দেখতে পারবে:


- Login History

- Failed Login

- Device List

- IP Activity

- Security Alert

- API Security





Super Admin করতে পারবে:


- Block Device

- Block IP

- Reset Session

- Force Logout

- Enable 2FA





==================================================


# DATABASE RELATION



Security


|


|---- Admin


|


|---- Seller


|


|---- Customer


|


|---- Audit Log


|


|---- Notification






----------------------------------


## paymentNotification


Data Type:


BOOLEAN



ব্যাখ্যা:


Payment Notification চালু কিনা।





----------------------------------


## deliveryNotification


Data Type:


BOOLEAN



ব্যাখ্যা:


Delivery Notification চালু কিনা।





----------------------------------


## promotionalNotification


Data Type:


BOOLEAN



ব্যাখ্যা:


Marketing Notification চালু কিনা।





==================================================


# 8. SECURITY SETTINGS



## securitySettingId


Data Type:


VARCHAR(50)



ব্যাখ্যা:


Security Configuration ID।





----------------------------------


## maxLoginAttempt


Data Type:


INT



ব্যাখ্যা:


কতবার ভুল Login করা যাবে।





----------------------------------


## sessionTimeout


Data Type:


INT



ব্যাখ্যা:


কত সময় পর Session Expire হবে।





----------------------------------


## twoFactorRequired


Data Type:


BOOLEAN



ব্যাখ্যা:


Admin-এর জন্য 2FA বাধ্যতামূলক কিনা।





----------------------------------


## passwordExpiryDays


Data Type:


INT



ব্যাখ্যা:


কতদিন পর Password Change করতে হবে।





==================================================


# 9. MAINTENANCE SETTINGS



## maintenanceMode


Data Type:


BOOLEAN



ব্যাখ্যা:


System Maintenance Mode চালু/বন্ধ।





----------------------------------


## maintenanceMessage


Data Type:


TEXT



ব্যাখ্যা:


Maintenance Message।





==================================================


# 10. SYSTEM CONTROL SETTINGS



## currency


Data Type:


VARCHAR(20)



ব্যাখ্যা:


System Currency।





Example:


BDT





----------------------------------


## timezone


Data Type:


VARCHAR(50)



ব্যাখ্যা:


System Timezone।





Example:


Asia/Dhaka





----------------------------------


## language


Data Type:


VARCHAR(20)



ব্যাখ্যা:


Default Language।





==================================================


# ADMIN CONTROL



Super Admin করতে পারবে:


- Add Setting

- Update Setting

- Enable/Disable Feature

- Change Commission

- Change Delivery Rule

- Configure Payment Gateway

- Manage Security





==================================================


# DATABASE RELATION



Settings


|


|---- Commission


|


|---- Delivery Charge


|


|---- Payment Gateway


|


|---- Firebase


|


|---- Notification


|


|---- Security


                                                                                                                                                                                                                                         
