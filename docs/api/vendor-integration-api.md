# Seller Integration With Sastodeal - Beta

```
Current application that is not feature-complete and is not usually released to the public.
Developers are usually still deciding on what features the program should have at this stage of software development.
```


## Postman Collection URL

```
https://www.getpostman.com/collections/e11d8c7f41438ffc7e82
```


## Http Status Code

`200`: OK

`400`: Bad Request

`401`: Unauthorized

`403`: Forbidden

`404`: Not Found

`403`: Request Timeout

`413`: Request Entity Too Large

`429`: Too Many Requests

`500`: Internal Server Error

`504`: Service Unavailable


## Integration Login

`API Endpoint`: /api/auth/integration/login

`Method`: POST

**Request**

```json
{
    "username": "<integration_username>",
    "password": "<integration_password>",
    "session_name": "Integration test session"
}
```

**Response**

`HTTP_STATUS`: 200

```json
{
    "session_token": "<session_token>",
    "refresh_token": "<refresh_token>",
    "token": "<jwt_auth_token>"
}
```

* `token` need to be add as `Bearer` token for Authorization in each and evey request.

**Error Response**

`HTTP_STATUS`: 401

```json
{
    "code": 401,
    "message": "Expired JWT Token"
}
```

**Error Response**

`HTTP_STATUS`: 403

```json
{
  "title": "An error occurred",
  "status": 403,
  "detail": "You do not have permission to access this resource."
}
```


## Applying Filter in List API

* `per-page`: specifies the maximum number of items to return. The value must be an integer. If the per-page is not specified, the system returns 20 matches.
* `page`: specifies the current page.
* `filter`: specifies filter which should be in JSON format

**Example List Request URL**

```
/api/pim/product?page-page=20&page=1&filter={"status": "enable"}
```


## Product API


### Create Simple Product API

`API Endpoint`: /api/pim/catalog/product/create

`Method`: POST

**Request**

```json
{
    "seller_sku": "w-tshirt-for-wm-2000",
    "type_id": "simple",
    "category": 1462,
    "name": "White Tshirt For Women/Men",
    "status": "enable",
    "price": 500,
    "quantity": 500,
    "special_from_date": "2021-08-14 00:00:00",
    "special_price": 250,
    "special_to_date": "2025-01-01 00:00:00",
    "description": "This is long description text",
    "short_description": "This is short_description text",
    "brand_name": "No brand",
    "color": "Black",
    "fit": "Relaxed fit",
    "ideal_for": "Men",
    "main_image": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000BEIGE.jpg",
    "image1": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000BROWN.jpg",
    "image2": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000GREEN.jpg",
    "image3": null,
    "image4": null,
    "image5": null,
    "image6": null,
    "image7": null,
    "image8": null,
    "materials": "Cotton",
    "occasion": "Work",
    "product_type": "Tee",
    "sleeves": "Half",
    "pattern": "",
    "length": "",
    "warranty_type": "No Warranty",
    "warranty_period": "",
    "return_exchange": "Yes",
    "whats_in_the_box": "",
    "weight": 1.5,
    "product_has_weight": "",
    "meta_keyword": "Apparel,Sports wear,Tshirt,Tees,Pants,Joggers",
    "meta_title": "White Tee For Women/Men|T-shirts|Sastodeal",
    "seller_attributes": [
        {
            "code": "new_one_attr",
            "label": "New one Attr",
            "value": "Value 1"
        },
        {
            "code": "new_two_attr",
            "label": "New two Attr",
            "value": "Value 2"
        }
    ]
}
```

**Response**

`HTTP_STATUS`: 200

```json
{
    "detail": "Successfully saved changes.",
    "item": {
        "_id": "62d748cf586ecfda503d6584",
        "sku": "sd-275846-1462-w-tshirt-for-wm-2000",
        "brand_name": "No brand",
        "category": [
            1456,
            1459,
            1462
        ],
        "color": "Black",
        "created_at": "2022-07-20 00:14:07",
        "description": "This is long description text",
        "fit": "Relaxed fit",
        "gallery": [
            {
                "media_type": "image",
                "title": "",
                "path_name": "/media/seller/275846/s/h/s/b/e/SHS1000BEIGE.jpg",
                "types": [
                    "image",
                    "small_image",
                    "thumbnail"
                ]
            },
            {
                "media_type": "image",
                "title": "",
                "path_name": "/media/seller/275846/s/h/s/b/r/SHS1000BROWN.jpg",
                "types": []
            },
            {
                "media_type": "image",
                "title": "",
                "path_name": "/media/seller/275846/s/h/s/g/r/SHS1000GREEN.jpg",
                "types": []
            }
        ],
        "ideal_for": "Men",
        "image1": "",
        "image2": "",
        "image3": null,
        "image4": null,
        "image5": null,
        "image6": null,
        "image7": null,
        "image8": null,
        "inventory": [
            {
                "source_code": "KTDU",
                "quantity": 500
            }
        ],
        "length": "",
        "main_image": "",
        "materials": "Cotton",
        "meta_keyword": "Apparel,Sports wear,Tshirt,Tees,Pants,Joggers",
        "meta_title": "White Tee For Women/Men|T-shirts|Sastodeal",
        "name": "White Tshirt For Women/Men",
        "occasion": "Work",
        "pattern": "",
        "price": 500,
        "product_has_weight": "",
        "product_type": "Tee",
        "return_exchange": "Yes",
        "seller_attributes": [
            {
                "code": "new_one_attr",
                "label": "New one Attr",
                "value": "Value 1"
            },
            {
                "code": "new_two_attr",
                "label": "New two Attr",
                "value": "Value 2"
            }
        ],
        "seller_sku": "w-tshirt-for-wm-2000",
        "short_description": "This is short_description text",
        "sleeves": "Half",
        "special_from_date": "2021-08-14 00:00:00",
        "special_price": 250,
        "special_to_date": "2025-01-01 00:00:00",
        "status": "enable",
        "type_id": "simple",
        "updated_at": "2022-07-20 00:14:07",
        "url_key": "sd-275846-1462-w-tshirt-for-wm-2000",
        "warranty_period": "",
        "warranty_type": "No Warranty",
        "weight": 1.5,
        "whats_in_the_box": ""
    }
}
```


### Create Variable Product API

`API Endpoint`: /api/pim/catalog/product/create

`Method`: POST

**Request**

```json
{
    "seller_sku": "cf-tshirt-for-wm-4000",
    "type_id": "variable",
    "category": 1462,
    "name": "Color full TShirt For Women/Men",
    "status": "enable",
    "variable_products": [
        {
            "name": "Black TShirt For Women/Men",
            "seller_sku": "cf-tshirt-for-wm-4000-b",
            "status": "enable",
            "main_image": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000BEIGE.jpg",
            "image1": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000BROWN.jpg",
            "image2": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000GREEN.jpg",
            "image3": null,
            "image4": null,
            "image5": null,
            "image6": null,
            "image7": null,
            "image8": null,
            "price": 800,
            "quantity": 500,
            "special_from_date": "2021-08-14 00:00:00",
            "special_price": 720,
            "special_to_date": "2025-01-01 00:00:00",
            "color": "Black"
        },
        {
            "name": "White TShirt For Women/Men",
            "seller_sku": "cf-tshirt-for-wm-4000-w",
            "status": "enable",
            "main_image": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000BEIGE.jpg",
            "image1": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000BROWN.jpg",
            "image2": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000GREEN.jpg",
            "image3": null,
            "image4": null,
            "image5": null,
            "image6": null,
            "image7": null,
            "image8": null,
            "price": 800,
            "quantity": 500,
            "special_from_date": "2021-08-14 00:00:00",
            "special_price": 720,
            "special_to_date": "2025-01-01 00:00:00",
            "color": "White"
        }
    ],
    "brand_name": "No brand",
    "description": "This is long description text",
    "short_description": "This is short_description text",
    "fit": "Relaxed fit",
    "ideal_for": "Men",
    "main_image": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000BEIGE.jpg",
    "image1": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000BROWN.jpg",
    "image2": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000GREEN.jpg",
    "image3": null,
    "image4": null,
    "image5": null,
    "image6": null,
    "image7": null,
    "image8": null,
    "materials": "Cotton",
    "occasion": "Work",
    "product_type": "Tee",
    "sleeves": "Half",
    "pattern": "",
    "length": "",
    "warranty_type": "No Warranty",
    "warranty_period": "",
    "return_exchange": "Yes",
    "whats_in_the_box": "",
    "weight": 1.5,
    "product_has_weight": "",
    "meta_keyword": "Apparel,Sports wear,Tshirt,Tees,Pants,Joggers",
    "meta_title": "Color full Tee For Women/Men|T-shirts|Sastodeal",
    "seller_attributes": [
        {
            "code": "new_one_attr",
            "label": "New one Attr",
            "value": "Value 1"
        },
        {
            "code": "new_two_attr",
            "label": "New two Attr",
            "value": "Value 2"
        }
    ]
}
```

**Response**

`HTTP_STATUS`: 200

```json
{
    "detail": "Successfully saved changes.",
    "item": {
        "_id": "62d74a12586ecfda503d7dc7",
        "sku": "sd-275846-1462-cf-tshirt-for-wm-4000",
        "brand_name": "No brand",
        "category": [
            1456,
            1459,
            1462
        ],
        "created_at": "2022-07-20 00:19:30",
        "description": "This is long description text",
        "fit": "Relaxed fit",
        "gallery": [
            {
                "media_type": "image",
                "title": "",
                "path_name": "/media/seller/275846/s/h/s/b/e/SHS1000BEIGE.jpg",
                "types": [
                    "image",
                    "small_image",
                    "thumbnail"
                ]
            },
            {
                "media_type": "image",
                "title": "",
                "path_name": "/media/seller/275846/s/h/s/b/r/SHS1000BROWN.jpg",
                "types": []
            },
            {
                "media_type": "image",
                "title": "",
                "path_name": "/media/seller/275846/s/h/s/g/r/SHS1000GREEN.jpg",
                "types": []
            }
        ],
        "ideal_for": "Men",
        "image1": "",
        "image2": "",
        "image3": null,
        "image4": null,
        "image5": null,
        "image6": null,
        "image7": null,
        "image8": null,
        "length": "",
        "main_attributes": [],
        "main_image": "",
        "materials": "Cotton",
        "meta_keyword": "Apparel,Sports wear,Tshirt,Tees,Pants,Joggers",
        "meta_title": "Color full Tee For Women/Men|T-shirts|Sastodeal",
        "name": "Color full TShirt For Women/Men",
        "occasion": "Work",
        "pattern": "",
        "product_has_weight": "",
        "product_type": "Tee",
        "return_exchange": "Yes",
        "seller_attributes": [
            {
                "code": "new_one_attr",
                "label": "New one Attr",
                "value": "Value 1"
            },
            {
                "code": "new_two_attr",
                "label": "New two Attr",
                "value": "Value 2"
            }
        ],
        "seller_sku": "cf-tshirt-for-wm-4000",
        "short_description": "This is short_description text",
        "sleeves": "Half",
        "status": "enable",
        "type_id": "variable",
        "updated_at": "2022-07-20 00:19:30",
        "url_key": "sd-275846-1462-cf-tshirt-for-wm-4000",
        "variable_products": [
            {
                "name": "Black TShirt For Women/Men",
                "seller_sku": "cf-tshirt-for-wm-4000-b",
                "status": "enable",
                "main_image": "",
                "image1": "",
                "image2": "",
                "image3": null,
                "image4": null,
                "image5": null,
                "image6": null,
                "image7": null,
                "image8": null,
                "price": 800,
                "special_from_date": "2021-08-14 00:00:00",
                "special_price": 720,
                "special_to_date": "2025-01-01 00:00:00",
                "color": "Black",
                "inventory": [
                    {
                        "source_code": "KTDU",
                        "quantity": 500
                    }
                ],
                "sku": "sd-275846-1462-cf-tshirt-for-wm-4000-b",
                "url_key": "sd-275846-1462-cf-tshirt-for-wm-4000-b",
                "gallery": [
                    {
                        "media_type": "image",
                        "title": "",
                        "path_name": "/media/seller/275846/s/h/s/b/e/SHS1000BEIGE.jpg",
                        "types": [
                            "image",
                            "small_image",
                            "thumbnail"
                        ]
                    },
                    {
                        "media_type": "image",
                        "title": "",
                        "path_name": "/media/seller/275846/s/h/s/b/r/SHS1000BROWN.jpg",
                        "types": []
                    },
                    {
                        "media_type": "image",
                        "title": "",
                        "path_name": "/media/seller/275846/s/h/s/g/r/SHS1000GREEN.jpg",
                        "types": []
                    }
                ]
            },
            {
                "name": "White TShirt For Women/Men",
                "seller_sku": "cf-tshirt-for-wm-4000-w",
                "status": "enable",
                "main_image": "",
                "image1": "",
                "image2": "",
                "image3": null,
                "image4": null,
                "image5": null,
                "image6": null,
                "image7": null,
                "image8": null,
                "price": 800,
                "special_from_date": "2021-08-14 00:00:00",
                "special_price": 720,
                "special_to_date": "2025-01-01 00:00:00",
                "color": "White",
                "inventory": [
                    {
                        "source_code": "KTDU",
                        "quantity": 500
                    }
                ],
                "sku": "sd-275846-1462-cf-tshirt-for-wm-4000-w",
                "url_key": "sd-275846-1462-cf-tshirt-for-wm-4000-w",
                "gallery": [
                    {
                        "media_type": "image",
                        "title": "",
                        "path_name": "/media/seller/275846/s/h/s/b/e/SHS1000BEIGE.jpg",
                        "types": [
                            "image",
                            "small_image",
                            "thumbnail"
                        ]
                    },
                    {
                        "media_type": "image",
                        "title": "",
                        "path_name": "/media/seller/275846/s/h/s/b/r/SHS1000BROWN.jpg",
                        "types": []
                    },
                    {
                        "media_type": "image",
                        "title": "",
                        "path_name": "/media/seller/275846/s/h/s/g/r/SHS1000GREEN.jpg",
                        "types": []
                    }
                ]
            }
        ],
        "warranty_period": "",
        "warranty_type": "No Warranty",
        "weight": 1.5,
        "whats_in_the_box": ""
    }
}
```


### Product List API

`API Endpoint`: /api/pim/catalog/product

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
                "_id": "62d748cf586ecfda503d6584",
                "sku": "sd-275846-1462-w-tshirt-for-wm-2000",
                "brand_name": "No brand",
                "category": [
                    1456,
                    1459,
                    1462
                ],
                "color": "Black",
                "created_at": "2022-07-20 00:14:07",
                "description": "This is long description text",
                "fit": "Relaxed fit",
                "gallery": [
                    {
                        "media_type": "image",
                        "title": "",
                        "path_name": "/media/seller/275846/s/h/s/b/e/SHS1000BEIGE.jpg",
                        "types": [
                            "image",
                            "small_image",
                            "thumbnail"
                        ]
                    },
                    {
                        "media_type": "image",
                        "title": "",
                        "path_name": "/media/seller/275846/s/h/s/b/r/SHS1000BROWN.jpg",
                        "types": []
                    },
                    {
                        "media_type": "image",
                        "title": "",
                        "path_name": "/media/seller/275846/s/h/s/g/r/SHS1000GREEN.jpg",
                        "types": []
                    }
                ],
                "ideal_for": "Men",
                "image1": "",
                "image2": "",
                "image3": null,
                "image4": null,
                "image5": null,
                "image6": null,
                "image7": null,
                "image8": null,
                "inventory": [
                    {
                        "source_code": "KTDU",
                        "quantity": 500
                    }
                ],
                "length": "",
                "main_image": "",
                "materials": "Cotton",
                "meta_keyword": "Apparel,Sports wear,Tshirt,Tees,Pants,Joggers",
                "meta_title": "White Tee For Women/Men|T-shirts|Sastodeal",
                "name": "White Tshirt For Women/Men",
                "occasion": "Work",
                "pattern": "",
                "price": 500,
                "product_has_weight": "",
                "product_type": "Tee",
                "return_exchange": "Yes",
                "seller_attributes": [
                    {
                        "code": "new_one_attr",
                        "label": "New one Attr",
                        "value": "Value 1"
                    },
                    {
                        "code": "new_two_attr",
                        "label": "New two Attr",
                        "value": "Value 2"
                    }
                ],
                "seller_sku": "w-tshirt-for-wm-2000",
                "short_description": "This is short_description text",
                "sleeves": "Half",
                "special_from_date": "2021-08-14 00:00:00",
                "special_price": 250,
                "special_to_date": "2025-01-01 00:00:00",
                "status": "enable",
                "type_id": "simple",
                "updated_at": "2022-07-20 00:14:07",
                "url_key": "sd-275846-1462-w-tshirt-for-wm-2000",
                "warranty_period": "",
                "warranty_type": "No Warranty",
                "weight": 1.5,
                "whats_in_the_box": ""
            }
        ]
    }
}
```


### Update Product API

`API Endpoint`: /api/pim/catalog/product/{{sku / seller_sku}}

`API Endpoint`: /api/pim/catalog/product/w-tshirt-for-wm-2000

`Method`: POST

**Request**

```json
{
    "seller_sku": "w-tshirt-for-wm-2000",
    "type_id": "simple",
    "category": 1462,
    "name": "White Tshirt For Women/Men - updated",
    "status": "enable",
    "price": 500,
    "quantity": 500,
    "special_from_date": "2021-08-14 00:00:00",
    "special_price": 250,
    "special_to_date": "2025-01-01 00:00:00",
    "description": "This is long description text",
    "short_description": "This is short_description text",
    "brand_name": "No brand",
    "color": "Black",
    "fit": "Relaxed fit",
    "ideal_for": "Men",
    "main_image": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000BEIGE.jpg",
    "image1": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000BROWN.jpg",
    "image2": "https://cdn.sastodeal.com/catalog/product/18678/SHACKET(SHS1000)-01/SHS1000GREEN.jpg",
    "image3": null,
    "image4": null,
    "image5": null,
    "image6": null,
    "image7": null,
    "image8": null,
    "materials": "Cotton",
    "occasion": "Work",
    "product_type": "Tee",
    "sleeves": "Half",
    "pattern": "",
    "length": "",
    "warranty_type": "No Warranty",
    "warranty_period": "",
    "return_exchange": "Yes",
    "whats_in_the_box": "",
    "weight": 1.5,
    "product_has_weight": "",
    "meta_keyword": "Apparel,Sports wear,Tshirt,Tees,Pants,Joggers",
    "meta_title": "White Tee For Women/Men|T-shirts|Sastodeal",
    "seller_attributes": [
        {
            "code": "new_one_attr",
            "label": "New one Attr",
            "value": "Value 1"
        },
        {
            "code": "new_two_attr",
            "label": "New two Attr",
            "value": "Value 2"
        }
    ]
}
```

**Response**

`HTTP_STATUS`: 200

```json
{
    "detail": "Successfully saved changes.",
    "item": {
        "_id": "62d748cf586ecfda503d6584",
        "sku": "sd-275846-1462-w-tshirt-for-wm-2000",
        "brand_name": "No brand",
        "category": [
            1456,
            1459,
            1462
        ],
        "color": "Black",
        "created_at": "2022-07-20 00:14:07",
        "description": "This is long description text",
        "fit": "Relaxed fit",
        "gallery": [
            {
                "media_type": "image",
                "title": "",
                "path_name": "/media/seller/275846/s/h/s/b/e/SHS1000BEIGE.jpg",
                "types": [
                    "image",
                    "small_image",
                    "thumbnail"
                ]
            },
            {
                "media_type": "image",
                "title": "",
                "path_name": "/media/seller/275846/s/h/s/b/r/SHS1000BROWN.jpg",
                "types": []
            },
            {
                "media_type": "image",
                "title": "",
                "path_name": "/media/seller/275846/s/h/s/g/r/SHS1000GREEN.jpg",
                "types": []
            }
        ],
        "ideal_for": "Men",
        "image1": "",
        "image2": "",
        "image3": null,
        "image4": null,
        "image5": null,
        "image6": null,
        "image7": null,
        "image8": null,
        "inventory": [
            {
                "source_code": "KTDU",
                "quantity": 500
            }
        ],
        "length": "",
        "main_image": "",
        "materials": "Cotton",
        "meta_keyword": "Apparel,Sports wear,Tshirt,Tees,Pants,Joggers",
        "meta_title": "White Tee For Women/Men|T-shirts|Sastodeal",
        "name": "White Tshirt For Women/Men - updated",
        "occasion": "Work",
        "pattern": "",
        "price": 500,
        "product_has_weight": "",
        "product_type": "Tee",
        "return_exchange": "Yes",
        "seller_attributes": [
            {
                "code": "new_one_attr",
                "label": "New one Attr",
                "value": "Value 1"
            },
            {
                "code": "new_two_attr",
                "label": "New two Attr",
                "value": "Value 2"
            }
        ],
        "seller_sku": "w-tshirt-for-wm-2000",
        "short_description": "This is short_description text",
        "sleeves": "Half",
        "special_from_date": "2021-08-14 00:00:00",
        "special_price": 250,
        "special_to_date": "2025-01-01 00:00:00",
        "status": "enable",
        "type_id": "simple",
        "updated_at": "2022-07-20 00:31:12",
        "url_key": "sd-275846-1462-w-tshirt-for-wm-2000",
        "warranty_period": "",
        "warranty_type": "No Warranty",
        "weight": 1.5,
        "whats_in_the_box": ""
    }
}
```


### Single Product View API

`API Endpoint`: /api/pim/catalog/product/{{sku / seller_sku}}

`API Endpoint`: /api/pim/catalog/product/w-tshirt-for-wm-2000

`Method`: GET

**Response**

`HTTP_STATUS`: 200

```json
{
    "item": {
        "_id": "62d748cf586ecfda503d6584",
        "sku": "sd-275846-1462-w-tshirt-for-wm-2000",
        "brand_name": "No brand",
        "category": [
            1456,
            1459,
            1462
        ],
        "color": "Black",
        "created_at": "2022-07-20 00:14:07",
        "description": "This is long description text",
        "fit": "Relaxed fit",
        "gallery": [
            {
                "media_type": "image",
                "title": "",
                "path_name": "/media/seller/275846/s/h/s/b/e/SHS1000BEIGE.jpg",
                "types": [
                    "image",
                    "small_image",
                    "thumbnail"
                ]
            },
            {
                "media_type": "image",
                "title": "",
                "path_name": "/media/seller/275846/s/h/s/b/r/SHS1000BROWN.jpg",
                "types": []
            },
            {
                "media_type": "image",
                "title": "",
                "path_name": "/media/seller/275846/s/h/s/g/r/SHS1000GREEN.jpg",
                "types": []
            }
        ],
        "ideal_for": "Men",
        "image1": "",
        "image2": "",
        "image3": null,
        "image4": null,
        "image5": null,
        "image6": null,
        "image7": null,
        "image8": null,
        "inventory": [
            {
                "source_code": "KTDU",
                "quantity": 500
            }
        ],
        "length": "",
        "main_image": "",
        "materials": "Cotton",
        "meta_keyword": "Apparel,Sports wear,Tshirt,Tees,Pants,Joggers",
        "meta_title": "White Tee For Women/Men|T-shirts|Sastodeal",
        "name": "White Tshirt For Women/Men - updated",
        "occasion": "Work",
        "pattern": "",
        "price": 500,
        "product_has_weight": "",
        "product_type": "Tee",
        "return_exchange": "Yes",
        "seller_attributes": [
            {
                "code": "new_one_attr",
                "label": "New one Attr",
                "value": "Value 1"
            },
            {
                "code": "new_two_attr",
                "label": "New two Attr",
                "value": "Value 2"
            }
        ],
        "seller_sku": "w-tshirt-for-wm-2000",
        "short_description": "This is short_description text",
        "sleeves": "Half",
        "special_from_date": "2021-08-14 00:00:00",
        "special_price": 250,
        "special_to_date": "2025-01-01 00:00:00",
        "status": "enable",
        "type_id": "simple",
        "updated_at": "2022-07-20 00:31:12",
        "url_key": "sd-275846-1462-w-tshirt-for-wm-2000",
        "warranty_period": "",
        "warranty_type": "No Warranty",
        "weight": 1.5,
        "whats_in_the_box": ""
    }
}
```


## Bulk Product Price Update API

`API Endpoint`: /api/pim/catalog/product-bulk/price

`Method`: POST

**Request**

```json
{
    "items": [
        {
            "seller_sku": "w-tshirt-for-wm-2000",
            "price": 400
        },
        {
            "sku": "sd-275846-1462-cf-tshirt-for-wm-4000-b",
            "price": 600,
            "special_price": 500,
            "special_from_date": "2021-07-16 00:00:00",
            "special_to_date": "2024-07-16 00:00:00"
        },
        {
            "seller_sku": "cf-tshirt-for-wm-4000-w",
            "price": 700,
            "special_price": null,
            "special_from_date": null,
            "special_to_date": null
        }
    ]
}
```

**Response**

`HTTP_STATUS`: 200

```json
{
    "detail": "Successfully saved changes."
}
```

**Error Response**

`HTTP_STATUS`: 400

```json
{
    "title": "An error occurred in few records",
    "status": 400,
    "detail": "An error occurred in few records",
    "bulk_errors": [
        {
            "array_key": 2,
            "array_data": {
                "seller_sku": "cf-tshirt-for-wm-4000-w-non-existing",
                "price": 700,
                "special_price": null,
                "special_from_date": null,
                "special_to_date": null
            },
            "errors": {
                "increment_id": {
                    "errors": [
                        "cf-tshirt-for-wm-4000-w-non-existing Seller sku not exist."
                    ]
                }
            }
        }
    ]
}
```

**About bulk price update API**

* `sku` or `seller_sku` can be used to update product price.
* Directly `sku` or `seller_sku` of variable product can be used.
* If the value is `null`, field will be unset.

| Field Name        |  Description |
| :---              | :--- |
sku                 | Sku of Product
seller_sku          | Sku provided by seller
price               | Price of Product
special_price       | Discount price offered by seller. To unset value need to pass `null` value.
special_to_date     | Discount Price start date, suppoted format (yyyy-mm-dd h:i:s), To unset value need to pass `null` value.
special_from_date   | Discount Price to date suppoted format (yyyy-mm-dd h:i:s) To unset value need to pass `null` value.


## Bulk Product Stock Update API

`API Endpoint`: /api/pim/catalog/product-bulk/stock

`Method`: POST

**Request**

```json
{
    "items": [
        {
            "seller_sku": "w-tshirt-for-wm-2000",
            "quantity": 10
        },
        {
            "sku": "sd-275846-1462-cf-tshirt-for-wm-4000-b",
            "quantity": 20
        }
    ]
}
```

**Response**

`HTTP_STATUS`: 200

```json
{
    "detail": "Successfully saved changes."
}
```

**Error Response**

`HTTP_STATUS`: 400

```json
{
    "title": "An error occurred in few records",
    "status": 400,
    "detail": "An error occurred in few records",
    "bulk_errors": [
        {
            "array_key": 2,
            "array_data": {
                "seller_sku": "cf-tshirt-for-wm-4000-w-non-existing",
                "quantity": 30
            },
            "errors": {
                "general": {
                    "errors": [
                        "Couldn't find document to update."
                    ]
                }
            }
        }
    ]
}
```

**About bulk stock update API**

* `sku` or `seller_sku` can be used to update product price.
* Directly `sku` or `seller_sku` of variable product can be used.
* If the value is `null`, field will be unset.

| Field Name        |  Description |
| :---              | :--- |
sku                 | Sku of Product
seller_sku          | Sku provided by seller
quantity            | Stock quantity of Product


## Sales Order API


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

| Order Status Code | Description | Vendor Type |
| ---- | ---- | ---- |
| cod_authorized | Cash on delivery authorized | Nepali vendor |
| prepaid_authorized | Prepaid authorized | Nepali vendor |
| ready_to_pickup | Ready to pickup | Nepali vendor |
| cb_confirmed | Cross border confirmed | Crossborder vendor |
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
      "increment_id": "77410290232",
      "tracking_type":"domestic or international", 
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
