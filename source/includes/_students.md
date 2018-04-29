# Students

## Register Student
```java
// Create Request Queue
String url = String url = "https://gocaps-interns.azurewebsites.net/api/UpdateStudent?code=12345qwerty&StuID=" + 
    FirebaseAuth.getInstance().getUid() + "&StuFirstName=" + f + "&StuLastName=" + l + 
    "&StuEmailAddress=" + e + "&StuPhoneNum=" + p + "&StuSchool=" + school + "&StrandID=" + 
    strand + "&StrandSession=" + (time == 0 ? "AM" : "PM");

// Setup Request
StringRequest request = new StringRequest(Request.Method.POST, url, new Response.Listener<String>(){
    @Override
    public void onResponse(String response) {
        if(new String("false").equals(response)){
            // User Had No Account
        } else {
            // User Has Account
        }
    }
}, new Response.ErrorListener() {
    @Override
    public void onErrorResponse(VolleyError error) {
        // API Was Unreachable
    }
});
```

Now, for a student to use the GO CAPS API, they will need to be have a registered account. Using our API, an account can be easily made provided the correct paramaters are fulliled.

### Parameters

Parameter | Description | Options
--------- | ----------- | -------
StuID | The ID of the student
StuFirstName | The first name of the student
StuLastName | The last name of the student
StuPhoneNum | The cell phone number of the student
StuSchool | The sending school of the student
StrandID | The ID of the stand the student is in
StrandSession | The meeting time of their strand | `AM` or `PM` Only

### Responses

Variable | Description 
------- | -----------
`true` | The account was made successfully
`false` | There was an error making the account.

## Find If User Has Registered

```java
// Open An HTTP Request with Volley
@Override
String url = "https://gocaps-interns.azurewebsites.net/api/UpdateStudent?code=12345qwerty&StuID=" +
    FirebaseAuth.getInstance().getUid();

// Setup Request
StringRequest request = new StringRequest(Request.Method.POST, url, new Response.Listener<String>(){
    @Override
    public void onResponse(String response) {
        if(new String("false").equals(response)){
            // User Had No Account
        } else {
            // User Has Account
        }
    }
}, new Response.ErrorListener() {
    @Override
    public void onErrorResponse(VolleyError error) {
        // API Was Unreachable
    }
});
```

> Breakdown of Returned User Data:

```json
{
    "StuId": "12345678dfvbgnh",
    "StuFirstName": "John",
    "StuLastName": "Doe",
    "StuPhoneNum":  "123-456-7890",
    "StuSchool": "Kickapoo",
    "StrandID": 1,
    "StrandSession": "AM"
}
```

At various points in your implementation you may want to check to see if a student has registered. Thankfully, you can easily check and see if they have finished the registration process. If the user exists in the system, the user's data will be returned. Should the account not exist, 

### Parameters

Variable | Description
-------- | -----------
StuID | The ID of the student

### Response Data

Key | Description
--- | -----------
StuID | The ID of the student
StuFirstName | The first name of the student
StuLastName | The last name of the student
StuPhoneNum | The cell phone number of the student
StuSchool | The sending school of the student
StrandID | The ID of the stand the student is in
StrandSession | The meeting time of their strand

<aside class="warning">
The data above will only be returned if the user account exists. If you get <code>false</code> returned, plese handle the response appropriately by having them register for an account.
</aside>