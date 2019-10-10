# Identity and Access Management

Access control in GCP are managed using __IAM__, __primitive roles__ and __scopes__.

__IAM__ provides _predefined roles_. These roles are grouped by service. These roles are designed to provide minimal set of permissions needed to carry out a task. Can also define _custom roles_.

__Primitive roles__ provide coarse-grained access controls to resources.

__Scopes__ are access controls that apply to instances of VMs.

Three type of roles: __primitive__, __predefined__, and __custom__

IAM roles support __separation of duties__ and __the principal of least privilege__. Separation of duties ensures that two or more people are required to complete a sensitive task.

IAM Resource Hierarchy: Organization => Project => Resources

[![Authentication Decision Tree](https://storage.googleapis.com/gweb-cloudblog-publish/images/4_jqGRVMm.max-1000x1000.png)](https://cloud.google.com/blog/products/identity-security/identity-and-authentication-the-google-cloud-way)

## Organization Node

* Organization is created by Google Sales.
* Owner is established at creation (G Suite Super Admin).
* It is the root node for Google Cloud Resources.
* 2 organization roles:
  * Organization Admin: control over all cloud resources.
  * Organization Viewer: View access to all resources.
  * Project Creator: controls project creation.

## Cloud Platform Authorization

* Uses Google's credential system:
  * Manage accounts from G Suite (Google-hosted domains) or Google accounts (@gmail).
  * Sync existing credentials using Google Cloud Directory Sync.
  * Optionally implement single sign-on (SSO).
* Features:
  * Session activity tracking.
  * Session management tools.
  * Security alerts.
  * Suspicious activity detection.

## Google Cloud Directory Sync (GCDS)

* Sync GSuite accounts to match the user data in existing LDAP or Active Directory databases:
  * Syncs groups and memberships, not content or settings.
  * Supports sophisticated rules for custom mapping of users, groups, non-employee contacts, user profiles, aliases, and exceptions.
* One-way synchronization from LDAP to directory.
* Runs as a utility in your server environment.

## Single Sign-On (SSO)

* BYO authentication mechanism.
* Federate.
* Revoke access using your existing credential management.
* Google Apps Directory Sync integrates with LDAP.

## Best Practices

* Principle of least priviledge.
* Use groups.
* Control who can change policies and group memberships.
* Audit policy changes: Audit logs record project-level permission changes.

## Project Roles

_Note: Add a new user to a Project by clicking on the account picture._

Groups of permissions.

* Primitive Roles:
  * Owner: All rights including deleting project.
  * Editor: Deploy applications, modify code, configure services, and viewer rights.
  * Viewer: Read-only access.
  * __Billing Administrator__ (???): Manage billing, add administrators, remove administrators.
* Curated Roles: Custom roles with individual permissions.

## Service Accounts

Service accounts are used to provide identities independent of human users.

Service accounts are identities that can be granted roles.

Service accounts are assigned to VMs

__Scopes__ are permissions granted to a VM to perform some operations.

An instance can only perfrom operations allowed by both __IAM roles__ assigned to the servie account and __scopes__ defined on the instance.

Allows you to delegate permissions to application to carryout server-to-server interactions.

* Name looks like an email address.
* Three different types:
  * User-created (custom).
  * Built-in (Compute Engine and App Engine default service accounts).
  * Google APIs service account (for Google internal processes).
* Authenticate with keys:
  * Google manages keys for App and Compute Engine.
  * You can manage keys for some resources.
* Can have roles assigned.
* Customizing Scopes for a VM:
  * Allows access to other Google Cloud Platform resources.
  * You can create an instance with customized scopes.
  * For user-created service accounts, use IAM roles instead.
