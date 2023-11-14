# ajax-api-basic-auth-post-request
 
JavaScript class that sends an Ajax POST request with 2 parameters to a third-party API with basic authentication and receives a data object in the postback.

To use this class, you would first create an instance of it, passing in your username, password, API URL, and request parameters. Then, you would call the send() method. The send() method will handle sending the request and calling the success or error callback function, depending on the outcome of the request.

    const username = 'my_username';
    const password = 'my_password';
    const apiUrl = 'https://api.example.com/endpoint';
    const parameters = {
    name: 'John Doe',
    age: 30,
    };

    const ajaxPost = new BasicAuthAjaxPost(username, password, apiUrl, parameters);

    ajaxPost.onSuccess = (responseDataObject) => {
    // Success!
    console.log(responseDataObject);
    };

    ajaxPost.onError = (errorMessage) => {
    // Error!
    console.error(errorMessage);
    };

    ajaxPost.send();

This code will send an Ajax POST request to the https://api.example.com/endpoint endpoint with the following parameters:

    {
        "name": "John Doe",
        "age": 30
    }

The request will be authenticated with basic authentication using the username and password variables.

If the request is successful, the onSuccess() callback function will be called with the response data object. The response data object will be a JSON object containing the data returned by the API.

If the request fails, the onError() callback function will be called with an error message.