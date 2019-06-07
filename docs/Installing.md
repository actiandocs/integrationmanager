# Installing

Actian Integration Manager Powered by Actian DataCloud 11

Actian Integration Manager On-premise 12

Agents 13

Files Installed by Actian Integration Manager 27

## Actian Integration Manager Powered by Actian DataCloud

There is no installation process for Integration Manager powered by
Actian DataCloud, because it is a web-based cloud platform. However,
Agents are installed when you initiate access to the Actian Integration
Manager.

**Logging In**

To log in to Integration Manager powered by DataCloud

Go to: <https://integration.actiandatacloud.com/>.

**Password Reset**

To reset your password for Actian Integration Manager powered by Actian
DataCloud

- Click the Forgot Password link in the lower right corner of the
  dialog box.

This opens a new page where you must enter the account ID associated
with Actian Integration Manager.

- Enter your account ID.

Integration Manager will allow you to change your password.

When finished, follow the standard procedures for logging into the
system, as explained in Logging In on page 11.

## Actian Integration Manager On-premise\*

To install Integration Manager

- Run the install as administrator. Once open, click next to start the
  installation.

<!-- end list -->

- (Discretionary) If you are prompted to install Java 8, note that
  Integration Manager requires the 64-bit version of Java, which you
  can find here:
  [https://www.oracle.com/technetwork/](https://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html)java/javase/downloads/jre8-downloads-2133155.html,
  named "jre-8u*xxx*-windows-x64.exe".

<!-- end list -->

- Read through and click the button 'I accept the terms of this
  license agreement'; failure to accept the license agreement will
  prevent the installation. Then click next.

<!-- end list -->

- Select your installation path. (If you do not want to use the
  default path, you may use the Browse Feature on the Installation
  Wizard to locate your desired path to use.) Click next.

<!-- end list -->

- Port Configurations is defaulted to port 8080. Change if needed.

<!-- end list -->

- Auto Startup Services after installation: Integration Manager and
  DataConnect Worker boxes are checked by default. (The services will
  be installed by default but will not be started unless the check
  boxes are set.) Then click next.

<!-- end list -->

- Select the path to your license. For more information, refer to the
  email that you initially received. Click next.

<!-- end list -->

- Confirm the installation settings, then click next to continue.

<!-- end list -->

- Wait for the files to write. Once installation is complete, click
  next so that the installer can configure the services. Then click
  next.

<!-- end list -->

- Shortcuts will be created on the Start menu and desktop. You may
  also select to have the shortcut made for the current user or for
  all on the current machine. Click Next and then Done to close the
  installation.

After completing these steps, you should see the services for “Actian
DataConnect Worker” and “Actian Integration Manager” in your list of
installed services. If you left the check boxes checked in Step 5, the
services should have a Status of “Running.”

The following files are installed to the installation path you selected
in Step 3.

- **bin** – location of the command scripts

- **conf** – location of any configuration files

- **di-standalone-engine** – location of the DataConnect stand alone
  engine

- **images -** location of Actian logo

- **lib** – location of any jar files needed

- **license** – default location where the license needs to be
  installed

- **samples** – test DataConnect v11 djar to use in a configuration

- **Uninstaller** – location of the uninstaller

The following files are also installed to
C:\\ProgramData\\Actian\\IntegrationManager:

- **embedded** – location of the data, worker, and zookeeper folders

- **logs** – worker and IM stack log location.

**Logging In**

Logging in to the Actian Integration Manager requires a web browser.
(See Supported Browsers on page 9.)

To log in

- Go to http://localhost:8080 in your web browser.

<!-- end list -->

- On the login screen, enter your new Actian username and password.

<!-- end list -->

- Click Login.

The Actian Integration Manager UI appears.

**Password Reset**

If you need to reset a password with Integration Manager On-premise,
contact your local administrator, who has the ability to reset all user
passwords.

## Agents

Our agent technology allows centralized cloud management of on-premise
integration jobs and related collateral. It allows secure
cloud-to-communication without special firewall rules or VPN.

The following scenarios are candidates for executing an integration with
the agent:

- Database connections that require drivers (such as ODBC) or
  connections on an internal network.

- Web-based services that are housed internally and not externally
  available.

- Using source or target files that are located on an internal
  network.

**Agent System Requirements**

Actian DataCloud Agent has the following system requirements.

Operating System and Software

- Microsoft Windows Server 2008 R2 (64-bit U.S. English edition) or
  later

- Java Runtime Environment 8 or higher

Hardware

Systems running DataCloud Agent should meet the following requirements:

- Multicore 64-bit processor, x86-64, 2 GHz or faster

- 40 GB free hard drive space

- 8 GB high-speed RAM minimum

- Outbound connection to the Internet

<!-- end list -->

- The hardware requirements for the DataCloud Agent are comparable to
  those for the Stand-Alone Engine package of Data Integrator. The
  Agent includes the stand-alone engine for local execution of
  integrations.

**Agent Installation**

**Before You Begin**

Observe the following points before you begin installing the DataCloud
Agent.

- If you install the DataCloud Agent on a machine that is also running
  one of the following DataConnect services, you may incur additional
  configuration requirements to avoid conflicts:

<!-- end list -->

- > DataConnect Design Studio

- > Integration Manager

- > Standalone Engine

<!-- end list -->

- You will need to initially log in to Integration Manager from the
  Agent to grant access to run jobs on your behalf. Make sure this
  access is available.

- Copy the installer to your local machine. Do not install over a
  network.

**Network Port Access**

The DataCloud Agent requires that the following ports be available on
the machine where you are installing the Agent.

<table>
<tbody>
<tr class="odd">
<td>Port</td>
<td>Service</td>
<td>Inbound/Outbound</td>
<td>Local/Remote</td>
<td>Description</td>
</tr>
<tr class="even">
<td>443</td>
<td>HTTP Secure</td>
<td>Inbound and Outbound</td>
<td>Remote</td>
<td>Secure HTTP port. Used to connect to the DataCloud for transmission of secure data.</td>
</tr>
<tr class="odd">
<td>9191</td>
<td>HTTP Connection</td>
<td>Inbound and Outbound</td>
<td>Local</td>
<td><p>Used internally by DataCloud Agent for the local administration and authentication page.</p>
<p>These ports can be changed during installation. To change the ports after installation, see Agent Settings on page 21.</p></td>
</tr>
<tr class="even">
<td>9192</td>
<td>HTTP Shutdown</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

**Installing on Windows**

To install DataCloud Agent on Windows

- Download the latest DataCloud Agent installer from the Agents tab
  within Integration Manager.

<!-- end list -->

- Log in to Windows as either the Administrator user or a member of
  the Administrators user group.

<!-- end list -->

- Right-click on the installer, choose Run as Administrator, and then
  click Next. The installer file name is agent-dx-win64.exe.

<!-- end list -->

- Click Next to begin the installation.

<!-- end list -->

- Make changes to the Connection and Shutdown ports if needed.

<!-- end list -->

- Click Install.

The installer extracts the DataCloud Agent and installs the service.

- Click Close when the installation is complete.

<!-- end list -->

- Launch the Agent Settings shortcut on your desktop.

<!-- end list -->

- Enter your DataCloud credentials and then click Authorize.

After the installation is complete, the agent runs as a Windows service
called DataCloudAgent.

Licensing

DataCloud Agent does not require its own license. It will confirm with
DataCloud that you have a cloud-enabled entitlement.

Install Locations

DataCloud Agent installs data in the following locations:

|                                                                       |                                                                                              |
| --------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Location                                                              | Purpose                                                                                      |
| C:\\Program Files\\Actian\\Agent\\Application\\logs\\Agent.log        | Holds any logging related to the Agent core.                                                 |
| C:\\Program Files\\Actian\\Agent\\Application\\conf\\Agent.properties | Contains configuration information for the Agent core (i.e. logging, locations for API etc). |
| C:\\Program Files\\Actian\\Agent\\AgentInstaller.log                  | Holds any logging related to the Installation process.                                       |
| C:\\ProgramData\\Actian\\Agent\\EngineData                            | Holds execution engine logs and other internal data.                                         |
| C:\\ProgramData\\Actian\\Agent\\JobArtifacts                          | Holds artifacts and files downloaded from the cloud that are to be executed.                 |
| C:\\ProgramData\\Actian\\Agent\\JobLogs                               | Staging area for logs before they are uploaded to the DataCloud.                             |

**Uninstalling from Windows**

Use Windows Control Panel to uninstall DataCloud Agent.

To uninstall the agent

- Open Windows Control Panel.

<!-- end list -->

- Click Uninstall a program.

<!-- end list -->

- Select DataCloud Agent from the list of installed programs.

<!-- end list -->

- Click the Uninstall button to launch the wizard.

<!-- end list -->

- In the uninstallation wizard, click Uninstall.

<!-- end list -->

- Click Finish when the uninstallation is complete.

**Managing the Agent**

The DataCloud Agent service is managed through Windows Services Manager.

To manage the service

- Open Windows Control Panel.

<!-- end list -->

- Click on System and Security and then go to Administrative Tools.

<!-- end list -->

- Double-click on Services.

<!-- end list -->

- Select Actian DataCloud Agent from the list of services.

<!-- end list -->

- Use the Start, Stop, and Restart links to manage the service.

To change the Windows account that runs the Agent

- Log on to Windows on the machine running the Agent using the
  Administrator account.

<!-- end list -->

- Open the Server Manager.

<!-- end list -->

- Under Configuration, select Services.

<!-- end list -->

- Stop the Actian DataCloud Agent service.

<!-- end list -->

- Right-click on the Actian DataCloud Agent service and then select
  Properties.

<!-- end list -->

- Select the Log On tab.

<!-- end list -->

- Select the This Account radio button.

<!-- end list -->

- Enter the login credentials for the appropriate domain account.

<!-- end list -->

- Click Apply and then OK.

<!-- end list -->

- Start the Actian DataCloud Agent service.

**Using DataCloud Agent**

Jobs are scheduled and run using the DataCloud Agent through the
Integration Manager console (powered by DataCloud). Log in to
Integration Manager as an administrator or with the same user
credentials used to register the agent.

**Running Integrations with the Agent**

You can configure specific integrations to run using the agent instead
of running on the cloud. This gives the integrations access to files and
databases from the system running the agent.

To configure an integration to run on the agent

- Select the Templates tab in the Integration Manager console.

<!-- end list -->

- Create a new job template or select an existing one.

<!-- end list -->

- Set the Run on property from Cloud to Agent.

<!-- end list -->

- Create a new job config for the template.

<!-- end list -->

- Set the package, entry point, and enter any necessary parameters for
  the integration.

Once you have created your template and a configuration, you can set a
schedule or use the Run Configuration Now ![](media/image1.wmf) button
to execute the integration.

- When you run a configuration, it executes on the configuration
  owner’s agent.

**Agent Status**

Click on the Agents tab in the Integration Manager console to see a list
of the agents associated with your account. This view shows the
registration, check-in, and status information for each agent.

|                       |          |                                                                                      |
| --------------------- | -------- | ------------------------------------------------------------------------------------ |
| Icon                  | Status   | Description                                                                          |
| ![](media/image2.wmf) | Online   | The agent is online as of the last check-in time and is ready to receive jobs.       |
| ![](media/image3.wmf) | Updating | The agent is being updated.                                                          |
| ![](media/image4.wmf) | Warning  | The agent has not reported back to DataCloud in over 3 hours and requires attention. |
| ![](media/image5.wmf) | Error    | The agent has not reported back to DataCloud in over 6 hours and requires attention. |
| ![](media/image6.wmf) | Offline  | The agent is currently offline.                                                      |

- The Status field indicates the health of the agent and whether it
  can accept any commands from the cloud. If this status is a Red
  “error” state, you will not be able to submit jobs until the
  problem is resolved.

**Managing Agents**

The Actions drop-down menu for each agent allows you to perform the
following actions for the agents connected to your DataCloud account.

|                |                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------- |
| Action         | Description                                                                                    |
| Update License | Sends the current Agent license from the DataCloud.                                            |
| Update Engine  | Updates the processing engine in the agent to the latest version.                              |
| Update Agent   | Updates the agent framework to the latest version.                                             |
| Deregister     | Revokes the Agent’s access to your account and sends a shutdown command to the remote service. |

- The agent must be in Online status for the Update License, Update
  Engine, or Update Agent actions to take effect.

**Viewing Agent Logs**

Agent logs are uploaded to Integration Manager upon job completion.

Logs also are temporarily stored locally in
{install}/Application/logs/Agent.log. If you report issues to Support,
you may be asked to send these logs to provide more information about
problems the agent has encountered.

**Updating DataCloud Agent**

After you have installed Actian DataCloud Agent, you can use the
Integration Manager console to perform updates at any time.

- The Agent license automatically updates weekly. The Agent service
  and engine do not automatically update.

**When to Update**

The DataCloud Agent uses a local version of the execution engine to run
integrations transmitted from your DataCloud account.

If you have designed your integration using the current version of
Design Studio but your Agent is still using an older version of the
engine, this could cause compatibility issues when it comes time for
your integration to run on the Agent.

- [Update your Agent](#RTF5570646174696e674167656e) and engine
  whenever you schedule a newly deployed integration to run using the
  Agent.

<span id="RTF5570646174696e674167656e" class="anchor"></span>**Updating
the Agent**

Before you begin the update process, make sure the computer running the
Agent is connected to a constant power source (not running on battery
power in the case of a laptop). If the computer loses power or crashes
during the update process, reinstall the agent manually. See Agent
Installation on page 14.

To update the Agent service, engine, and license

- Log in to the Integration Manager console.

<!-- end list -->

- Go to the Agents page.

<!-- end list -->

- Locate your agent in the table.

<!-- end list -->

- Ensure the version (listed in the Version column) is 3.0.0 or
  higher.

<!-- end list -->

- Click the Actions drop-down menu and then select the appropriate
  option:

<!-- end list -->

- > Update Agent: Updates the Agent service and execution engine.

- > Update Engine: Updates the execution engine used by the Agent for
  > running jobs.

- > Update License: Updates the engine license to the latest available
  > for your account.

<!-- end list -->

- You might need to restart the Agent service after the update. See
  Managing the Agent on page 17.

**Accessing On-Premise File Storage with Agent**

A common scenario for using DataCloud Agent to execute an integration is
when you need to read or write a file stored either locally or on a
network.

By default, the Agent runs using the Windows Local System account. This
is normally sufficient to access files stored on the same machine as the
Agent.

Files stored on a network require changing the account running the
DataCloud Agent to use an account that has proper access to the network
share (usually a domain account for the network). See Managing the Agent
on page 17.

- When designating a network resource during design, use the full
  network path (for example, \\\\servername\\folder\\filename.csv).

**Agent Settings**

**DataCloud Account Management**

The Agent installer adds an icon to your desktop to access the local
Agent management page to set your DataCloud credentials.

Open the Agent Settings shortcut or go to
[�http://localhost:9191/agent/settings](http://localhost:9191/agent/settings)
in a browser on the computer running the Agent to access the Agent
settings page.

**Changing Ports**

After installation, you can change the ports used by the local
configuration page.

To change configuration ports

- Log in to Windows as Administrator.

<!-- end list -->

- Open the following file using a text editor: C:\\Program
  Files\\Actian\\Agent\\Application\\conf\\server.xml

<!-- end list -->

- To change the HTTP Connection port, edit the port value in the
  following section:

\<Connector port="9191" protocol="HTTP/1.1"  
               connectionTimeout="20000"  
               redirectPort="8443" /\>

- To change the HTTP Shutdown port, edit the port value in the
  following line:

\<Server port="9192" shutdown="SHUTDOWN"\>

- Save changes to the file.

<!-- end list -->

- Restart the Agent service. See Managing the Agent on page 17.

**Concurrent Execution**

By default, the Agent executes one job at a time, with additional jobs
going into the job queue. You can change this setting for the Agent to
allow up to 4 concurrent executions (one concurrent execution per
integration).

- When the Agent operates in non-concurrent mode, jobs are executed in
  first-in-first-out (FIFO) order. If you allow concurrent executions,
  however, the jobs may not be executed in the order they were
  submitted. When designing your integrations, make sure you do not
  introduce dependencies that could lead to unexpected results if the
  jobs are executed out of order.

To change the concurrency setting

- Log in to Windows as Administrator.

<!-- end list -->

- Open the following file using a text editor: C:\\Program
  Files\\Actian\\Agent\\Application\\conf\\Agent.properties

<!-- end list -->

- Edit the following line to change the maximum concurrent executions
  to a value between 1 and 4.

agent.concurrency = 1

- Save changes to the file.

<!-- end list -->

- Restart the Agent service. See Managing the Agent on page 17.

<!-- end list -->

- Use care when editing the Agent.properties file. The Agent uses this
  file to locate its execution engine and connect to the DataCloud.
  Inadvertent changes could cause the Agent to stop working.

**Best Practices for Using Agent**

To ensure your use of the Actian DataCloud Agent is successful, here are
some important concepts and best practices.

- Ensure the agent can access your DataCloud account over the internet
  by providing your cloud account credentials and opening appropriate
  firewall ports (see Agent Installation on page 14). This lets you
  use the Integration Manager console to manage integrations and
  synchronize jobs with the agent.

- A successful agent installation includes the ability to access data
  sources in the on-premise environment. This requires that access be
  given for local data resources, including permissions, credentials,
  and installation of any necessary drivers or clients.

- No data is sent by the Agent to the DataCloud unless your design
  allows for it. Only deployed packages, logs, and job status details
  are exchanged. For this reason, the agent is ideal for handling
  sensitive data.

To fully test your design, use the on-premise version of Actian Data
Integrator to design integrations destined for the agent. Talk to your
Actian account executive to find out more.

**Scheduling Agent Jobs**

The Integration Manager console allows you to set a schedule for
agent-executed jobs using a cron expression, which is a specially
formatted text string.

The example below is a cron expression representing a schedule that will
run at 1:25 P.M. on the first day of each month.

0 25 13 1 \* ? \*

![](media/image7.wmf)

**Building a Cron Expression**

A cron expression is composed of 6 or 7 values separated by spaces. Each
of these values represents part of the schedule and can be either a
number or a certain special character.

Expression Fields

|              |          |                 |                    |
| ------------ | -------- | --------------- | ------------------ |
| Field        | Required | Values          | Special Characters |
| Second       | Yes      | 0-59            | , - \* /           |
| Minute       | Yes      | 0-59            | , - \* /           |
| Hour         | Yes      | 0-23            | , - \* /           |
| Day of Month | Yes      | 1-31            | , - \* / L W ?     |
| Month        | Yes      | 1-12 or JAN-DEC | , - \* /           |
| Day of Week  | Yes      | 1-7 or SUN-SAT  | , - \* / \# ?      |
| Year         | No       | 1970-2099       | , - \* /           |

Special Characters

Special characters allow you to specify wildcards, ranges, and other
conditions for each field.

<table>
<tbody>
<tr class="odd">
<td>Character</td>
<td>Description</td>
<td>Examples</td>
</tr>
<tr class="even">
<td>*</td>
<td>All values for the field are selected.</td>
<td>* in the Hour field means every hour.</td>
</tr>
<tr class="odd">
<td>?</td>
<td>No specific value required. Only usable in the Day of Month and Day of Week fields.</td>
<td>To set a schedule that runs on Sundays regardless of the day of the month, use a ? in the Day of Month field and a 1 in the Day of Week field.</td>
</tr>
<tr class="even">
<td>-</td>
<td>Specify a range (inclusive) between 2 values.</td>
<td>1-3 in the Hour field (along with a 0 in the Minute and Second fields) is triggered at 1:00 A.M., 2:00 A.M., and 3:00 A.M.</td>
</tr>
<tr class="odd">
<td>,</td>
<td>Separate multiple values.</td>
<td>1,3 in the Hour field means 1:00 A.M. and 3:00 A.M.</td>
</tr>
<tr class="even">
<td>/</td>
<td>Incremental trigger. Enter in the format X/Y, where X is the starting value and Y is the increment.</td>
<td>0/15 in the Minute field means the schedule begins at minute 00 and then runs every 15 minutes thereafter.</td>
</tr>
<tr class="odd">
<td>L</td>
<td><p>Last day of the month or week.</p>
<p>Can be combined with other values in each field as illustrated below.</p>
<ul>
<li><p>Day of Month: L-X, where X is a number of days to offset from the last calendar day of the month.</p></li>
<li><p>Day of Week: XL, where X is a day value (1-7).</p></li>
</ul></td>
<td><p>L in the Day of Month field means the last calendar day of the month.</p>
<p>L-2 in the Day of Month field means the second-to-last calendar day of the month.</p>
<p>L in the Day of Week field simply means 7 (Saturday).</p>
<p>7L in the Day of Week field means the last Saturday of the month.</p></td>
</tr>
<tr class="even">
<td>W</td>
<td>Weekday (Monday-Friday) nearest the given day. Enter in the format XW, where X is the day of the month.</td>
<td><p>12W in the Day of Month field is triggered on the 12th day of the month if that day falls on a weekday. If the 12th falls on a Saturday or Sunday, the schedule runs on the following Monday.</p>
<p>LW in the Day of Month field is triggered on the last weekday of the month.</p></td>
</tr>
<tr class="odd">
<td>#</td>
<td><p>Exact monthly instance of the specified day of the week. Enter in the format X#Y, where X is the day of the week and Y is the instance.</p>
<ul>
<li><p>A value using X#5 will not be triggered for the month if there are not 5 of day X within the month.</p></li>
</ul></td>
<td>2#3 in the Day of Week field means the 3rd Monday each month.</td>
</tr>
</tbody>
</table>

**Examples**

Below are several examples of simple and complex cron expressions.

Simple Daily

Run the schedule at 9:00 A.M. every day.

0 0 9 \* \* ? \*

|         |         |       |              |       |             |      |
| ------- | ------- | ----- | ------------ | ----- | ----------- | ---- |
| Seconds | Minutes | Hours | Day of Month | Month | Day of Week | Year |
| 0       | 0       | 9     | \*           | \*    | ?           | \*   |

Complex Daily

Run the schedule every 5 seconds for 1 minute beginning at 9:00 A.M.
every day.

0/5 0 9 \* \* ? \*

|         |         |       |              |       |             |      |
| ------- | ------- | ----- | ------------ | ----- | ----------- | ---- |
| Seconds | Minutes | Hours | Day of Month | Month | Day of Week | Year |
| 0/5     | 0       | 9     | \*           | \*    | ?           | \*   |

Simple Weekly

Run the schedule at 9:25 A.M. every Friday.

0 25 9 \* \* 6 \*

|         |         |       |              |       |             |      |
| ------- | ------- | ----- | ------------ | ----- | ----------- | ---- |
| Seconds | Minutes | Hours | Day of Month | Month | Day of Week | Year |
| 0       | 25      | 9     | \*           | \*    | 6           | \*   |

Complex Weekly

Run the schedule at 9:00 A.M. every Friday, but only in January or
February of 2014.

0 0 9 \* 1,2 6 2014

|         |         |       |              |       |             |      |
| ------- | ------- | ----- | ------------ | ----- | ----------- | ---- |
| Seconds | Minutes | Hours | Day of Month | Month | Day of Week | Year |
| 0       | 0       | 9     | \*           | 1,2   | 6           | \*   |

Monthly

Run the schedule at 9:00 A.M., 9:22 A.M., and 9:44 A.M. on the last
Thursday of each month.

0 0,22,44 9 ? \* L5 \*

|         |         |       |              |       |             |      |
| ------- | ------- | ----- | ------------ | ----- | ----------- | ---- |
| Seconds | Minutes | Hours | Day of Month | Month | Day of Week | Year |
| 0       | 0,22,44 | 9     | ?            | \*    | L5          | \*   |

Yearly

Run the schedule at 2:27 P.M., 3:27 P.M., and 4:27 P.M. on the weekday
nearest the 12th day of the month every October.

0 27 14-16 12W 10 ? \*

|         |         |       |              |       |             |      |
| ------- | ------- | ----- | ------------ | ----- | ----------- | ---- |
| Seconds | Minutes | Hours | Day of Month | Month | Day of Week | Year |
| 0       | 27      | 14-16 | 12W          | 10    | ?           | \*   |

## Files Installed by Actian Integration Manager

When initiating access to Actian Integration Manager, the ProgramFiles
and ProgramData install several items on your computer:

- **Cosmos.ini** – This is where a user will need to go to change or
  update the license file.

- **IntegrationManager.log** – This is the location of the log files;
  they will assist a user in troubleshooting issues.

- **Worker.log** – This is location of the DataConnect Worker log;
  they will assist with troubleshooting issues.
