<em><h2>What is a POST Request?</h2></em>
<p>A POST is an HTTP Verb similar to a GET request, this specifies that a client is posting data on the given Endpoint. A POST request is a method that is used when we need to send some additional information inside the body of the request to the server. When we send a POST request we generally intend to have some modification at the server such as updation, deletion, or addition. One of the classic example of a POST request is the Login page. When you first Sign Up for anything, let's say Facebook, you send your personal information such as a password to the server. The server creates a new account with the same details and that account is added permanently on the Facebook server. You just created a new resource on to the server. POST requests are very popular and are mostly used whenever you are sending some sensitive information such as submitting a form or sending sensitive information to the server.</p>
<p>In this tutorial, we will explore different features of POST Requests and how we can create them in Postman. Before we will try to use an example to get a clear idea about a POST Request.</p>

<em><h2>POST Request in Postman</h2> </em>
<p>Every REST endpoint has its own HTTP verb associated with it. If an endpoint specifies that it should be called using the POST HTTP verb, then clients are bound to call the Endpoint with POST HTTP verb only. Let's first check what happens when we request the GET method instead of the POST method for a POST Endpoint. Also to check what happens when we do POST Request without Body.</p>

<em><h3>GET Request on POST Endpoint</h3></em>
<p>1.Use the API <em>http://restapi.demoqa.com/customer/register</em> (This API is used for registering a new customer) in the Postman endpoint bar and press Send. Make sure that GET is selected in the Method type dropdown.</p>
<img src="https://www.toolsqa.com/gallery/Postman/1.POST%20Request%20in%20Postman.png">
<p>2.See the HTTP status code, it will be 405 Method not allowed. Which means that we are hitting the endpoint with incorrect method type. The below image shows the details.</p>
<img src="https://www.toolsqa.com/gallery/Postman/2.IncorrectMethodTypeStatusCode.png">
<p>3.See the response below under the Body tab and focus on fault error.</p>
<img src="https://www.toolsqa.com/gallery/Postman/3.Customer_API_Example_Response.png">
<p>It means that the method type we used is not valid and another method type is expected. So we will try to change that and see if we get the correct response.</p>
<br>
<h3><em>POST Request without Body</em></h3>
<p>1.Change the method type to POST and press SEND</p>
<img src="https://www.toolsqa.com/gallery/Postman/4.Customer_API_Example_Change_Method_Type.png">
<p>2.Now, look at the Response Body and Response Status code.</p>
<img src="https://www.toolsqa.com/gallery/Postman/5.Customer_API_Example_POST_Response.png">
<p>Fault Invalid Post Request means that the post data that we entered is not valid. Recall that we add the information inside the body of the request, so we need to enter something into the request body and see if that format matches the format expected. Also, you can see the status code which says 400 BAD Request. It means that the request parameters are not matching the server parameters to get a response.</p>
<h3><em>Post Request in Postman</em></h3>
<p>1.Now let us add a Request Body to our POST request. Every Endpoint will be documented with what kind of Method type and the format of the body that it expects. Let us see what body this request expects and how to add it. For that click on the Body tab</p>
<img src="https://www.toolsqa.com/gallery/Postman/6.Customer_API_Example_Body.png">
<p>2.Click on raw and select format type as JSON, since we have to send the incorrect format that the server expects.</p>
<img src="https://www.toolsqa.com/gallery/Postman/7.Raw_Json_Select.png">
<p>3.This endpoint expects a Json body which contains the details of the new user. Below is a sample Json body. Copy and Paste the following in the body tab of Postman.</p>

    {

      * “FirstName”: “value”*
      
      * “LastName : “value”,*
      
      “UserName : “value”,
      
      “Password”: “value”,
      
      “Email”: “Value”
      
      }

<p>Change the attribute value to any value you want (take reference from the below image).</p>
<img src="https://www.toolsqa.com/gallery/Postman/8.Customer_API_Example_JSON_String.png">
<p>4.Press Send and see the Response Body and Response Status.</p>
<img src="https://www.toolsqa.com/gallery/Postman/9.Customer_API_Example_User_Already_Exist.png">
<p>The error Fault User Already Exits means that in the database, a similar entry has already been created by you or anyone else earlier. Whereas if you see that the Response Status is 200 OK, which means that server accepted the request and sent back a successful response. We can also infer from this that the response body was correct and the server was able to interpret the response body. Now in this API Request, Email and Username should be unique. So you can change those values (anyone will also work).</p>
<br>
<p>If the values are unique, you will get this response</p>
<img src="https://www.toolsqa.com/gallery/Postman/10.Customer_API_Example_Success.png">
