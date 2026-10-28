# SC-300 practice questions

These 15 scenario questions cover the four SC-300 domains in proportion to their weights in the [official study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/sc-300) (skills measured as of October 28, 2026). Each answer explains why the right option works, why the others fail, and links to the Microsoft Learn page behind it. For the study guide and cheat sheet, see the [README](README.md).

> Unofficial study notes by Examice. Not affiliated with or endorsed by Microsoft. The practice questions are original and are not taken from the exam.

### Question 1

*Domain: Implement and manage user identities*

Contoso has an administrative unit named Paris. The only member of the unit is the security group Paris-Staff, which holds 80 users. Megan has the Helpdesk Administrator role scoped to the Paris unit, but she cannot reset passwords for any of the 80 users. You need Megan to reset passwords for those users and no one else. What should you do?

- A. Make Paris-Staff a role-assignable group.
- B. Add the 80 users themselves to the Paris administrative unit, for example with a dynamic membership rule on the unit.
- C. Create a second administrative unit inside Paris that contains the group's members.
- D. Assign Megan the Helpdesk Administrator role at the tenant scope.

<details><summary>Show answer</summary>

**B.** Adding a group to an administrative unit brings the group object into scope, not its members. To let a scoped admin manage the users, the users must be members of the unit themselves. A dynamic membership rule on the unit keeps that list current.

- A is wrong because role-assignable groups let you assign roles to a group. They do not change what an administrative unit covers.
- C is wrong because administrative units cannot be nested.
- D is wrong because a tenant scope lets Megan reset passwords for every user, which breaks the "no one else" requirement.

Docs: [Administrative units](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/administrative-units), [dynamic membership for administrative units](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/admin-units-members-dynamic)

</details>

### Question 2

*Domain: Implement and manage user identities*

You are a Global Administrator. HR wants to tag users with a cost center that only HR staff can read or change, so you plan an attribute set named HR with a custom security attribute named CostCenter. When you open Custom security attributes in the Microsoft Entra admin center, you cannot add an attribute set. What should you do first, using the least privilege?

- A. Buy Microsoft Entra ID P2 licenses for the HR staff.
- B. Store the cost center in a directory extension attribute instead.
- C. Assign yourself the Privileged Role Administrator role.
- D. Assign yourself the Attribute Definition Administrator role.

<details><summary>Show answer</summary>

**D.** Out of the box, not even a Global Administrator can read, define, or assign custom security attributes. Attribute Definition Administrator defines attribute sets and attributes. Later, HR staff who assign values need Attribute Assignment Administrator, scoped to the HR set.

- A is wrong because custom security attributes are available in every Microsoft Entra ID edition.
- B is wrong because anyone who can read the object can read a directory extension, so it fails the requirement that only HR can read the value.
- C is wrong because Privileged Role Administrator lets you assign roles, which a Global Administrator can already do. It grants no attribute permissions itself.

Docs: [Custom security attributes](https://learn.microsoft.com/en-us/entra/fundamentals/custom-security-attributes-overview)

</details>

### Question 3

*Domain: Implement and manage user identities*

Contoso has acquired Fabrikam. Both use their own Microsoft Entra tenant. Fabrikam employees must appear in the Contoso tenant automatically, be updated when their details change in Fabrikam, and be removed when they leave. Contoso admins must be able to stop the process at any time. What should you configure?

- A. In the Contoso tenant, a synchronization job that pulls users from Fabrikam. Nothing is needed in Fabrikam.
- B. In the Fabrikam tenant, a cross-tenant synchronization configuration with the user scope and attribute mappings. In the Contoso tenant, allow user synchronization into the tenant in the inbound cross-tenant access settings for Fabrikam.
- C. In the Contoso tenant, a single bulk invitation of every Fabrikam user from a CSV file.
- D. Microsoft Entra Connect Sync installed in both tenants.

<details><summary>Show answer</summary>

**B.** Cross-tenant synchronization is a push from the source tenant, here Fabrikam. The scope and the attribute mappings are configured in the source. The target tenant, Contoso, opts in with the inbound setting that allows user synchronization, and target admins can stop synchronization at any time.

- A is wrong because cross-tenant synchronization does not pull from the target side.
- C is wrong because a bulk invitation runs once. It does not update or remove accounts as Fabrikam staff change or leave.
- D is wrong because Connect Sync synchronizes on-premises AD DS to Microsoft Entra ID. It does not synchronize one Entra tenant to another.

Docs: [Cross-tenant synchronization](https://learn.microsoft.com/en-us/entra/identity/multi-tenant-organizations/cross-tenant-synchronization-overview)

</details>

### Question 4

*Domain: Implement and manage user identities*

Your organization uses pass-through authentication. One Authentication Agent runs on the Microsoft Entra Connect server. Last night the server rebooted for patches, and nobody could sign in to Microsoft 365 for 20 minutes. What should you do to prevent this?

- A. Open inbound TCP port 443 from the internet to the Entra Connect server.
- B. Enable seamless single sign-on.
- C. Install the Authentication Agent on two more servers so that at least three agents run.
- D. Ask Microsoft to raise the tenant's agent limit to 100.

<details><summary>Show answer</summary>

**C.** With pass-through authentication, passwords are validated on premises by the Authentication Agents. Microsoft recommends at least three agents in production so that sign-ins continue when one server is down.

- A is wrong because the agents make outbound connections only. Opening inbound ports adds exposure and does nothing for availability.
- B is wrong because seamless SSO adds Kerberos sign-in on domain joined devices. It does not validate passwords, so it cannot cover for a missing agent.
- D is wrong because the limit is 40 agents per tenant and the problem is having only one agent, not reaching a limit.

Docs: [Pass-through authentication quickstart](https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/how-to-connect-pta-quick-start), [seamless SSO](https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/how-to-connect-sso)

</details>

### Question 5

*Domain: Implement authentication and access management*

A new employee who works remotely starts on Monday. Company policy says new staff must register a passkey (FIDO2) on their first sign-in and must never be given a password. What should you give the employee?

- A. A Temporary Access Pass with a lifetime that covers the first sign-in.
- B. A temporary password that must be changed at the next sign-in.
- C. A link to the self-service password reset registration page.
- D. An exclusion from MFA registration until the passkey is registered.

<details><summary>Show answer</summary>

**A.** A Temporary Access Pass is a passcode with a time limit, issued by an admin, that lets a user sign in and register passwordless methods such as a passkey. You can make it single use and set its lifetime between 10 minutes and 30 days.

- B is wrong because a temporary password is still a password, which the policy forbids.
- C is wrong because SSPR resets a password for a user who can already prove their identity. The new employee has no methods registered yet.
- D is wrong because an exclusion removes a requirement but gives the user no credential to sign in with.

Docs: [Temporary Access Pass](https://learn.microsoft.com/en-us/entra/identity/authentication/howto-authentication-temporary-access-pass), [passkeys (FIDO2)](https://learn.microsoft.com/en-us/entra/identity/authentication/how-to-authentication-passkeys-fido2)

</details>

### Question 6

*Domain: Implement authentication and access management*

You wrote a Conditional Access policy that requires a compliant device for all resources. Before you enforce it, you want a week of data that shows which of your users' actual sign-ins would fail, without blocking anyone. What should you do?

- A. Run the What If tool for each user every day.
- B. Set the policy to Off and review the Conditional Access insights workbook.
- C. Set the policy to Report-only and review the results in the sign-in logs.
- D. Turn the policy on and exclude all users.

<details><summary>Show answer</summary>

**C.** Report-only mode evaluates the policy during each sign-in without enforcing it and records the result, such as success, failure, or user action required, in the sign-in log details. Note that a report-only policy that requires a compliant device can still prompt users on macOS, iOS, and Android to pick a device certificate.

- A is wrong because What If simulates one scenario you describe. It does not evaluate the sign-ins your users actually make.
- B is wrong because a policy that is off is not evaluated, so there is nothing to report.
- D is wrong because a policy that excludes everyone applies to no sign-in.

Docs: [Report-only mode](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-conditional-access-report-only), [What If tool](https://learn.microsoft.com/en-us/entra/identity/conditional-access/what-if-tool)

</details>

### Question 7

*Domain: Implement authentication and access management*

An employee is let go at 10:00. At 10:02 an admin disables the account. The employee still has Outlook open on a laptop, connected to Exchange Online with an access token issued at 09:45. The tenant has no Conditional Access policies. What happens?

- A. The employee keeps mail access until about 10:45, when the access token expires.
- B. The employee keeps mail access until an admin also revokes all refresh tokens.
- C. Nothing changes until you create a Conditional Access policy that turns on continuous access evaluation.
- D. Exchange Online stops accepting the session within minutes, because disabling an account is a critical event under continuous access evaluation.

<details><summary>Show answer</summary>

**D.** Services such as Exchange Online, SharePoint Online, and Teams subscribe to critical Microsoft Entra events, including an account being disabled or deleted, and enforce them in near real time. Critical event evaluation needs no Conditional Access policy, so every tenant gets it.

- A is wrong because a token lifetime of 1 hour is the behavior without continuous access evaluation. CAE exists to close that gap.
- B is wrong because revoking refresh tokens is one critical event, but disabling the account is another. Either one is enough.
- C is wrong because critical event evaluation needs no Conditional Access policy.

Docs: [Continuous access evaluation](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-continuous-access-evaluation)

</details>

### Question 8

*Domain: Implement authentication and access management*

You want users to complete MFA whenever Microsoft Entra ID Protection rates a sign-in as medium or high risk. All users have Microsoft Entra ID P1 licenses. What do you need?

- A. A Conditional Access policy with a sign-in risk condition. P1 licenses are enough.
- B. A Conditional Access policy with a sign-in risk condition, and Microsoft Entra ID P2 licenses for the users in scope.
- C. Security defaults.
- D. A named location that lists risky IP addresses.

<details><summary>Show answer</summary>

**B.** Risk-based Conditional Access, which uses user risk and sign-in risk as conditions, requires Microsoft Entra ID P2. Microsoft directs you to configure risk policies in Conditional Access; the docs say the legacy risk policies inside ID Protection retire on October 1, 2026.

- A is wrong because P1 includes Conditional Access but not risk-based conditions.
- C is wrong because security defaults are a fixed baseline that you cannot target at a risk level.
- D is wrong because a named location is a static list of IP ranges you maintain. It does not use ID Protection's risk scoring.

Docs: [Risk policies](https://learn.microsoft.com/en-us/entra/id-protection/concept-identity-protection-policies), [Microsoft Entra licensing](https://learn.microsoft.com/en-us/entra/fundamentals/licensing), [security defaults](https://learn.microsoft.com/en-us/entra/fundamentals/security-defaults)

</details>

### Question 9

*Domain: Plan and implement workload identities*

Twelve Azure Functions apps must read secrets from the same key vault. The security team wants to grant access once, to a single identity, and the identity must keep working when the apps are deleted and recreated during deployments. What should you use?

- A. A system-assigned managed identity on each app.
- B. An app registration with a client secret stored in each app's settings.
- C. One user-assigned managed identity, assigned to all twelve apps.
- D. A user account with a password that never expires.

<details><summary>Show answer</summary>

**C.** A user-assigned managed identity is a standalone Azure resource. You can assign it to many resources, and it survives when they are deleted, so the key vault access is granted once and stays in place.

- A is wrong because each system-assigned identity is tied to one resource and is deleted with it, so you would grant access twelve times and again after every rebuild.
- B is wrong because a client secret is a credential you must store, protect, and rotate. Managed identities remove that work.
- D is wrong because a user account is the wrong identity type for a workload, and a password that never expires is a standing risk.

Docs: [Managed identities for Azure resources](https://learn.microsoft.com/en-us/entra/identity/managed-identities-azure-resources/overview)

</details>

### Question 10

*Domain: Plan and implement workload identities*

Two weeks ago you turned on the admin consent workflow and made Ana, a Cloud Application Administrator, a reviewer. Today a user requests consent for an app that asks for the Microsoft Graph application permission User.Read.All. Ana can see the request but cannot approve it. Why?

- A. Only a Global Administrator can approve requests for Microsoft Graph application permissions.
- B. Reviewers can deny or block requests but can never approve them.
- C. Requests expire after 24 hours, and this one has already expired.
- D. Ana must also be listed as an owner of the app.

<details><summary>Show answer</summary>

**A.** A reviewer can see, block, or deny any request, and can approve one when they hold the permissions to grant that consent. Requests for Microsoft Graph app roles, which are application permissions, are the exception: only a Global Administrator can approve them.

- B is wrong because reviewers with the right permissions can approve other requests.
- C is wrong because you choose how many days requests stay valid when you configure the workflow.
- D is wrong because app ownership is not a requirement for reviewing consent requests.

Docs: [Configure the admin consent workflow](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/configure-admin-consent-workflow), [permissions and consent](https://learn.microsoft.com/en-us/entra/identity-platform/permissions-consent-overview)

</details>

### Question 11

*Domain: Plan and implement workload identities*

Users sign in to a SaaS app through Microsoft Entra ID. They may open the app from personal devices, but they must not download files on those devices. Managed devices have no limits. What should you configure?

- A. A Conditional Access policy that blocks access to the app from unmanaged devices.
- B. A Defender for Cloud Apps API connector for the app and a file policy.
- C. Microsoft Entra application proxy in front of the app.
- D. A Conditional Access policy for the app that targets unmanaged devices and uses the session control "Use Conditional Access App Control", plus a session policy in Microsoft Defender for Cloud Apps that blocks downloads.

<details><summary>Show answer</summary>

**D.** Conditional Access app control routes the session through Defender for Cloud Apps, where a session policy can allow access while blocking downloads. The session policy only works when a Conditional Access policy sends the traffic there. Apps that use Microsoft Entra ID are onboarded to app control automatically.

- A is wrong because blocking access entirely breaks the requirement that personal devices may open the app.
- B is wrong because API connectors give visibility and governance through the app's own APIs. Stopping a download inside a live session needs Conditional Access app control.
- C is wrong because application proxy publishes on-premises web apps. It does not apply session controls to a SaaS app.

Docs: [Conditional Access app control](https://learn.microsoft.com/en-us/defender-cloud-apps/proxy-intro-aad), [session policies](https://learn.microsoft.com/en-us/defender-cloud-apps/session-policy-aad)

</details>

### Question 12

*Domain: Plan and automate identity governance*

Your admins should hold Global Administrator only when they need it, for at most 2 hours at a time, after approval by one of two security leads, and with a reason recorded for each use. What should you do?

- A. Give the admins permanent active assignments and add a Conditional Access policy with a sign-in frequency of 2 hours.
- B. Make the admins eligible for Global Administrator in Privileged Identity Management, and set the role to an activation maximum of 2 hours, require justification, and require approval with the two leads as approvers.
- C. Create an access review of Global Administrator that runs every 2 hours.
- D. Assign the role permanently and remove it by hand after each task.

<details><summary>Show answer</summary>

**B.** PIM role settings control activation: the maximum duration can be 1–24 hours, and you can require a justification and approval. Microsoft recommends at least two approvers, and approvers do not need an admin role themselves.

- A is wrong because sign-in frequency forces users to sign in again but leaves the role active all the time, with no approval.
- C is wrong because access reviews recertify access on a schedule. They do not grant elevation for a limited time.
- D is wrong because removing access by hand has no approval step, no enforced time limit, and depends on someone remembering.

Docs: [PIM role settings](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-how-to-change-default-settings)

</details>

### Question 13

*Domain: Plan and automate identity governance*

You are about to turn on a Conditional Access policy that requires a compliant device for all users and all resources. Your two emergency access accounts are cloud only Global Administrators. Which two actions follow Microsoft's guidance? Choose two.

- A. Exclude the group that holds the emergency access accounts from the new policy.
- B. Synchronize the emergency access accounts from on-premises AD DS so that they survive a cloud outage.
- C. Register a passkey (FIDO2) for each emergency access account.
- D. Change the accounts' role to Security Reader to lower the risk.

<details><summary>Show answer</summary>

**A and C.** Microsoft recommends excluding emergency access accounts from Conditional Access policies that block or restrict sign-in, usually through a dedicated group, and protecting them with a sign-in method that resists phishing. A passkey (FIDO2) is the recommended method, and it also satisfies mandatory MFA for Azure.

- B is wrong because emergency access accounts should be cloud only on the `*.onmicrosoft.com` domain, not federated or synchronized, so that an on-premises failure cannot lock them out.
- D is wrong because emergency access accounts exist to recover the tenant, which needs the Global Administrator role.

Docs: [Emergency access accounts](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/security-emergency-access)

</details>

### Question 14

*Domain: Plan and automate identity governance*

You want every guest in all Microsoft 365 groups and Teams reviewed each quarter by the group owners, and guests who are denied should lose access automatically when each review ends. What should you configure?

- A. An access review of one group, with self-review and a monthly recurrence.
- B. An access package for each group with an assignment expiration of 90 days.
- C. A Conditional Access policy that blocks guest sign-ins every 90 days.
- D. An access review that targets all Microsoft 365 groups with guest users, with group owners as reviewers, a quarterly recurrence, and "Auto apply results to resource" turned on.

<details><summary>Show answer</summary>

**D.** The scope "All Microsoft 365 groups with guest users" creates recurring reviews across your groups and Teams, and reviews only guests. Group owners can be the reviewers, with a fallback reviewer for groups that have no owner. "Auto apply results to resource" removes denied users when the review ends.

- A is wrong because it covers one group, lets guests approve themselves, and runs on the wrong schedule.
- B is wrong because an access package expiration applies only to access granted through that package, not to guests already added to groups.
- C is wrong because Conditional Access has no control that reviews or removes guests on a schedule.

Docs: [Create an access review](https://learn.microsoft.com/en-us/entra/id-governance/create-access-review), [access reviews overview](https://learn.microsoft.com/en-us/entra/id-governance/access-reviews-overview)

</details>

### Question 15

*Domain: Plan and automate identity governance*

Your security team must run KQL queries over 12 months of Microsoft Entra sign-in logs and correlate them with other Azure data. The tenant has Microsoft Entra ID P2. What should you do?

- A. Download the sign-in log as a CSV file from the admin center each month.
- B. Nothing, because Microsoft Entra ID P2 keeps sign-in logs for 12 months.
- C. Create a diagnostic setting that sends sign-in logs to a Log Analytics workspace, and set the workspace retention to cover 12 months.
- D. Create a diagnostic setting that streams sign-in logs to an event hub, and nothing else.

<details><summary>Show answer</summary>

**C.** Diagnostic settings can send sign-in and audit logs to a Log Analytics workspace, where you query them with KQL in tables such as `SigninLogs` and correlate them with other Azure Monitor data. The workspace's own retention setting controls how long the data stays.

- A is wrong because CSV exports give you no KQL and depend on someone exporting every month.
- B is wrong because Microsoft Entra ID P1 and P2 keep sign-in logs for 30 days.
- D is wrong because an event hub streams logs to another system such as a SIEM. It is not a place to store and query them with KQL.

Docs: [Diagnostic settings](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/howto-configure-diagnostic-settings), [analyze logs with KQL](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/howto-analyze-activity-logs-log-analytics), [data retention](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/reference-reports-data-retention), [Log Analytics retention](https://learn.microsoft.com/en-us/azure/azure-monitor/logs/data-retention-configure)

</details>

## More practice

The [Examice SC-300 practice bank](https://examice.com/exams/microsoft/sc-300?utm_source=github&utm_medium=social&utm_campaign=sc-300-study-guide-and-practice-questions&utm_content=link_3) has 460+ questions, each with a written explanation and a discussion. The first 5 are free.
