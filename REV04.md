# REV.04 - Native geometry, rendering and handover

Contest #2801401 - Luxury Crystal & Perfume Boutique (~99 sqm).

This revision implements the employer's 16 November 2026 comment on entry #94: "the office can be joind with store , table in middle can be long for display , need uniqe touch".

## Geometry and dimensions

`layout_geometry.json` is the millimetre source for the CAD plan/elevations and both Blender scenes. `scripts/geometry.py` regenerates that source. All branches use the 2800 mm ceiling datum and the same walls, window openings, doors, columns and fixture footprints.

| Element | REV.04 definition |
| --- | --- |
| 04 OFFICE & BACK-OF-HOUSE STORE | 14.605 m² coordinate footprint; one combined space and one 900 mm concealed entrance |
| Management desk | 1600 x 650 x 750 mm; east side, with file cabinet and task chair |
| S-01 to S-03 | Three concealed stock units, each 1100 x 450 x 2200 mm; south-wall position preserves the west window |
| PKG-01 packing worktop | 1400 x 600 x 900 mm; 950 mm working route |
| I-01 central table | 4400 x 1100 x 950 mm, long axis north-south, R550 rounded short ends and 300 mm knee recess |
| T-01 to T-04 | Four 450 x 450 mm upholstered stools, seat height 650 mm and footrest 280 mm, at the southern scent-testing end |
| Table-side clear routes | West 2270 mm; east 2750 mm |
| Routes beside stool footprints | West 1820 mm; east 2300 mm |
| North table clearance | 1900 mm |
| VIP-S / VIP-A1 / VIP-A2 | Front-to-table clearances 400 / 400 / 400 mm; seats arranged north/east/south of one elliptical table; 1500 mm two-seat sofa with a clear 380 mm leg zone |
| VIP-T | 1300 x 550 x 390 mm ellipse, one elliptical pedestal; identical 2D and 3D envelope |
| Pantry S / WC S access | Continuous route around the south side of COL-1; proposed 900 mm D-04/D-05 altered openings, conservative 864 mm swept-body width including open leaves; site verification required |
| D-03 | Original 900 mm position retained; 90-degree-open leaf and arc in CAD, closed flush door in VIEW 02; continuous external approach and entry maintain 864 mm swept-body clearance in the open state |
| OFFICE-G1 | Neutral matte privacy glass from floor to 1100 mm, clear glass above |
| Zone 03 / VIP-C | 18.86 m² polygon; salon label inside the same polygon; VIP-C belongs to Zone 01 |
| CV-01 plaster light vault | 5000 x 1700 mm footprint, recessed above the 2800 mm ceiling |
| LP-01 art pendant | 3800 x 440 mm bounding footprint; underside 2250 mm above floor, centred over the table |

The central table combines graduated product stands, fine champagne-metal frames around local glass covers, gift-box display and a scent-testing end. Fine vertical plaster flutes are modelled on its base and the main arched niches. The cove vault and art pendant follow the same central axis. Wall finishes are matte paint over plaster, with fine metal trim as a separate detail.

The original raster label remains 99.27 m². The L-shaped coordinate boundary measures 113.21235 m² including the 14.78130 m² existing service core, leaving 98.43105 m². The four zones partition that latter footprint without overlap. The 14.605 m² combined backstage area is the union of the original 04/05 zone footprints; it includes walls and fixtures and is not a certified net usable area.

D-04 and D-05 are proposed alterations to existing core walls, widening the previous design's 800 mm nominal openings to 900 mm. The plan distinguishes the affected walls on `A-WALL-ALTER` and labels both openings with a site-verification note. The 850 mm route requirement depends on confirming the existing wall construction and the feasibility of these alterations on site; the proposed widths are not surveyed existing conditions.

## Native images and exact-camera proof

The design images are rendered in Blender 5.1.1 with Cycles, native meshes, procedural materials and physically placed lights. No AI image generator, generative retouching, painted-over render or photographic interior backdrop is used. The parametric pipeline was prepared with coding assistance; this does not assert manual-only authorship.

The window view uses a neutral presentation background, not a measured or surveyed exterior scene. Physical sky illumination remains active in the scene.

The six final files retain their existing names:

- `assets/blender_view1_main_gallery.jpg`
- `assets/blender_view2_vip_lounge.jpg`
- `assets/blender_view1_wireframe_samecam.jpg`
- `assets/blender_view2_wireframe_samecam.jpg`
- `assets/blender_view3_vitrine_closeup.jpg`
- `assets/blender_view4_wireframe_cutaway.jpg`

VIEW 01 and VIEW 02 are each paired with a white-model/Freestyle image. The pipeline compares camera matrices, lens, shift, resolution, pixel aspect, object visibility and evaluated mesh hashes. Only shading and line presentation change between the pair; glass remains transparent so products remain visible. VIEW 04 is a separate architectural cutaway.

VIEW 04 uses a full pale matte override, with silhouette/border lines and no dense crease or material-boundary linework. The current render log and native mesh diagnostics distinguish line-projection warnings from actual geometry defects; the Chinese report records the final counts. Earlier isolation logs are retained as historical evidence only.

`exports/render_manifest.json` records Blender version, geometry-source hash, script hashes, image hashes, camera records and paint audit. The compositor refuses a revision, source, image or native-file mismatch. `exports/board_manifest.json` binds each board and preview to the actual current input bytes. Independent reopening is recorded in `exports/blender_reopen_validation.json`.

Walls, columns and ceiling use OC-17 White Dove; painted niches and fixture bodies use OC-85 Mayonnaise. The hex values `#F3EFE6` and `#E6DEC8` are digital colour approximations, not manufacturer-certified colour values. Both paint shaders are matte with roughness 0.85; physical paint samples remain the colour reference. No stone/travertine wall cladding, wood veneer or heavy wall panels are specified. Product gift boxes are separate display contents.

## Delivery and public preview

`deliverables/` contains BT-01 to BT-04 at 3200 x 2400 px. `review/previews/` contains the corresponding 1200 x 900 px review copies. The four-page A3 landscape PDF and native Master Pack ZIP are in `exports/`. Legacy board and ZIP aliases resolve to the current content.

`docs/` contains only a watermarked 1200 px public preview, local fonts and these notes. It does not expose native CAD, Blender, ZIP or PDF files. Previous public-site bytes are preserved under `review/rev04_before/boards/docs_site/`. Local preparation does not deploy or submit the revision.

BT-01 includes all four original client product references, each labelled `CLIENT PRODUCT REF 1..4 / NOT A RENDER`, alongside VIEW 03/04. The three attachments named `Gemini_Generated_Image` are shown only as client references, never as our Blender renders or model textures. BT-03 enlarges individual wall elevations; BT-04 includes the same-source VIP/office plan and long-table section.

The DXF is R2010 with native editable text and dimensions. The companion DWG is a native R2000 binary produced by LibreDWG; text and dimensions are outlined/decomposed for conversion compatibility. Both conversion directions report zero errors, and the local roundtrip comparison and audit have zero differences or errors; the DWG-to-DXF reader can emit HATCH handle warnings, counted in the current validation report. This validates the local conversion scope, not operation in Autodesk AutoCAD, which has not been tested. Conversion messages and scope are retained in `exports/dwg_validation.json` and `review/dxf2dwg.log` / `review/dwg2dxf.log`.

## Rebuild and validation

From the project root, using the installed environment:

```sh
PYTHONDONTWRITEBYTECODE=1 /usr/local/bin/python3.11 scripts/geometry.py
PYTHONDONTWRITEBYTECODE=1 /usr/local/bin/python3.11 scripts/build_cad.py
PYTHONDONTWRITEBYTECODE=1 /usr/local/bin/python3.11 scripts/convert_dwg.py
/Applications/Blender.app/Contents/MacOS/Blender -b --factory-startup --python-exit-code 1 --python scripts/render_blender.py
/Applications/Blender.app/Contents/MacOS/Blender -b --factory-startup --python-exit-code 1 --python scripts/render_cad_axonometric.py
PYTHONDONTWRITEBYTECODE=1 /usr/local/bin/python3.11 scripts/verify.py
/Applications/Blender.app/Contents/MacOS/Blender -b exports/Crystal_Perfume_Boutique_99sqm.blend --python-exit-code 1 --python scripts/verify_blender_rev04.py
PYTHONDONTWRITEBYTECODE=1 /usr/local/bin/python3.11 scripts/compose_boards.py
PYTHONDONTWRITEBYTECODE=1 /usr/local/bin/python3.11 scripts/verify_rev04.py
```

`verify_rev03.py` is a compatibility entry point for the current REV.04 delivery verification. `BOUTIQUE_PREVIEW=1` directs draft renders to the review folder and does not replace the final assets. A partial final render is rejected.

COL-1 is labelled 450 x 700 mm nominal; the preserved source coordinates measure 451 x 700 mm. The north dimension string is explicitly 1850 wall + 5500 window + 1450 wall = 8800 mm. Pantry/WC labels are positioned clear of fixture symbols and door lines.

The acceptance record consists of the actual current JSON reports plus visual inspection of all four board previews and PDF rasterizations. Collision checks cover the modelled fixture/structure footprints and door/route checks recorded by the geometry verifier; they do not certify site installation or building-code compliance.
