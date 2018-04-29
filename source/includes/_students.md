# Students

## Register Student
```java
// Open An HTTP Request with Volley
RequestQueue queue = Volley.newRequestQueue(getContext());
String url = "https://gocaps-interns.azurewebsites.net/api/UpdateStudent?code=12345qwerty&StuID=" + 
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
> Don't forget to replace token with your authorization token from Azure!

Now, for a student to use the GO CAPS API, they will need to be have a registered account. Using our API, an account can be easily made provided the correct paramaters are fulliled.

For this you will need to pass in the following required paramaters:

Parameter | Description | Options
--------- | ----------- | -------
StuID | The ID of the student
StuFirstName | The first name of the student
StuLastName | The last name of the student
StuPhoneNum | The cell phone number of the student
StuSchool | The sending school of the student
StrandID | The ID of the stand the student is in
StrandSession | The meeting time of their strand | `AM` or `PM` Only

## Find If User Has Registered

```java
// Open An HTTP Request with Volley
RequestQueue queue = Volley.newRequestQueue(getContext());
String url = "https://gocaps-interns.azurewebsites.net/api/UpdateStudent?code=12345qwerty&StuID=" + FirebaseAuth.getInstance().getUid();

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

```swift

```
> Don't forget to replace token with your authorization token from Azure!

At various points in your implementation you may want to check to see if a student has registered. Thankfully, you can easily check and see if they have finished the registration process.

For this you will need to pass in the following required paramaters:

Parameter | Description
--------- | -----------
StuID | The ID of the student