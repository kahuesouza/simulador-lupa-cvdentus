# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Primary users are dentists and other clinical professionals evaluating a CVDentus dental loupe purchase, trying it on virtually through their own webcam before deciding — either on their own or guided by a salesperson/consultant during a sales conversation. They are non-technical, may be on a phone as often as a desktop, and want a fast, low-friction answer to "how would this actual model look and fit on my face" without needing to visit a showroom.

## Product Purpose

A browser-based virtual try-on simulator for CVDentus dental loupes. It lets a visitor pick one of 6 real loupe models (Ergo, Kepler, Galileu — each in TTL/fixed or Flip-up variants), see it rendered on their own live face via real-time face tracking with correct 3D occlusion (the loupe convincingly sits in front of/behind facial geometry), fine-tune its fit manually if automatic tracking doesn't land perfectly, preview the optical magnification effect through a separate live-camera simulator, and inspect any model as a 360° rotatable 3D product view.

## Positioning

Competing dental-loupe sellers show static product photos or, at best, a size chart. This simulator gives a physically-calibrated, live, real-time AR try-on per exact SKU — not a generic mockup — running entirely client-side in the browser with no app install. That combination (real per-model 3D assets + live face tracking + correct occlusion + a physically matched calibration engine) is the mechanism a competitor could not simply screenshot and copy.

## Operating Context

- Deployed as a static site on GitHub Pages: https://kahuesouza.github.io/simulador-lupa-cvdentus/
- Runs standalone in a mobile or desktop browser, most often reached from a CVDentus marketing/sales context (social, site, or a salesperson sending the link mid-conversation).
- A companion, separately-deployed magnification simulator is embedded via iframe (https://kahuesouza.github.io/simulador-magnificacao-cvdentus/), sharing the device camera with the main try-on flow — the two must not fight over camera access.
- No login, no backend, no analytics pipeline currently wired in; all processing (face tracking, 3D rendering) happens on-device.

## Capabilities and Constraints

- Face tracking and 3D rendering via Jeeliz FaceFilter (Apache 2.0, self-hosted) + Three.js r112 (pinned for compatibility with JeelizThreeHelper) — do not upgrade Three.js without re-validating the occluder/loader pipeline.
- 6 real product GLB models, each with its own bridge-point calibration and a per-model fine-tune override (scale/x/y/z) captured directly from the user's live-camera testing — these values are hard-won ground truth, not placeholders, and must not be reset or "simplified" away.
- Assets are pre-optimized for mobile load speed (WebP textures at native resolution, simplified geometry) after an earlier version was too slow on phones — any new asset added to this flow should follow the same treatment.
- A pre-fit calibration/"aligning tracking" step runs before the loupe appears, and again on every model switch.
- Manual fine-tune sliders exist because automatic tracking is a best-effort fit, not a guarantee, across different face shapes/camera angles.
- Brand rule inherited from CVD Vale/CVDentus: any imagery representing a product must be faithful to the real product — no generic or invented loupe likenesses standing in for an actual SKU.

## Evidence on Hand

- Real reference photos per model (assets/ref-*.png) used as model-picker thumbnails.
- A real photo/video of a person wearing a CVDentus loupe in profile (assets/hero-lupa-perfil.png, assets/hero-lupa-video.mp4) used as the hero visual.
- CVDentus logo (assets/logo-cvdentus-color.png).
- No testimonials, case studies, or usage-metrics evidence on hand; none should be invented.

## Product Principles

- The calibration is the product — visual polish must never come at the cost of the per-model fit accuracy already validated live with real faces.
- Assume the visitor is on a phone, on real mobile data, mid-conversation with a salesperson — every added asset or feature is judged against load speed first.
- Never depict a loupe that isn't a real, identifiable CVDentus SKU; product imagery is evidence, not decoration.
- Manual override is a first-class path, not a hidden escape hatch — automatic tracking will not fit every face perfectly, and the UI should make the fix obvious rather than apologize for needing it.
