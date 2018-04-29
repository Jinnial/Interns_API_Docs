# Making Requests

```java
// Create Request Queue
RequestQueue queue = Volley.newRequestQueue(getContext());
String url = // See Individual API Docs

// Setup Request
StringRequest request = new StringRequest(Request.Method.POST, url, new Response.Listener<String>(){
    @Override
    public void onResponse(String response) {
        // Processing
    }
}, new Response.ErrorListener() {
    @Override
    public void onErrorResponse(VolleyError error) {
        // API Was Unreachable
    }
});

//Add to Request Queue
queue.add(request);
```

> Don't forget to replace `12345qwerty`` with your authorization token from Azure!

In order to use our API, your going to have to make HTTP requests to our system. In this section you can find some code snippets to configure your HTTP requests.

Programming Language | Library Name
-------------------- | ------------
Java | Volley
Swift | AlamoFire
Objective C | AlamoFire

In order to use our API though, you will need to API authorization key. You can obtain an API token by going to the Microsoft Azure Functions panel.

`Authorization: 12345qwerty`

<aside class="notice">
You must replace <code>12345qwerty</code> with your personal API key.
</aside>