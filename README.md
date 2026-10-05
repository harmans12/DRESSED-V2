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
