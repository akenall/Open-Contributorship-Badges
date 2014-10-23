![ORCID logo](https://lh5.googleusercontent.com/-0dELP2HzkxM/UJrdjlgcCuI/AAAAAAAAAIo/McpGV07_uG0/s144/Orcid_Logo_rgb.png)

#ORCID Architecture

<sub>_Last update: 23 October 2014. Please refer to http://support.orcid.org for the latest ORCID documentation._</sub>

##About ORCID
[ORCID](http://orcid.org) provides a unique digital identifier (an [ORCID iD](http://support.orcid.org/knowledgebase/articles/116780-structure-of-the-orcid-identifier)) that distinguishes you from other researchers. ORCID supports automated linkages between you and your professional activities. These connections ensure that your contributions are recognized, whatever the outlet.

ORCID is a non-profit, community-driven organization supported by member organizations. It provides the Registry for free to the research community.

##MozFest ORCID Development Environment
Any experimentation or hacking involving the ORCID Registry or ORCID iDs during MozFest will be done in [ORCID's Sandbox environment](http://support.orcid.org/knowledgebase/articles/166623-about-the-orcid-sandbox). This environment is identical to the production environment, except that it houses only test data. There are also safeguards to prevent from accidentally emailing someone from the Sandbox.

##The ORCID API
ORCID provides two levels of APIs, a public one and a member one. For the purposes of the MozFest 2014 project, we will be assuming the use of the member API, so the information provided on this page may not be applicable to general public API implementations. 

_(If you're interested in more information about the differences between the ORCID APIs, see [this comparison table](http://www.slideshare.net/ORCIDSlides/orcid-membership-levels).)_

###Underlying Authority Access
The ORCID API is uses on [OAuth2.0](http://oauth.net/2/) to manage authorizations, sign in and access to ORCID information. Its implementation is very similar to that used by [Facebook](https://developers.facebook.com/docs/reference/dialogs/oauth/) or [Twitter](https://dev.twitter.com/oauth).

* [Resources for learning OAuth2.0](http://support.orcid.org/knowledgebase/articles/180285-introduction-to-the-orcid-api#Info)
* [Presenting ORCID permission screens from your system](http://support.orcid.org/knowledgebase/articles/409707-presenting-orcid-in-your-system)

###Using the ORCID API

The ORCID API can be used to:

![Authenticate](https://lh5.googleusercontent.com/EH_2SOfm5gq9AsLsXtJB9Uh3WBQ3gu9GSgLL5275udFrvIwg5iNWTQsu5aMGsXsHoHgy4UfyTTc=w2512-h1076)

**Authenticate the user** 

_Allow a user sign into your system using ORCID Sign In._

* At the moment, the sign in process is identical to getting an iD. Please refer to the links below for more information.

![Get iD](https://lh3.googleusercontent.com/cksp3Dt2W7lbyo8evXivi0GPVlFl8lF8Vc28oOSCo_oc6LNsTSu8EZ79WAdQGya5dXH7TZF7588=w2512-h1076)

**Get an authenticated ORCID iD**

_Ensure that you are getting the correct ORCID iD. Have a user log into the ORCID system so that the ORCID Registry provides the iD to your system._

* [Overview documentation](http://support.orcid.org/knowledgebase/articles/187066-get-an-id-integration-manger)
* [Technical flow & sample implementations](http://support.orcid.org/knowledgebase/articles/187465-get-an-id-technical-developer)

![Read iD](https://lh3.googleusercontent.com/Iv2RIZUsSyFKg7opwDLf9CIUnfgAlb_2Kw7Q5G4VbFCzSIKnboX2NNhUDjne6ifOeX-a5rPozls=w2512-h1076) ![Write iD](https://lh4.googleusercontent.com/Brrt1sH-uW8OsHbAXhuFIOccAsZALySvzrgEDIUERn4uAjzG1RcPfWQ3VZe6gmADRNdkC6R-cmg=w2512-h1076) ![Update iD](https://lh5.googleusercontent.com/SJGvkMHnGjdaz7c78coJcMdfr967cZ5KIENR4vcxu55a5EPpUh1KVRz7HGeh5_leNJpnDNqlJ7U=w2512-h1076)

**Read, write and/or update information in an ORCID Record**

_Each ORCID iD has an associated ORCID Record that contains information associated with this iD. After obtaining permission from the user (via OAuth), your system can read the record and/or add/update items on the record._

* READING INFORMATION
	* [Overview documentation](http://support.orcid.org/knowledgebase/articles/187495-get-information-integration-manager)
	* [Technical flow](http://support.orcid.org/knowledgebase/articles/187514-get-information-technical-developer)
* ADDING INFORMATION
	* [Overview documentation](http://support.orcid.org/knowledgebase/articles/171012-add-works-integration-manager)
	* [Technical flow & sample implementations](http://support.orcid.org/knowledgebase/articles/177528-add-works-technical-developer)
* UPDATING INFORMATION
	* [Overview documentation](http://support.orcid.org/knowledgebase/articles/338830-update-information-integration-manager)
	* [Technical flow](http://support.orcid.org/knowledgebase/articles/357502-update-information-technical-developer)

_When reading from or writing to an ORCID record, the data will be exchanged using the ORCID Message structure. This structure is usually in XML, though can be presented in other formats (such as JSON)._

* [About the ORCID Message structure](https://github.com/ORCID/ORCID-Source/blob/master/orcid-model/src/main/resources/README.md)
* [Recommended XSD for MozFest - Version 1.2_rc5](https://github.com/ORCID/ORCID-Source/blob/master/orcid-model/src/main/resources/orcid-message-1.2_rc5.xsd)
* [Detailed descriptions of the data included in the ORCID Message](http://support.orcid.org/knowledgebase/topics/32832-orcid-xml)

###General Documentation

The ORCID API is very well documented, and there are several sample implementations that have been contributed by the community that can be used as starting points.

* [ORCID API Documentation](http://support.orcid.org)
* [Registering to use the API on ORCID's Sandbox](http://support.orcid.org/knowledgebase/articles/180285-introduction-to-the-orcid-api#SandboxCreds)