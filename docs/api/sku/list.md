# SKU List API

This API Lists all the SKUs of a Vendor in paginated format

## Method
GET

## Endpoint
    https://www.sastodeal.com/rest/V1/seller-products/{page_number_here}

## Request Header
    Authorization: Bearer {bearer_token_here}
    Content-Type: application/json

## Request Body
    keep empty

## Response
    {
        "items": [
            {
                "sku": "49.699-MMART",
                "name": "Meizan Corn Oil  2Lit Jar ",
                "price": "850.00",
                "special_price": "0.00",
                "special_from_date": null,
                "special_to_date": null,
                "stock_status": "1",
                "stock_quantity": "15"
            }
        ],
        "current_page": 1,
        "total_pages": 1
    }

# Examples
## C Sharp
    var client = new RestClient("https://www.sastodeal.com/rest/V1/seller-products/1");
    client.Timeout = -1;
    var request = new RestRequest(Method.GET);
    request.AddHeader("Authorization", "Bearer bearer_token_here");
    request.AddHeader("Content-Type", "application/json");
    IRestResponse response = client.Execute(request);
    Console.WriteLine(response.Content);

## PHP
    <?php

    $curl = curl_init();

    curl_setopt_array($curl, array(
    CURLOPT_URL => 'https://www.sastodeal.com/rest/V1/seller-products/1',
    CURLOPT_RETURNTRANSFER => true,
    CURLOPT_ENCODING => '',
    CURLOPT_MAXREDIRS => 10,
    CURLOPT_TIMEOUT => 0,
    CURLOPT_FOLLOWLOCATION => true,
    CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
    CURLOPT_CUSTOMREQUEST => 'GET',
    CURLOPT_HTTPHEADER => array(
            'Authorization: Bearer bearer_token_here',
            'Content-Type: application/json'
        ),
    ));

    $response = curl_exec($curl);

    curl_close($curl);
    echo $response;


## javascript
    var myHeaders = new Headers();
    myHeaders.append("Authorization", "Bearer bearer_token_here");
    myHeaders.append("Content-Type", "application/json");

    var requestOptions = {
    method: 'GET',
    headers: myHeaders,
    redirect: 'follow'
    };

    fetch("https://www.sastodeal.com/rest/V1/seller-products/1", requestOptions)
    .then(response => response.text())
    .then(result => console.log(result))
    .catch(error => console.log('error', error));