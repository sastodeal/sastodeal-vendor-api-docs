### Sales Order List API

`API Endpoint`: /api/sales/sales/order

`Method`: GET

**Response**

`HTTP_STATUS`: 200

```json
{
    "data_collection": {
        "meta": {
            "per_page": 20,
            "result_count": 1,
            "total_count": 1,
            "last_page": 1,
            "current_page": 1,
            "from": 0,
            "to": 20
        },
        "results": [
            {
                "_id": "62cfbc9d586ecfda50f19ff5",
                "base_discount_amount": 0,
                "base_grand_total": 270,
                "base_subtotal": 270,
                "billing_address": {
                    "address_type": "billing",
                    "city": "Lalitpur",
                    "country_id": "NP",
                    "customer_address_id": 123,
                    "email": "customer@sastodeal.com",
                    "entity_id": 571216,
                    "firstname": "Test",
                    "lastname": "Customer",
                    "parent_id": 286323,
                    "postcode": "44703",
                    "region": "Provinces No 3",
                    "region_code": "Provinces No 3",
                    "region_id": 2040,
                    "street": [
                        "Sital Height",
                        "Near om itta bhatta"
                    ],
                    "telephone": "9800000000"
                },
                "created_at": "2022-07-20 01:55:03",
                "email": "customer@sastodeal.com",
                "firstname": "Test",
                "grand_total": 270,
                "items": [
                    {
                        "discount_amount": 0,
                        "discount_percent": 0,
                        "item_id": 458907,
                        "name": "Meon Best Premium Quality Simple And Elegant Design Hot Case , Hot Pot, Roti Box Serve Casserole (2000 ml)",
                        "original_price": 699,
                        "price": 270,
                        "qty_canceled": 0,
                        "qty_invoiced": 0,
                        "qty_ordered": 1,
                        "qty_refunded": 0,
                        "qty_shipped": 0,
                        "row_total": 270,
                        "sku": "sd-275846-637-greenplasticassu20",
                        "weight": 0,
                        "base_grand_total_amount": 270,
                        "total_commission": 30.51,
                        "actual_seller_amount": 239.49,
                        "commission_rate": 11.3
                    }
                ],
                "lastname": "Customer",
                "payment": {
                    "additional_information": [
                        "Cash on Delivery/ Scan & Pay (Scan & Pay is only applicable for inside valley & Biratnagar customers)",
                        null
                    ],
                    "amount_ordered": 270,
                    "method": "cashondelivery"
                },
                "shipping_address": {
                    "address_type": "shipping",
                    "city": "Lalitpur",
                    "country_id": "NP",
                    "customer_address_id": 32733,
                    "email": "customer@sastodeal.com",
                    "entity_id": 571215,
                    "firstname": "Test",
                    "lastname": "Customer",
                    "parent_id": 286323,
                    "postcode": "44703",
                    "region": "Provinces No 3",
                    "region_code": "Provinces No 3",
                    "region_id": 2040,
                    "street": [
                        "Sital Height",
                        "Near om itta bhatta"
                    ],
                    "telephone": "9800000000"
                },
                "state": "new",
                "status": "cod_authorized",
                "status_histories": [
                    {
                        "comment": "sms-sent",
                        "created_at": "2022-07-14 06:49:39",
                        "is_customer_notified": null,
                        "is_visible_on_front": 1,
                        "status": "cod_authorized"
                    }
                ],
                "total_item_count": 1,
                "total_qty_ordered": 1,
                "updated_at": "2022-07-20 01:55:03",
                "weight": 0,
                "full_name": "Test Customer",
                "increment_id": "77410290233",
                "platform_fee": 30.51,
                "payment_method": "Cash on Delivery/ Scan & Pay (Scan & Pay is only applicable for inside valley & Biratnagar customers)",
                "item_price": 270,
                "vendor_amount": 239.49,
                "order_date": "2022-07-14 06:49:39",
                "customer_details": "Test Customer, Sital Height, Lalitpur, Provinces No 3, 44703, 9800000000"
            }
        ]
    }
}
```

**Order List Filters**

* Nepali vendor must use `["cod_authorized", "prepaid_authorized"]` to fetch orders for fullfillment.
* Crossborder vendor must use `cb_confirmed` to fetch orders for fulfillment.

```
/api/sales/sales/order?page-page=20&page=1&filter={"status": ["cod_authorized", "prepaid_authorized"]}

/api/sales/sales/order?page-page=20&page=1&filter={"status": "cb_confirmed"}
```


### Single Sales Order View API

`API Endpoint`: /api/sales/sales/order/{{_id / increment_id}}

`API Endpoint`: /api/sales/sales/order/77410290233

`Method`: GET

**Response**

`HTTP_STATUS`: 200

```json
{
    "_id": "62cfbc9d586ecfda50f19ff5",
    "base_discount_amount": 0,
    "base_grand_total": 270,
    "base_subtotal": 270,
    "billing_address": {
        "address_type": "billing",
        "city": "Lalitpur",
        "country_id": "NP",
        "customer_address_id": 123,
        "email": "customer@sastodeal.com",
        "entity_id": 571216,
        "firstname": "Test",
        "lastname": "Customer",
        "parent_id": 286323,
        "postcode": "44703",
        "region": "Provinces No 3",
        "region_code": "Provinces No 3",
        "region_id": 2040,
        "street": [
            "Sital Height",
            "Near om itta bhatta"
        ],
        "telephone": "9800000000"
    },
    "created_at": "2022-07-20 01:55:03",
    "email": "customer@sastodeal.com",
    "firstname": "Test",
    "grand_total": 270,
    "items": [
        {
            "discount_amount": 0,
            "discount_percent": 0,
            "item_id": 458907,
            "name": "Meon Best Premium Quality Simple And Elegant Design Hot Case , Hot Pot, Roti Box Serve Casserole (2000 ml)",
            "original_price": 699,
            "price": 270,
            "qty_canceled": 0,
            "qty_invoiced": 0,
            "qty_ordered": 1,
            "qty_refunded": 0,
            "qty_shipped": 0,
            "row_total": 270,
            "sku": "sd-275846-637-greenplasticassu20",
            "weight": 0,
            "base_grand_total_amount": 270,
            "total_commission": 30.51,
            "actual_seller_amount": 239.49,
            "commission_rate": 11.3
        }
    ],
    "lastname": "Customer",
    "payment": {
        "additional_information": [
            "Cash on Delivery/ Scan & Pay (Scan & Pay is only applicable for inside valley & Biratnagar customers)",
            null
        ],
        "amount_ordered": 270,
        "method": "cashondelivery"
    },
    "shipping_address": {
        "address_type": "shipping",
        "city": "Lalitpur",
        "country_id": "NP",
        "customer_address_id": 32733,
        "email": "customer@sastodeal.com",
        "entity_id": 571215,
        "firstname": "Test",
        "lastname": "Customer",
        "parent_id": 286323,
        "postcode": "44703",
        "region": "Provinces No 3",
        "region_code": "Provinces No 3",
        "region_id": 2040,
        "street": [
            "Sital Height",
            "Near om itta bhatta"
        ],
        "telephone": "9800000000"
    },
    "state": "new",
    "status": "cod_authorized",
    "status_histories": [
        {
            "comment": "sms-sent",
            "created_at": "2022-07-14 06:49:39",
            "is_customer_notified": null,
            "is_visible_on_front": 1,
            "status": "cod_authorized"
        }
    ],
    "total_item_count": 1,
    "total_qty_ordered": 1,
    "updated_at": "2022-07-20 01:55:03",
    "weight": 0,
    "full_name": "Test Customer",
    "increment_id": "77410290233",
    "platform_fee": 30.51,
    "payment_method": "Cash on Delivery/ Scan & Pay (Scan & Pay is only applicable for inside valley & Biratnagar customers)",
    "item_price": 270,
    "vendor_amount": 239.49,
    "order_date": "2022-07-14 06:49:39",
    "customer_details": "Test Customer, Sital Height, Lalitpur, Provinces No 3, 44703, 9800000000"
}
```


## Bulk Order Status Change API

`API Endpoint`: /api/sales/order/updateable-status/{{increment_id}}

`API Endpoint`: /api/sales/order/updateable-status/77410290232

`Method`: POST

**Request**

```json
{
    "skus": [
        "sd-275846-637-greenplasticassu20"
    ],
    "status": "cb_ready_to_pickup",
    "comment": "readyo to pickup"
}
```

**Response**

`HTTP_STATUS`: 200

```json
{
    "title": "success",
    "status": 200,
    "detail": "Successfully updated."
}
```

* `cod_authorized` and `prepaid_authorized` orders will be only able to updated for `ready_to_pickup`.
* `cb_confirmed` order will only be able to updated for `cb_ready_to_pickup`.

| Order Status Code  | Description                  | Vendor Type        |
| ------------------ | ---------------------------- | ------------------ |
| cod_authorized     | Cash on delivery authorized  | Nepali vendor      |
| prepaid_authorized | Prepaid authorized           | Nepali vendor      |
| ready_to_pickup    | Ready to pickup              | Nepali vendor      |
| cb_confirmed       | Cross border confirmed       | Crossborder vendor |
| cb_ready_to_pickup | Cross border ready to pickup | Crossborder vendor |


## Bulk Order Cancel API

`API Endpoint`: /api/sales/cancelable-status/{{increment_id}}

`API Endpoint`: /api/sales/cancelable-status/77410290232

`Method`: POST

**Request**

```json
{
    "items": [
        {
            "sku": "sd-275846-637-greenplasticassu20",
            "reason": "size_out_of_stock"
        }
    ],
    "comment": "Not in inventory"
}
```

**Response**

`HTTP_STATUS`: 200

```json
{
    "title": "success",
    "status": 200,
    "detail": "Successfully updated."
}
```

**Cancel Reason Code List**

https://sastodealpvtltd-my.sharepoint.com/:x:/g/personal/bharat_sastodeal_com/EQe75DMc7F9CsoifEFWGj8EBQ-Wsn70etXniwzC9Rcewiw?e=G9JXi8



## Shop Global Order Tracking API
`API Endpoint`: /api/sales/fk/order/tracking

`Method`: POST

**Request**

```json
{
  "items": [
    {
      "item_id": 458906,
      "item_status": "SUCCESS",
      "tracking_number": "N69991415001",
      "tracking_type":"domestic or international", 
      "increment_id": "77410290232",
      "trackingList": [
        {
          "trackingManifestNo": "N69991412",
          "trackingDate": "27-06-2022",
          "trackingName": "NA",
          "trackingCode": "NA",
          "trackingOrigin": "Kathmandu - NEPAL",
          "trackingDestination": "",
          "trackingRemarks": null,
          "trackingTime": "0813"
        }
      ]
    }
  ]
}
```

**Response**

`HTTP_STATUS`: 200

```json
{
    "status": 200,
    "title": "Successfull",
    "detail": "Successfully Saved."
}
```