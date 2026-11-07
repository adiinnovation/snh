CAREPOINT — WEEKDAY + DOCTOR LEAVE DATE UPDATE

This version is based on CarePoint_Doctor_Booking_App_Weekday_Disabled. The original design and existing booking features are retained.

New addition:
- Each doctor has a leaveDates array.
- Dates entered in that doctor's leaveDates array are disabled in that doctor's date picker.
- Weekly non-consulting weekdays and past dates continue to be disabled.
- The booking form checks leave dates again before opening WhatsApp.

How to set a doctor's leave:
Open index.html and find the doctors array. Add leave dates to the relevant doctor's record using YYYY-MM-DD:
leaveDates:["2026-11-12","2026-11-13"]

Example:
{id:1, name:"Dr. Anjali Menon", ..., days:["Monday","Wednesday","Friday"], leaveDates:["2026-11-12"]}

Use leaveDates:[] when the doctor has no leave dates configured. Set dates separately for each doctor. The included arrays are empty by default; enter the actual leave dates when needed.

No doctor-photo watermark or photo protection changes have been added in this version.

Run:
Extract the ZIP and open index.html in a browser. Keep hospital-logo.svg in the same folder.

Calendar appearance update: doctor leave dates are disabled and highlighted in red; weekly non-consulting days and past dates remain grey.

Latest fixes:
- Fixed a JavaScript syntax issue that stopped the doctor list from rendering.
- Department filter buttons now use a responsive grid: three columns on standard mobile widths and two columns on very narrow screens.
- Leave dates remain disabled and highlighted red; weekly non-consulting and past dates remain grey.

Latest corrections:
- Doctor leave dates are shown with a strong red background and red border in the calendar. The leave date remains disabled.
- OP number entered in the booking form is included in the prefilled WhatsApp request. If left blank, it is sent as "Not provided".
- Add each doctor's leave dates in that doctor's leaveDates array in YYYY-MM-DD format. Example: leaveDates:["2026-11-12","2026-11-15"]. An empty array means no leave dates have been configured.

Preferred consulting times update:
- Each doctor has a preferredTimes array in the doctors list.
- Supported values: "Morning", "Evening", and "Any available time".
- The booking form displays the selected doctor's configured times.
- The selected date and preferred time are checked together before the request is sent.
- The chosen preferred time is included in the WhatsApp message.

Example doctor setting:
preferredTimes:["Morning","Evening"]

If a doctor is flexible, use:
preferredTimes:["Any available time"]

The current doctor timing values are sample defaults. Replace them with each doctor's actual consulting sessions.

DATE-SPECIFIC OP TIMING OVERRIDES (NEW)
Each doctor has:
- preferredTimes: the doctor's normal weekly OP timing.
- specialSessions: date-specific timing overrides. If a date exists in specialSessions, only the times listed for that exact date are offered. This overrides the normal preferredTimes for that date.

Example:
preferredTimes:["Morning","Evening"],
specialSessions:{
  "2026-11-09":["Morning"]
}

For 9 Nov 2026, this doctor will show Morning only, even though the normal schedule includes Morning and Evening. On other consulting dates, both normal timings appear.

To add another date:
specialSessions:{
  "2026-11-09":["Morning"],
  "2026-11-13":["Evening"]
}

To remove a special date, delete that date entry from specialSessions. Date format must be YYYY-MM-DD.

When a patient chooses a date in the booking calendar:
- The preferred-time dropdown is refreshed for that exact date.
- Any previously selected time is cleared to avoid carrying a time over from another date.
- Only valid OP sessions for that date are shown.
- The selected date and time are validated again before WhatsApp opens.
- The selected OP time is included in the WhatsApp request.

The sample special session currently added is for Dr. Anjali Menon on 2026-11-09 (Morning only). Replace or remove this demo date to match the hospital's actual schedule.
