ECDOE eLearning Project Tracker deployment

FILES
- index.html: upload to the GitHub repository root.
- Code.gs: paste into the Apps Script project attached to the spreadsheet.

GOOGLE CLOUD
1. Open Google Cloud Console.
2. Configure the OAuth consent screen.
3. Create an OAuth Client ID of type Web application.
4. Add this authorised JavaScript origin:
   https://elearning-ecdoe.github.io
5. Copy the Client ID into:
   - index.html -> CONFIG.GOOGLE_CLIENT_ID
   - Code.gs -> CONFIG.GOOGLE_CLIENT_ID

APPS SCRIPT
1. Open the tracker spreadsheet.
2. Extensions -> Apps Script.
3. Replace the default Code.gs with the supplied Code.gs.
4. Deploy -> New deployment -> Web app.
5. Execute as: Me.
6. Who has access: Anyone.
7. Authorise and deploy.
8. Copy the URL ending in /exec into index.html -> CONFIG.APPS_SCRIPT_URL.

GITHUB
1. Rename your old index.html as a backup.
2. Upload the supplied index.html and logo2.png to:
   elearning-ecdoe/Project-Tracker
3. Commit changes.
4. Open:
   https://elearning-ecdoe.github.io/Project-Tracker/

ACCESS RULE
- The Google ID token is verified in Apps Script.
- The verified email must match either Email or Alternative Email in
  eLearning_Team.
- Every create and update repeats the server-side access validation.
- Users not in the team sheet remain dashboard-only.

IMPORTANT
The spreadsheet must remain viewable through its CSV endpoint for the public
dashboard. Do not publish the eLearning_Team sheet publicly if it contains
sensitive personal details. A stronger privacy design would load dashboard
and team names through the Apps Script API instead of public CSV.
