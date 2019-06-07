# Security Best Practices

## Enable Macro Encryption

Never hard-code sensitive credentials or personal information within
your integration designs. Always use macros and macro encryption at
design time for such data. For more information about encrypting macro
values at design time, see [Managing Macro Sets and
Macros](http://docs.actian.com/dataconnect/11.2/index.html#page/User%2FManaging_Macro_Sets_and_Macros.htm%23).

Integration Manager stores macro values within a database. You should
enable Macro Encryption for any production installations of Integration
Manager so that sensitive data cannot be viewed directly form the
database. See Encryption of Macro Values at Rest on page 65. When
enabled, all macro values are encrypted.

- We highly recommend that you do not share encryption keys between
  environments.

If you are a DataCloud customer, Macro Encryption is always enabled.

## Enable HTTPS

Integration Manager authenticates all user access over HTTP or HTTPS
protocols. Enable HTTPS (TLS 1.2) for any production installations of
Integration Manager so that your API traffic cannot be read if
intercepted. See Configuring HTTPS on page 63.

If you are a DataCloud customer, HTTPS (TLS 1.2) is always enabled.

## Other Best Practices

- Connect only to external sources and targets that support and enable
  TLS 1.2 connections.

- Perform penetration testing on any internet-facing installations of
  Integration Manager at regular intervals. If you are a DataCloud
  customer, Actian Corporation takes care of this for you.

- Perform security reviews on any integration design that you plan on
  deploying to an internet-facing installation of Integration Manager
  or DataCloud. We can help: Contact our Services and Solutions team
  for more information. Partners are required to submit for security
  reviews prior to publishing an integration to their end users.
