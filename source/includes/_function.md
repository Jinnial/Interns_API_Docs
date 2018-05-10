# Azure Functions

## AddAffiliate
Adds an affiliate

### Parameters

Parameter | Description | Options
--------- | ----------- | -------
AffiliateName | Name of affiliate
AffiliateLocation | Location of affiliate

### Responses

Variable | Description 
------- | -----------
`true` | The affiliate was added correctly
`false` | There was an error adding the affiliate

## AddContact
Adds a contact

### Parameters

Parameter | Description 
--------- | ----------- 
ContactFirstName | First name of contact
ContactLastName | Last name of contact
ContactPhoneNum | Phone number of contact
ContactOffice | Office number of contact
ContactEmailAddress | Email address of contact

### Responses

Variable | Description 
------- | -----------
`ContactID` | The contact was added correctly, and the function returned an auto-generated ContactID
`999` | There was an error adding the contact

## AddPartner
Adds a partner

### Parameters

Parameter | Description 
--------- | ----------- 
ContactID | Contact ID for the contact associated with this partner
PartnerName | Name of partner
PartnerAddress | Address of partner
PartnerPhoneNum | Phone number of partner

### Responses

Variable | Description 
------- | -----------
`true` | The contact was added correctly, and the function returned an auto-generated ContactID
`false` | There was an error adding the contact

## AddShadow
Adds a shadow

### Parameters

Parameter | Description 
--------- | ----------- 
PartnerID | Partner ID for the partner associated with this shadow
ShadowName | Name of shadow
ShadowStarTime | Time the shadow begins
ShadowEndTime | Time the shadow ends
ShadowLocation | Where the shadow is located
ShadowDressCode | Required dress for shadow
ShadowParking | Parking details regarding this shadow
ShadowOtherDetails | Any other details regarding this shadow
ShadowMaxEnrollment | Maximum number of students that can be assigned to this shadow

### Responses

Variable | Description 
------- | -----------
`true` | The shadow was added correctly
`false` | There was an error adding the shadow

## AddStrand
Adds a strand

### Parameters

Parameter | Description 
--------- | ----------- 
AffiliateID | ID of affiliate associated with this strand
TeachID | ID of teacher that will be teaching this strand
StrandName | Name of this strand
StrandLocation | Where this strand is located

### Responses

Variable | Description 
------- | -----------
`true` | The strand was added correctly
`false` | There was an error adding the strand

## AddStudent
Adds a student

### Parameters

Parameter | Description | Options
--------- | ----------- | --------
StuID | ID of student to be added
StrandID | ID of strand this student is enrolled in
StuFirstName | Student's first name
StuLastName | Student's last name
StuSchool | School this student attends
StuAge | Student's age
StuEmailAddress | Student's email address
StuPhoneNum | Student's phone number
StrandSession | Session of strand this student is enrolled in | `AM` or `PM` only

### Responses

Variable | Description 
------- | -----------
`true` | The student was added correctly
`false` | There was an error adding the student

## AddTeacher
Adds a teacher

### Parameters

Parameter | Description
--------- | ----------- 
TeachID | ID for this teacher
TeachFirstName | Teacher's first name
TeachLastName | Teacher's last name
TeachPhoneNum | Teacher's phone number
TeachEmailAddress | Teacher's email address

### Responses

Variable | Description 
------- | -----------
`true` | The teacher was added correctly
`false` | There was an error adding the teacher

## AssignStudent
Assigns a student to a shadow

### Parameters

Parameter | Description
--------- | ----------- 
StuID | ID of student to be assigned to a shadow
ShadowID | ID of shadow student is to be assigned to

### Responses

Variable | Description 
------- | -----------
`true` | The student was assigned to the shadow properly
`false` | There was an error assigning the student to the shadow

## ClockIn
Clocks a student in

### Parameters

Parameter | Description
--------- | ----------- 
RegShadowID | ID of the registered shadow that the student is associated with
InTime | Time student is clocking in
InLat | Latitude student is at while clocking in
InLong | Longitude student is at while clocking in
Date | Date on which student is clocking in

### Responses

Variable | Description 
------- | -----------
`ClockID` | The student was clocked in properly, and a ClockID variable was returned
`0` | There was an error clocking the student in

## ClockOut
Clocks a student out

### Parameters

Parameter | Description
--------- | ----------- 
ClockID | ClockID of clock instance that is to be clocked out
OutTime | Time student is clocking out
OutLat | Latitude student is at while clocking out
OutLong | Longitude student is at while clocking out

### Responses

Variable | Description 
------- | -----------
`true` | The student was clocked out properly
`false` | There was an error clocking the student out

## IsShadowFull
Determines if a shadow is full or not

### Parameters

Parameter | Description
--------- | ----------- 
ShadowID | ID of shadow user is testing

### Responses

Variable | Description 
------- | -----------
`true` | The shadow is full
`false` | The shadow is not full
`something went wrong` | There was an error determining if the shadow is full

## RemovePartner
Removes a specified partner

### Parameters

Parameter | Description
--------- | ----------- 
PartnerID | ID of partner to be removed

### Responses

Variable | Description 
------- | -----------
`true` | The partner was removed properly
`false` | The was an error removing the partner

## RemoveShadow
Removes a shadow

### Parameters

Parameter | Description
--------- | ----------- 
ShadowID | ID of shadow to be removed

### Responses

Variable | Description 
------- | -----------
`true` | The shadow was removed properly
`false` | The was an error removing the shadow

## ShowContactWithContactID
Returns contact information for a specified contact

### Parameters

Parameter | Description
--------- | ----------- 
ContactID | ID of contact to display

### Responses

> Breakdown of Returned User Data:

```json
{
    "ContactID": "3",
    "ContactFirstName": "John",
    "ContactLastName": "Doe",
    "ContactPhoneNum":  "123-456-7890",
    "ContactOffice": "17-B",
    "ContactEmailAddress": "john@email.com"
}
```

Variable | Description 
------- | -----------
`false` | The was an error displaying the contact information

## ShowLatestClockInfoWithStuID
Returns most recent clock info for a specified student

### Parameters

Parameter | Description
--------- | ----------- 
StuID | ID of student to display latest clock info for

### Responses

> Breakdown of Returned User Data:

```json
{
    "ClockID": "5",
    "RegShadowID": "2",
    "InTime": "10:10:10.0000000",
    "OutTime":  "12:30:34.0000000",
    "InLat": "37.785834",
    "InLong": "-122.406417",
    "OutLat": "37.785834",
    "OutLong": "-122.406417",
    "Date": "2018-05-09"
}
```

Variable | Description 
------- | -----------
`false` | The was an error displaying the clock info

## ShowPartnerAndContactWithContactID
Returns partner and contact info for a specified contact

### Parameters

Parameter | Description
--------- | ----------- 
ContactID | ID of contact to display info for

### Responses

> Breakdown of Returned User Data:

```json
{
    "PartnerID": "5",
    "ContactID": "2",
    "PartnerName": "Medicine Inc.",
    "PartnerAddress":  "123 E South St",
    "PartnerPhoneNum": "417-777-7777",
    "ContactFirstName": "John",
    "ContactLastName": "Doe",
    "ContactPhoneNum": "417-888-8888",
    "ContactOffice": "22-C",
    "ContactEmailAddress": "john@email.com"
}
```

Variable | Description 
------- | -----------
`false` | The was an error displaying the partner and contact info

## ShowPartners
Returns all available partners

### Parameters

None

### Responses

> Breakdown of Returned User Data:

```json
{
    "PartnerID": "5",
    "ContactID": "2",
    "PartnerName": "Medicine Inc.",
    "PartnerAddress":  "123 E South St",
    "PartnerPhoneNum": "417-777-7777",
    "ContactFirstName": "John",
    "ContactLastName": "Doe",
    "ContactPhoneNum": "417-888-8888",
    "ContactOffice": "22-C",
    "ContactEmailAddress": "john@email.com"
}
```

Variable | Description 
------- | -----------
`false` | The was an error displaying the partner info


## ShowPartnerWithPartnerID
Returns partner info for a specified partner

### Parameters

Parameter | Description
--------- | ----------- 
PartnerID | ID of partner to display info for

### Responses

> Breakdown of Returned User Data:

```json
{
    "PartnerID": "5",
    "ContactID": "2",
    "PartnerName": "Medicine Inc.",
    "PartnerAddress":  "123 E South St",
    "PartnerPhoneNum": "417-777-7777"
}
```

Variable | Description 
------- | -----------
`false` | The was an error displaying the partner info

## ShowShadowAvailability
Returns availability of a specified shadow

### Parameters

Parameter | Description
--------- | ----------- 
ShadowID | ID of shadow to display availability of

### Responses

> Breakdown of Returned User Data:

```json
{
    "ShadowMaxEnrollment": "12",
    "Enrolled": "8"
}
```

Variable | Description 
------- | -----------
`false` | The was an error displaying the shadow availability info

## ShowShadowAvailabilityJSON
Same as ShowShadowAvailability, but returns an HttpResponseMessage rather than a string

### Parameters

Parameter | Description
--------- | ----------- 
ShadowID | ID of shadow to display availability of

### Responses

> Breakdown of Returned User Data:

```json
{
    "ShadowMaxEnrollment": "12",
    "Enrolled": "8"
}
```

Variable | Description 
------- | -----------
`false` | The was an error displaying the shadow availability info

## ShowShadowsInStrand
Returns all shadows in a specified strand

### Parameters

Parameter | Description
--------- | ----------- 
StrandID | ID of strand to show all associated shadows

### Responses

> Breakdown of Returned User Data:

```json
{
    "ShadowID": "6", 
    "PartnerID": "5",
    "ShadowName": "Medicine Shadow 1",
    "ShadowStartTime":  "10:15:00.000",
    "ShadowEndTime": "12:15:00.000",
    "ShadowLocation": "171 N Third Ave",
    "ShadowDressCode": "Business Casual",
    "ShadowParking": "Parking Lot On Site",
    "ShadowOtherDetails": "Bring A Pen",
    "ShadowMaxEnrollment": "14",
    "StrandID": "2"
}
```

Variable | Description 
------- | -----------
`false` | The was an error displaying the shadow info

## ShowShadowsInStrandJSON
Same as ShowShadowsInStrand, but returns an HttpResponseMessage instead of a string

### Parameters

Parameter | Description
--------- | ----------- 
StrandID | ID of strand to show all associated shadows

### Responses

> Breakdown of Returned User Data:

```json
{
    "ShadowID": "6", 
    "PartnerID": "5",
    "ShadowName": "Medicine Shadow 1",
    "ShadowStartTime":  "10:15:00.000",
    "ShadowEndTime": "12:15:00.000",
    "ShadowLocation": "171 N Third Ave",
    "ShadowDressCode": "Business Casual",
    "ShadowParking": "Parking Lot On Site",
    "ShadowOtherDetails": "Bring A Pen",
    "ShadowMaxEnrollment": "14",
    "StrandID": "2"
}
```

Variable | Description 
------- | -----------
`false` | The was an error displaying the shadow info

## ShowShadowWithShadowID
Returns info on a specified shadow

### Parameters

Parameter | Description
--------- | -----------
ShadowID | ID of shadow to display information of 

### Responses

> Breakdown of Returned User Data:

```json
{
    "ShadowID": "6", 
    "PartnerID": "5",
    "ShadowName": "Medicine Shadow 1",
    "ShadowStartTime":  "10:15:00.000",
    "ShadowEndTime": "12:15:00.000",
    "ShadowLocation": "171 N Third Ave",
    "ShadowDressCode": "Business Casual",
    "ShadowParking": "Parking Lot On Site",
    "ShadowOtherDetails": "Bring A Pen",
    "ShadowMaxEnrollment": "14",
    "StrandID": "2"
}
```

Variable | Description 
------- | -----------
`false` | The was an error displaying the shadow info

## ShowStrands
Returns info on all strands

### Parameters

None

### Responses

> Breakdown of Returned User Data:

```json
{
    "StrandID": "6", 
    "AffilaiteID": "5",
    "TeachID": "4hslUGfIebSgJnk1AKAYQ5Qtahma2",
    "StrandName":  "Medical",
    "StrandLocation": "Springfield Regional Hospital"
}
```

Variable | Description 
------- | -----------
`false` | The was an error displaying the strand info

## StudentsInSession
Returns info on all students in a specified session

### Parameters

Parameter | Description | Options
--------- | ----------- | -------
StrandID | ID of strand to display information of
StrandSession | Specific session of strand to display information of | Must be `AM` or `PM`

### Responses

> Breakdown of Returned User Data:

```json
{
    "StuID": "hslUGfIebSgJnk1AKAYQ5Qtahma2",
    "StrandID": "6", 
    "StuFirstName": "John",
    "StuLastName": "Doe",
    "StuSchool":  "Kickapoo",
    "StuAge": "17",
    "StuEmailAddress": "student@email.com",
    "StuPhoneNum": "417-555-5555",
    "StrandSession": "AM"
}
```

Variable | Description 
------- | -----------
`false` | The was an error displaying the strand info

## UpdatePartner
Updates partner

### Parameters

Parameter | Description
--------- | ----------- 
ContactID | ID of contact associated with partner
PartnerName | Partner's name
PartnerAddress | Partner's address
PartnerPhoneNum | Partner's phone number

### Responses

Variable | Description 
------- | -----------
`true` | The partner info was updated properly
`false` | The was an error updating the partner info

## UpdateShadow
Updates shadow

### Parameters

Parameter | Description
--------- | ----------- 
ShadowID | ID of shadow to update
PartnerID | ID of partner shadow is associated with
ShadowName | Name of shadow
ShadowStartTime | Shadow's start time
ShadowEndTime | Shadow's end time
ShadowLocation | Shadow's location
ShadowDressCode | Shadow's dress code
ShadowParking | Shadow's parking availability and info
ShadowOtherDetails | Any other important details regarding shadow
ShadowMaxEnrollment | Maximum number of students that can be assigned to shadow

### Responses

Variable | Description 
------- | -----------
`true` | The shadow info was updated properly
`false` | The was an error updating the shadow info

## UpdateStudent
Updates student

### Parameters

Parameter | Description | Options
--------- | ----------- | ------ 
StuID | ID of student to update
StrandID | ID of strand this student is associated with
StuFirstName | Student's first name
StuLastName | Student's last name
StuSchool | School that student attends
StuAge | Student's age
StuEmailAddress | Student's email address
StuPhoneNum | Student's phone number
StrandSession | Session of strand student is enrolled in | Must be `AM` or `PM`


### Responses

Variable | Description 
------- | -----------
`true` | The student info was updated properly
`false` | The was an error updating the student info

## UpdateTeacher
Updates teacher

### Parameters

Parameter | Description | Options
--------- | ----------- | ------ 
TeachID | ID of teacher to update
TeachFirstName | Teacher's first name
TeachLastName | Teacher's last name
TeachPhoneNum | Teacher's phone number
TeachEmailAddress | Teacher's email address



### Responses

Variable | Description 
------- | -----------
`true` | The teacher info was updated properly
`false` | The was an error updating the teacher info

