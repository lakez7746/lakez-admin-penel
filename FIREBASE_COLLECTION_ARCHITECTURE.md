# FIREBASE COLLECTION ARCHITECTURE
# LAKEZ Marketplace — সম্পূর্ণ সংশোধিত ও আপডেটেড ভার্সন
 
=================================================
# সংশোধনের সারসংক্ষেপ
=================================================
 
নতুন যোগ হয়েছে:
- categories
- brands
- campaigns
- banners
- return_requests
- merchants
- seller_kyc
- delivery_zones
- sessions
- device_logs
- seller_follows
- fraud_alerts
- coupon_usage
- webhook_logs
সংশোধন হয়েছে:
- sellers (অসম্পূর্ণ fields যোগ হয়েছে)
- customers (অসম্পূর্ণ fields যোগ হয়েছে)
- orders (product details যোগ হয়েছে)
- products (variants structure স্পষ্ট হয়েছে)
- parcels (Steadfast-specific fields যোগ হয়েছে)
- wallets (duplication সমাধান হয়েছে)
- notifications (receiverType যোগ হয়েছে)
- messages (fraud detection fields যোগ হয়েছে)
- coupons (voucher fields যোগ হয়েছে)
=================================================
# 1. admins
=================================================
 
admins
    └── adminId (ADMIN-000000001)
          ├── adminName
          ├── adminEmail
          ├── adminPhone
          ├── passwordHash               ← Firebase Auth পরিচালনা করে
          ├── role
          │     values:
          │       super_admin
          │       finance_admin
          │       order_admin
          │       seller_manager
          │       courier_manager
          │       support_admin
          ├── permissions                ← JSON: module wise canView/canCreate/canEdit/canDelete
          ├── twoFactorEnabled
          ├── ipRestriction
          ├── sessionToken
          ├── accountStatus
          │     values: active / inactive / blocked
          ├── lastLoginDate
          ├── loginAttempt
          ├── createdAt
          └── updatedAt
 
=================================================
# 2. sellers
=================================================
 
sellers
    └── sellerId (SLR-0000000001)
          │
          ├── ── BASIC INFORMATION ──
          ├── shopId (SHP-0000000001)
          ├── shopName
          ├── ownerName
          ├── email
          ├── phoneNumber
          ├── profileImage
          ├── joinDate
          ├── lastLogin
          │
          ├── ── SHOP INFORMATION ──
          ├── shopLogo
          ├── shopBanner
          ├── shopDescription
          ├── shopAddress
          ├── district
          ├── upazila
          ├── union
          ├── area
          ├── postalCode
          │
          ├── ── SELLER STATUS ──
          ├── status
          │     values: active / inactive / suspended / banned
          ├── statusReason
          ├── statusUpdatedBy
          ├── statusUpdatedDate
          │
          ├── ── KYC REFERENCE ──
          ├── kycStatus
          │     values: pending / approved / rejected
          ├── kycId                      ← seller_kyc collection-এর reference
          │
          ├── ── COMMISSION ──
          ├── commissionType
          │     values: percentage / fixed
          ├── commissionRate
          │     examples: 5 / 8 / 10 / 12 / 14 / 16 / 18 / 20
          │
          ├── ── PAYMENT INFORMATION ──
          ├── bkashNumber
          ├── nagadNumber
          ├── bankAccountName
          ├── bankAccountNumber
          ├── bankName
          ├── branchName
          │
          ├── ── PICKUP INFORMATION ──
          ├── pickupContactName
          ├── pickupContactPhone
          ├── pickupDistrict
          ├── pickupUpazila
          ├── pickupUnion
          ├── pickupArea
          ├── pickupAddress
          ├── pickupLatitude
          ├── pickupLongitude
          │
          ├── ── BUSINESS STATISTICS ──
          ├── totalProducts
          ├── totalOrders
          ├── totalDeliveredOrders
          ├── totalCancelledOrders
          ├── totalReturnedOrders
          ├── totalSalesAmount
          ├── averageRating
          │
          ├── ── ACCOUNT CONTROL ──
          ├── canAddProduct
          ├── canWithdraw
          ├── canReceiveOrders
          ├── canCreateVoucher           ← নতুন: Seller voucher তৈরি করতে পারবে কিনা
          ├── adminNotes
          │
          └── ── DATES ──
              ├── createdAt
              └── updatedAt
 
=================================================
# 3. seller_kyc
=================================================
 
seller_kyc
    └── kycId
          ├── sellerId
          ├── shopId
          │
          ├── ── NID INFORMATION ──
          ├── nidNumber
          ├── nidFrontImage
          ├── nidBackImage
          │
          ├── ── TRADE LICENSE ──
          ├── tradeLicenseNumber
          ├── tradeLicenseImage
          │
          ├── ── VERIFICATION ──
          ├── verificationStatus
          │     values: pending / approved / rejected
          ├── rejectionReason
          ├── verifiedBy
          ├── verifiedDate
          │
          └── ── DATES ──
              ├── submittedAt
              └── updatedAt
 
=================================================
# 4. seller_follows
=================================================
 
seller_follows
    └── followId
          ├── customerId                 ← কে follow করেছে
          ├── sellerId                   ← কাকে follow করেছে
          ├── shopId
          ├── shopName
          ├── shopLogo
          └── createdAt
 
=================================================
# 5. customers
=================================================
 
customers
    └── customerId (CUS-0000000001)
          │
          ├── ── BASIC INFORMATION ──
          ├── fullName
          ├── phoneNumber
          ├── email
          ├── profileImage
          ├── gender
          ├── dateOfBirth
          ├── joinDate
          ├── lastLogin
          │
          ├── ── STATUS ──
          ├── status
          │     values: active / blocked / banned
          ├── statusReason
          ├── statusUpdatedDate
          ├── statusUpdatedBy
          │
          ├── ── DEFAULT ADDRESS ──
          ├── defaultDistrict
          ├── defaultUpazila
          ├── defaultUnion               ← নতুন: ইউনিয়ন
          ├── defaultArea
          ├── defaultFullAddress
          ├── defaultPostalCode
          ├── defaultLatitude
          ├── defaultLongitude
          │
          ├── ── ADDRESS BOOK (Sub-collection) ──
          ├── addressBook/
          │     └── addressId
          │           ├── receiverName
          │           ├── receiverPhone
          │           ├── district
          │           ├── upazila
          │           ├── union          ← নতুন
          │           ├── area
          │           ├── fullAddress
          │           ├── postalCode
          │           ├── latitude
          │           ├── longitude
          │           └── isDefault
          │
          ├── ── STATISTICS ──
          ├── totalOrders
          ├── completedOrders
          ├── cancelledOrders
          ├── returnedOrders
          ├── totalSpent
          ├── averageOrderValue
          ├── lastOrderDate
          │
          ├── ── WALLET ──
          ├── walletBalance
          ├── refundBalance
          ├── couponBalance
          ├── totalRefundReceived
          │
          ├── ── COUPONS ──
          ├── usedCoupons
          ├── activeCoupons
          ├── expiredCoupons
          │
          ├── ── ACTIVITY ──
          ├── lastOrderId
          ├── lastLoginIp
          ├── deviceInfo
          ├── accountCreatedFrom
          │     values: android / ios / web
          │
          ├── ── COMPLAINTS ──
          ├── totalComplaints
          ├── openComplaints
          ├── resolvedComplaints
          │
          ├── ── REVIEWS ──
          ├── totalReviews
          ├── averageReviewRating
          │
          ├── ── SECURITY ──
          ├── emailVerified
          ├── phoneVerified
          ├── twoFactorEnabled
          │
          ├── ── ACCOUNT CONTROL ──
          ├── canPlaceOrder
          ├── canWriteReview
          ├── canUseCoupon
          ├── canReceiveNotifications
          ├── adminNotes
          │
          └── ── DATES ──
              ├── createdAt
              └── updatedAt
 
=================================================
# 6. categories
=================================================
 
categories
    └── categoryId
          ├── name
          ├── slug
          ├── parentCategoryId           ← Sub-category support (null = top level)
          ├── image
          ├── icon
          ├── description
          ├── sortOrder
          ├── isActive
          ├── productCount
          ├── createdBy
          ├── createdAt
          └── updatedAt
 
=================================================
# 7. brands
=================================================
 
brands
    └── brandId
          ├── name
          ├── slug
          ├── logo
          ├── description
          ├── isActive
          ├── productCount
          ├── createdBy
          ├── createdAt
          └── updatedAt
 
=================================================
# 8. products
=================================================
 
products
    └── productId (PRD-0000000001)
          │
          ├── ── BASIC INFORMATION ──
          ├── sellerId
          ├── shopId
          ├── categoryId
          ├── subCategoryId
          ├── brandId
          ├── productName
          ├── shortDescription
          ├── fullDescription
          │
          ├── ── STATUS ──
          ├── productStatus
          │     values: pending / approved / rejected / hidden / blocked
          ├── approvalDate
          ├── approvedBy
          ├── rejectionReason
          │
          ├── ── PRICING ──
          ├── regularPrice
          ├── salePrice
          ├── costPrice
          ├── taxAmount
          ├── discountAmount
          ├── discountType
          │     values: percentage / fixed
          │
          ├── ── INVENTORY ──
          ├── sku
          ├── barcode
          ├── stockQuantity
          ├── minimumStockAlert
          ├── soldQuantity
          ├── reservedQuantity
          ├── stockStatus
          │     values: in_stock / low_stock / out_of_stock
          │
          ├── ── IMAGES ──
          ├── thumbnailImage
          ├── galleryImages              ← Array of image URLs
          ├── imageCount
          │
          ├── ── VARIANTS (স্পষ্ট structure) ──
          ├── hasVariant
          ├── variantType
          │     examples: size / color / size_color
          ├── variants                   ← Array
          │     └── variantId
          │           ├── color         ← Black / White / Blue
          │           ├── size          ← S / M / L / XL / XXL
          │           ├── stock
          │           ├── price
          │           ├── sku           ← PRD-001-BLK-XL
          │           └── images        ← variant-specific images
          │
          ├── ── SHIPPING ──
          ├── weight
          ├── length
          ├── width
          ├── height
          ├── shippingClass
          ├── pickupRequired
          │
          ├── ── REVIEW SUMMARY ──
          ├── totalReviews
          ├── averageRating
          ├── fiveStarCount
          ├── fourStarCount
          ├── threeStarCount
          ├── twoStarCount
          ├── oneStarCount
          │
          ├── ── SALES STATISTICS ──
          ├── totalViews
          ├── totalWishlist
          ├── totalOrders
          ├── totalDeliveredOrders
          ├── totalReturnedOrders
          ├── totalRevenue
          │
          ├── ── VISIBILITY ──
          ├── isFeatured
          ├── isTrending
          ├── isBestSelling
          ├── isRecommended
          ├── showOnHomepage
          │
          ├── ── SEO ──
          ├── slug
          ├── metaTitle
          ├── metaDescription
          ├── searchKeywords
          │
          ├── ── CONTROL ──
          ├── canPurchase
          ├── canReview
          ├── adminNotes
          ├── sellerNotes
          │
          └── ── DATES ──
              ├── createdAt
              └── updatedAt
 
=================================================
# 9. orders
=================================================
 
orders
    └── orderId (ORD-0000000001)
          │
          ├── ── BASIC INFORMATION ──
          ├── orderDate
          ├── orderTime
          ├── orderSource
          │     values: android / ios / web
          ├── orderStatus
          │     values:
          │       pending / confirmed / processing /
          │       pickup_requested / picked_up / in_transit /
          │       out_for_delivery / delivered /
          │       cancelled / returned / refunded
          │
          ├── ── CUSTOMER INFORMATION ──
          ├── customerId
          ├── customerName
          ├── customerPhone
          ├── customerEmail
          ├── deliveryDistrict
          ├── deliveryUpazila
          ├── deliveryUnion              ← নতুন
          ├── deliveryArea
          ├── deliveryAddress
          ├── deliveryPostalCode
          │
          ├── ── SELLER INFORMATION ──
          ├── sellerId
          ├── shopId
          ├── sellerName
          ├── shopName
          ├── sellerPhone
          │
          ├── ── PRODUCT ORDER INFORMATION ──
          ├── productId
          ├── productName
          ├── sku
          ├── category
          ├── brand
          ├── variantId
          ├── size
          ├── color
          ├── quantity
          ├── unitPrice
          ├── subtotal
          │
          ├── ── PICKUP INFORMATION ──
          ├── locationId
          ├── pickupContactName
          ├── pickupContactPhone
          ├── pickupDistrict
          ├── pickupUpazila
          ├── pickupArea
          ├── pickupAddress
          │
          ├── ── MERCHANT INFORMATION ──
          ├── merchantId
          │
          ├── ── COURIER INFORMATION ──
          ├── courierId
          ├── courierName
          ├── trackingCode
          ├── parcelId
          │
          ├── ── PICKUP STATUS ──
          ├── pickupRequestId
          ├── pickupStatus
          │     values:
          │       pending / requested / accepted /
          │       rider_assigned / picked_up / failed / cancelled
          ├── pickupRequestDate
          ├── pickupDate
          │
          ├── ── PICKUP RIDER ──
          ├── pickupRiderId
          ├── pickupRiderName
          ├── pickupRiderPhone
          ├── pickupAssignedDate
          ├── pickupCompletedDate
          │
          ├── ── DELIVERY STATUS ──
          ├── deliveryStatus
          │     values:
          │       pending / assigned / picked_from_hub /
          │       out_for_delivery / delivered / failed / returned
          ├── deliveryRiderId            ← Admin only
          ├── deliveryRiderName          ← Admin only
          ├── deliveryRiderPhone         ← Admin only
          ├── deliveryAssignedDate
          ├── deliveryCompletedDate
          ├── deliveryDate
          ├── deliveryTime
          ├── deliveryVerified
          ├── receiverName
          ├── receiverPhone
          │
          ├── ── DELIVERY CHARGE ──
          ├── deliveryZoneType
          │     values: inside_district / outside_district
          ├── deliveryCharge
          │
          ├── ── PAYMENT INFORMATION ──
          ├── paymentMethod
          │     values: COD / bKash / Nagad
          ├── paymentStatus
          │     values: pending / paid / failed / refunded
          ├── paymentTransactionId
          │
          ├── ── ORDER AMOUNT ──
          ├── productAmount
          ├── deliveryCharge
          ├── discountAmount
          ├── couponDiscount
          ├── voucherDiscount            ← নতুন: voucher থেকে discount
          ├── finalAmount
          │
          ├── ── COMMISSION ──
          ├── commissionType
          ├── commissionRate
          ├── commissionAmount
          ├── adminCommissionAmount
          ├── sellerReceivableAmount
          │
          ├── ── SETTLEMENT ──
          ├── settlementEligible
          │     values: yes / no
          ├── settlementStatus
          │     values: pending / ready / completed
          ├── settlementDate
          │
          ├── ── RETURN INFORMATION ──
          ├── returnRequested
          ├── returnReason
          ├── returnDate
          ├── returnStatus
          │     values: none / requested / approved / returned / rejected
          │
          ├── ── CANCELLATION ──
          ├── cancelReason
          ├── cancelDate
          ├── cancelledBy
          │
          ├── ── ADMIN CONTROL ──
          ├── adminNotes
          ├── sellerNotes
          ├── systemNotes
          ├── fraudFlag
          ├── manualReviewRequired
          │
          └── ── DATES ──
              ├── createdAt
              └── updatedAt
 
=================================================
# 10. order_items
=================================================
 
order_items
    └── orderItemId
          ├── orderId
          ├── productId
          ├── variantId
          ├── productName
          ├── sku
          ├── color
          ├── size
          ├── quantity
          ├── unitPrice
          ├── totalPrice
          └── createdAt
 
=================================================
# 11. return_requests
=================================================
 
return_requests
    └── returnId (RTN-0000000001)
          ├── orderId
          ├── customerId
          ├── sellerId
          ├── productId
          │
          ├── ── RETURN REASON ──
          ├── reason
          ├── description
          ├── images                     ← Array of image URLs
          │
          ├── ── STATUS ──
          ├── status
          │     values:
          │       requested / approved / rejected /
          │       pickup_scheduled / picked_up / completed
          ├── rejectionReason
          │
          ├── ── ADMIN CONTROL ──
          ├── reviewedBy
          ├── reviewedDate
          ├── adminNotes
          │
          ├── ── REFUND ──
          ├── refundEligible
          ├── refundAmount
          ├── refundStatus
          │     values: pending / processed / rejected
          │
          └── ── DATES ──
              ├── createdAt
              └── updatedAt
 
=================================================
# 12. merchants
=================================================
 
merchants
    └── merchantId (LAKEZ_MAIN_MERCHANT)
          │
          ├── ── BASIC INFORMATION ──
          ├── companyName
          ├── merchantEmail
          ├── merchantPhone
          │
          ├── ── COURIER API CONFIGURATION ──
          ├── apiKey                     ← Encrypted
          ├── secretKey                  ← Encrypted
          ├── baseUrl
          ├── sandboxMode
          │     values: yes / no
          │
          ├── ── CONNECTION ──
          ├── connectionStatus
          │     values: connected / disconnected
          ├── lastConnectionCheck
          │
          ├── ── COURIER SERVICE ──
          ├── courierId
          ├── courierName                ← Steadfast
          ├── courierStatus
          │     values: active / inactive
          │
          ├── ── WEBHOOK ──
          ├── webhookUrl
          ├── webhookStatus
          │     values: active / inactive
          │
          ├── ── API STATS ──
          ├── totalApiRequest
          ├── successfulApiRequest
          ├── failedApiRequest
          │
          ├── ── SECURITY ──
          ├── encryptionStatus
          ├── lastSecurityCheck
          │
          ├── ── ADMIN CONTROL ──
          ├── canCreateParcel
          ├── canCancelParcel
          ├── canSyncTracking
          ├── accountStatus
          │     values: active / inactive / suspended
          │
          └── ── DATES ──
              ├── createdAt
              └── updatedAt
 
=================================================
# 13. parcels
=================================================
 
parcels
    └── parcelId
          ├── orderId
          ├── merchantId
          ├── sellerId
          ├── customerId
          ├── locationId
          │
          ├── ── STEADFAST SPECIFIC FIELDS ──
          ├── consignment_id             ← Steadfast API থেকে আসে
          ├── store_id                   ← Steadfast Merchant Store ID
          ├── trackingCode
          ├── steadfast_status           ← Steadfast-এর নিজস্ব status
          ├── courierRequestId
          ├── apiResponseStatus
          │     values: success / failed / pending
          │
          ├── ── COD INFORMATION ──
          ├── cod_amount                 ← COD টাকার পরিমাণ
          ├── cod_status
          │     values: pending / collected / transferred
          ├── cod_collected_date
          │
          ├── ── PICKUP ──
          ├── pickupId
          ├── pickupRequestId
          ├── pickupStatus
          │     values:
          │       pending / requested / accepted /
          │       rider_assigned / picked_up / failed / cancelled
          ├── pickupRequestDate
          ├── pickupDate
          │
          ├── ── PICKUP RIDER ──
          ├── pickupRiderId
          ├── pickupRiderName
          ├── pickupRiderPhone
          ├── pickupAssignedDate
          ├── pickupCompletedDate
          │
          ├── ── DELIVERY ──
          ├── deliveryStatus
          │     values:
          │       pending / assigned / picked_from_hub /
          │       out_for_delivery / delivered / failed / returned
          ├── deliveryRiderId
          ├── deliveryRiderName
          ├── deliveryRiderPhone
          ├── deliveryAssignedDate
          ├── deliveryCompletedDate
          ├── deliveryDate
          ├── deliveryTime
          ├── deliveryVerified
          ├── receiverName
          ├── receiverPhone
          │
          ├── ── RETURN (RTO) ──
          ├── returnStatus
          │     values: no_return / return_requested / returned
          ├── returnDate
          ├── returnReason
          ├── rtoPickupLocationId        ← Return হলে কোথায় যাবে
          │
          ├── ── WEBHOOK ──
          ├── webhookLastUpdate          ← নতুন
          ├── webhookRawData             ← নতুন: Steadfast থেকে আসা raw data
          │
          └── ── DATES ──
              ├── createdAt
              └── updatedAt
 
=================================================
# 14. webhook_logs
=================================================
 
webhook_logs
    └── webhookLogId
          ├── source                     ← steadfast / bkash / nagad
          ├── eventType                  ← delivery_update / payment_update / return
          ├── parcelId
          ├── orderId
          ├── rawPayload                 ← Courier থেকে আসা সম্পূর্ণ data
          ├── processedStatus
          │     values: success / failed / pending
          ├── errorMessage
          ├── processedAt
          └── createdAt
 
=================================================
# 15. pickup_locations
=================================================
 
pickup_locations
    └── locationId (LOC-0000000001)
          ├── merchantId
          ├── sellerId
          ├── shopId
          ├── shopName
          ├── sellerName
          │
          ├── ── CONTACT ──
          ├── pickupContactName
          ├── pickupContactPhone
          │
          ├── ── ADDRESS ──
          ├── pickupDistrict
          ├── pickupUpazila
          ├── pickupUnion                ← নতুন
          ├── pickupArea
          ├── pickupAddress
          │
          ├── ── LOCATION TYPE ──
          ├── locationType
          │     values: shop / warehouse / branch / home
          │
          ├── ── STATUS ──
          ├── locationStatus
          │     values: active / inactive / pending / suspended
          ├── isDefaultLocation
          │
          ├── ── PICKUP TIME ──
          ├── pickupAvailableTime
          ├── pickupInstruction
          │
          ├── ── VERIFICATION ──
          ├── verificationStatus
          │     values: pending / verified / rejected
          ├── verifiedBy
          ├── verifiedDate
          │
          ├── adminNote
          └── ── DATES ──
              ├── createdAt
              └── updatedAt
 
=================================================
# 16. couriers
=================================================
 
couriers
    └── courierId (CUR-STEADFAST)
          ├── name                       ← Steadfast
          ├── apiConfig
          ├── courierStatus
          │     values: active / inactive
          └── createdAt
 
=================================================
# 17. delivery_zones
=================================================
 
delivery_zones
    └── zoneId
          ├── district                   ← ঢাকা / সিলেট / চট্টগ্রাম...
          ├── upazila
          ├── union
          ├── area
          ├── postalCode
          ├── isServiceable              ← এই এলাকায় delivery হয় কিনা
          ├── deliveryCharge             ← এই zone-এর specific charge (optional)
          ├── estimatedDays              ← আনুমানিক delivery সময়
          ├── createdAt
          └── updatedAt
 
=================================================
# 18. delivery_charges
=================================================
 
delivery_charges
    └── chargeId (DC-000000001)
          ├── courierId
          ├── courierName
          │
          ├── ── ZONE BASED CHARGE ──
          ├── chargeZoneType
          │     values: inside_district / outside_district
          ├── pickupDistrict
          ├── deliveryDistrict
          ├── sameDistrictRule
          ├── deliveryChargeAmount
          │     example:
          │       Same District = 60 টাকা
          │       Different District = 120 টাকা
          ├── returnChargeAmount
          │
          ├── ── WEIGHT BASED (Future) ──
          ├── minimumWeight
          ├── maximumWeight
          ├── extraWeightCharge
          │
          ├── ── AREA BASED (Future) ──
          ├── areaType
          │     values: city / outside_city / rural
          ├── areaName
          │
          ├── ── STATUS ──
          ├── status
          │     values: active / inactive
          ├── priority
          │
          ├── ── ADMIN CONTROL ──
          ├── createdBy
          ├── updatedBy
          ├── adminNote
          │
          └── ── DATES ──
              ├── createdAt
              └── updatedAt
 
=================================================
# 19. wallets
=================================================
 
# নোট: sellers collection থেকে wallet object সরানো হয়েছে।
# শুধুমাত্র এই wallets collection ব্যবহার হবে। (duplication সমাধান)
 
wallets
    └── walletId (WALLET-000000001)
          ├── sellerId
          ├── shopId
          │
          ├── ── BALANCE ──
          ├── currentBalance
          ├── pendingBalance
          ├── totalEarning
          ├── totalWithdraw
          ├── totalCommissionPaid
          │
          ├── ── SETTLEMENT ENTRY ──
          ├── settlementId
          ├── orderId
          ├── parcelId
          ├── amountAdded
          │
          ├── ── TRANSACTION TYPE ──
          ├── transactionType
          │     values:
          │       order_income / withdraw / refund / adjustment
          │
          ├── ── TRANSACTION STATUS ──
          ├── transactionStatus
          │     values: pending / completed / cancelled
          │
          ├── ── WITHDRAW CONTROL ──
          ├── withdrawAvailable
          ├── minimumWithdrawAmount
          │
          ├── ── ADMIN CONTROL ──
          ├── walletStatus
          │     values: active / inactive / blocked
          ├── adminNote
          │
          └── ── DATES ──
              ├── createdAt
              └── updatedAt
 
=================================================
# 20. settlements
=================================================
 
settlements
    └── settlementId
          ├── orderId
          ├── parcelId
          ├── sellerId
          │
          ├── ── DELIVERY INFO ──
          ├── deliveryStatus
          │     values: delivered / pending
          ├── deliveredDate
          ├── settlementCreatedDate
          │
          ├── ── AMOUNT ──
          ├── productAmount
          ├── commissionType
          ├── commissionRate
          ├── commissionAmount
          ├── deliveryZoneType
          ├── deliveryCharge
          ├── deliveryChargeDeducted
          ├── grossAmount
          ├── totalDeduction
          ├── sellerPayableAmount
          │
          ├── ── STATUS ──
          ├── settlementStatus
          │     values: pending / approved / paid / rejected
          ├── paymentRequestStatus
          │     values: not_requested / requested / processing / completed
          │
          ├── ── ADMIN CONTROL ──
          ├── adminNote
          ├── processedBy
          └── processedDate
 
=================================================
# 21. withdraw_requests
=================================================
 
withdraw_requests
    └── withdrawId (WITHDRAW-000000001)
          ├── sellerId
          ├── walletId
          ├── requestDate
          │
          ├── ── AMOUNT ──
          ├── requestedAmount
          ├── availableBalanceBefore
          ├── availableBalanceAfter
          │
          ├── ── PAYMENT METHOD ──
          ├── paymentMethod
          │     values: bKash / Nagad / Bank
          ├── accountName
          ├── accountNumber
          ├── bankName
          ├── branchName
          │
          ├── ── STATUS ──
          ├── withdrawStatus
          │     values:
          │       pending / approved / processing /
          │       completed / rejected / cancelled
          ├── rejectionReason
          │
          ├── ── ADMIN PROCESS ──
          ├── approvedBy
          ├── approvedDate
          ├── processedBy
          ├── processedDate
          ├── paymentTransactionId
          ├── paymentProof
          │
          ├── ── SECURITY ──
          ├── verificationStatus
          │     values: verified / unverified
          └── adminNote
 
=================================================
# 22. transactions
=================================================
 
transactions
    └── transactionId (TXN-0000000001)
          ├── transactionDate
          ├── transactionType
          │     values:
          │       order_payment / commission / delivery_charge /
          │       seller_wallet_credit / withdraw / refund / adjustment
          │
          ├── ── ORDER INFO ──
          ├── orderId
          ├── parcelId
          ├── customerId
          ├── paymentMethod
          │     values: COD / bKash / Nagad
          │
          ├── ── SELLER INFO ──
          ├── sellerId
          ├── shopId
          │
          ├── ── AMOUNT ──
          ├── transactionAmount
          ├── previousBalance
          ├── currentBalance
          │
          ├── ── COMMISSION ──
          ├── commissionRate
          ├── commissionAmount
          │
          ├── ── DELIVERY CHARGE ──
          ├── deliveryZoneType
          ├── deliveryChargeAmount
          │
          ├── ── WALLET ──
          ├── walletId
          ├── walletAction
          │     values: credit / debit
          ├── referenceId
          │
          ├── ── WITHDRAW ──
          ├── withdrawId
          ├── paymentTransactionId
          ├── paymentStatus
          │     values: pending / completed / failed
          │
          ├── ── REFUND ──
          ├── refundAmount
          ├── refundReason
          │
          ├── ── ADJUSTMENT ──
          ├── adjustmentType
          │     values: add / subtract
          ├── adjustmentReason
          │
          ├── ── STATUS ──
          ├── transactionStatus
          │     values: pending / completed / failed / cancelled
          │
          ├── ── ADMIN ──
          ├── createdBy
          └── adminNote
 
=================================================
# 23. coupons (সংশোধিত + Voucher যোগ)
=================================================
 
coupons
    └── couponId
          │
          ├── ── BASIC INFORMATION ──
          ├── couponCode                 ← Example: LAKEZ100
          ├── couponName                 ← Example: New Year Offer
          │
          ├── ── VOUCHER TYPE ──
          ├── voucherSource
          │     values: admin / seller    ← Admin voucher নাকি Seller voucher
          ├── voucherType
          │     values:
          │       admin_platform_voucher  ← সব পণ্যে প্রযোজ্য
          │       admin_free_delivery     ← Official Free Delivery Voucher
          │       seller_store_voucher    ← নির্দিষ্ট Seller-এর store
          │       seller_product_voucher  ← নির্দিষ্ট Product-এর জন্য
          ├── isOfficialVoucher
          │     values: true / false      ← "Official Voucher of Delivery" badge
          │
          ├── ── DISCOUNT INFORMATION ──
          ├── discountType
          │     values: percentage / fixed_amount / free_delivery
          ├── discountValue
          │     example:
          │       10% অথবা 100 টাকা অথবা 60 টাকা delivery discount
          │
          ├── ── ELIGIBILITY ──
          ├── minimumOrderAmount
          │     example: 499 টাকার পণ্য কিনলে free delivery
          ├── maximumDiscountAmount
          │
          ├── ── FREE DELIVERY SPECIFIC ──
          ├── freeDelivery
          ├── deliveryZone
          │     values: inside_district / outside_district / all
          ├── partialDeliveryDiscount    ← নতুন: পুরো free না, কিছু discount
          │     example: 399 টাকায় 60 টাকা discount
          │
          ├── ── TIME VALIDATION ──     ← নতুন: সময় নির্ধারিত হয়েছে কিনা
          ├── hasTimeLimit
          │     values: true / false
          ├── startDate
          ├── expiryDate
          ├── isExpired                  ← System auto-update করবে
          ├── remainingDays              ← System calculate করবে
          ├── remainingHours             ← System calculate করবে
          │
          ├── ── AMOUNT VALIDATION ──   ← নতুন: amount নির্ধারিত হয়েছে কিনা
          ├── hasAmountLimit
          │     values: true / false
          ├── totalBudget                ← মোট কত টাকার discount দেওয়া হবে
          ├── usedBudget                 ← কত টাকা ইতিমধ্যে গেছে
          ├── remainingBudget            ← System calculate করবে
          │
          ├── ── TARGET CONTROL ──
          ├── targetType
          │     values:
          │       all_customer / specific_customer /
          │       specific_seller / specific_product / specific_category
          ├── sellerId                   ← Seller voucher হলে
          ├── productId                  ← Product voucher হলে
          ├── categoryId                 ← Category voucher হলে
          │
          ├── ── USAGE CONTROL ──
          ├── usageLimit
          ├── usedCount
          ├── userLimit                  ← একজন customer কতবার ব্যবহার করতে পারবে
          ├── stackable
          │     values: true / false     ← একসাথে দুটো voucher ব্যবহার যাবে কিনা
          │
          ├── ── APPROVAL (Seller Voucher) ──
          ├── approvalStatus
          │     values: pending / approved / rejected
          │     নোট: Seller voucher Admin approve করবে
          ├── approvedBy
          ├── approvedDate
          ├── rejectionReason
          │
          ├── ── STATUS ──
          ├── couponStatus
          │     values: active / inactive / expired
          │
          ├── ── CREATED BY ──
          ├── createdBy                  ← adminId বা sellerId
          ├── createdByType
          │     values: admin / seller
          │
          └── ── DATES ──
              ├── createdAt
              └── updatedAt
 
=================================================
# 24. coupon_usage
=================================================
 
coupon_usage
    └── usageId
          ├── couponId
          ├── customerId
          ├── orderId
          ├── discountAmount
          ├── voucherSource              ← admin / seller
          └── usedAt
 
=================================================
# 25. campaigns
=================================================
 
campaigns
    └── campaignId
          ├── title
          ├── description
          ├── bannerImage
          │
          ├── ── DISCOUNT ──
          ├── discountType
          │     values: percentage / fixed / free_delivery
          ├── discountValue
          ├── minimumOrderAmount
          │
          ├── ── TARGET ──
          ├── targetType
          │     values: all / specific_seller / specific_category / specific_product
          ├── sellerId
          ├── categoryId
          ├── productId
          │
          ├── ── TIME ──
          ├── startDate
          ├── endDate
          ├── isActive
          │
          ├── ── ADMIN CONTROL ──
          ├── createdBy
          ├── createdAt
          └── updatedAt
 
=================================================
# 26. banners
=================================================
 
banners
    └── bannerId
          ├── title
          ├── image
          ├── targetUrl
          ├── targetType
          │     values: product / seller / category / campaign / external
          ├── targetId
          ├── position
          │     values: home_top / home_middle / home_bottom / category_top
          ├── sortOrder
          ├── status
          │     values: active / inactive
          ├── startDate
          ├── endDate
          ├── createdBy
          ├── createdAt
          └── updatedAt
 
=================================================
# 27. notifications
=================================================
 
notifications
    └── notificationId
          ├── receiverId
          ├── receiverType               ← নতুন: customer / seller / admin
          ├── title
          ├── message
          ├── notificationImage
          │
          ├── ── TYPE ──
          ├── notificationType
          │     values:
          │       order / payment / settlement / pickup /
          │       delivery / withdraw / promotion / system
          │
          ├── ── ORDER RELATED ──
          ├── orderId
          ├── parcelId
          ├── trackingCode
          │
          ├── ── PUSH NOTIFICATION ──
          ├── deviceToken
          ├── platform
          │     values: android / ios / web
          │
          ├── ── STATUS ──
          ├── readStatus
          │     values: unread / read
          ├── readDate
          │
          ├── ── ACTION ──
          ├── actionType
          │     values:
          │       open_order / open_product / open_payment /
          │       open_wallet / open_tracking / none
          ├── actionId
          │
          └── ── DATES ──
              ├── createdAt
              └── sentAt
 
=================================================
# 28. reviews
=================================================
 
reviews
    └── reviewId
          ├── customerId
          ├── sellerId
          ├── productId
          ├── orderId
          │
          ├── ── RATING ──
          ├── productRating              ← 1-5
          ├── sellerRating               ← 1-5
          ├── deliveryRating             ← 1-5
          │
          ├── ── CONTENT ──
          ├── reviewTitle
          ├── reviewDescription
          ├── reviewImages
          │
          ├── ── VERIFIED PURCHASE ──
          ├── verifiedPurchase
          ├── deliveredOrderId
          │
          ├── ── STATUS ──
          ├── reviewStatus
          │     values: pending / approved / rejected / hidden
          ├── rejectionReason
          │
          ├── ── SELLER RESPONSE ──
          ├── sellerReply
          ├── replyDate
          │
          ├── ── MODERATION ──
          ├── moderatedBy
          ├── moderatedDate
          │
          ├── ── REPORT ──
          ├── reportId
          ├── reportedBy
          ├── reportReason
          ├── reportStatus
          │     values: pending / reviewed / resolved
          │
          └── ── DATES ──
              ├── createdAt
              └── updatedAt
 
=================================================
# 29. conversations
=================================================
 
conversations
    └── conversationId
          ├── customerId
          ├── sellerId
          ├── orderId
          ├── lastMessage
          ├── lastMessageTime
          ├── unreadCountCustomer
          ├── unreadCountSeller
          ├── fraudAlertSent             ← নতুন: fraud alert পাঠানো হয়েছে কিনা
          └── updatedAt
 
=================================================
# 30. messages
=================================================
 
messages
    └── messageId
          ├── conversationId
          ├── senderId
          ├── senderType
          │     values: customer / seller / admin
          ├── message
          ├── messageType
          │     values: text / image / order_link
          │
          ├── ── FRAUD DETECTION ──     ← সংশোধিত ও বিস্তারিত
          ├── fraudFlag
          ├── containsPhone              ← ফোন নম্বর detected
          ├── containsAddress            ← ঠিকানা detected
          ├── containsAmount             ← টাকার পরিমাণ detected
          ├── fraudType
          │     values: phone / address / amount / external_link / other
          ├── alertSent                  ← Admin-কে alert গেছে কিনা
          │
          └── sentAt
 
=================================================
# 31. fraud_alerts
=================================================
 
fraud_alerts
    └── alertId
          ├── conversationId
          ├── messageId
          ├── customerId
          ├── sellerId
          │
          ├── ── ALERT TYPE ──
          ├── alertType
          │     values: phone / address / amount / external_link / other
          ├── detectedContent            ← কী detected হয়েছে
          ├── originalMessage            ← সম্পূর্ণ message
          │
          ├── ── STATUS ──
          ├── alertStatus
          │     values: pending / reviewed / resolved / dismissed
          ├── reviewedBy
          ├── reviewedDate
          ├── adminNote
          │
          └── createdAt
 
=================================================
# 32. tickets
=================================================
 
tickets
    └── ticketId (CMP-0000000001)
          ├── orderId
          ├── customerId
          ├── sellerId
          ├── issueType
          ├── description
          ├── attachments
          ├── status
          │     values: open / under_review / resolved / closed
          ├── priority
          │     values: low / medium / high / urgent
          ├── assignedTo
          ├── resolution
          ├── createdAt
          └── updatedAt
 
=================================================
# 33. audit_logs
=================================================
 
audit_logs
    └── auditId
          ├── createdDate
          ├── userId
          ├── userType
          │     values: admin / seller / customer / system
          ├── userName
          ├── actionType
          │     values:
          │       login / logout / create / update / delete /
          │       approve / reject / payment / refund / settlement / withdraw
          ├── moduleName
          ├── actionDescription
          ├── tableName
          ├── recordId
          ├── oldValue                   ← JSON
          ├── newValue                   ← JSON
          ├── ipAddress
          ├── deviceInformation
          ├── loginSessionId
          ├── transactionId
          ├── amountChanged
          └── approvalStatus
 
=================================================
# 34. security_logs
=================================================
 
security_logs
    └── logId
          ├── userId
          ├── userType
          │     values: admin / seller / customer
          ├── loginId
          ├── loginEmail
          ├── loginStatus
          │     values: success / failed / blocked
          ├── loginDateTime
          ├── failureReason
          ├── ipAddress
          ├── deviceId
          ├── deviceName
          ├── deviceType
          │     values: android / ios / windows / web
          ├── locationInfo
          └── createdAt
 
=================================================
# 35. sessions
=================================================
 
sessions
    └── sessionId
          ├── adminId
          ├── accessToken
          ├── refreshToken
          ├── deviceId
          ├── ipAddress
          ├── createdAt
          ├── expiresAt
          └── sessionStatus
                values: active / expired / revoked
 
=================================================
# 36. device_logs
=================================================
 
device_logs
    └── deviceLogId
          ├── userId
          ├── userType
          │     values: admin / seller / customer
          ├── deviceId
          ├── deviceName
          ├── deviceType
          │     values: android / ios / windows / web
          ├── deviceToken                ← FCM Push Token
          ├── browser
          ├── operatingSystem
          ├── ipAddress
          ├── trustedDevice
          ├── firstSeen
          └── lastSeen
 
=================================================
# 37. settings
=================================================
 
settings
    └── settingId
          ├── settingKey
          ├── settingValue
          ├── settingType
          │     values: text / number / boolean / image / json
          ├── category
          │     values:
          │       general / commission / delivery /
          │       payment / firebase / notification /
          │       security / maintenance / system
          ├── updatedBy
          └── updatedAt
 
=================================================
# COLLECTION SUMMARY
=================================================
 
মোট Collection: 37টি
 
নতুন যোগ হয়েছে (14টি):
01. categories
02. brands
03. campaigns
04. banners
05. return_requests
06. merchants
07. seller_kyc
08. delivery_zones
09. sessions
10. device_logs
11. seller_follows
12. fraud_alerts
13. coupon_usage
14. webhook_logs
 
সংশোধিত হয়েছে (9টি):
01. sellers        — KYC reference, canCreateVoucher, union field
02. customers      — union field, full address book
03. orders         — product details, union field, voucherDiscount
04. products       — variants structure স্পষ্ট
05. parcels        — Steadfast fields, COD fields, webhook fields
06. wallets        — duplication সমাধান
07. notifications  — receiverType যোগ
08. messages       — fraud detection fields বিস্তারিত
09. coupons        — voucher type, time validation, amount validation, approval
 
=================================================
# COLLECTION RELATIONS
=================================================
 
sellers ──────────────── seller_kyc
sellers ──────────────── seller_follows (customers follow sellers)
sellers ──────────────── pickup_locations
sellers ──────────────── wallets
sellers ──────────────── products
sellers ──────────────── orders
sellers ──────────────── settlements
sellers ──────────────── withdraw_requests
 
customers ────────────── orders
customers ────────────── reviews
customers ────────────── conversations
customers ────────────── tickets
customers ────────────── seller_follows
 
products ─────────────── categories
products ─────────────── brands
products ─────────────── order_items
products ─────────────── reviews
 
orders ───────────────── order_items
orders ───────────────── parcels
orders ───────────────── settlements
orders ───────────────── transactions
orders ───────────────── return_requests
orders ───────────────── notifications
orders ───────────────── coupon_usage
 
parcels ──────────────── merchants
parcels ──────────────── couriers
parcels ──────────────── pickup_locations
parcels ──────────────── webhook_logs
parcels ──────────────── settlements
 
merchants ────────────── couriers
merchants ────────────── parcels
 
conversations ────────── messages
conversations ────────── fraud_alerts
 
coupons ──────────────── coupon_usage
campaigns ────────────── banners
 
admins ───────────────── sessions
admins ───────────────── device_logs
admins ───────────────── audit_logs
admins ───────────────── security_logs
 
===============================================
