# Bulk Inventory, Price, Special Price Update API

This API Bulk Updates Inventory, Price, Special price and Special Price From Date and Special Price To date

## Method
GET

## Endpoint
    https://www.sastodeal.com/rest/V1/seller-products/update

## Request Header
    Authorization: Bearer {bearer_token_here}
    Content-Type: application/json

## Request Body
    {
        "products" : [
            {
                "sku": "53.34",
                "price": "1800.01",
                "special_price": "1660.01",
                "special_from_date": "2021-05-02 00:00:00",
                "special_to_date": "2022-05-02 00:00:00",
                 "stock_quantity": "98"
            }
        ]
    }


## Response
response: message of success or failure due to products not belonging to this seller
* This is WIP and will be modified in the next release*

# Examples
## C Sharp
    var json_request_here = "Add the json request string here";
    var client = new RestClient("https://www.sastodeal.com/rest/V1/seller-products/update");
    client.Timeout = -1;
    var request = new RestRequest(Method.POST);
    request.AddHeader("Authorization", "Bearer {bearer_token_here}");
    request.AddHeader("Content-Type", "application/json");
    request.AddParameter("application/json", json_request_here,  ParameterType.RequestBody);
    IRestResponse response = client.Execute(request);
    Console.WriteLine(response.Content);
## PHP
    <?php

    $json_string_here = "add json request string here";

    $curl = curl_init();

    curl_setopt_array($curl, array(
        CURLOPT_URL => 'https://www.sastodeal.com/rest/V1/seller-products/update',
        CURLOPT_RETURNTRANSFER => true,
        CURLOPT_ENCODING => '',
        CURLOPT_MAXREDIRS => 10,
        CURLOPT_TIMEOUT => 0,
        CURLOPT_FOLLOWLOCATION => true,
        CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
        CURLOPT_CUSTOMREQUEST => 'POST',
        CURLOPT_POSTFIELDS => $json_string_here,
        CURLOPT_HTTPHEADER => array(
            'Authorization: Bearer {bearer_token_here}',
            'Content-Type: application/json'
        ),
    ));

    $response = curl_exec($curl);

    curl_close($curl);
    echo $response;

## javascript
    var json_string_here = "add json request string here";

    var myHeaders = new Headers();
    
    myHeaders.append("Authorization", "Bearer {bearer_token_here}");
    myHeaders.append("Content-Type", "application/json");

    var raw = JSON.stringify(json_string_here);

    var requestOptions = {
        method: 'POST',
        headers: myHeaders,
        body: raw,
        redirect: 'follow'
    };

    fetch("https://www.sastodeal.com/rest/V1/seller-products/update", requestOptions)
        .then(response => response.text())
        .then(result => console.log(result))
        .catch(error => console.log('error', error));