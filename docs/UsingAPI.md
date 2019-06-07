# Using Integration Manager API

The purpose of this guide is to provide programmers, developers, and
technical managers with the knowledge of the Integration Manager
Application Programming Interface (API).

- Not all users have full access to the Actian Integration Manager
  API. To have full access a user must own the Actian Integration
  Manager Development Package that includes Integration Manager,
  access to the Designer, and access to the API. Contact your account
  executive to verify that your account has access to the API.

## Available Services

The Actian Integration Manager API provides the following:

- Job Execution API

- Job Configuration API

- Repository Manager API

- Macro Manager API

- License Manager API

- Agent Manager API

- Account Management API

## Job Execution

Execute Jobs and inspect the status of queued, running, and recently
finished Jobs. Job - Container for a RuntimeConfig snapshot typically
created from a JobConfig or ad hoc API call.Authorization via JWT Token
\[Authorization header, Bearer authentication scheme\]

**/jobs**

|        |                                                                                                                                                                                                                                                                                                        |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| POST   | Creates and asyncronously queues a new Job. Returns a UUID to track the Job's progress. This is not an idempotent call\!                                                                                                                                                                               |
| GET    | Gets a list of queued, cancelled, aborted, running, and/or completed Jobs, sorted by scheduled time.                                                                                                                                                                                                   |
| DELETE | Attempts to cancel or abort all queued and/or running Jobs. There is no guarantee that a job will be cancelled before it runs OR that it will be aborted before it completes. No information will be returned about the number of jobs cancelled or aborted, even if there are no eligible candidates. |

**/jobs/_uuid_**

|        |                                                                                                                                                                                                   |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| GET    | Retrieves details about a specific Job based on its UUID.                                                                                                                                         |
| DELETE | Attempts to cancel or abort a specific queued or running Job based on its UUID. There is no guarantee that a job will be cancelled before it runs OR that it will be aborted before it completes. |

**/jobs/_uuid_/log**

|     |                                                                                     |
| --- | ----------------------------------------------------------------------------------- |
| GET | Retrieves the Log file for a completed Job. Queued or running jobs will return 404. |

## Job Configuration

Build and maintain hierarchical Job Configurations.

- **JobTemplate** - Abstract container for RuntimeConfig info that can
  be inherited by a JobConfig.

- **JobConfig** - Executable and/or schedulable container for a
  RuntimeConfig.

Soft deletes are permanent after 30 days.

Authorization via JWT Token \[Authorization header, Bearer
authentication scheme\].

**/jobstemplates**

|      |                                     |
| ---- | ----------------------------------- |
| POST | Creates a new JobTemplate record.   |
| GET  | Gets a list of JobTemplate records. |

**/jobstemplates/_id_/clone**

|      |                                                                            |
| ---- | -------------------------------------------------------------------------- |
| POST | Clones a JobTemplate with a new Id, empty external Id, and new Audit info. |

**/jobstemplates/_id_/files/_key_**

|        |                                                                                |
| ------ | ------------------------------------------------------------------------------ |
| GET    | Retrieves File found at {key}. Key can include pathInfo.                       |
| PUT    | Creates/replaces File found at {key}. Key can include pathInfo.                |
| DELETE | Deletes File found at {key}. Key can include pathInfo. (Internal: Hard Delete) |

**/jobstemplates/_id_/jobconfigs**

|      |                                                                |
| ---- | -------------------------------------------------------------- |
| POST | Creates a new JobConfig record. TemplateId in body is ignored. |
| GET  | Gets a list of JobConfig records for this JobTemplate.         |

**/jobstemplates/_id_/package/entrypoints**

|     |                                                     |
| --- | --------------------------------------------------- |
| GET | Retrieves Entry Point list for JobTemplate Package. |

**/jobsconfigs**

|      |                                   |
| ---- | --------------------------------- |
| POST | Creates a new JobConfig record.   |
| GET  | Gets a list of JobConfig records. |

**/jobsconfigs/_id_**

|        |                                                                              |
| ------ | ---------------------------------------------------------------------------- |
| GET    | Retrieves a specific JobConfig based on its record id or external id.        |
| PUT    | Replaces an existing JobConfig based on its record id or external id.        |
| DELETE | Deletes a specific JobConfig based on its record id. (Internal: Soft Delete) |

**/jobconfigs/_id_/clone**

|      |                                                                          |
| ---- | ------------------------------------------------------------------------ |
| POST | Clones a JobConfig with a new Id, empty external Id, and new Audit info. |

**/jobsconfigs/_id_/files**

|      |                                                        |
| ---- | ------------------------------------------------------ |
| GET  | Gets a list of JobConfig Files.                        |
| POST | Creates File found at {key}. Key can include pathInfo. |

**/jobsconfigs/_id_/files/_key_**

|        |                                                                                |
| ------ | ------------------------------------------------------------------------------ |
| GET    | Retrieves File found at {key}. Key can include pathInfo.                       |
| PUT    | Replaces File found at {key}. Key can include pathInfo.                        |
| DELETE | Deletes File found at {key}. Key can include pathInfo. (Internal: Hard Delete) |

**/jobsconfigs/_id_/jobs**

|        |                                                                                                                                                                                                                                                                                                                           |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| POST   | Creates and asyncronously queues a new Job based on this JobConfig. Returns a UUID to track the Job's progress. This is not an idempotent call\!                                                                                                                                                                          |
| GET    | Gets a list of queued, cancelled, aborted, running, and/or completed Jobs for this JobConfig, sorted by scheduled time.                                                                                                                                                                                                   |
| DELETE | Attempts to cancel or abort all queued and/or running Jobs for this JobConfig. There is no guarantee that a job will be cancelled before it runs OR that it will be aborted before it completes. No information will be returned about the number of jobs cancelled or aborted, even if there are no eligible candidates. |

**/jobconfigs/_id_/package/entrypoints**

|     |                                                   |
| --- | ------------------------------------------------- |
| GET | Retrieves Entry Point list for JobConfig Package. |

## Repository Manager

Manage common package and file repositories within an Account.

- **Packages** - contains global djars

- **Files** - contains other global ad hoc files

- **Extensions** - holds product extensions such as MCF, DMS

Authorization via JWT Token \[Authorization header, Bearer
authentication scheme\].

**/packages**

|      |                                                           |
| ---- | --------------------------------------------------------- |
| GET  | Gets a list of package names.                             |
| POST | Creates Package found at {key}. Key can include pathInfo. |

**/packages/_key_**

|        |                                                             |
| ------ | ----------------------------------------------------------- |
| GET    | Retrieves Package found at {key}. Key can include pathInfo. |
| PUT    | Replaces Package found at {key}. Key can include pathInfo.  |
| DELETE | Deletes the Package found at {key} (HARD delete)            |

**/packages/_key_/entrypoints**

|     |                                                                            |
| --- | -------------------------------------------------------------------------- |
| GET | Retrieves Entry Point list for Package at {key}. Key can include pathInfo. |

**/packages/_key_/macrosets**

|     |                                                                                  |
| --- | -------------------------------------------------------------------------------- |
| GET | Retrieves embedded MacroSet list for Package at {key}. Key can include pathInfo. |

**/packages/_key_/projects**

|     |                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------- |
| GET | Retrieves Project list for Package at {key}. Key can include pathInfo. This list will be empty for v9 or earlier djars. |

**/files**

|      |                                                                                   |
| ---- | --------------------------------------------------------------------------------- |
| GET  | Gets a list of ad hoc files and artifacts (maps, processes, common files, etc...) |
| POST | Creates File found at {key}. Key can include pathInfo.                            |

**/files/_key_**

|        |                                                          |
| ------ | -------------------------------------------------------- |
| GET    | Retrieves file found at {key}. Key can include pathInfo. |
| PUT    | Replaces file found at {key}. Key can include pathInfo.  |
| DELETE | Deletes the file found at {key} (HARD delete)            |

**/extensions**

|      |                                                                               |
| ---- | ----------------------------------------------------------------------------- |
| POST | Adds or updates a Product Extension. (Asynchronously deployed to all Servers) |
| GET  | Gets a list of currently deployed Product Extensions.                         |

**/extensions/_type_/_name_/_version_**

|        |                                                                                                           |
| ------ | --------------------------------------------------------------------------------------------------------- |
| GET    | Retrieves information about a specific versioned Product Extension.                                       |
| DELETE | Deletes a specific versioned Product Extension, which is then asynchronously undeployed from all Servers. |

## Macro Manager

Manage global macros within an Account.

Authorization via JWT Token \[Authorization header, Bearer
authentication scheme\].

**/macrosets**

|      |                                    |
| ---- | ---------------------------------- |
| GET  | Retrieves a list of MacroSet names |
| POST | Creates a new MacroSet             |

**/macrosets/_id_**

|        |                                                                             |
| ------ | --------------------------------------------------------------------------- |
| GET    | Retrieves a specific MacroSet                                               |
| PUT    | Replaces an existing MacroSet                                               |
| DELETE | Clears a specific MacroSet based on its id (hard delete of keys and values) |

**/macrosets/_id_/macros**

|      |                                     |
| ---- | ----------------------------------- |
| POST | Creates a Macro (within a MacroSet) |

**/macrosets/_id_/name**

|     |                               |
| --- | ----------------------------- |
| PUT | Change the name of a MacroSet |

**/macrosets/_id_/macros/_name_**

|        |                                                        |
| ------ | ------------------------------------------------------ |
| GET    | Retrieves a Macro                                      |
| PUT    | Replaces a Macro                                       |
| DELETE | Deletes a specific Macro based on its id (hard delete) |

**/macro**

|     |                            |
| --- | -------------------------- |
| GET | Retrieves a list of Macros |

## License Manager

View and update licensing information.

**/license**

|     |                                                             |
| --- | ----------------------------------------------------------- |
| GET | Retrieves current licensing information                     |
| PUT | New licensing information with a valid, signed license file |

## Agent Manager

Manage agents within an Account.

**/agents**

|     |                              |
| --- | ---------------------------- |
| GET | Gets a list of Agent records |

**/agents/_id_**

|        |                                                       |
| ------ | ----------------------------------------------------- |
| PATCH  | Sends control message to Agent record based on its id |
| DELETE | Deregisters an Agent                                  |

## Account Management

Account and User Administration.

**/accounts**

|     |                             |
| --- | --------------------------- |
| GET | Retrieves Main Account info |

**/users**

|      |                       |
| ---- | --------------------- |
| POST | Creates a new User.   |
| GET  | Gets a list of Users. |

**/users/_id_**

|     |                                                               |
| --- | ------------------------------------------------------------- |
| GET | Retrieves a specific User based on its record id or username. |
| PUT | Replaces an existing User based on its record id or username. |

**/resourcegroups**

|      |                                 |
| ---- | ------------------------------- |
| POST | Creates a new Resource Group.   |
| GET  | Gets a list of Resource Groups. |

**/resourcegroups/_id_**

|        |                                                                          |
| ------ | ------------------------------------------------------------------------ |
| GET    | Retrieves a specific Resource Group based on its record id.              |
| PUT    | Replaces an existing Resource Group based on its record id.              |
| DELETE | Deletes a specific Group based on its record id. (Internal: Soft Delete) |

**/resourcegroups/id/resources**

|      |                                                       |
| ---- | ----------------------------------------------------- |
| POST | Adds a Resource to this Resource Group.               |
| GET  | Retrieves a list of Resources in this Resource Group. |

**/resourcegroups/id/resources**

|      |                                                      |
| ---- | ---------------------------------------------------- |
| POST | Adds a Grantee to this Resource Group.               |
| GET  | Retrieves a list of Grantees in this Resource Group. |
