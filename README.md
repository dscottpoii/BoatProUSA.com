# BoatProUSA.com
Boat Pro USA

Boat Pro USA Complete Deployment Guide
Boat Pro USA — Complete Step-by-Step Deployment Guide

Audience: A first-time website publisher. Every important step is written out.
What this kit does

This kit gives you:

    A clean Google Apps Script with the duplicate declaration removed.
    A Google Sheets CRM connection.
    A public Boat Pro USA website ready for GitHub Pages.
    A working free-guide signup flow after the Apps Script is redeployed.
    Legal pages, SEO files, a thank-you page, and mobile-friendly website files.
    Paid membership buttons that remain safely disabled until Stripe and secure login are finished.

Important status before you begin

The website files are configured to use this Google Apps Script address:

https://script.google.com/macros/s/AKfycbwSLD7gmeiUItt2wJVozJU1AX_2NzJwrnynRCxEvA_LhcRYIxhAtXXd1Oi2tzUImpYV8A/exec

The code inside this kit is clean. However, the live address still showed the old error on July 24, 2026:

SyntaxError: Identifier 'SHEET_NAME' has already been declared (line 1, file "Untitled 2")

That means the code was fixed in the package, but Google is still serving an older deployed version. You must complete Part 2 and choose New version when redeploying.
Part 1 — Download and open the kit
Step 1: Download the ZIP

    Download BoatProUSA_COMPLETE_DEPLOYMENT_KIT_2026-07-24.zip.
    Look in your computer’s Downloads folder.
    Find the ZIP file.

Step 2: Extract the ZIP

On Windows:

    Right-click the ZIP file.
    Click Extract All.
    Leave the suggested folder name in place.
    Click Extract.
    Wait for the new folder to open.

Do not try to edit files while they are still inside the ZIP.
Step 3: Understand the folders

Open the extracted folder. You will see:

    01_INSTRUCTIONS — the instructions you are reading.
    02_GOOGLE_APPS_SCRIPT — the clean server code.
    03_GOOGLE_SHEETS — exact CRM column templates.
    04_WEBSITE_READY_TO_UPLOAD — only the files that belong in the website repository.
    05_TESTING_AND_TROUBLESHOOTING — final tests and common fixes.
    06_REFERENCE_ARTIFACTS — updated supporting files from earlier work.

Do not upload the whole deployment-kit folder to GitHub. Later, you will upload only the contents of 04_WEBSITE_READY_TO_UPLOAD.
Part 2 — Fix and redeploy Google Apps Script
Goal of this part

You will replace the old Apps Script files with one clean Code.gs file and redeploy the existing web app. Editing the existing deployment keeps the same /exec address.
Step 1: Sign in to the correct Google account

    Open a new browser tab.
    Go to https://script.google.com/.
    Sign in with the Google account that can open both:
        The Boat Pro USA Subscriber CRM spreadsheet.
        The 2026 Annapolis Boat Shows PDF.
    If you are signed into several Google accounts, check the profile picture in the upper-right corner and select the correct account.

The script must be able to edit the spreadsheet and read the PDF.
Step 2: Open the existing Apps Script project

    On the Apps Script home screen, look under My Projects.
    Open the Boat Pro USA subscriber or newsletter project.
    If you do not know which project is correct, open the project that contains a file named Untitled 2 or code containing SHEET_NAME.
    When the project opens, look at the file list on the left side.

Do not create a new project unless you truly cannot locate the old one. A new project creates a different /exec address.
Step 3: Delete the old duplicate files

    In the left file list, find Untitled 2.
    Move your mouse over the file name.
    Click the three-dot menu beside the file.
    Click Delete.
    Confirm the deletion.
    Repeat this for every old .gs file except one file that you will keep as Code.gs.
    You should end with one .gs file named Code.gs.

Important: Do not paste the new code below old code. Replace the old code completely.
Step 4: Replace Code.gs

    Return to the extracted deployment kit.
    Open 02_GOOGLE_APPS_SCRIPT.
    Open Code.gs with Notepad or another plain-text editor.
    Press Ctrl+A to select all the code.
    Press Ctrl+C to copy it.
    Return to the Apps Script browser tab.
    Click Code.gs in the left file list.
    Click inside the code editor.
    Press Ctrl+A to select all old code.
    Press Backspace or Delete.
    Press Ctrl+V to paste the clean code.
    Press Ctrl+S to save.

Step 5: Show the manifest file

    In Apps Script, click the gear icon labeled Project Settings on the left.
    Find Show “appsscript.json” manifest file in editor.
    Turn that setting on.
    Click the editor icon on the left to return to the file list.
    You should now see appsscript.json.

Step 6: Replace appsscript.json

    In the deployment kit, open 02_GOOGLE_APPS_SCRIPT/appsscript.json.
    Press Ctrl+A, then Ctrl+C.
    Return to Apps Script.
    Click appsscript.json.
    Press Ctrl+A inside the editor.
    Press Backspace or Delete.
    Press Ctrl+V.
    Press Ctrl+S.

Step 7: Run the setup function

The setup function checks the spreadsheet and PDF, creates missing sheet tabs if necessary, repairs the header row, adds the missing Status header to the Unsubscribes tab, freezes row 1, and sets the spreadsheet time zone to America/New_York.

    At the top of the Apps Script editor, find the function dropdown.
    Click the dropdown.
    Select setupBoatPro.
    Click Run.
    Google may ask for permission.
    Click Review permissions.
    Choose the correct Google account.
    If Google displays an “unverified” warning for your own script, click Advanced.
    Click the option to continue to the Boat Pro project.
    Click Allow.
    Wait until the execution status says Execution completed.

If it says Execution failed, open 05_TESTING_AND_TROUBLESHOOTING/TROUBLESHOOTING.md and match the error message.
Step 8: Redeploy the existing web app

This is the step that makes the fixed code live.

    In Apps Script, click Deploy in the upper-right corner.
    Click Manage deployments.
    Find the existing deployment marked Web app.
    Click the pencil icon to edit it.
    Find Version.
    Choose New version. Do not leave it on the old version.
    Enter this description: Boat Pro clean subscriber service - July 24 2026.
    Set Execute as to Me.
    Set Who has access to Anyone.
    Click Deploy.
    Approve permissions again if Google asks.
    Copy the web app URL ending in /exec.
    Compare it with the configured address shown at the top of this guide.

When you edit the existing deployment, the address should stay the same. If Google gives you a different address, follow the fallback instructions in 02_GOOGLE_APPS_SCRIPT/IF_THE_URL_CHANGES.md before uploading the website.
Step 9: Test the health address

    Open a new browser tab.
    Paste this exact address:

https://script.google.com/macros/s/AKfycbwSLD7gmeiUItt2wJVozJU1AX_2NzJwrnynRCxEvA_LhcRYIxhAtXXd1Oi2tzUImpYV8A/exec?action=health

    Press Enter.
    A working service should display text containing:

"ok":true

    It should also contain:

"service":"Boat Pro USA subscriber service"

Do not continue to the public signup test until this health check works.
Part 3 — Check the Google Sheets CRM
Step 1: Open the CRM

Open:

https://docs.google.com/spreadsheets/d/13XSLWLfjOmSd9KhvW7BoS1SNaHbCgMgvAJSCQofZz1g/edit

The spreadsheet title should be Boat Pro USA Subscriber CRM.
Step 2: Check the three tabs

At the bottom, confirm these exact tab names exist:

    Subscribers
    Email_Log
    Unsubscribes

Do not add spaces, change capitalization, or rename these tabs.
Step 3: Check the Subscribers header row

Click the Subscribers tab. Row 1 should contain these 15 headings from A1 through O1:

    Subscriber ID
    First Name
    Last Name
    Email
    Status
    Source
    Consent
    Consent Timestamp
    Signup Timestamp
    Guide Sent
    Guide Sent Timestamp
    Unsubscribe Token
    Unsubscribe Timestamp
    Last Updated
    Error

Step 4: Check Email_Log

Click Email_Log. Row 1 should contain:

    Timestamp
    Email
    Event
    Status
    Message ID
    Details

Step 5: Check Unsubscribes

Click Unsubscribes. Row 1 should contain:

    Timestamp
    Email
    Token
    Source
    Status

The older sheet had only four headings. Running setupBoatPro adds the fifth heading, Status, without deleting subscriber data.
Step 6: Check spreadsheet time zone

    In Google Sheets, click File.
    Click Settings.
    Confirm the time zone is an Eastern Time setting for New York.
    If it is not, select (GMT-05:00) Eastern Time – New York or the closest New York option.
    Click Save and reload.

The setup function also attempts to set America/New_York automatically.
Part 4 — Check the free guide PDF
Step 1: Open the guide

Open:

https://drive.google.com/file/d/1lKNfxDKJxN-zOeXcmiVevKvSPZj2GopP/view

The file should be named:

2026 Annapolis Boat Shows - Do's & Don'ts Guide - The Boat Pro.pdf
Step 2: Confirm it is a PDF

    Make sure the file opens as a PDF.
    Make sure the guide pages display correctly.
    Make sure the Google account deploying Apps Script can open it.

Step 3: Restrict the direct Drive link

The script emails the PDF as an attachment. The PDF does not need to be public.

    Click Share.
    Under General access, choose Restricted.
    Make sure the Apps Script owner still has access.
    Click Done.

This stops a permanent public Drive link from becoming the main delivery method.
Part 5 — Upload the website to GitHub
Repository information

    GitHub repository: dscottpoii/BoatProUSA.com
    Branch: main
    Custom domain: BoatProUSA.com

Step 1: Back up the current repository

    Open https://github.com/dscottpoii/BoatProUSA.com.
    Sign in to GitHub.
    Click the green Code button.
    Click Download ZIP.
    Keep that backup in your Downloads folder.

Step 2: Open the correct source folder on your computer

    Return to the extracted deployment kit.
    Open 04_WEBSITE_READY_TO_UPLOAD.
    Confirm you can see index.html and the assets folder.

You must upload the files inside this folder. Do not upload the folder itself as one extra level.
Step 3: Upload the new files

    Return to the GitHub repository page.
    Confirm the branch dropdown says main.
    Click Add file.
    Click Upload files.
    Open the 04_WEBSITE_READY_TO_UPLOAD folder in Windows File Explorer.
    Press Ctrl+A to select every file and folder inside it.
    Drag the selected items into the GitHub upload box.
    Wait until GitHub lists all uploaded files.
    Scroll to Commit changes.
    In the message box, enter: Deploy clean Boat Pro USA 2026 website.
    Choose Commit directly to the main branch.
    Click Commit changes.

Important: Uploading new files replaces files with the same names, but it does not automatically delete unrelated old files. Review the repository afterward and remove any old premium PDF, workbook, tutorial, or direct-download file that should not remain public.
Step 4: Check the repository root

After the commit, the first page of the repository should show:

    index.html
    about.html
    guides.html
    members.html
    privacy.html
    terms.html
    refund-policy.html
    thank-you.html
    CNAME
    robots.txt
    sitemap.xml
    assets folder

If all files appear inside an extra folder, the website will not find index.html. Move them to the repository root.
Part 6 — Turn on GitHub Pages

    On the GitHub repository page, click Settings.
    In the left menu, click Pages.
    Under Build and deployment, set Source to Deploy from a branch.
    Set the branch to main.
    Set the folder to / (root).
    Click Save.
    In Custom domain, enter BoatProUSA.com.
    Click Save.
    Leave Enforce HTTPS unchecked only while GitHub is creating the certificate.
    Return later and check Enforce HTTPS after GitHub allows it.

The repository already contains a CNAME file with BoatProUSA.com.
Part 7 — Set the domain DNS records

Open the website where the BoatProUSA.com domain was purchased. This may be GoDaddy, Namecheap, Squarespace Domains, Cloudflare, or another registrar.
Add four A records for the main domain

Create these four records:
Type 	Name/Host 	Value
A 	@ 	185.199.108.153
A 	@ 	185.199.109.153
A 	@ 	185.199.110.153
A 	@ 	185.199.111.153

Use the default TTL if the registrar asks for one.
Add one CNAME record for www
Type 	Name/Host 	Value
CNAME 	www 	dscottpoii.github.io

Remove conflicting old A records or a conflicting www record. Do not create a wildcard * record.
Part 8 — Test the complete signup flow

Use a real email address that is not already listed in the Subscribers tab.
Test 1: Website pages

Open https://BoatProUSA.com/ and check:

    The logo appears.
    The menu works.
    Guides opens.
    DIY Tutorials opens.
    Newsletters opens.
    Membership opens.
    About opens.
    Privacy, Terms, and Refund Policy open.
    The site works on a phone.

Test 2: Free-guide form

    Go to the homepage.
    Scroll to Get the 2026 Annapolis Boat Shows Guide.
    Enter a first name.
    Enter a last name.
    Enter a new test email address.
    Check the consent box.
    Click Email My Free Guide.
    Confirm the browser reaches https://BoatProUSA.com/thank-you.html.

Test 3: CRM row

    Open the Google Sheet.
    Open Subscribers.
    Look at the newest row.
    Confirm the email is correct.
    Confirm Status says Active.
    Confirm Consent says Yes.
    Confirm Guide Sent says Yes.
    Confirm the Error cell is blank.

Test 4: Email delivery

    Open the test email inbox.
    Check Spam or Junk if necessary.
    Open the Boat Pro USA email.
    Confirm the 2026 guide is attached.
    Confirm the support email is Info@BoatProUSA.com.
    Confirm the mailing address is shown.

Test 5: Email log

    Open the Email_Log tab.
    Confirm a guide_delivery event appears.
    Confirm its status says sent.

Test 6: Unsubscribe

    Click the unsubscribe link in the test email.
    Confirm the browser says the address is unsubscribed.
    Return to the Subscribers tab.
    Confirm Status changed to Unsubscribed.
    Confirm Unsubscribe Timestamp is filled in.
    Open the Unsubscribes tab.
    Confirm the test appears with Status success.

Test 7: Duplicate signup

    Submit the same test email again.
    Confirm the system does not send unlimited duplicate copies.
    Confirm the CRM does not create unnecessary duplicate rows.

Part 9 — What must remain disabled

Do not enable the $19.99 DIY or $24.99 Complete checkout buttons yet.

Before paid membership can launch, you still need:

    Real Stripe Checkout links.
    Stripe webhook signature verification.
    A secure database or verified membership status.
    Passwordless email login or secure one-time links.
    Server-side access checks.
    Protected downloads that do not reveal permanent public file URLs.
    Cancellation and renewal processing.

The current site intentionally displays paid options without working checkout links. This is safer than collecting payment before access control is ready.
Final launch rule

The free subscriber website is ready to promote only after all four items below are true:

    The Apps Script health page contains "ok":true.
    A new test subscriber appears in Google Sheets.
    The test email receives the correct PDF attachment.
    The unsubscribe link changes the CRM status.

Keep this guide with your Boat Pro USA records.
