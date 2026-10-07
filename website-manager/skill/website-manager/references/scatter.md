# Framed drag-and-drop layout ("scatter") — built 6 Oct for LOEWE

Polina's request: like her mock-up (loose cards of different sizes), on LOEWE: move the Live Laugh Loewe sky scene to the bottom;
all pictures/videos in frames like the main page, they "float in evenly and fall onto the text", can be dragged and stay where dropped.

Built as a test copy (live page untouched): `commercial/loewe-test.html` (noindex) + `commercial/scatter.js` + `commercial/scatter.css`, commit 6158489.
- Each section is a stage; its media become `figure.sc` pieces in `.shr-frame`-style frames (sky → navy + caption on hover).
- Layout: seeded lanes around the text block (4 lanes desktop, 2 on phones), sizes vary, wide pictures reach into the next lane.
- Entry: pieces drop from above one by one with a light spring bounce, then float gently.
- Drag: stiff spring to the pointer, pushes others aside; on release it is pinned and others move their home out of the way; stage grows if needed. Touch: hold 260 ms, then drag.
- Click without drag → opens large (video with sound and controls). Max 3 videos play at once.
Open choices for Polina: text solid (pieces bounce off it) or not; same layout each visit vs random; remember dragged positions; captions.
Since then (6–8 Oct) the LOGO chat built "floating stages" for all white pages + an `?edit` editor saving `layout.json` — compare and keep one system.
