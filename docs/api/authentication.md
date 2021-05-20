# Vendor Authentication API

Sastodeal Vendor APIs uses [Bearer Token for authentication](https://swagger.io/docs/specification/authentication/bearer-authentication/)

## How to make a request
### Endpoint
    https://www.sastodeal.com/rest/V1/integration/customer/token

### Request
    Body Type: Form Data OR Multi-Part Form Data
    username {username_text}
    password {password_text}

### Response
    *Bearer token with a JSON String which looks like:*
    "g4q0ljyzmynjbcq1m8ek1h7k3h75tflz"

# Examples
## C Sharp
    var client = new RestClient("https://www.sastodeal.com/rest/V1/integration/customer/token");
    client.Timeout = -1;
    var request = new RestRequest(Method.POST);
    request.AlwaysMultipartFormData = true;
    request.AddParameter("username", "youremail@domain.com");
    request.AddParameter("password", "yourpasshere");
    IRestResponse response = client.Execute(request);
    Console.WriteLine(response.Content);

## PHP
    <?php

    $curl = curl_init();

    curl_setopt_array($curl, array(
        CURLOPT_URL => 'https://www.sastodeal.com/rest/V1/integration/customer/token',
        CURLOPT_RETURNTRANSFER => true,
        CURLOPT_ENCODING => '',
        CURLOPT_MAXREDIRS => 10,
        CURLOPT_TIMEOUT => 0,
        CURLOPT_FOLLOWLOCATION => true,
        CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
        CURLOPT_CUSTOMREQUEST => 'POST',
        CURLOPT_POSTFIELDS => array(
                'username' => 'youremail@domain.com',
                'password' => 'yourpasshere'
            )
    ));

    $response = curl_exec($curl);

    curl_close($curl);
    echo $response;

## javascript
    var myHeaders = new Headers();
   
    var formdata = new FormData();
    formdata.append("username", "youremail@domain.com");
    formdata.append("password", "yourpasshere");

    var requestOptions = {
        method: 'POST',
        headers: myHeaders,
        body: formdata,
        redirect: 'follow'
    };

    fetch("https://www.sastodeal.com/rest/V1/integration/customer/token", requestOptions)
    .then(response => response.text())
    .then(result => console.log(result))
    .catch(error => console.log('error', error));