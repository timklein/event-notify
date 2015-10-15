# event-notify

*event-notify* is a server side utility for querying the *Eventbrite* user API for a list of attendess for owned events, then notifying the user prior to the start of the event via SMS utilizing the *Twilio* API.

Currently, *event-notify* is set up to pull the "answer" element (in this case, a cell phone number) from a custom question that is added to the *Eventbrite* event ticket order form. 

Currently, users will need to set up an app in their Eventbrite settings to obtain a Personal OAuth token, and will need the Account SID and Authorization Token from their Twilio developer account.

## Usage

Authorization information should be added to the *config/configVars.sample* file and the extension for the file should be changed to *.json*.

A call to the */events* path in a browser window will trigger a GET request to *Eventbrite*, parse the returned attendees list and send SMS messages to all attendees.

## To Do

+ Filter out invalid phone numbers.
+ Convert to a cron job that only sends one message per attendee at a specified time prior to the start of the event.
+ Personalize messages utilizing other data retrieved from the API.