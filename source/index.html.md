---
title: GOCAPS Intern API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - java
  - swift

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - students

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Required External Libaries

To make it easy for you to implement your code, we advise using the following external code libraries:

Platform  | Name    | Description
--------- | ------- | -----------
Android | Volley | Allows for Easy HTTP Requests
Android/iOS | Firebase | Allows for Notifications, Real-Time Databasing, and Usage Data

# Authentication

GO CAPS uses API keys to allow access to the API. You can obtain an API token by going to the Microsoft Azure Functions panel.

`Authorization: 12345qwerty`

<aside class="notice">
You must replace <code>12345qwerty</code> with your personal API key.
</aside>