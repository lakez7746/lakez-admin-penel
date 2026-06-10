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
# ORDER MANAGEMENT DATABASE DESIGN

## Order Basic Information

orderId:
ORD-0000000001

orderDate

orderTime

orderSource

Available Values:

* android
* ios
* web

---

## Customer Information

customerId

customerName

customerPhone

customerEmail

---

## Seller Information

sellerId

shopId

shopName

sellerDistrict

commissionRate

---

## Product Information

productId

productName

sku

variant

quantity

unitPrice

subtotal

---

## Delivery Address

receiverName

receiverPhone

district

upazilaOrCity

area

fullAddress

---

## Delivery Charge Information

deliveryZoneType

Available Values:

* inside_district
* outside_district

deliveryCharge

freeDeliveryApplied

couponApplied

couponCode

discountAmount

---

## Order Amount

productAmount

deliveryAmount

discountAmount

totalAmount

finalPayableAmount

---

## Payment Information

paymentMethod

Available Values:

* cod
* bkash
* nagad

paymentStatus

Available Values:

* unpaid
* paid
* refunded

paymentTransactionId

---

## Courier Information

courierName

courierOrderId

trackingCode

pickupRequestId

---

## Order Status

orderStatus

Available Values:

* pending
* confirmed
* pickup_requested
* picked_up
* in_transit
* delivered
* cancelled
* returned
* refunded

statusUpdatedDate

statusUpdatedBy

---

## Settlement Information

settlementStatus

Available Values:

* not_ready
* settlement_pending
* payment_ready
* settled

settlementDate

settlementId

---

## Commission Information

commissionType

Available Values:

* percentage
* fixed

commissionRate

commissionAmount

sellerReceivableAmount

adminCommissionAmount

---

## Wallet Information

walletProcessed

walletProcessedDate

sellerWalletTransactionId

---

## Return Information

returnRequested

returnReason

returnDate

returnStatus

---

## Refund Information

refundRequested

refundAmount

refundDate

refundStatus

---

## Admin Controls

adminNotes

fraudFlag

manualReviewRequired

priorityOrder

---

# ORDER STATUS FLOW

Pending
↓
Confirmed
↓
Pickup Requested
↓
Picked Up
↓
In Transit
↓
Delivered
↓
Settlement Pending
↓
Payment Ready
↓
Withdraw Requested
↓
Paid

---

# DELIVERY CHARGE LOGIC

Rule 1:

Seller District = Customer District

Result:

deliveryZoneType = inside_district

Apply Inside District Delivery Charge

---

Rule 2:

Seller District ≠ Customer District

Result:

deliveryZoneType = outside_district

Apply Outside District Delivery Charge

---

# FREE DELIVERY LOGIC

If:

freeDeliveryApplied = true

Then:

deliveryCharge = 0

---

# SETTLEMENT LOGIC

When Order Status = Delivered

↓

Admin Reviews Delivery

↓

Admin Clicks Submit Settlement

↓

System Calculates Commission

↓

Commission Deducted

↓

Seller Wallet Credited

↓

Settlement Status = Payment Ready

---

# ADMIN CONTROL PERMISSIONS

Admin Can:

* View Orders
* Confirm Orders
* Cancel Orders
* Review Fraud Orders
* Manage Delivery Charges
* Monitor Courier Status
* Submit Settlement
* View Commission Details
* View Seller Receivable Amount
* Review Returns
* Review Refunds
 # SETTLEMENT MANAGEMENT DATABASE DESIGN

## Settlement Basic Information

settlementId:
SET-0000000001

orderId

sellerId

shopId

customerId

createdDate

createdTime

---

## Order Information

orderAmount

deliveryCharge

discountAmount

finalOrderAmount

paymentMethod

courierName

trackingCode

deliveryDate

---

## Commission Information

commissionType

Available Values:

* percentage
* fixed

commissionRate

commissionAmount

adminReceivableAmount

sellerReceivableAmount

---

## Settlement Status

settlementStatus

Available Values:

* pending
* under_review
* approved
* rejected
* payment_ready
* completed

statusUpdatedDate

statusUpdatedBy

---

## Settlement Approval

approvedBy

approvalDate

approvalNotes

rejectedBy

rejectionDate

rejectionReason

---

## Wallet Processing

walletProcessed

Available Values:

* yes
* no

walletProcessedDate

sellerWalletTransactionId

---

## Seller Wallet Impact

previousAvailableBalance

creditedAmount

newAvailableBalance

---

## Admin Revenue Impact

previousAdminRevenue

commissionAdded

newAdminRevenue

---

## Courier Verification

courierDeliveryVerified

Available Values:

* yes
* no

verificationDate

verifiedBy

---

## Settlement Security

fraudCheckStatus

Available Values:

* pending
* passed
* flagged

manualReviewRequired

riskLevel

Available Values:

* low
* medium
* high

---

## Settlement Notes

adminNotes

sellerNotes

systemNotes

---

# SETTLEMENT FLOW

Order Status

Delivered

↓

Settlement Created

↓

Settlement Status = Pending

↓

Admin Reviews Delivery

↓

Courier Verification

↓

Commission Calculation

↓

Admin Clicks Submit Settlement

↓

Commission Deducted

↓

Seller Wallet Credited

↓

Settlement Status = Payment Ready

↓

Seller Can Request Withdraw

↓

Settlement Status = Completed

---

# COMMISSION CALCULATION LOGIC

Example:

Order Amount = 1500

Commission Rate = 10%

Commission Amount = 150

Seller Receivable Amount = 1350

Admin Receivable Amount = 150

---

# WALLET UPDATE LOGIC

Before Settlement

Seller Available Balance = 5000

Settlement Amount = 1350

After Settlement

Seller Available Balance = 6350

---

# ADMIN CONTROL PERMISSIONS

Admin Can:

* View Settlements
* Approve Settlements
* Reject Settlements
* Recalculate Commission
* Verify Courier Delivery
* Credit Seller Wallet
* View Settlement History
* View Seller Earnings
* View Admin Revenue
* Flag Suspicious Settlements
 # WALLET MANAGEMENT DATABASE DESIGN

## Wallet Basic Information

walletId:
WLT-0000000001

sellerId

shopId

walletCreatedDate

lastUpdatedDate

---

## Available Balance

availableBalance

Description:

Seller can withdraw this amount

---

## Pending Balance

pendingBalance

Description:

Delivered orders waiting for settlement

---

## Total Earnings

totalEarnings

Description:

Lifetime seller earnings

---

## Total Withdrawn

totalWithdrawn

Description:

Total amount already withdrawn

---

## Total Commission Paid

totalCommissionPaid

Description:

Total commission collected by admin

---

## Total Orders Revenue

totalOrderRevenue

Description:

Total sales amount

---

## Last Settlement Information

lastSettlementId

lastSettlementDate

lastSettlementAmount

---

## Last Withdraw Information

lastWithdrawId

lastWithdrawDate

lastWithdrawAmount

---

## Wallet Status

walletStatus

Available Values:

* active
* suspended
* locked

---

## Wallet Security

suspiciousActivity

Available Values:

* yes
* no

manualReviewRequired

---

## Wallet Statistics

totalSettlements

totalWithdrawRequests

successfulWithdraws

rejectedWithdraws

---

## Admin Controls

canWithdraw

canReceiveSettlement

adminNotes

---

# WALLET BALANCE FLOW

Order Delivered

↓

Settlement Pending

↓

Admin Approves Settlement

↓

Commission Deducted

↓

Seller Wallet Available Balance Increased

↓

Seller Can Request Withdraw

---

# WALLET EXAMPLE

Before Settlement

Available Balance = 5000

Settlement Amount = 1350

After Settlement

Available Balance = 6350

---

# ADMIN CONTROL PERMISSIONS

Admin Can:

* View Wallet
* Lock Wallet
* Suspend Wallet
* Enable Withdraw
* Disable Withdraw
* View Wallet History
* View Settlement History
* View Earnings History
# WITHDRAW MANAGEMENT DATABASE DESIGN

## Withdraw Basic Information

withdrawId:
WDR-0000000001

sellerId

shopId

walletId

requestDate

requestTime

---

## Seller Information

sellerName

shopName

phoneNumber

---

## Withdraw Amount Information

requestedAmount

availableBalanceAtRequest

withdrawCharge

finalPayableAmount

---

## Payment Method

paymentMethod

Available Values:

* bkash
* nagad
* bank

accountName

accountNumber

bankName

branchName

---

## Withdraw Status

withdrawStatus

Available Values:

* pending
* under_review
* approved
* rejected
* processing
* paid

statusUpdatedDate

statusUpdatedBy

---

## Admin Approval

approvedBy

approvalDate

approvalNotes

---

## Rejection Information

rejectedBy

rejectionDate

rejectionReason

---

## Payment Information

paymentDate

paymentTransactionId

paymentReference

paidAmount

---

## Wallet Impact

walletBalanceBefore

walletBalanceAfter

---

## Security Check

fraudCheckStatus

Available Values:

* pending
* passed
* flagged

manualReviewRequired

---

## Withdraw Statistics

withdrawCount

totalWithdrawnAmount

---

## Notes

sellerNotes

adminNotes

systemNotes

---

# WITHDRAW FLOW

Seller Available Balance

↓

Seller Creates Withdraw Request

↓

Withdraw Status = Pending

↓

Admin Reviews Request

↓

Approve / Reject

↓

If Approved

↓

Payment Processing

↓

Admin Sends Payment

↓

Withdraw Status = Paid

↓

Wallet Balance Updated

---

# EXAMPLE

Available Balance = 5000

Withdraw Request = 3000

After Payment

Available Balance = 2000

Withdraw Status = Paid

---

# ADMIN CONTROL PERMISSIONS

Admin Can:

* View Withdraw Requests
* Approve Withdraw Requests
* Reject Withdraw Requests
* Mark Payment As Paid
* View Withdraw History
* View Seller Payment Details
* View Transaction References
* Flag Suspicious Requests

---

# SELLER RULES

Seller Can Request Withdraw Only If:

availableBalance > minimumWithdrawAmount

walletStatus = active

canWithdraw = true
 # TRANSACTION MANAGEMENT DATABASE DESIGN

## Transaction Basic Information

transactionId:
TRX-0000000001

transactionDate

transactionTime

---

## Related Information

orderId

settlementId

withdrawId

refundId

sellerId

customerId

shopId

---

## Transaction Type

transactionType

Available Values:

* order_payment
* settlement_credit
* commission_deduction
* withdraw_request
* withdraw_payment
* refund
* delivery_charge
* coupon_discount
* adjustment

---

## Transaction Direction

transactionDirection

Available Values:

* credit
* debit

---

## Transaction Amount

amount

currency

Available Values:

* BDT

---

## Payment Information

paymentMethod

Available Values:

* cod
* bkash
* nagad
* bank

paymentReference

gatewayTransactionId

---

## Wallet Information

walletId

walletBalanceBefore

walletBalanceAfter

---

## Commission Information

commissionRate

commissionAmount

adminRevenueAmount

sellerReceivableAmount

---

## Transaction Status

transactionStatus

Available Values:

* pending
* processing
* completed
* failed
* cancelled
* refunded

statusUpdatedDate

statusUpdatedBy

---

## Refund Information

refundAmount

refundReason

refundDate

---

## Delivery Information

deliveryCharge

deliveryZoneType

Available Values:

* inside_district
* outside_district

---

## Security Information

fraudCheckStatus

Available Values:

* pending
* passed
* flagged

manualReviewRequired

riskLevel

Available Values:

* low
* medium
* high

---

## Audit Information

createdBy

updatedBy

createdDate

updatedDate

ipAddress

deviceInfo

---

## Notes

sellerNotes

adminNotes

systemNotes

---

# TRANSACTION FLOW EXAMPLES

Example 1

Customer Order Amount = 1500

Transaction Type = order_payment

Transaction Direction = credit

Amount = 1500

Status = completed

---

Example 2

Settlement Created

Commission = 150

Seller Receivable = 1350

Transaction Type = settlement_credit

Transaction Direction = credit

Amount = 1350

Status = completed

---

Example 3

Seller Withdraw = 3000

Transaction Type = withdraw_payment

Transaction Direction = debit

Amount = 3000

Status = completed

---

# ADMIN CONTROL PERMISSIONS

Admin Can:

* View All Transactions
* Search Transactions
* Filter Transactions
* View Transaction History
* Export Transaction Reports
* View Commission Reports
* View Settlement Reports
* View Withdraw Reports
* View Refund Reports
* Flag Suspicious Transactions

---

# REPORTING SUPPORT

Generate Reports By:

* Date
* Seller
* Customer
* Order
* Transaction Type
* Payment Method
* Status
* District
* Courier
# DELIVERY CHARGE MANAGEMENT DATABASE DESIGN

## Delivery Charge Basic Information

deliveryChargeId:
DCH-0000000001

createdDate

lastUpdatedDate

updatedBy

---

## Inside District Delivery Charge

insideDistrictCharge

Description:

Seller District = Customer District

Example:

80

---

## Outside District Delivery Charge

outsideDistrictCharge

Description:

Seller District ≠ Customer District

Example:

130

---

## Charge Status

chargeStatus

Available Values:

* active
* inactive

---

## Free Delivery Settings

freeDeliveryEnabled

Available Values:

* yes
* no

---

## Free Delivery Rules

freeDeliveryType

Available Values:

* all_orders
* minimum_order_amount
* coupon_based
* campaign_based

minimumOrderAmount

---

## Coupon Delivery Discount

couponDeliveryDiscountEnabled

Available Values:

* yes
* no

deliveryDiscountAmount

deliveryDiscountType

Available Values:

* fixed
* percentage

---

## Campaign Delivery Discount

campaignDeliveryEnabled

Available Values:

* yes
* no

campaignName

campaignStartDate

campaignEndDate

campaignDiscountAmount

---

## Delivery Zone Information

deliveryZoneType

Available Values:

* inside_district
* outside_district

---

## Statistics

totalInsideDistrictOrders

totalOutsideDistrictOrders

totalFreeDeliveryOrders

totalDeliveryRevenue

---

## Admin Controls

canEditDeliveryCharge

canEnableFreeDelivery

canDisableFreeDelivery

adminNotes

---

# DELIVERY CHARGE LOGIC

Rule 1

Seller District = Customer District

Result

deliveryZoneType = inside_district

deliveryCharge = insideDistrictCharge

---

Rule 2

Seller District ≠ Customer District

Result

deliveryZoneType = outside_district

deliveryCharge = outsideDistrictCharge

---

# FREE DELIVERY LOGIC

If:

freeDeliveryEnabled = yes

Then:

deliveryCharge = 0

---

# MINIMUM ORDER FREE DELIVERY

Example

minimumOrderAmount = 2000

If Order Amount ≥ 2000

Then

deliveryCharge = 0

---

# COUPON DELIVERY DISCOUNT LOGIC

Example

Delivery Charge = 130

Coupon Discount = 50

Customer Pays = 80

---

# ADMIN CONTROL PERMISSIONS

Admin Can:

* Change Inside District Charge
* Change Outside District Charge
* Enable Free Delivery
* Disable Free Delivery
* Create Delivery Campaign
* Edit Delivery Campaign
* View Delivery Revenue
* View Delivery Statistics
  # PICKUP MANAGEMENT DATABASE DESIGN

## Pickup Basic Information

pickupId:
PCK-0000000001

orderId

sellerId

shopId

pickupRequestDate

pickupRequestTime

---

## Seller Information

sellerName

shopName

pickupContactName

pickupPhone

---

## Pickup Address Information

district

upazilaOrCity

area

fullAddress

---

## Customer Information

customerId

customerName

customerPhone

---

## Courier Information

courierName

Available Values:

* steadfast

courierPickupId

trackingCode

---

## Parcel Information

totalProducts

totalQuantity

parcelWeight

parcelType

Available Values:

* fashion
* watch
* shoes
* accessories

---

## Pickup Status

pickupStatus

Available Values:

* pending
* requested
* accepted
* rider_assigned
* picked_up
* failed
* cancelled

statusUpdatedDate

statusUpdatedBy

---

## Rider Information

riderName

riderPhone

riderId

assignedDate

pickupDate

---

## Pickup Verification

pickupVerified

Available Values:

* yes
* no

verifiedBy

verificationDate

---

## Failure Information

failureReason

failedDate

---

## Security Information

manualReviewRequired

fraudFlag

---

## Notes

sellerNotes

adminNotes

systemNotes

---

# AUTOMATIC PICKUP FLOW

Customer Places Order

↓

Order Confirmed

↓

System Reads Seller Pickup Address

↓

System Creates Pickup Request

↓

Pickup Status = Requested

↓

Steadfast API Receives Request

↓

Rider Assigned

↓

Parcel Picked Up

↓

Pickup Status = Picked Up

↓

Order Status = In Transit

---

# PICKUP RETRY LOGIC

If Pickup Failed

↓

Pickup Status = Failed

↓

System Allows Re-Request Pickup

↓

New Pickup Request Created

---

# MULTI-SELLER LOGIC

If 3 Different Sellers Receive Orders

Seller A → Pickup Request A

Seller B → Pickup Request B

Seller C → Pickup Request C

System Creates Separate Pickup Requests Automatically

---

# ADMIN CONTROL PERMISSIONS

Admin Can:

* View Pickup Requests
* Monitor Pickup Status
* Retry Failed Pickup
* Cancel Pickup Request
* View Rider Information
* View Pickup History
* View Courier Tracking
* Flag Suspicious Pickup Activity
                                                                                                                                                                                                                                             
