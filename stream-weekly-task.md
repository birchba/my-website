# Stream extract for the Monday sales meeting

Run this on your PC in the Claude desktop app, with Chrome connected. Do the first run with you watching, so you can show Claude where things are in Stream.

**Scheduled task:** Mondays at 06:15, before the 06:45 meeting-page refresh. The PC must be on.

---

STREAM EXTRACT FOR THE SALES MEETING (Mondays 06:15). Alliance Platform Lifts. Our financial year runs 1 April to 31 March.

Use Chrome to open Stream (I am already signed in). READ ONLY: never create, edit, delete or send anything in Stream.

1. Sales figures. Open Reports, then Monthly activity. For the current financial year (April to today), take each month's value and number of jobs from the report's own figures: the orders won / sales line, not quotes issued. Write down which column or line you used. Work out:
   - the year-to-date total (from 1 April)
   - this month so far
   - last month
   - every month since April

2. Install dates. Find every open job with an install date in the next 10 weeks, and every job that is past its install start date but not finished. For each, record:
   - the job or PL number
   - the site or job name
   - the client
   - the salesperson
   - the install date
   - whether Stream shows the date as provisional or confirmed

   If Stream doesn't show provisional or confirmed, write status "unknown" and say so in notes.

3. Save the results as a JSON file called stream-weekly.json in SharePoint, in the Alliance Platform Lifts site under Documents > Sales > Claude outputs (replace last week's file). Use the Microsoft 365 connector's upload, or the synced SharePoint folder on this PC. Use exactly this shape:

```
{"as_of": "YYYY-MM-DD", "source": "Stream",
 "sales": {"year": "2026/27", "ytd_value": 0, "ytd_count": 0,
           "month_label": "November 2026", "month_value": 0, "month_count": 0,
           "last_month_label": "October 2026", "last_month_value": 0,
           "by_month": [{"month": "2026-04", "value": 0, "count": 0}],
           "measure": "which Stream column or line you used"},
 "installs": [{"pl": "PL1234", "name": "site or job", "client": "", "owner": "Ben", "date": "YYYY-MM-DD", "status": "provisional|confirmed|unknown"}],
 "installing_past_start": [{"pl": "", "name": "", "owner": "", "date": "YYYY-MM-DD"}],
 "notes": ["anything you could not find or were unsure of"]}
```

Values are plain numbers in pounds, with no £ sign or commas. Check that the file is valid JSON before saving. End with one line: what you saved, and anything missing.
