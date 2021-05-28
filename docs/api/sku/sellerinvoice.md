# Seller Packed Order Delivery Slip API

All ordres in `PACKED` status will be available in this API.

## Method
GET

## Endpoint
    https://sellerinvoice.sastodeal.com/api/packed/fetch?username={username}&password={password}

# Response
## Success
```
[
    {
        "orderLocation": "M01",
        "orderId": "M0156730",
        "orderNo": "410216759",
        "extenalOrderNo": "410216759",
        "paymentMethod": "COD",
        "status": "Allocated",
        "orderDate": "28/05/2021 19:13:23",
        "orderAmount": "90.00",
        "orderCurrency": "NPR",
        "conversionRate": "1.00",
        "customerName": "Test  Manandhar",
        "shipAddress1": "thahity",
        "shipAddress2": "Provinces No 3 area\nKathmandu",
        "shipAddress3": "",
        "landmark": "",
        "latitude": "",
        "longitude": "",
        "shipCity": "Kathmandu",
        "shipState": "Provinces No 3",
        "shipCountry": "NEPAL",
        "shipPincode": "44602",
        "shipPhone1": "9851186277",
        "shipPhone2": "9851186277",
        "shipEmail1": "sodhancha@gmail.com",
        "shipEmail2": "sodhancha@gmail.com",
        "billName": "Test  Manandhar",
        "billAddress1": "thahity",
        "billAddress2": "Provinces No 3",
        "billAddress3": "",
        "billCity": "Kathmandu",
        "billState": "Provinces No 3",
        "billCountry": "NEPAL",
        "billPincode": "44602",
        "billPhone1": "9851186277",
        "billPhone2": "9851186277",
        "billEmail1": "sodhancha@gmail.com",
        "billEmail2": "sodhancha@gmail.com",
        "orderRemarks": null,
        "shippingCharges": "80.00",
        "handlingCharge2": "0.00",
        "storeCredit": "0.00",
        "isVerifiedOrder": "1",
        "isOnHold": "0",
        "giftvoucher": "0.00",
        "otherDiscount": "0.00",
        "discountCode": "null",
        "promoCode": null,
        "promoName": null,
        "cancelRemark": "",
        "isGiftwrap": "0",
        "giftwrapMsg": "",
        "deliverySlot": "",
        "customDataFeld1": "",
        "customDataFeld2": "",
        "customDataFeld3": "",
        "customDataFeld4": "Cash on Delivery/ Scan & Pay (Scan & Pay is only a",
        "customDataFeld5": "",
        "customDataFeld6": "",
        "customDataFeld7": "",
        "customDataFeld8": "",
        "customDataFeld9": "",
        "customDataFeld10": "",
        "discountAmount": "0.000",
        "taxAmount": "0.00",
        "updatedDate": "28/05/2021 19:23:01",
        "mode": "wms",
        "IsReplacementOrder": "No",
        "originalOrderno": "",
        "customerCode": "999999",
        "extCustomerCode": "",
        "clientId": "0",
        "fulfillmentLocCode": "SHO",
        "extFulFillmentLocCode": "SHO",
        "orderSourceName": "SastoDeal Live",
        "collectibleAmount": "90.00",
        "totalOrderLine": "1",
        "delFulfillmentMode": "2",
        "orderSource": "M01",
        "orderType": "SO",
        "shipByDate": "30/05/2021 19:13:23",
        "processAfterDate": "",
        "masterorderNo": "212844",
        "priority": "Normal",
        "pickupLocation": "",
        "items": [
            {
                "lineno": "338728",
                "extLineno": "338728",
                "internalLineNo": "1",
                "sku": "SUBAL_TEST_CAT_1",
                "primaryUPC": null,
                "skuName": "Subal TEST Cat 1",
                "imageUrl": "https://cdn.sastodeal.com/catalog/product/m/e/meizan_corn_oil.jpeg",
                "uom": "Each",
                "uomqty": "1.00",
                "conversion": "1.00",
                "orderQty": "1.00",
                "commitedQty": null,
                "cancelledQty": "0.00",
                "shippedQty": "0.00",
                "returnQty": "0.00",
                "unitPrice": "10.00",
                "discountAmt": "0.00",
                "promoCode": null,
                "promoName": null,
                "taxAmount": "0.00",
                "openQty": "0.00",
                "udf1": "",
                "udf2": "",
                "udf3": "",
                "udf4": "",
                "udf5": "",
                "udf6": "",
                "udf7": "",
                "udf8": "",
                "udf9": "",
                "udf10": "",
                "bundleSkuCode": null
            }
        ],
        "paymentItems": [],
        "codcharge": "0.00"
    }
]
```

## Failure
When no orders in this status are available
```
{
    "message": "No packed orders available.",
}
```

When authentication failure
```
{
    "message": "Message will be variable depending on what kind of input was provided",
}
```