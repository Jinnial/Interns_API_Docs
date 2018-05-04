# Teachers

## Find If Teacher Has Registered

```java
// Open An HTTP Request with Volley
@Override
String url = "https://gocaps-interns.azurewebsites.net/api/DoesTeacherExist?code=12345qwerty&StuID=" +
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
  "TeachID": "example",
  "TeachStrand": 2,
  "TeachFirstName": "Brenden",
  "TeachLastName": "Reeves",
  "TeachPhoneNum": "417-355-1529",
  "TeachEmailAddress": "reevesb375@gmail.com"
}
```

At various points in your implementation you may want to check to see if a teacher has registered. Thankfully, you can easily check and see if they have finished the registration process. If the user exists in the system, the user's data will be returned.

### Parameters

Variable | Description
-------- | -----------
uID | The ID of the Teacher

### Response Data

Key | Description
--- | -----------
result | Tells if the function found a user
TeachStrand | The ID of the strand which they teach
TeachID | The ID of the teacher
TeachFirstName | The first name of the student
TeachLastName | The last name of the student
TeachPhoneNum | The cell phone number of the student
TeachEmail | The email of the instructor

<aside class="warning">
The data above will only be returned if the user account exists. If the <code>result</code> value returns false, the user account does not exist. Please handle this response appropriately by having them register for an account.
</aside>