# FIREBASE COLLECTION ARCHITECTURE

=================================================

admins
    └── adminId
          ├── name
          ├── email
          ├── role
          ├── permissions
          ├── status
          └── createdAt

=================================================

sellers
    └── sellerId
          ├── shopInfo
          ├── personalInfo
          ├── commission
          ├── wallet
          ├── status
          └── createdAt

=================================================

customers
    └── customerId
          ├── name
          ├── phone
          ├── address
          ├── status
          └── createdAt

=================================================

products
    └── productId
          ├── sellerId
          ├── categoryId
          ├── brandId
          ├── name
          ├── price
          ├── stock
          ├── variants
          ├── images
          ├── approvalStatus
          └── createdAt

=================================================

orders
    └── orderId
          ├── customerId
          ├── sellerId
          ├── parcelId
          ├── paymentInfo
          ├── deliveryInfo
          ├── orderStatus
          └── createdAt

=================================================

order_items
    └── orderItemId
          ├── orderId
          ├── productId
          ├── quantity
          ├── unitPrice
          └── totalPrice

=================================================

parcels
    └── parcelId
          ├── merchantId
          ├── courierId
          ├── customerId
          ├── pickupLocationId
          ├── trackingCode
          ├── status
          └── createdAt

=================================================

pickup_locations
    └── locationId
          ├── sellerId
          ├── district
          ├── city
          ├── area
          ├── address
          └── phone

=================================================

couriers
    └── courierId
          ├── name
          ├── apiConfig
          ├── status
          └── createdAt

=================================================

wallets
    └── walletId
          ├── sellerId
          ├── currentBalance
          ├── pendingBalance
          ├── totalWithdraw
          └── updatedAt

=================================================

settlements
    └── settlementId
          ├── sellerId
          ├── orderId
          ├── commissionAmount
          ├── deliveryCharge
          ├── payableAmount
          ├── status
          └── createdAt

=================================================

withdraw_requests
    └── withdrawId
          ├── sellerId
          ├── walletId
          ├── amount
          ├── paymentMethod
          ├── status
          └── createdAt

=================================================

transactions
    └── transactionId
          ├── type
          ├── sellerId
          ├── amount
          ├── referenceId
          ├── status
          └── createdAt

=================================================

delivery_charges
    └── chargeId
          ├── insideDistrictCharge
          ├── outsideDistrictCharge
          ├── weightRules
          └── updatedAt

=================================================

coupons
    └── couponId
          ├── code
          ├── discountType
          ├── discountValue
          ├── expiryDate
          ├── status
          └── createdAt

=================================================

notifications
    └── notificationId
          ├── receiverId
          ├── type
          ├── title
          ├── message
          ├── readStatus
          └── createdAt

=================================================

reviews
    └── reviewId
          ├── productId
          ├── customerId
          ├── rating
          ├── review
          ├── status
          └── createdAt

=================================================

audit_logs
    └── auditId
          ├── userId
          ├── action
          ├── module
          ├── oldValue
          ├── newValue
          └── createdAt

=================================================

security_logs
    └── logId
          ├── ipAddress
          ├── device
          ├── event
          ├── status
          └── createdAt

=================================================

conversations
    └── conversationId
          ├── customerId
          ├── sellerId
          ├── orderId
          ├── lastMessage
          └── updatedAt

=================================================

messages
    └── messageId
          ├── conversationId
          ├── senderId
          ├── message
          ├── fraudFlag
          └── sentAt

=================================================

tickets
    └── ticketId
          ├── orderId
          ├── customerId
          ├── sellerId
          ├── issueType
          ├── status
          └── createdAt

=================================================

settings
    └── settingId
          ├── key
          ├── value
          ├── type
          └── updatedAt
