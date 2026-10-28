# SC-300 study guide and practice questions

SC-300 is the exam for the Microsoft Certified: Identity and Access Administrator Associate certification. It is aimed at administrators who run identity and access in Microsoft Entra: users and groups, hybrid sync, authentication, Conditional Access, application access, and identity governance. This repository holds a study guide mapped to the current skills outline, a study plan for six weeks, a cheat sheet of limits and license rules, and 15 original practice questions with explanations.

> Unofficial study notes by [Examice](https://examice.com/exams/microsoft/sc-300?utm_source=github&utm_medium=social&utm_campaign=sc-300-study-guide-and-practice-questions&utm_content=link_1). Not affiliated with or endorsed by Microsoft. The practice questions are original and are not taken from the exam.

## Contents

- [Exam at a glance](#exam-at-a-glance)
- [What the exam covers](#what-the-exam-covers)
- [Study plan](#study-plan)
- [Cheat sheet](#cheat-sheet)
- [Free official resources](#free-official-resources)
- [Practice questions](#practice-questions)
- [Exam day tips](#exam-day-tips)
- [FAQ](#faq)
- [Contributing](#contributing)
- [License](#license)

## Exam at a glance

| Item | Official detail |
| --- | --- |
| Certification | Microsoft Certified: Identity and Access Administrator Associate |
| Exam | SC-300: Microsoft Identity and Access Administrator |
| Level | Intermediate |
| Exam time | 100 minutes |
| Passing score | 700 on a scaled range of 1–1,000 (a scaled score, not 70% of the questions) |
| Price | $165 USD in the United States; the price depends on the country or region where the exam is proctored |
| Delivery | Proctored, scheduled through Pearson VUE |
| Languages | English, German, Spanish, French, Italian, Japanese, Korean, Portuguese (Brazil), Chinese (Simplified), and Chinese (Traditional) |
| Skills outline | Current as of October 28, 2026 for the English exam; translated versions are updated about eight weeks later |
| Validity | 12 months, renewed for free by passing an online assessment on Microsoft Learn |
| Retakes | 24 hours after a first failed attempt, then 14 days between later attempts, with at most 5 attempts in 12 months |

Source: [certification page](https://learn.microsoft.com/en-us/credentials/certifications/identity-and-access-administrator/), [SC-300 study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/sc-300), [exam scoring](https://learn.microsoft.com/en-us/credentials/certifications/exam-scoring-reports), [retake policy](https://learn.microsoft.com/en-us/credentials/support/retake-policy), and [renewal](https://learn.microsoft.com/en-us/credentials/certifications/renew-your-microsoft-certification), checked October 28, 2026.

## What the exam covers

| Domain | Weight |
| --- | --- |
| Implement and manage user identities | 20–25% |
| Implement authentication and access management | 25–30% |
| Plan and implement workload identities | 20–25% |
| Plan and automate identity governance | 20–25% |

Source: [SC-300 study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/sc-300), skills measured as of October 28, 2026, checked October 28, 2026. The study guide's summary list gives authentication and access management 25–30%, while the heading above that section's skill list shows 20–25%. This table follows the summary list. The guide also notes that most questions cover generally available features, with commonly used preview features possible.

The skills below are a summary in our own words. Read the official study guide for the full list.

### Implement and manage user identities

- **Tenant configuration.** Assign built-in roles, build custom roles, and work out a user's effective permissions when several roles apply. Decide when an administrative unit is the right way to scope an admin role, then create one. Add and verify custom domains, set company branding, and adjust tenant, user, group, and device settings. Docs: [Roles](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/concept-understand-roles), [custom roles](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/custom-create), [administrative units](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/administrative-units), [custom domains](https://learn.microsoft.com/en-us/entra/fundamentals/add-custom-domain), [company branding](https://learn.microsoft.com/en-us/entra/fundamentals/how-to-customize-branding).
- **Users, groups, and devices.** Create and manage users and groups, including dynamic membership. Define and assign custom security attributes. Run bulk changes from the admin center or with Microsoft Graph PowerShell. Know the difference between joining and registering a device. Assign licenses directly and through groups, and report on them. Docs: [dynamic groups](https://learn.microsoft.com/en-us/entra/identity/users/groups-dynamic-membership), [custom security attributes](https://learn.microsoft.com/en-us/entra/fundamentals/custom-security-attributes-overview), [bulk create users](https://learn.microsoft.com/en-us/entra/identity/users/users-bulk-add), [Microsoft Graph PowerShell](https://learn.microsoft.com/en-us/powershell/microsoftgraph/overview), [device identities](https://learn.microsoft.com/en-us/entra/identity/devices/overview), [group-based licensing](https://learn.microsoft.com/en-us/entra/identity/users/licensing-groups-assign).
- **External users and tenants.** Control who can invite guests and from which domains. Invite one guest or many, and manage guest accounts afterward. Configure inbound, outbound, and trust settings for other Entra tenants, and set up cross-tenant synchronization. Federate with outside identity providers over SAML or WS-Fed. Docs: [B2B collaboration](https://learn.microsoft.com/en-us/entra/external-id/what-is-b2b), [external collaboration settings](https://learn.microsoft.com/en-us/entra/external-id/external-collaboration-settings-configure), [cross-tenant access](https://learn.microsoft.com/en-us/entra/external-id/cross-tenant-access-overview), [cross-tenant synchronization](https://learn.microsoft.com/en-us/entra/identity/multi-tenant-organizations/cross-tenant-synchronization-overview), [SAML and WS-Fed federation](https://learn.microsoft.com/en-us/entra/external-id/direct-federation).
- **Hybrid identity.** Run Entra Connect Sync or Entra Cloud Sync, choose between password hash synchronization and pass-through authentication, add seamless single sign-on, plan a move off AD FS, and monitor sync with Connect Health. Docs: [Connect Sync and Connect Health](https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/whatis-azure-ad-connect), [Cloud Sync](https://learn.microsoft.com/en-us/entra/identity/hybrid/cloud-sync/what-is-cloud-sync), [password hash sync](https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/how-to-connect-password-hash-synchronization), [pass-through authentication](https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/how-to-connect-pta-quick-start), [seamless SSO](https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/how-to-connect-sso), [migrate from federation](https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/migrate-from-federation-to-cloud-authentication).

### Implement authentication and access management

- **User authentication.** Plan authentication for the tenant, then enable and manage methods in the Authentication methods policy: certificates, Temporary Access Pass, Microsoft Authenticator, and passkeys (FIDO2). Set tenant MFA settings, deploy self-service password reset, roll out Windows Hello for Business, block weak passwords with password protection, and enable Entra Kerberos for hybrid users. Know how to disable an account and revoke its sessions. Docs: [authentication methods](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-authentication-methods), [certificate-based authentication](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-certificate-based-authentication), [Temporary Access Pass](https://learn.microsoft.com/en-us/entra/identity/authentication/howto-authentication-temporary-access-pass), [passkeys](https://learn.microsoft.com/en-us/entra/identity/authentication/how-to-authentication-passkeys-fido2), [SSPR](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-sspr-howitworks), [password protection](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-password-ban-bad), [Windows Hello for Business](https://learn.microsoft.com/en-us/windows/security/identity-protection/hello-for-business/), [Entra Kerberos](https://learn.microsoft.com/en-us/entra/identity/authentication/kerberos), [revoke access](https://learn.microsoft.com/en-us/entra/identity/users/users-revoke-access).
- **Conditional Access.** Plan policies, set assignments and controls, and test before you enforce. Manage sessions, restrict by device, and understand continuous access evaluation. Use authentication context and protected actions for step up on sensitive data and admin actions. Start policies from templates. Docs: [Conditional Access overview](https://learn.microsoft.com/en-us/entra/identity/conditional-access/overview), [report-only mode](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-conditional-access-report-only), [What If tool](https://learn.microsoft.com/en-us/entra/identity/conditional-access/what-if-tool), [session lifetime](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-session-lifetime), [continuous access evaluation](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-continuous-access-evaluation), [authentication context](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-conditional-access-cloud-apps), [protected actions](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/protected-actions-overview), [templates](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-conditional-access-policy-common).
- **ID Protection.** Respond to user risk and sign-in risk with Conditional Access, drive MFA registration with registration campaigns, and investigate and remediate risky users, risky sign-ins, and risky workload identities. Docs: [ID Protection](https://learn.microsoft.com/en-us/entra/id-protection/overview-identity-protection), [risk policies](https://learn.microsoft.com/en-us/entra/id-protection/concept-identity-protection-policies), [registration campaign](https://learn.microsoft.com/en-us/entra/identity/authentication/how-to-mfa-registration-campaign), [workload identity risk](https://learn.microsoft.com/en-us/entra/id-protection/concept-workload-identity-risk).
- **Global Secure Access.** Deploy the client, then publish private apps with Entra Private Access, filter internet traffic with Entra Internet Access, and route Microsoft 365 traffic through the Microsoft traffic profile. Docs: [Global Secure Access](https://learn.microsoft.com/en-us/entra/global-secure-access/overview-what-is-global-secure-access), [traffic forwarding profiles](https://learn.microsoft.com/en-us/entra/global-secure-access/concept-traffic-forwarding), [Windows client](https://learn.microsoft.com/en-us/entra/global-secure-access/how-to-install-windows-client).

### Plan and implement workload identities

- **Identities for apps and Azure workloads.** Pick between a managed identity, a service principal, a user account, and a managed service account. Create managed identities, attach them to Azure resources, and use them to reach other resources. Docs: [managed identities](https://learn.microsoft.com/en-us/entra/identity/managed-identities-azure-resources/overview).
- **Enterprise applications.** Configure app and tenant settings, give the right admins the right app roles, publish on-premises web apps through application proxy, integrate SaaS apps, assign users and groups, control user and admin consent, and group apps into collections for My Apps. Docs: [application management](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/what-is-application-management), [application proxy](https://learn.microsoft.com/en-us/entra/identity/app-proxy/overview-what-is-app-proxy), [SaaS app tutorials](https://learn.microsoft.com/en-us/entra/identity/saas-apps/tutorial-list), [user consent](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/configure-user-consent), [admin consent workflow](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/configure-admin-consent-workflow), [collections](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/access-panel-collections).
- **App registrations.** Plan and create registrations, configure authentication, add API permissions, and define app roles. Docs: [register an app](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app), [application and service principal objects](https://learn.microsoft.com/en-us/entra/identity-platform/app-objects-and-service-principals), [permissions and consent](https://learn.microsoft.com/en-us/entra/identity-platform/permissions-consent-overview), [app roles](https://learn.microsoft.com/en-us/entra/identity-platform/howto-add-app-roles-in-apps).
- **Defender for Cloud Apps.** Find shadow IT with cloud discovery, connect apps through APIs, apply restrictions the app enforces itself, route sessions through Conditional Access app control, write access and session policies, govern OAuth apps, and use the cloud app catalog. Docs: [Defender for Cloud Apps](https://learn.microsoft.com/en-us/defender-cloud-apps/what-is-defender-for-cloud-apps), [cloud discovery](https://learn.microsoft.com/en-us/defender-cloud-apps/set-up-cloud-discovery), [app connectors](https://learn.microsoft.com/en-us/defender-cloud-apps/enable-instant-visibility-protection-and-governance-actions-for-your-apps), [Conditional Access app control](https://learn.microsoft.com/en-us/defender-cloud-apps/proxy-intro-aad), [session policies](https://learn.microsoft.com/en-us/defender-cloud-apps/session-policy-aad), [OAuth app policies](https://learn.microsoft.com/en-us/defender-cloud-apps/app-permission-policy).

### Plan and automate identity governance

- **Entitlement management.** Plan entitlements, build catalogs and access packages, handle requests, attach terms of use, decide what happens to external users when their access ends, and manage connected organizations. Docs: [entitlement management](https://learn.microsoft.com/en-us/entra/id-governance/entitlement-management-overview), [create an access package](https://learn.microsoft.com/en-us/entra/id-governance/entitlement-management-access-package-create), [external users](https://learn.microsoft.com/en-us/entra/id-governance/entitlement-management-external-users), [connected organizations](https://learn.microsoft.com/en-us/entra/id-governance/entitlement-management-organization), [terms of use](https://learn.microsoft.com/en-us/entra/identity/conditional-access/terms-of-use).
- **Access reviews.** Plan and create reviews, track progress, and act on results by hand when needed. Docs: [access reviews](https://learn.microsoft.com/en-us/entra/id-governance/access-reviews-overview), [create a review](https://learn.microsoft.com/en-us/entra/id-governance/create-access-review).
- **Privileged access.** Configure Privileged Identity Management for Entra roles, Azure resource roles, and groups, run the request and approval flow, read PIM audit history, and create emergency access accounts. Docs: [PIM](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-configure), [role settings](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-how-to-change-default-settings), [PIM for Groups](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/concept-pim-for-groups), [Azure resources in PIM](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-resource-roles-discover-resources), [approvals](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-approval-workflow), [PIM audit log](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-how-to-use-audit-log), [emergency access accounts](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/security-emergency-access).
- **Monitoring.** Read sign-in, audit, and provisioning logs, send them to Log Analytics, storage, or Event Hubs with diagnostic settings, query them with KQL, analyze them with workbooks, and raise Identity Secure Score. Docs: [monitoring and health](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/overview-monitoring-health), [diagnostic settings](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/howto-configure-diagnostic-settings), [analyze logs with KQL](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/howto-analyze-activity-logs-log-analytics), [workbooks](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/overview-workbooks), [Identity Secure Score](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/concept-identity-secure-score).

## Study plan

About 50 hours over six weeks. Build a lab first: an Azure free account gives you an Entra tenant, and the [premium editions page](https://learn.microsoft.com/en-us/entra/fundamentals/get-started-premium) links to an Entra ID P2 trial, which you need for PIM, ID Protection, access reviews, and entitlement management. Do every task below in that tenant, not only on paper.

| Week | Focus | Tasks | Hours |
| --- | --- | --- | --- |
| 1 | Tenant and identities | Read the study guide once. Create 20 test users from a CSV, two dynamic groups, and a custom domain. Set company branding. Create an administrative unit, scope a Helpdesk Administrator to it, and test what that admin can and cannot reset. Define one custom security attribute set. | 8 |
| 2 | External and hybrid identity | Restrict guest invitations to an allow list of domains, then invite a guest. Read the inbound, outbound, and trust settings in cross-tenant access. Draw the sign-in flow for password hash sync, pass-through authentication, and seamless SSO. If you can run a Windows Server VM with AD DS, install the Cloud Sync agent and sync a test OU. | 8 |
| 3 | Authentication and Conditional Access | Enable Temporary Access Pass and passkeys in the Authentication methods policy and register a passkey with a TAP. Turn on SSPR for a pilot group. Add 10 terms to the custom banned password list. Build three Conditional Access policies in report-only mode and check the results in the sign-in log. Run the What If tool against each. | 9 |
| 4 | ID Protection, Global Secure Access, and workload identities | Write user risk and sign-in risk policies in Conditional Access. Start an MFA registration campaign. Read the three traffic forwarding profiles. Give an Azure VM a managed identity and use it to read a storage account. Register an app with one delegated and one application permission and two app roles. | 8 |
| 5 | Enterprise apps and governance | Add a gallery SaaS app with SAML SSO. Set user consent to verified publishers and turn on the admin consent workflow. In Defender for Cloud Apps, create a session policy that blocks downloads from unmanaged devices. Create a catalog, an access package with an approval policy, and a connected organization. Create a quarterly access review of guests. | 9 |
| 6 | Privileged access, monitoring, and review | Make a user eligible for a role in PIM, require approval, and activate it. Create two emergency access accounts with passkeys. Send sign-in and audit logs to a Log Analytics workspace and run five KQL queries. Take the free practice assessment, then reread the cheat sheet for every domain where you scored low. | 8 |

## Cheat sheet

### Licenses

| Feature | License that includes it |
| --- | --- |
| Conditional Access | Entra ID P1 |
| Risk-based Conditional Access (user and sign-in risk) | Entra ID P2 |
| SSPR with writeback to on-premises AD | Entra ID P1 |
| Administrative units | Entra ID P1 for each admin scoped to the unit; members need only Free |
| Custom banned password list | Entra ID P1 |
| Password protection for users synced from AD DS | Entra ID P1, even with only the global list |
| Custom security attributes | All editions |
| Application proxy | Entra ID P1 or P2 |
| PIM for Entra roles, Azure resources, and groups | Entra ID P2, Entra ID Governance, or Entra Suite |
| Core access reviews and entitlement management | Entra ID P2; some features need Entra ID Governance |
| Cross-tenant synchronization of users | Entra ID P1 for each synced user, in the source tenant |
| Cross-tenant synchronization of groups | Entra ID Governance or Entra Suite |
| Internet Access for Microsoft services | Entra ID P1 or P2 |
| Entra Internet Access and Entra Private Access | Entra Suite, or each standalone |
| Sending logs to Log Analytics for KQL | Entra ID P1 or P2 |

Docs: [Entra licensing](https://learn.microsoft.com/en-us/entra/fundamentals/licensing), [ID Governance licensing](https://learn.microsoft.com/en-us/entra/id-governance/licensing-fundamentals), [administrative units](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/administrative-units), [password protection](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-password-ban-bad), [cross-tenant synchronization](https://learn.microsoft.com/en-us/entra/identity/multi-tenant-organizations/cross-tenant-synchronization-overview), [Global Secure Access](https://learn.microsoft.com/en-us/entra/global-secure-access/overview-what-is-global-secure-access).

### User identities

- An administrative unit holds only users, groups, and devices, and units cannot be nested. Adding a group puts the group object in scope, not its members. ([Docs](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/administrative-units))
- Global Administrator has no access to custom security attributes by default. Attribute Definition Administrator defines them and Attribute Assignment Administrator assigns them. They apply to users and service principals. ([Docs](https://learn.microsoft.com/en-us/entra/fundamentals/custom-security-attributes-overview))
- Cross-tenant access: B2B collaboration is on by default and B2B direct connect is blocked by default. Inbound trust settings decide whether you accept another tenant's MFA, compliant device, and hybrid joined device claims. ([Docs](https://learn.microsoft.com/en-us/entra/external-id/cross-tenant-access-overview))
- Cross-tenant synchronization is a push from the source tenant. Scope and attribute mapping live in the source tenant. The target tenant must allow user sync in its inbound settings and can stop sync at any time. Only internal members sync, not the source tenant's own guests. ([Docs](https://learn.microsoft.com/en-us/entra/identity/multi-tenant-organizations/cross-tenant-synchronization-overview))

| Hybrid option | Where the password is checked | Facts to remember |
| --- | --- | --- |
| Password hash synchronization | Microsoft Entra ID | The agent pulls hashes from a domain controller every 2 minutes. Only a salted SHA256 hash of the MD4 hash (1,000 PBKDF2 iterations) leaves your network. |
| Pass-through authentication | On-premises AD, through agents | Run at least 3 agents in production; the limit is 40 per tenant. Agents need only outbound connections on port 443. |
| Federation with AD FS | AD FS | Microsoft documents migration to password hash sync or pass-through authentication. |
| Seamless SSO | Not a sign-in method on its own | Adds Kerberos SSO on domain joined devices. Works with password hash sync or pass-through, not with AD FS. |

Docs: [password hash sync](https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/how-to-connect-password-hash-synchronization), [pass-through authentication](https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/how-to-connect-pta-quick-start), [seamless SSO](https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/how-to-connect-sso), [migrate from federation](https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/migrate-from-federation-to-cloud-authentication).

Cloud Sync uses a lightweight provisioning agent with its configuration stored in the cloud. Several agents can be active at once for failover, it handles disconnected AD forests, and it can now sync computer objects for hybrid join. ([Docs](https://learn.microsoft.com/en-us/entra/identity/hybrid/cloud-sync/what-is-cloud-sync))

### Authentication and access management

| Temporary Access Pass setting | Default | Allowed values |
| --- | --- | --- |
| Minimum lifetime | 1 hour | 10–43,200 minutes (30 days) |
| Maximum lifetime | 8 hours | 10–43,200 minutes (30 days) |
| Default lifetime | 1 hour | Within the minimum and maximum |
| One-time use | Off | On or off |
| Length | 8 characters | 8–48 characters |

Docs: [Temporary Access Pass](https://learn.microsoft.com/en-us/entra/identity/authentication/howto-authentication-temporary-access-pass).

- SSPR for administrators always requires two methods and never allows security questions (Microsoft calls this the two-gate policy). You cannot change it. ([Docs](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-sspr-policy))
- The custom banned password list holds at most 1,000 terms and is combined with Microsoft's global list. On premises, only domain controllers running the DC agent enforce it. ([Docs](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-password-ban-bad), [on premises](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-password-ban-bad-on-premises))
- Access tokens last 1 hour by default, which is why revoking sessions alone can leave a gap that continuous access evaluation closes. ([Docs](https://learn.microsoft.com/en-us/entra/identity/users/users-revoke-access))

| Conditional Access tool | What it does |
| --- | --- |
| Report-only mode | Evaluates the policy on live sign-ins without enforcing it. Results appear in the sign-in log. Not available for the user actions scope. |
| What If tool | Simulates one sign-in for a user, agent identity, or single tenant service principal. Includes only enabled and report-only policies. |
| Continuous access evaluation | Services such as Exchange Online, SharePoint Online, and Teams act within minutes on critical events: account disabled or deleted, password changed or reset, MFA enabled for the user, refresh tokens revoked, or high user risk. Critical event evaluation needs no Conditional Access policy. |
| Authentication context | A label you attach to sensitive data or actions (SharePoint sites, Defender for Cloud Apps, custom apps) and target with a policy. |
| Protected actions | Admin permissions bound to an authentication context, such as managing Conditional Access, cross-tenant access settings, network locations, and hard deletes. |

Docs: [report-only](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-conditional-access-report-only), [What If](https://learn.microsoft.com/en-us/entra/identity/conditional-access/what-if-tool), [CAE](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-continuous-access-evaluation), [authentication context](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-conditional-access-cloud-apps), [protected actions](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/protected-actions-overview).

- Configure user risk and sign-in risk policies in Conditional Access. The docs say the legacy risk policies inside ID Protection retire on October 1, 2026. A secure password change remediates user risk; completing MFA remediates sign-in risk. ([Docs](https://learn.microsoft.com/en-us/entra/id-protection/concept-identity-protection-policies))
- Mandatory MFA for Azure: since October 2024 for the Azure portal, Entra admin center, and Intune admin center; from October 1, 2025 for create, update, and delete operations from Azure CLI, Azure PowerShell, the Azure mobile app, infrastructure as code tools, and REST APIs. ([Docs](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-mandatory-multifactor-authentication))

| Global Secure Access part | What it covers | License |
| --- | --- | --- |
| Entra Private Access | Zero Trust access to private corporate resources; builds on application proxy | Entra Suite or standalone |
| Entra Internet Access | Secure web gateway for internet and SaaS traffic | Entra Suite or standalone |
| Internet Access for Microsoft services | Direct path for Microsoft traffic through the Microsoft traffic profile | Entra ID P1 or P2 |

Docs: [Global Secure Access](https://learn.microsoft.com/en-us/entra/global-secure-access/overview-what-is-global-secure-access).

### Workload identities

| | System-assigned managed identity | User-assigned managed identity |
| --- | --- | --- |
| Created | By enabling it on the resource | As its own Azure resource |
| Lifecycle | Deleted with the resource | Independent of any resource |
| Sharing | One resource only | Can be assigned to many resources |

Docs: [managed identities](https://learn.microsoft.com/en-us/entra/identity/managed-identities-azure-resources/overview).

- An app has one application object, in its home tenant, and a service principal in every tenant that uses it. ([Docs](https://learn.microsoft.com/en-us/entra/identity-platform/app-objects-and-service-principals))
- Microsoft recommends allowing user consent only for apps from verified publishers. In the admin consent workflow, reviewers need the permissions to grant consent themselves, and only a Global Administrator can approve requests for Microsoft Graph application permissions. ([User consent](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/configure-user-consent), [admin consent workflow](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/configure-admin-consent-workflow))
- The application proxy private network connector needs no inbound firewall ports; it makes outbound connections only. ([Docs](https://learn.microsoft.com/en-us/entra/identity/app-proxy/overview-what-is-app-proxy))
- A Defender for Cloud Apps session policy needs a Conditional Access policy with the session control "Use Conditional Access App Control". Entra ID apps onboard automatically; apps on other identity providers need manual onboarding. ([Docs](https://learn.microsoft.com/en-us/defender-cloud-apps/session-policy-aad))

### Identity governance

| PIM role setting | What to remember |
| --- | --- |
| Activation maximum duration | 1–24 hours |
| On activation | Require MFA or a Conditional Access authentication context, a justification, a ticket number, or approval |
| Approvers | Pick at least one; Microsoft recommends two. Approvers need no admin role. |
| Assignment types | Eligible or active, each permanent or with an end date |
| Reauthentication | After one reauthentication, further activations within 10 minutes skip the prompt, across Entra roles, Azure roles, and PIM for Groups |

Docs: [PIM role settings](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-how-to-change-default-settings).

- Emergency access accounts: create two or more, cloud only, on the `*.onmicrosoft.com` domain, with Global Administrator. Use a passkey (FIDO2), with a method different from your other admins. Exclude them from Conditional Access policies that block or restrict sign-in, and test them regularly. ([Docs](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/security-emergency-access))
- Access reviews: "Auto apply results to resource" removes denied users when the review ends. In a group review with group owners as reviewers, only owners at the start of the review count. ([Docs](https://learn.microsoft.com/en-us/entra/id-governance/create-access-review))
- Entitlement management can block and then remove an external user who was invited through an access package once their last assignment ends. ([Docs](https://learn.microsoft.com/en-us/entra/id-governance/entitlement-management-external-users))

| Log | Entra ID Free | Entra ID P1 | Entra ID P2 |
| --- | --- | --- | --- |
| Audit logs | 7 days | 30 days | 30 days |
| Sign-in logs | 7 days | 30 days | 30 days |
| Risky sign-ins | 7 days | 30 days | 90 days |

Docs: [data retention](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/reference-reports-data-retention). To keep logs longer, use diagnostic settings: Log Analytics for KQL queries (tables such as `SigninLogs` and `AuditLogs`), a storage account to archive, or an event hub to stream to a SIEM. ([Diagnostic settings](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/howto-configure-diagnostic-settings), [KQL](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/howto-analyze-activity-logs-log-analytics)) Identity Secure Score is recalculated every 24 hours. ([Docs](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/concept-identity-secure-score))

## Free official resources

- [Certification page](https://learn.microsoft.com/en-us/credentials/certifications/identity-and-access-administrator/): exam details, scheduling, price for your country, and renewal.
- [SC-300 study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/sc-300): the full skills outline and change log.
- [Course SC-300T00](https://learn.microsoft.com/en-us/training/courses/sc-300t00): the instructor course, which runs 4 days. Its online learning paths are free:
  - [Implement an identity management solution using Microsoft Entra ID](https://learn.microsoft.com/en-us/training/paths/implement-identity-management-solution/)
  - [Implement an authentication and access management solution](https://learn.microsoft.com/en-us/training/paths/implement-authentication-access-management-solution/)
  - [Implement access management for apps](https://learn.microsoft.com/en-us/training/paths/implement-access-management-for-apps/)
  - [Plan and implement an identity governance strategy](https://learn.microsoft.com/en-us/training/paths/plan-implement-identity-governance-strategy/)
- [Free practice assessment](https://aiskillsnavigator.microsoft.com/credentials/cert-9170bd1835d0135db1ac9c66c30647089047f26f041be093e111963322607699): now on AI Skills Navigator; you need to sign in.
- [Exam sandbox](https://aka.ms/examdemo): try the question types and exam interface.
- [Exam Readiness Zone](https://learn.microsoft.com/en-us/shows/exam-readiness-zone/?terms=SC-300): SC-300 prep videos.
- [Microsoft Entra documentation](https://learn.microsoft.com/en-us/entra/).
- Lab: an [Azure free account](https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account) for a tenant, and the [premium editions page](https://learn.microsoft.com/en-us/entra/fundamentals/get-started-premium) for the Entra ID P2 trial link. The same page mentions the [Microsoft 365 Developer Program](https://developer.microsoft.com/en-us/microsoft-365/dev-program) sandbox for those who qualify.

## Practice questions

[practice-questions.md](practice-questions.md) has 15 original scenario questions across all four domains, each with the answer, why the other options are wrong, and a link to the docs. For more, the [Examice SC-300 practice bank](https://examice.com/exams/microsoft/sc-300?utm_source=github&utm_medium=social&utm_campaign=sc-300-study-guide-and-practice-questions&utm_content=link_2) has 460+ questions with a written explanation and a discussion under each, and the first 5 are free.

## Exam day tips

- You have 100 minutes. Microsoft does not publish a question count for SC-300; it says most of its exams have 40–60 questions. ([Exam duration](https://learn.microsoft.com/en-us/credentials/support/exam-duration-exam-experience))
- Microsoft Learn is available inside the exam for role exams like SC-300, but the clock keeps running. Use it to confirm one setting name or limit, not to research a topic.
- 5 minutes of break time are built in. After a break you cannot return to questions you have already seen, and you cannot take a break in the middle of a lab or a problem and solution set.
- Wrong answers cost nothing, and questions with several parts award a point for each correct part, so answer everything. Some questions are unscored and you will not know which. ([Scoring](https://learn.microsoft.com/en-us/credentials/certifications/exam-scoring-reports))
- Many SC-300 scenarios turn on two words: "least privileged" for roles and "minimum license" for features. Keep the license table above in your head.
- Register with a personal Microsoft account, not a work account, so your records stay with you if you change jobs.

## FAQ

**How hard is SC-300?**
Microsoft rates it Intermediate. The audience profile expects working knowledge of Azure, Microsoft 365, AD DS, PowerShell, and KQL. The pass mark is a scaled 700 out of 1,000, which is not the same as 70% correct. ([Study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/sc-300), [scoring](https://learn.microsoft.com/en-us/credentials/certifications/exam-scoring-reports))

**How long should I study for SC-300?**
Microsoft does not publish a study time. The instructor course SC-300T00 runs 4 days. The plan in this guide takes about 50 hours over six weeks with a lab tenant; add time if Entra is new to you. ([Course](https://learn.microsoft.com/en-us/training/courses/sc-300t00))

**Does the Identity and Access Administrator certification expire?**
Yes, after 12 months. Renewal is free: pass an unproctored assessment on Microsoft Learn, open book, during the six months before expiry, and the certification is extended one year from its expiration date. You can retake the renewal assessment as often as you need; after the second try, wait 24 hours between attempts. ([Renewal](https://learn.microsoft.com/en-us/credentials/certifications/renew-your-microsoft-certification), [retake policy](https://learn.microsoft.com/en-us/credentials/support/retake-policy))

**What is the SC-300 retake policy?**
Wait 24 hours after the first failed attempt and 14 days between each later attempt, with no more than 5 attempts in 12 months from the first. You cannot retake an exam you passed unless the certification has expired, and retakes are paid where a fee applies. ([Retake policy](https://learn.microsoft.com/en-us/credentials/support/retake-policy))

**What changed in the October 28, 2026 update?**
The change log marks minor changes to three sections: user authentication, Global Secure Access, and privileged access. The domain names stay the same. ([Study guide change log](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/sc-300))

**Can I use Microsoft Learn during SC-300?**
Yes. Associate and expert exams give access to learn.microsoft.com, except Q&A, practice assessments, and your profile. No extra time is added. ([Exam duration](https://learn.microsoft.com/en-us/credentials/support/exam-duration-exam-experience))

## Contributing

Found an outdated limit, a broken link, or a wrong answer? Open an issue or a pull request with a link to the Microsoft doc that shows the correct fact.

## License

Text and questions © Examice, licensed under CC BY 4.0. See [LICENSE](LICENSE).

Microsoft, Microsoft Entra, Azure, and Microsoft 365 are trademarks of the Microsoft group of companies. This repository is not affiliated with or endorsed by Microsoft.
