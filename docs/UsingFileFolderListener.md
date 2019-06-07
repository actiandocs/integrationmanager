# Using the File Folder Listener Service

How the Listener Service Works 53

Error Handling 54

The File Folder Listener Service monitors directories for files and will
execute a pre-defined Job Configuration when triggered.

## Installation and Configuration

The File Folder Listener Service is included with the installation of
Integration Manager. A Windows service is registered with the name
Actian File Folder Listener and must be started manually after
configuration is complete.

To configure file listeners, you must update the
file-folder-listener-listeners.yml file found in your installation
path’s conf directory.

Default Path:

C:\\ProgramData\\Actian\\IntegrationManager\\conf\\file-folder-listener-listeners.yml

Listener Properties:

<table>
<tbody>
<tr class="odd">
<td>Property</td>
<td>Default Value</td>
<td>Description</td>
</tr>
<tr class="even">
<td>id</td>
<td></td>
<td>Identifier for the listener</td>
</tr>
<tr class="odd">
<td>name</td>
<td></td>
<td>Name of the listener</td>
</tr>
<tr class="even">
<td>config-id</td>
<td></td>
<td>The configuration id to run</td>
</tr>
<tr class="odd">
<td>active</td>
<td>true</td>
<td>Whether or not the listener is active</td>
</tr>
<tr class="even">
<td>delete-files</td>
<td>false</td>
<td><p>When set to false, files will be moved to a .backup directory after the job is submitted.</p>
<p>When set to true, files will be deleted from the system after the job is submitted.</p></td>
</tr>
<tr class="odd">
<td>auto-create-directories</td>
<td>false</td>
<td>Automatically creates any non-existent directories in the path of the directory specified</td>
</tr>
<tr class="even">
<td>recursive</td>
<td>false</td>
<td>Searches for changes to files in all subdirectories</td>
</tr>
<tr class="odd">
<td>flatten-directories</td>
<td>false</td>
<td>Used in conjunction with recursive, removes any subdirectories from the path of file (just the file name remains)</td>
</tr>
<tr class="even">
<td>directory</td>
<td></td>
<td>The directory to monitor</td>
</tr>
<tr class="odd">
<td>include-pattern</td>
<td></td>
<td>Includes files if the file name matches the regular expression pattern you specify in the space provided</td>
</tr>
<tr class="even">
<td>exclude-pattern</td>
<td></td>
<td>Excludes files if the file name matches the regular expression pattern you specify in the space provided</td>
</tr>
<tr class="odd">
<td>incoming-message-name</td>
<td>msg1</td>
<td>The name of the djmessage object passed to the dataconnect process</td>
</tr>
</tbody>
</table>

Example file-folder-listener-listeners.yml configuration:

listeners:

- id: listener1

name: listener1name

config-id: 10

active: true

delete-files: true

auto-create-directories: false

recursive: false

flatten-directories: false

directory: C:\\Program
Files\\Actian\\IntegrationManager\\listener\\1

include-pattern: ^runme.txt

exclude-pattern: ^skipme.txt

incoming-message-name: msgTest

- id: listener2

name: listener2name

config-id: 2

active: true

delete-files: false

auto-create-directories: false

recursive: false

flatten-directories: false

directory: C:\\Program
Files\\Actian\\IntegrationManager\\listener\\2

include-pattern: ^runme.txt

exclude-pattern: ^skipme.txt

incoming-message-name: msgTest

## How the Listener Service Works

When a file is placed in a directory that a listener is monitoring, and
it matches the criteria (include/exclude patterns), a POST call is made
against /jobconfigs/{id}/listener endpoint. The payload is the file
contents sent as plain/text. The payload is set as the incoming
djmessage body, and any headers that are sent to the listener endpoint
will be available as properties on the djmessage. By default, the
djmessage name will be msg1, but you can override this through your
listener configuration. The message name will be sent over as a query
parameter.

For example, if you have a listener configured with the following
properties:

id: listener1

name: listener1name

config-id: 10

active: true

delete-files: true

auto-create-directories: false

recursive: false

flatten-directories: false

directory: C:\\Program Files\\Actian\\IntegrationManager\\listener\\1

include-pattern: ^runme.txt

exclude-pattern: ^skipme.txt

incoming-message-name: msgTest

When a file named “runme.txt” is placed in the directory “C:\\Program
Files\\Actian\\IntegrationManager\\listener\\1,” the following API call
is made, which runs a job: POST
/jobconfigs/10/listener?messageName=msgTest

Within a DataConnect process, you would have access to the file contents
in msgTest body.

Some file metadata is available in msgTest properties.

Example Metadata:

|                  |                                                                                                                                        |                                                                       |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Property         | Description                                                                                                                            | Sample Value                                                          |
| fileabsolute     | A boolean option specifying whether the consumed file denotes an absolute path or not                                                  | true                                                                  |
| fileabsolutepath | Only the file name (the name with no leading paths)                                                                                    | C:\\Program Files\\Actian\\IntegrationManager\\listener\\1\\runme.txt |
| filelastmodified | A Long value containing the last modified timestamp of the file                                                                        | 1517516603175                                                         |
| filelength       | A long value containing the file size                                                                                                  | 16                                                                    |
| filename         | Name of the consumed file as a relative file path with offset from the starting directory configured on the endpoint                   | runme.txt                                                             |
| filenameconsumed | The name of the file that was consumed                                                                                                 | runme.txt                                                             |
| filenameonly     | Only the file name (the name with no leading paths)                                                                                    | runme.txt                                                             |
| fileparent       | The parent path                                                                                                                        | C:\\Program Files\\Actian\\IntegrationManager\\listener\\1            |
| filepath         | The file path. For relative files this is the starting directory + the relative filename. For absolute files this is the absolute path | C:\\Program Files\\Actian\\IntegrationManager\\listener\\1\\runme.txt |
| filerelativepath | The relative path                                                                                                                      | runme.txt                                                             |

## Error Handling

If an error occurs while invoking the API endpoint, the file that
triggered the event is moved into an .error directory. When the API call
is successful, if the delete-files property is set to true, the file are
deleted from the system.

It is up to end users to do their own error handling within their
DataConnect process to back up the file if an error occurs. This is why
the delete-files property defaults to false.
