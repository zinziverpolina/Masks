# Site weight — measured 5 Oct 2026 (do this as the LAST stage)

GitHub Pages limit ~1 GB. Site without .git ≈ 980 MB: video 827 MB (57 mp4), jpg 82 MB, GLB 69 MB (53 files).
Full table: Masks repo `website-manager/videos-2026-10-05.csv`. Pages since changed (Hennessy removed etc.) — re-measure:
`git ls-files -z | xargs -0 du -b | sort -rn | head -60`

Heaviest pages then: LOEWE SS22 195 MB · LOEWE Christmas 148 · Nina Ricci 109 · HOROSOAPS 93 · HYPERTRASH 90 · Posters 87 · artistic 2050 66 · SHR 59 · Nothing review 48 · Clara 39.
Heaviest videos: clara-1 33 MB · posters-v1 30 · hypertrash-v1 30 · horosoaps-v1 29 · posters-v2 29 · nothing/phone/hq 24 · loewe-xmas-1 23 · loewe-owl-p 23 · horosoaps-v3 23 · horosoaps-3 22.

Why: master-level bitrates (10–14 Mbit/s) and every clip in 2–3 formats (16:9, 9:16, 4:5); LOEWE verticals up to 2250×3000.

## Plan
1. Re-encode all videos: `ffmpeg -i in.mp4 -c:v libx264 -preset slow -crf 22..24 -pix_fmt yuv420p -c:a aac -b:a 128k -movflags +faststart out.mp4`;
   cap the short side at 1080. Test: clara-1 33→6–8 MB, loewe-ww-1 20→6–8 MB, SSIM 0.993 (no visible loss). Expect ~250 MB instead of 830.
2. Long clips → Vimeo/YouTube. Polina says links exist in "the first iteration of the commercial portfolio" — NOT in the repo history
   (only B Pressure vimeo.com/348256701 and youtu.be/YwgAX1AkGR4, both artistic). Ask her for the source (Slides / Behance / old site). Behance is blocked from the cloud.
3. 3D models: `npx @gltf-transform/cli optimize in.glb out.glb --compress meshopt --texture-compress webp --texture-size 1024`.
   Test: xm-owl 5.2→1.2 MB, shr-squad-monster 4.3→1.0, lw-peas 3.7→0.6, shr-mouth-arch 3.7→1.0 → all ~17 MB instead of 69.
   Meshopt needs a decoder: in three.js `loader.setMeshoptDecoder(MeshoptDecoder)` (three/addons/libs/meshopt_decoder.module.js) in float-scene.js, shr-world.js and any stage code; model-viewer handles it itself. Check every card in a browser.
   The models are not "heavy" for the 1 GB limit — this is for speed (the intro loads ~25 models at once).
4. Remove `review/nothing/` when the Nothing review is done.
5. Order: tell the other chats to keep off `commercial/video` and `commercial/models` → build locally → show Polina → push.
