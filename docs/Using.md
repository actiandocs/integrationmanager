# Using Integration Manager

## Creating an Account

For users of Integration Manager powered by Actian DataCloud, before
accessing Integration Manager, you must create an account by redeeming
your invitation provided in the email received from Actian Order
Fulfillment.

**Logging In**

**For Cloud-based:** See Logging In on page 11

**For On-premise:** Logging In on page 13

- Logging in to Actian Integration Manager requires a web browser. See
  Supported Browsers on page 9.

## Integration Manager Interface

![](media/image1.wmf)

The Integration Manager interface is divided into three main areas:

- Header section

<!-- end list -->

- Dashboard

<!-- end list -->

- Footer

## Getting Started with Templates and Configuration

This section leads you through the following steps:

- Creating a template

<!-- end list -->

- Adding a configuration to your template

<!-- end list -->

- Running your configuration

**Create a Template**

Templates represent a reusable configuration with instructions for
running your DataConnect job. The template includes a package, macros,
and location to execute the job on Actian’s DataCloud or on-premise
through an Agent.

To create a template

- Click the Templates tab.

![](media/image2.wmf)

- Click the Add button.

![](media/image3.wmf)

- Enter a name for your template and then click Go.

The template details pane is displayed:

![](media/image4.wmf)

1\. Details

- Specify the following template details:

Run Location

Specify where to run the configuration: in the Cloud or on-premises with
an Agent.

Package

- > Select your package by clicking Add Package to open the Select a
  > Package dialog.

<!-- end list -->

- > Click the Upload New Package button to browse for your package
  > locally, then click Add Package.

**On-Premise Note:** You may use samples provided at C:\\Program
Files\\Actian\\IntegrationManager\\samples

- > The entry point must be a process. If your package only has one
  > entry point, it will be selected automatically.

Set an entry point from the package, then click Save.

- > The entry point must be a process. If your package only has one
  > entry point, it will be selected automatically.

<!-- end list -->

- Click Next.

![](media/image5.wmf)

2\. Macros

You may either add a macro or import a macro. Follow the appropriate
procedure below.

To add a macro

- Click Macros.

<!-- end list -->

- Click the Add button, then select Add Macro from the dropdown.

<!-- end list -->

- Enter the macro name

<!-- end list -->

- Provide a value, if needed.

<!-- end list -->

- If the macro needs to be secured, click the toggle on the right.

<!-- end list -->

- Click Next.

To import a macro

This method only supports XML and JSON files. For more information about
macros and how they are used, see the Actian DataConnect documentation
at:
[http://docs.actian.com/dataconnect/](http://docs.actian.com/dataconnect/11.1/index.html)11.1/index.html.

- Click Macros.

<!-- end list -->

- Click Add.

<!-- end list -->

- Click Import Macro File from the dropdown.

<!-- end list -->

- Browse for your macro file locally, select the file name, and click
  Open.

<!-- end list -->

- Click Next.

![](media/image6.wmf)

3\. Files

To add files to the template

- Click Files.

<!-- end list -->

- Either drag and drop files into the Files pane or click Browse Files
  to browse locally for your files.

4\. Permissions

- For users who do not have Administrator permissions, the Permissions
  step is grayed out, indicating that permissions may not be changed.
  Contact your administrator to make changes to your administrative
  permissions.

To set permissions for groups and users to run the configuration

- Click Permissions.

<!-- end list -->

- Assign group permissions by clicking Add, selecting the group from
  the dropdown, and then clicking Save.

<!-- end list -->

- Add specific users by clicking Add, selecting the user from the
  dropdown.

<!-- end list -->

- Set individual permissions by clicking the toggles for Read, Write,
  and Run.

<!-- end list -->

- Click Create Template to finish creating your template.

**Not Ready to Finish the Template?** If you are not ready to make the
template available for configuration runs, you may either delete it or
save it as a draft. Click Cancel to choose. Saving as a draft will set
the template to inactive. To make it active, in the Templates list, you
must click the template name and then click the Active toggle to On.
This will make the template active.

You may now add a configuration to your template.

**Add a Configuration to Your Template**

Configurations inherit values from the template so you can simply
execute the configuration or choose to override specific instructions,
making a configuration fully customizable. Using templates makes
managing multiple configurations simpler.

To add a configuration to your template

- Open your template from the list on the Templates tab.

<!-- end list -->

- Click the Configurations tab.

![](media/image7.wmf)

- Click Add a Configuration button.

<!-- end list -->

- Enter a name for your configuration, then click Go.

1\. Details

- (Optional) The package name is inherited from the template by
  default. You may change the package to customize your configuration.

<!-- end list -->

- (Optional) The entry point is inherited from the template by
  default. You may change the entry point to customize your
  configuration.

<!-- end list -->

- Click Add Schedule to create the schedule for your configuration.

You may choose from these options:

- > On Demand

- > Interval

- > Daily

- > Weekly

- > Monthly

- > Custom

Custom schedules require creating a cron expression. For more
information, see:
[https://](https://en.wikipedia.org/wiki/Cron)en.wikipedia.org/wiki/Cron.

- After setting up your desired schedule, click Save.

<!-- end list -->

- Click Next.

![](media/image8.wmf)

2\. Macros

You may either add a macro or import a macro. Follow the appropriate
procedure below.

To add a macro

- Click Macros.

<!-- end list -->

- Click the Add button, then select Add Macro from the dropdown.

<!-- end list -->

- Enter the macro name

<!-- end list -->

- Provide a value, if needed.

<!-- end list -->

- If the macro needs to be secured, click the toggle on the right.

<!-- end list -->

- Click Next.

To import a macro

This method only supports XML and JSON files. For more information about
macros and how they are used, see the Actian DataConnect documentation
at:
[http://docs.actian.com/dataconnect/](http://docs.actian.com/dataconnect/11.1/index.html)11./index.html.

- Click Macros.

<!-- end list -->

- Click Add.

<!-- end list -->

- Click Import Macro File from the dropdown.

<!-- end list -->

- Browse for your macro file locally, select the file name, and click
  Open.

<!-- end list -->

- Click Next.

![](media/image9.wmf)

**3. Files**

To add files to the template

- Click Files.

<!-- end list -->

- Either drag and drop files into the Files pane or click Browse Files
  to browse locally for your files.

4\. Permissions

- For users who do not have Administrator permissions, the Permissions
  step is grayed out, indicating that permissions may not be changed.
  Contact your administrator to make changes to your administrative
  permissions.

To set permissions for groups and users to run the configuration

- Click Permissions.

<!-- end list -->

- Add specific users by clicking Add, selecting the user from the
  dropdown.

<!-- end list -->

- Set individual permissions by clicking the toggles for Read, Write,
  and Run.

<!-- end list -->

- Click Create Configuration to finish creating your configuration.

**Not Ready to Finish the Configuration?** If you are not ready to make
the configuration available, you may either delete it or save it as a
draft. Click Cancel to choose. Saving as a draft will set the
configuration to inactive. To make it active, in the Configurations
list, you must click the configuration name and then click the Active
toggle to On. This will make the configuration active.

Your newly created Configuration is displayed.

![](media/image10.wmf)

**Run Your Configuration**

Now that you have successfully created a template and configuration, you
may run the configuration.

The integration is executed when you run the configuration. When
completed, runtime metrics will be available for review.

To run your configuration

Click Run Configuration (in the upper right corner).

![](media/image11.wmf)

The Jobs Status appears, revealing the current status of the job once
the Configuration has been run.

![](media/image12.wmf)

Job information is listed at the bottom of the display, including the
date and time started, job ID, status, duration, and the log of the
configuration.

To check the configuration log, click the icon at the far right on the
line, under the Log column. This displays metrics about the job and the
generated log file.

## Resetting Your Password

If you have forgotten your password for Actian Integration Manager,
click the Forgot Password link on the login screen.

Follow the instructions to reset your password and log in to the
Integration Manager.

## Using JobConfig Aliasing

APIs in Integration Manager can accept an alias to call a JobConfig
listener. The jobconfig-aliases API allows aliasing a JobConfig listener
with a name. An alias name may be mapped to one JobConfig. The API
supports assignment of multiple aliases for a JobConfig.

**Creating a JobConfig Alias**

The following is an example of assigning the alias “alias1” with
JobConfig “1”:

POST /api/jobconfig-aliases HTTP/1.1

Host: localhost:8080

Authorization: Bearer:eyJhbGciOi...

Content-Type: application/json

{

"name": "alias1",

"jobConfigId": "1"

}

**Calling a Listener by JobConfig Alias**

The following is an example that calls a listener with the JobConfig
alias “alias1” created above.

POST
/api/listener/alias1?messagename=messageName\&outmessagename=outMessageName
HTTP/1.1

Host: localhost:8080

Authorization: Bearer:eyJhbGciOi...

Content-Type: text/plain

Message Body

In the example above, the route /api/listener/alias1 is an alias of
/api/jobconfig/1/listener. The JobConfig alias for listeners, endpoint
POST api/listener/{alias}, enables using the same functionality as
calling POST api/jobconfig/{id}/listener.

Run JobConfiguration with text message input and text message output (if
running synchronously). If the out message is not supplied, the job will
execute asynchronously. The out message may be retrieved by GET
/api/job/{id} after the job is complete.

**Managing JobConfig Aliases**

Other than creating aliases for JobConfiguration, the API provides
administration requests to manage (modify, read, and delete) aliases.

Here is an example of updating the same alias to point to a different
JobConfig “2”:

PUT /api/jobconfig-aliases/alias1

Host: localhost:8080

Authorization: Bearer:eyJhbGciOi...

Content-Type: application/json

{

“name”: “alias1”,

“jobConfigId”: “2”R

}

And an example of retrieving JobConfig alias “alias1”:

GET /api/jobconfig-aliases/alias1

Host: localhost:8080

Authorization: Bearer:eyJhbGciOi...

An example of deleting JobConfig alias “alias1”:

DELETE /api/jobconfig-aliases/alias1

Host: localhost:8080

Authorization: Bearer:eyJhbGciOi...

The following is an example to retrieve all JobConfig aliases:

GET /api/jobconfig-aliases

Host: localhost:8080

Authorization: Bearer:eyJhbGciOi...

For more information about jobconfig-aliases requests, responses, and
error messaging, see Available Services and Documentation on page 49.

## Configuring Job Notifications

Job notifications allow you to receive email notifications for
unsuccessful jobs based on Job Configuration.

Emails are sent whenever a subscribed-to configuration ends in an ERROR
or ABORTED state. A subscription to a Job Configuration is made through
an API call. You must be an admin of the account to create or modify
subscriptions within the account. You can also activate or deactivate
subscriptions by updating the "active" field using the PUT. The
endpoints can be found at:
[http://](http://actian-im-api-docs-us-east-1.s3-website-us-east-1.amazonaws.com/#/)actian-im-api-docs-us-east-1.s3-website-us-east-1.amazonaws.com/\#/,
but they are also listed in Step 2.

To enable job notifications, you must update the application.properties
file and then subscribe to job configurations to begin receiving email
notifications.

To configure job notifications

- Set key-value pairs in the application.properties file.

<!-- end list -->

- > Enable notifications:

notification.enabled =true

- > Configure the SMTP server:

spring.mail.host=_\<smtp-host-url\>_

spring.mail.username=_\<smtp-username\>_

spring.mail.password=_\<smtp-password\>_

spring.mail.properties.mail.transport.protocol=smtp

spring.mail.properties.mail.smtp.port=587

spring.mail.properties.mail.smtp.auth=true

spring.mail.properties.mail.smtp.starttls.enable=true

spring.mail.properties.mail.smtp.starttls.required=true

- > Configure the email sender and recipients:

notification.mailFrom=_\<email\>_

notification.mailTo=_\<email\>_

- Create a subscription to a Job Configuration using the Rest API.

<!-- end list -->

- > Here is an example of a POST call to create a subscription:

POST /api/jobconfigs/{id}/subscriptions

Host: localhost:8080

Authorization: Bearer:eyJhbGciOi…

Content-type: application/json

{

"active" : "true"

}

- > These are all the endpoints for managing subscriptions:

<!-- end list -->

- > POST: api/jobconfigs/{id}/subscription

- > PUT: api/subscriptions/{id}

- > DELETE: api/subscriptions/{id}

- > GET: api/subscriptions/{id}

- > GET: api/subscriptions

<!-- end list -->

- > For more information about the REST API endpoints, see
  > [http://actian-im-api-docs-us-](http://actian-im-api-docs-us-east-1.s3-website-us-east-1.amazonaws.com/#/)east-1.s3-website-us-east-1.amazonaws.com/\#/.

## Installing and Configuring the Aggregator Service

The Aggregator Service provides an API that enables you to submit
messages that will aggregate into one larger message. After the messages
have been aggregated, they will be submitted as one job to the Job
Configuration listener API. Supported data formats are XML, JSON, and
RECORD.

XML and JSON data types will be aggregated into an array and sent to the
listener API. RECORD data types will be separated by the line separator
type for the system that is running the aggregator processor.

**Configuration**

To configure aggregators, you will need to update the
aggregator-config.yml file.

Aggregator Properties

<table>
<tbody>
<tr class="odd">
<td>Property</td>
<td>Default Value</td>
<td>Description</td>
</tr>
<tr class="even">
<td>name</td>
<td></td>
<td>Name of the aggregator</td>
</tr>
<tr class="odd">
<td>entity-id</td>
<td></td>
<td>The ID for which entity type to invoke</td>
</tr>
<tr class="even">
<td>entity-type</td>
<td></td>
<td><p>The entity type for the aggregator</p>
<p>Valid types (case-sensitive): jobconfig</p></td>
</tr>
<tr class="odd">
<td>account-id</td>
<td></td>
<td>Account ID that owns the entity</td>
</tr>
<tr class="even">
<td>active</td>
<td>true</td>
<td>Specifies whether this particular aggregator is active</td>
</tr>
<tr class="odd">
<td>completion-size</td>
<td>200</td>
<td>The number of messages to aggregate before submitting the aggregated message to the listener API</td>
</tr>
<tr class="even">
<td>completion-timeout</td>
<td>10000</td>
<td>The amount of time (in millisenconds) to wait after receiving the last message before submitting the aggregated message to the listener API</td>
</tr>
<tr class="odd">
<td>data-type</td>
<td></td>
<td><p>The data type for the submitted message to the aggregator API. This determines how the messages are aggregated.</p>
<p>Valid types (case-sensitive): record, xml, json</p></td>
</tr>
</tbody>
</table>

Example aggregator-config.yml configuration

aggregators:

- name: Aggregator-Config-xml

entity-id: 21

entity-type: jobconfig

account-id: 1

active: true

completion-size: 5

completion-timeout: 5000

data-type: xml

- name: Aggregator-Config-json

entity-id: 22

entity-type: jobconfig

account-id: 1

active: true

completion-size: 5

completion-timeout: 5000

data-type: json

- name: Aggregator-Config-record

entity-id: 23

entity-type: jobconfig

account-id: 1

active: true

completion-size: 5

completion-timeout: 5000

data-type: record

**How the Aggregator Service Works**

Messages can be submitted to POST:
\<endpoint\>/api/aggregators?type=\<entity-type\>\&id=\<entity-id\>.
These messages will be aggregated according to the corresponding entry
in aggregator-config.yml. When the number of messages received equals
completion-size, or the completion-timeout is reached after the last
message is received, then the aggregated message will be submitted to
\<endpoint\>/api/jobconfigs/\<entity-id\>/listener. The aggregated
message can be accessed through djmessage 'msg1' within the dataconnect
process.

Sample request to the aggregator API

POST /api/aggregators?type=jobconfig\&id=22

Host: \<endpoint\>

Authorization: \<bearer-token\>

Content-Type: text/plain

\<note\>

\<to\>Tove\</to\>

\<from\>Jani\</from\>

\<heading\>Reminder\</heading\>

\<body\>Don't forget me this weekend\!\</body\>

\</note\>

**Example Messages**

- The following example aggregated messages were generated after five
  submissions for the singular messages to the Aggregator API.

**XML**

Singular message submitted to the aggregator API

\<note\>

\<to\>Tove\</to\>

\<from\>Jani\</from\>

\<heading\>Reminder\</heading\>

\<body\>Don't forget me this weekend\!\</body\>

\</note\>

Aggregated message to be sent to the listener API

\<items type="array"\>

\<note\>

\<to\>Tove\</to\>

\<from\>Jani\</from\>

\<heading\>Reminder\</heading\>

\<body\>Don't forget me this weekend\!\</body\>

\</note\>\<note\>

\<to\>Tove\</to\>

\<from\>Jani\</from\>

\<heading\>Reminder\</heading\>

\<body\>Don't forget me this weekend\!\</body\>

\</note\>\<note\>

\<to\>Tove\</to\>

\<from\>Jani\</from\>

\<heading\>Reminder\</heading\>

\<body\>Don't forget me this weekend\!\</body\>

\</note\>\<note\>

\<to\>Tove\</to\>

\<from\>Jani\</from\>

\<heading\>Reminder\</heading\>

\<body\>Don't forget me this weekend\!\</body\>

\</note\>\<note\>

\<to\>Tove\</to\>

\<from\>Jani\</from\>

\<heading\>Reminder\</heading\>

\<body\>Don't forget me this weekend\!\</body\>

\</note\>

\</items\>

**JSON**

Singular message submitted to the aggregator API

{

"to": "Tove",

"from": "Jani",

"heading": "Reminder",

"body": "Don't forget me this weekend\!"

}

Aggregated message to be sent to the listener API

\[

{

"to": "Tove",

"from": "Jani",

"heading": "Reminder",

"body": "Don't forget me this weekend\!"

},{

"to": "Tove",

"from": "Jani",

"heading": "Reminder",

"body": "Don't forget me this weekend\!"

},{

"to": "Tove",

"from": "Jani",

"heading": "Reminder",

"body": "Don't forget me this weekend\!"

},{

"to": "Tove",

"from": "Jani",

"heading": "Reminder",

"body": "Don't forget me this weekend\!"

},{

"to": "Tove",

"from": "Jani",

"heading": "Reminder",

"body": "Don't forget me this weekend\!"

}

\]

**RECORD**

Singular message submitted to the aggregator API

"Tove","Jani","Reminder","Don't forget me this weekend\!"

Aggregated message to be sent to the listener API

"Tove","Jani","Reminder","Don't forget me this weekend\!"

"Tove","Jani","Reminder","Don't forget me this weekend\!"

"Tove","Jani","Reminder","Don't forget me this weekend\!"

"Tove","Jani","Reminder","Don't forget me this weekend\!"

"Tove","Jani","Reminder","Don't forget me this weekend\!"
