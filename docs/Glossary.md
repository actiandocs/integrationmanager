# Glossary

**Agents**

A DataConnect application that runs on-premise but can be scheduled from
the Integration Manager powered by Actian DataCloud and can be used to
perform an integration between on-premise and cloud-based resources.
Agents may be used for different purposes, such as Job Processor, Engine
Facade, File Flinger, Message Publisher, or Stream Publisher to
DataCloud.

**Configuration**

It specifies which Package should be executed, and provides any needed
system variables (see Macros) and files to run the Package. The
Configuration may also specify a schedule on which to run, or be run on
demand. The Configuration may inherit assets (Macros, Files, Package,
and Entry Point) from a Template, or it may override those assets.

**Credentials**

Username/Password

**Entry Point**

The place where the execution of a Package begins. Every Package must
define one or more entry points. The entry point must be a process.

**Job**

Every time a Configuration executes, that instance of the execution is a
Job. Each Job is associated with runtime metrics and results, often
found in the log.

**Log**

DataConnect engine log related to a Job.

**Macros**

Most packages are designed to require Configuration values. These
Configuration values can be supplied as key-value pairs called Macros,
specified at the global level, the Template level, or the Configuration
level. If the same Macro key is provided multiple places, the
Configuration Macro overrides the Template Macro, which would override
the Global Macro. Macros can be added individually or through a Macro
file in either XML or JSON format.

**Package**

The maps and processes created with DataConnect that will be executed
once the Configuration is run. This will be a DataConnect djar file.

**Template**

Specifies what Package should be executed and provides any needed system
variables (see Macros) and files to run the Package. The Template cannot
be executed or scheduled, but provides the basis for one or more
Configurations that may inherit assets (Macros, Files, Package, and
Entry Point) from the Template.
