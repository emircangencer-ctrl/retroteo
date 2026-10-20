# Stage 05 — test report

## Passed locally

- `node --test tests/*.test.mjs`: ROM validator unit tests pass.
- `node --check src/app.js` and `node --check src/nes-rom.js`: syntax pass.
- HTML and package/configuration files are present; Vite entry imports the local stylesheet and JSNES API.
- The player UI wires `NesBrowser` load/start/destroy, pause/resume, keyboard/gamepad support supplied by JSNES, and pointer-driven touch controls.
- The service worker cache name is bumped to `retroplay-shell-v5`.

## Not verified in this environment

The container cannot resolve `registry.npmjs.org` (DNS `EAI_AGAIN`), so `npm install`, the Vite production bundle, and live emulation could not be executed here. Netlify's build is configured to install the pinned JSNES dependency and Vite before publishing. Do not call this a fully end-to-end verified release until the Netlify build and at least one real `.nes` ROM are tested in desktop and Android browsers.

## Scope

Actual emulation is connected for NES `.nes` files only. Other platforms remain unsupported for gameplay. Save-state and SRAM UI are future work.
