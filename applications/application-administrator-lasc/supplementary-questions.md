# Supplementary Questions: Superior Court of Los Angeles County, Application Administrator

Answers are written in first person and backed by `master/career_inventory.md`. Lines marked **[CONFIRM]** in the notes at the bottom are details I filled in around an inventory entry; check them before submitting.

---

## Q01: Instructions acknowledgment

Check the box.

---

## Q02: Education verification

Check the box. **Attach a legible copy of the Cal Poly Pomona diploma or unofficial transcript** to the application. This is required for Option III (BS + 1 year of applications administration) to count. Backup option: email it to mpenate@lacourt.ca.gov.

---

## Q03: Describe your experience supporting, configuring, or administering software applications. Include employers, specific applications, and your duties.

I've supported and administered business applications at four employers.

VCA Consultants, IT Technician II (May 2024 to present): I administer the applications for a 120-user engineering firm with offices in Los Angeles, Denver, and Orange. The biggest one is our Omnissa (formerly VMware) Horizon virtual desktop platform, which every employee works in. I build, patch, and test the gold images for seven department pools, and I use App Volumes to deliver department-specific software only to the people who need it: VSCode for the IT/Code pool, CBECC and other government energy compliance tools for the Green and Energy Modeler pools, and engineering applications for CAD and Structural. I manage user accounts in Active Directory and Entra ID, and I set up and maintain single sign-on, MFA, and Conditional Access for Ajera (our ERP), Zoom, Bluebeam, GitHub, GitLab, and Microsoft 365. Before the Ajera SSO rollout, I standardized account email addresses across AD, Entra ID, Autodesk, Bluebeam, Zoom, and Ajera so every login would match. I also run our self-hosted GitLab server (I upgraded it to version 19.0.1-ee so our internal tools could use its API), manage the Microsoft 365 license pool within a 20-seat cap, set up Zoom Booking Pages for staff, and wrote the Ajera Cloud login and usage guide that we publish to employees.

iKrusher, IT Systems Administrator (Feb 2024 to May 2024): I was the only IT person for 56 users. I administered the Microsoft 365 tenant (Exchange Online, SharePoint, Teams, and licensing), set up M365 policies, onboarded new users, and wrote onboarding runbooks that cut about 30 minutes off each new hire. I managed 50+ Windows and Mac computers in Intune and opened and tracked support cases with our vendors and ISP until they were resolved.

The Flex Company, IT & Operations Coordinator (Nov 2020 to Jul 2022): I managed accounts and access for about 30 users across Google Workspace, Slack, Asana, and other SaaS tools. I ran regular access reviews that cut stale accounts and unused channels by about 20%, moved 10,000+ files into Google Workspace Shared Drives with no data loss, and built the company knowledge base in Google Sites.

Five Acres, IT Technician and Data Architect (Jul 2017 to Jul 2019): As an IT Technician in a healthcare setting with strict compliance rules, I managed Active Directory accounts and processed application access requests through the IT service desk. After I was promoted to Data Architect, I trained staff on Welligent, the web-based records system the agency used, covering navigation, common problems, and how to avoid them. I also extended an internal web application that parsed and cleaned incident report data for the research team, and wrote its deployment and maintenance documentation.

---

## Q04: Describe a time when you helped resolve a technical problem for a user. How did you gather information, work through the problem, and decide when to escalate it?

A user at VCA told me the Scopebox Sync plug-in wasn't showing up in Revit 2025 on their virtual desktop. I started by getting the basics from them: which Revit version, whether the plug-in had ever worked for them, and whether it was missing every time they logged in. Then I checked our VM matrix, the document where we track what's installed in each gold image. It said Scopebox was supposed to be there, so this wasn't a missing install. Something was stopping Revit from loading it.

Revit only loads add-ins from one specific folder per version (%ProgramData%\Autodesk\Revit\Addins\[version]). When I looked in the image, the Scopebox bundle had been put somewhere else. I copied it into the correct folder for every Revit version we run, not just 2025, so the same problem wouldn't come back for someone on an older version. After I rebuilt the pool snapshot, I had the user log in again and confirmed the plug-in loaded.

I didn't escalate this one. Gold image maintenance is part of my job, I could see the cause, and the fix had a clear way back if it went wrong. I escalate when one of those things isn't true. If a fix needs access I don't have, if it would change something for everyone outside the work I normally own, or if I've worked on it for a while and still can't find the cause, I bring it to my IT Director with what I've already checked. If the problem is on the vendor's side, I open a case with the vendor and keep the user updated. A Bluebeam license that stopped applying after a Bluebeam service outage is a good example. Nothing on our end had changed, so I treated it as a vendor issue first. It turned out a fresh sign-in was all it needed.

---

## Q05: A business user asks for a change to how an application works. What steps would you take to understand the request, and how would you make sure the change does not cause problems for other users?

First I'd talk to the person and find out what problem they're trying to solve. The change people ask for isn't always the best fix, and sometimes a setting that already exists covers it. I'd also ask who else uses that part of the application, and if the change touches shared settings, I'd check with their supervisor or the application owner before going further.

Next I'd look at how far the change reaches. If it can be limited to the users who asked for it, that's usually the safer route. At VCA, when the Green and Energy Modeler teams needed CBECC and other energy compliance tools, the quick option was to install them in the main desktop image. That would have put software on every desktop in the company, most of it unused, and every update would have meant rebuilding all seven pools. I delivered the tools through App Volumes and assigned them only to those two pools, so nobody else's desktop changed.

Then I'd test before anything goes live. All of my desktop image changes go to a test pool first. I log in, open the applications that department relies on, and check that nothing else broke. I keep the previous snapshot so I can roll back quickly. I did the same when I reorganized our Group Policy: I tested each policy's scope before moving it, so settings only applied to the users and computers they were meant for.

Last, I'd tell affected users what's changing and when, schedule it for a time that doesn't interrupt their work, and update the documentation afterward. At the Court I'd expect a formal change approval process, and I'd follow it.

---

## Q06: Describe any experience you have testing software or following a test plan. How did you document results and report problems? If you do not have this experience, describe how you would approach testing a new software release.

I haven't worked from a formal test plan written by a QA team, but testing before release is a regular part of my job at VCA. Every change to our virtual desktop images (application patches, new software, Windows updates) goes to a test pool before it reaches users. I build the new snapshot in vCenter, log in to the test pool, open the main applications for that department, and check that add-ins load and user profiles carry over correctly. Only after that do I push it to production. I followed the same process when we moved all seven desktop pools from Windows 10 to Windows 11.

For documentation, I keep the VM matrix up to date so we know exactly what's installed in each image, and I maintain runbooks for image builds. I also put our Dynamic Environment Manager configuration under git version control, so every change has a record of what changed and when. If a test fails, I write down how to reproduce it, what I expected, and what actually happened. Then I either fix it before release or take it to my IT Director or the vendor.

For a new release at the Court, I'd start by reading the release notes to see what changed. I'd write test cases based on what each type of user actually does in the application, and I'd run them with test accounts set up for each role. I'd record a pass or fail for every case with enough detail that someone else could repeat it, report any defects with the steps to reproduce them, and retest once they're fixed. I'd also update the training aids and user guides for anything that changes for users.

---

## Q07: A user requests access to an application beyond what their role normally has. What steps would you take before granting the request, and why are those steps important?

I'd ask for the request in writing through a ticket, so there's a record from the start. Then I'd find out exactly what the user needs to do and why. Often the task can be done with a smaller permission than the one they asked for, or someone who already has the access can do it for them.

Next I'd get approval from the user's supervisor and from the owner of the application or data, following whatever procedure the Court has for elevated access. If the need is temporary, I'd set an end date and make sure the access actually gets removed. I'd grant only the narrowest permission that covers the task and document who approved it and why.

These steps matter because extra access is how data gets exposed. Sometimes it's a mistake, sometimes it's a compromised account, and sometimes it's misuse. Court data is sensitive, and the Court has to be able to show who could see what and who approved it. It protects the user, too, because if something goes wrong, the record shows the access was approved and limited.

I work this way now. At VCA I review AD and SaaS group memberships every quarter to remove access people no longer need. When an internal application needed to send email for a group of users, I limited its permission to that one group instead of granting access to every mailbox in the company. At Five Acres, in a healthcare setting, every application access request went through the service desk for the same reasons.

---

## Q08: Describe two examples where you collaborated with your team or vendor staff on a challenging configuration request from a customer. Explain your role as the team provided a feasible solution.

**Example 1: Email permissions for a custom application (VCA).** Our Data Scientist was building a Python application that needed to send email as users in one department. The fastest way to do that in Microsoft 365 is to give the application permission to send mail as anyone in the organization. That would have meant a bug or a leaked credential could send email from any account in the company, including leadership. I met with the Data Scientist to pin down exactly whose mailboxes the application needed. Then I set up role-based access control in Exchange Online with a management scope limited to that group, and granted the application's Microsoft Graph permission through that scope. My role was the administrator responsible for the security side: I explained the risk, proposed the scoped approach, and did the configuration. The application worked as planned, and it can't touch any mailbox outside that group.

**Example 2: Client share links after a SharePoint migration (VCA).** The Benchmarking team works with more than 700 building clients, and each one needed a link to only their own files. I migrated more than 200,000 building files to SharePoint using Microsoft's migration agent on a dedicated sync VM. Creating 700+ share links by hand would have taken days and invited mistakes, like sending a client the wrong building's files. I worked with the Benchmarking team to understand how their files were organized and how they planned to send the links. Then I wrote a Python script using the Microsoft Graph API that generated a share link for each building and matched it to the right client. My role was to run the migration, build and test the script, and hand the team a list they could send out directly.

---

## Notes before submitting

- **[CONFIRM] Q04 gathering steps:** The inventory records the Scopebox ticket's cause and fix, but not the questions you asked the user. Adjust the first paragraph to match what you actually asked.
- **[CONFIRM] Q04 escalation:** The escalation criteria (IT Director, vendor cases) are written as your general practice. Make sure they match how escalation works at VCA.
- **[CONFIRM] Q05/Q06 "keep the previous snapshot to roll back":** This follows from the test-pool workflow but isn't stated in the inventory. Keep it only if that's what you do.
- **[CONFIRM] Q06 "if a test fails, I write down...":** This is a general description of how you report problems. Tone it down if it sounds more formal than what you actually do.
- **[CONFIRM] Q08 Example 1:** "Met with the Data Scientist" and "leadership" are framing details. The core facts (RBAC, management scope, Graph API, least privilege instead of tenant-wide) come from the inventory.
- **[CONFIRM] Q08 Example 2:** The inventory says you migrated the files yourself and wrote the script so the Benchmarking team could send each client the right link. "Worked with the team to understand how their files were organized" is framing.
- **Character limits:** Q08 (about 3,000 characters) and Q03 (about 2,800) are the longest; the others run 1,400 to 1,700. If the portal cuts one off, shorten Q03's Flex Company paragraph or the middle of each Q08 example first. Drop the bold example labels in Q08 if the field is plain text.
