# DRESSED — New Development Repository

This is the isolated DRESSED development build. It is intentionally separate from the currently working DRESSED deployment.

## What is included
- Clean, vertically ordered mobile popups/forms.
- Add/Edit Look with separate **What are you wearing?** and **Notes** fields.
- Multiple outfit photos with removable previews.
- Calendar with **Add Event Manually**.
- Manual events support name, date, start/end time, venue, category and notes.
- Event details popup showing date, time, venue, assigned look and notes, with Edit/Delete controls.
- Invitation-created and manually-created events use the same calendar data model.
- Existing JPG/PNG invitation flow is retained.
- PDF reader keeps native text extraction and has an OCR fallback for image-only PDFs, with support extended beyond six pages.

## Render / GitHub layout
Keep these files at the repository root:
`Dockerfile`, `requirements.txt`, `index.html`, `manifest.webmanifest`, the icon PNGs, `render.yaml`, and `server/`.

Do not add a `public/` requirement unless the Dockerfile is changed accordingly.

## Test checklist
1. Home → Add Invitation → test the known-good Bijli JPG/PNG.
2. My Looks → Add a Look → confirm the popup is ordered and readable.
3. Add a Look → enter What are you wearing? + Notes → save → reopen and confirm both remain.
4. Calendar → Add Event Manually → create an event → confirm it appears on the correct date.
5. Tap an event → confirm details, assigned look, notes and Edit are present.
6. Test the AAMIL × SHRAVYA image-only PDF and confirm all invitation pages are considered.
7. Test the selectable-text Pre Wedding PDF as a regression test.

Do not replace the existing DRESSED repository until this new deployment passes the checklist.


## Update prepared in ChatGPT (12 Oct 2026)
- Added a Wardrobe tab with clothing photo uploads, categories, colour and notes.
- Wardrobe items are saved with the active local profile and can be used to create a saved look.
- Added working Profiles and Settings screens; profile switching includes wardrobe data.
- Settings supports exporting and importing a JSON backup of profiles, events, looks and wardrobe.
- Added a dismissible invitation sheet with a manual-event shortcut.
- Tapping a look photo/name opens its full look view.
- Existing `server/app.py` and `server/parser.py` are unchanged; invitation OCR/parser behavior has not been modified.


## Follow-up fixes (12 Oct 2026)
- Hardened event-to-look assignment and added clearer picker states and save errors.
- Profile switching now compares IDs consistently, reports failures, and refreshes all active profile data.
- Wardrobe allows saving individual clothing items without a photo; photos are compressed before storage to reduce browser quota failures.
- Save failures show an actionable message instead of silently doing nothing.
