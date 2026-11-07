CAREPOINT — DOCTOR APPOINTMENT REQUEST APP

Updated features:
- Hospital logo image in the title bar (hospital-logo.svg placeholder).
- Hospital name shown beside the logo (edit the text in index.html).
- Optional OP number field included in WhatsApp request.
- Weekly consulting weekdays configured separately for each doctor in the doctors array.
- Date selection checks the chosen doctor's weekly schedule and shows a clear availability message.
- Booking submission is blocked if the selected doctor is not scheduled on that weekday.

How to customize:
1. Replace hospital-logo.svg with your own logo image (keep the filename, or update the src in index.html).
2. Change "Your Hospital Name" in index.html to the actual hospital name.
3. Edit each doctor's days array, using full weekday names, e.g. ["Monday","Wednesday","Friday"].
4. Replace sample doctor profiles, degrees, specialties and photos with verified clinic details.

How to run:
Extract the ZIP and open index.html in a browser. An internet connection is needed for Bootstrap and Google Fonts CDNs and the sample doctor photos.

Important:
This is a front-end appointment request app. It opens WhatsApp to +91 85899 00277 with a pre-filled request; the user must press Send. It does not store patient data or confirm appointments. All doctor profiles and schedules are sample values until verified by the hospital.

Latest update: The appointment date picker now disables past dates and all weekdays on which the selected doctor does not consult. Only the doctor's configured consulting weekdays can be selected. This uses a custom calendar because standard browser date inputs do not support disabling individual weekdays.
