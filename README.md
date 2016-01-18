# Twilio SMS Authentication Script

This authentication script is a two step authentication, where the first step is password authentication 
against the local Gluu Server LDAP, and the second step is validation of an SMS code.

If the person has no registered mobile number, the user will be prompted to enter a mobile 
number, which will be validated.

This script uses the Twilio service to send the message. You'll need to sign-up with Twilio to 
get an account to acquire the sid and token. 

As of Gluu Server version 2.4.1, Twilio java libraries and dependencies are included with the core 
distribution of oxauth. However, if you are using an earlier version, try 
[downloading](http://search.maven.org/#browse%7C-1416163511) the last version of the library without
dependencies and install it in /opt/tomcat/endorsed folder. If you are missing libraries, add them one 
by one to avoid conflicts with the Gluu Server.

There are three required custom properties:
    twilio_sid     Your account id at Twilio
    twilio_token   The API secret provided by Twilio
    from_number    The number you are using [E.164](https://www.twilio.com/help/faq/phone-numbers/how-do-i-format-phone-numbers-to-work-internationally) number formatting.