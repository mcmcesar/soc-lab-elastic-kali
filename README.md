```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<style id="lumi-runtime">
/* luminous.css */
/*
 * Luminous runtime stylesheet — injected once into every generated widget's
 * <head> by the C++ widget agent (id="lumi-runtime"). Single Source of Truth
 * for ALL design tokens and pre-baked .lumi-* component classes. The SI prompts
 * (design.md / html_generation.jinja2 / chart.jinja2) must NOT re-declare these
 * tokens or component CSS; they only reference them.
 *
 * Sections:
 *   1. Web fonts (Google Sans Flex + Google Sans Code)
 *   2. Light token :root (from previewer tokens.css, verbatim)
 *   3. Dark token overrides — REMAPPED to :root so canvas/D3 readers of
 *      getComputedStyle(document.documentElement) resolve dark values (D3).
 *   4. Short diagram/chart aliases (bridge legacy --surface / --chart-N names).
 *   5. In-scope pre-baked .lumi-* component classes.
 */

/* ============================================================
 * 1. WEB FONTS & ICONOGRAPHY
 *    Loads Google Sans Flex, Google Sans Code, and Material Symbols Outlined.
 *    Enforces the dual-class iconography rendering protocol.
 * ============================================================ */
@import url('https://fonts.googleapis.com/css2?family=Google+Sans+Flex:ital,wght@0,300..700;1,300..700&family=Google+Sans+Code:ital,wght,MONO@0,300..700,0..1;1,300..700,0..1&family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200&display=swap');

/* Dual-Class Iconography */
.lumi-icon {
  font-family: 'Luminous Symbols', 'Material Symbols Outlined';
  font-weight: normal;
  font-style: normal;
  font-size: 20px;
  line-height: 1;
  letter-spacing: normal;
  text-transform: none;
  display: inline-block;
  white-space: nowrap;
  word-wrap: normal;
  direction: ltr;
  font-feature-settings: 'liga';
  -webkit-font-smoothing: antialiased;
  vertical-align: middle;
}

.material-icon {
  font-family: 'Material Symbols Outlined';
  font-weight: normal;
  font-style: normal;
  font-size: 20px;
  line-height: 1;
  letter-spacing: normal;
  text-transform: none;
  display: inline-block;
  white-space: nowrap;
  word-wrap: normal;
  direction: ltr;
  -webkit-font-smoothing: antialiased;
  vertical-align: middle;
}

/* ============================================================
 * 2. LIGHT TOKENS (:root)
 * ============================================================ */
:root {
  --body-bg: transparent;
  --ff-sans: 'Google Sans Flex', 'Google Sans Text', 'Google Sans', sans-serif;
  --ff-mono: 'Google Sans Code', 'Google Sans Mono', monospace;

  --lumi-sys-spacing--xxs: 2px;
  --lumi-sys-spacing--xs: 4px;
  --lumi-sys-spacing--s: 8px;
  --lumi-sys-spacing--m: 12px;
  --lumi-sys-spacing--l: 16px;
  --lumi-sys-spacing--xl: 20px;
  --lumi-sys-spacing--xxl: 24px;
  --lumi-sys-spacing--3xl: 28px;
  --lumi-sys-spacing--4xl: 36px;

  --lumi-sys-shape--none: 0px;
  --lumi-sys-shape--extra-small: 4px;
  --lumi-sys-shape--small: 8px;
  --lumi-sys-shape--medium: 12px;
  --lumi-sys-shape--large: 16px;
  --lumi-sys-shape--large-increased: 20px;
  --lumi-sys-shape--large-max: 24px;
  --lumi-sys-shape--xl: 28px;
  --lumi-sys-shape--xl-increased: 32px;
  --lumi-sys-shape--xl-max: 40px;
  --lumi-sys-shape--xxl: 48px;
  --lumi-sys-shape--xxl-increased: 56px;
  --lumi-sys-shape--full: 999px;

  --lumi-sys-elevation--level1: 0 0 20px 0 rgba(0, 0, 0, 0.04);
  --lumi-sys-elevation--level2: 0 0 20px 0 rgba(0, 0, 0, 0.11);

  --lumi-sys-color--surface: #fdfcfc;
  --lumi-sys-color--surface-dim: #f2f0f0;
  --lumi-sys-color--surface-bright: #ffffff;
  --lumi-sys-color--surface-background: #fdfcfc;
  --lumi-sys-color--surface-accent: #9dd2ff;
  --lumi-sys-color--surface-container: #f2f0f0;
  --lumi-sys-color--surface-container-high: #e6e6e6;
  --lumi-sys-color--on-surface: #000000;
  --lumi-sys-color--on-surface-default: #000000;
  --lumi-sys-color--on-surface-variant: rgba(0, 0, 0, 0.55);
  --lumi-sys-color--on-surface-de-emphasis: rgba(0, 0, 0, 0.55);
  --lumi-sys-color--on-surface-low: rgba(0, 0, 0, 0.08);
  --lumi-sys-color--positive: #008052;
  --lumi-sys-color--positive-container: #daf9d4;
  --lumi-sys-color--on-positive-container: #009954;
  --lumi-sys-color--error: #de2d29;
  --lumi-sys-color--error-container: #ffdeec;
  --lumi-sys-color--on-error-container: #de2d29;
  --lumi-sys-color--accent: #9dd2ff;
  --lumi-sys-color--accent-container: #dcf1ff;
  --lumi-sys-color--accent-fixed: #3186ff;
  --lumi-sys-color--primary: #3186ff;
  --lumi-sys-color--on-primary: #ffffff;
  --lumi-sys-color--black: #000000;
  --lumi-sys-color--white: #ffffff;
  --lumi-sys-color--outline: #727676;
  --lumi-sys-color--stroke-default: #e3e3e3;

  /* --- Luminous Typography Tokens: Display (Carbon SSoT) --- */
  --lumi-sys-typography-type-scale--display-l-font-name: 'Google Sans Flex';
  --lumi-sys-typography-type-scale--display-l-font-size: 2.625rem;
  --lumi-sys-typography-type-scale--display-l-line-height: 3rem;
  --lumi-sys-typography-type-scale--display-l-font-tracking: 0rem;
  --lumi-sys-typography-type-scale--display-l-font-weight: 280;
  --lumi-sys-typography-type-scale--display-l-font-wght: 280;
  --lumi-sys-typography-type-scale--display-l-font-width: 100;
  --lumi-sys-typography-type-scale--display-l-font-rond: 100;
  --lumi-sys-typography-type-scale--display-l-opsz: 42;

  --lumi-sys-typography-type-scale--display-m-font-name: 'Google Sans Flex';
  --lumi-sys-typography-type-scale--display-m-font-size: 2.25rem;
  --lumi-sys-typography-type-scale--display-m-line-height: 2.75rem;
  --lumi-sys-typography-type-scale--display-m-font-tracking: 0rem;
  --lumi-sys-typography-type-scale--display-m-font-weight: 320;
  --lumi-sys-typography-type-scale--display-m-font-wght: 320;
  --lumi-sys-typography-type-scale--display-m-font-width: 100;
  --lumi-sys-typography-type-scale--display-m-font-rond: 100;
  --lumi-sys-typography-type-scale--display-m-opsz: 36;

  --lumi-sys-typography-type-scale--display-s-font-name: 'Google Sans Flex';
  --lumi-sys-typography-type-scale--display-s-font-size: 2rem;
  --lumi-sys-typography-type-scale--display-s-line-height: 2.375rem;
  --lumi-sys-typography-type-scale--display-s-font-tracking: 0rem;
  --lumi-sys-typography-type-scale--display-s-font-weight: 360;
  --lumi-sys-typography-type-scale--display-s-font-wght: 360;
  --lumi-sys-typography-type-scale--display-s-font-width: 100;
  --lumi-sys-typography-type-scale--display-s-font-rond: 100;
  --lumi-sys-typography-type-scale--display-s-opsz: 32;

  /* --- Luminous Typography Tokens: Headline (Carbon SSoT) --- */
  --lumi-sys-typography-type-scale--headline-l-font-name: 'Google Sans Flex';
  --lumi-sys-typography-type-scale--headline-l-font-size: 1.75rem;
  --lumi-sys-typography-type-scale--headline-l-line-height: 2.25rem;
  --lumi-sys-typography-type-scale--headline-l-font-tracking: 0rem;
  --lumi-sys-typography-type-scale--headline-l-font-weight: 350;
  --lumi-sys-typography-type-scale--headline-l-font-wght: 350;
  --lumi-sys-typography-type-scale--headline-l-font-width: 100;
  --lumi-sys-typography-type-scale--headline-l-font-rond: 20;
  --lumi-sys-typography-type-scale--headline-l-opsz: 28;

  --lumi-sys-typography-type-scale--headline-m-font-name: 'Google Sans Flex';
  --lumi-sys-typography-type-scale--headline-m-font-size: 1.5rem;
  --lumi-sys-typography-type-scale--headline-m-line-height: 1.75rem;
  --lumi-sys-typography-type-scale--headline-m-font-tracking: 0rem;
  --lumi-sys-typography-type-scale--headline-m-font-weight: 380;
  --lumi-sys-typography-type-scale--headline-m-font-wght: 380;
  --lumi-sys-typography-type-scale--headline-m-font-width: 100;
  --lumi-sys-typography-type-scale--headline-m-font-rond: 20;
  --lumi-sys-typography-type-scale--headline-m-opsz: 24;

  --lumi-sys-typography-type-scale--headline-s-font-name: 'Google Sans Flex';
  --lumi-sys-typography-type-scale--headline-s-font-size: 1.25rem;
  --lumi-sys-typography-type-scale--headline-s-line-height: 1.5rem;
  --lumi-sys-typography-type-scale--headline-s-font-tracking: 0rem;
  --lumi-sys-typography-type-scale--headline-s-font-weight: 470;
  --lumi-sys-typography-type-scale--headline-s-font-wght: 470;
  --lumi-sys-typography-type-scale--headline-s-font-width: 94;
  --lumi-sys-typography-type-scale--headline-s-font-rond: 20;
  --lumi-sys-typography-type-scale--headline-s-opsz: 20;

  /* --- Luminous Typography Tokens: Body (Carbon SSoT) --- */
  --lumi-sys-typography-type-scale--body-l-font-name: 'Google Sans Flex';
  --lumi-sys-typography-type-scale--body-l-font-size: 1.0625rem;
  --lumi-sys-typography-type-scale--body-l-line-height: 1.5rem;
  --lumi-sys-typography-type-scale--body-l-font-tracking: 0rem;
  --lumi-sys-typography-type-scale--body-l-font-weight: 400;
  --lumi-sys-typography-type-scale--body-l-font-wght: 400;
  --lumi-sys-typography-type-scale--body-l-font-width: 92;
  --lumi-sys-typography-type-scale--body-l-font-rond: 0;
  --lumi-sys-typography-type-scale--body-l-opsz: 17;

  --lumi-sys-typography-type-scale--body-m-font-name: 'Google Sans Flex';
  --lumi-sys-typography-type-scale--body-m-font-size: 0.9375rem;
  --lumi-sys-typography-type-scale--body-m-line-height: 1.25rem;
  --lumi-sys-typography-type-scale--body-m-font-tracking: 0rem;
  --lumi-sys-typography-type-scale--body-m-font-weight: 400;
  --lumi-sys-typography-type-scale--body-m-font-wght: 400;
  --lumi-sys-typography-type-scale--body-m-font-width: 92;
  --lumi-sys-typography-type-scale--body-m-font-rond: 0;
  --lumi-sys-typography-type-scale--body-m-opsz: 15;

  --lumi-sys-typography-type-scale--body-s-font-name: 'Google Sans Flex';
  --lumi-sys-typography-type-scale--body-s-font-size: 0.8125rem;
  --lumi-sys-typography-type-scale--body-s-line-height: 1.0625rem;
  --lumi-sys-typography-type-scale--body-s-font-tracking: 0rem;
  --lumi-sys-typography-type-scale--body-s-font-weight: 400;
  --lumi-sys-typography-type-scale--body-s-font-wght: 400;
  --lumi-sys-typography-type-scale--body-s-font-width: 92;
  --lumi-sys-typography-type-scale--body-s-font-rond: 0;
  --lumi-sys-typography-type-scale--body-s-opsz: 13;

  /* --- Luminous Typography Tokens: Label (Carbon SSoT) --- */
  --lumi-sys-typography-type-scale--label-l-font-name: 'Google Sans Flex';
  --lumi-sys-typography-type-scale--label-l-font-size: 1.0625rem;
  --lumi-sys-typography-type-scale--label-l-line-height: 1.5rem;
  --lumi-sys-typography-type-scale--label-l-font-tracking: 0rem;
  --lumi-sys-typography-type-scale--label-l-font-weight: 370;
  --lumi-sys-typography-type-scale--label-l-font-wght: 370;
  --lumi-sys-typography-type-scale--label-l-font-width: 92;
  --lumi-sys-typography-type-scale--label-l-font-rond: 0;
  --lumi-sys-typography-type-scale--label-l-opsz: 17;

  --lumi-sys-typography-type-scale--label-m-font-name: 'Google Sans Flex';
  --lumi-sys-typography-type-scale--label-m-font-size: 0.9375rem;
  --lumi-sys-typography-type-scale--label-m-line-height: 1.25rem;
  --lumi-sys-typography-type-scale--label-m-font-tracking: 0rem;
  --lumi-sys-typography-type-scale--label-m-font-weight: 370;
  --lumi-sys-typography-type-scale--label-m-font-wght: 370;
  --lumi-sys-typography-type-scale--label-m-font-width: 92;
  --lumi-sys-typography-type-scale--label-m-font-rond: 0;
  --lumi-sys-typography-type-scale--label-m-opsz: 15;

  --lumi-sys-typography-type-scale--label-s-font-name: 'Google Sans Flex';
  --lumi-sys-typography-type-scale--label-s-font-size: 0.8125rem;
  --lumi-sys-typography-type-scale--label-s-line-height: 1.25rem;
  --lumi-sys-typography-type-scale--label-s-font-tracking: 0rem;
  --lumi-sys-typography-type-scale--label-s-font-weight: 370;
  --lumi-sys-typography-type-scale--label-s-font-wght: 370;
  --lumi-sys-typography-type-scale--label-s-font-width: 92;
  --lumi-sys-typography-type-scale--label-s-font-rond: 0;
  --lumi-sys-typography-type-scale--label-s-opsz: 13;

  --lumi-sys-opacity-state--hover: 0.08;
  --lumi-sys-opacity-state--focus: 0.08;
  --lumi-sys-opacity-state--pressed: 0.12;
  --lumi-sys-opacity-state--disabled: 0.12;
  --lumi-sys-opacity-state--disabled-label: 0.38;

  --lumi-sys-color--code-background: #000000;
  --lumi-sys-color--code-primary-text: #ffffff;
  --lumi-sys-color--code-blue-text: #4fa0ff;
  --lumi-sys-color--code-green-text: #60d673;
  --lumi-sys-color--code-grey-text: #808080;
  --lumi-sys-color--code-pink-text: #ff96da;
  --lumi-sys-color--code-purple-text: #969dff;
  --lumi-sys-color--code-red-text: #ff5a59;
  --lumi-sys-color--code-yellow-text: #ffdb0f;

  --lumi-sys-color--chart-series-1: #2575fc;
  --lumi-sys-color--chart-series-2: #5b6e9e;
  --lumi-sys-color--chart-series-3: #228a49;
  --lumi-sys-color--chart-series-4: #62991b;
  --lumi-sys-color--chart-series-5: #1e564d;
  --lumi-sys-color--chart-series-6: #526a45;
  --lumi-sys-color--chart-series-7: #2780c4;
  --lumi-sys-color--chart-series-8: #997112;
  --lumi-sys-color--chart-series-9: #705ec2;
  --lumi-sys-color--chart-series-10: #c84288;
}

/* ============================================================
 * 3. DARK TOKENS  (REMAPPED to :root — Decision D3)
 *    Canvas / Chart.js / D3 read getComputedStyle(document.documentElement);
 *    the theme-sync listener sets data-theme="dark" on <html>, so dark values
 *    MUST live on :root (not scoped to body) to prevent black-chart regressions.
 * ============================================================ */
:root[data-theme="dark"],
body.dark-mode,
:root[data-theme="dark"] body {
  --body-bg: #0f0f0f;
  --lumi-sys-elevation--level1: 0 0 20px 0 rgba(0, 0, 0, 0.28);
  --lumi-sys-elevation--level2: 0 0 20px 0 rgba(0, 0, 0, 0.40);

  --lumi-sys-color--surface: #0f0f0f;
  --lumi-sys-color--surface-dim: #141414;
  --lumi-sys-color--surface-bright: #1c1c1c;
  --lumi-sys-color--surface-background: #0f0f0f;
  --lumi-sys-color--surface-accent: #14204f;
  --lumi-sys-color--surface-container: #141414;
  --lumi-sys-color--surface-container-high: #1c1c1c;
  --lumi-sys-color--on-surface: #e0e0e0;
  --lumi-sys-color--on-surface-default: #e0e0e0;
  --lumi-sys-color--on-surface-variant: rgba(255, 255, 255, 0.55);
  --lumi-sys-color--on-surface-de-emphasis: rgba(255, 255, 255, 0.55);
  --lumi-sys-color--on-surface-low: rgba(255, 255, 255, 0.12);
  --lumi-sys-color--positive: #0ebc5f;
  --lumi-sys-color--positive-container: #002220;
  --lumi-sys-color--on-positive-container: #0ebc5f;
  --lumi-sys-color--error: #ff4c45;
  --lumi-sys-color--error-container: #3c0202;
  --lumi-sys-color--on-error-container: #ff4c45;
  --lumi-sys-color--accent: #1f3b9b;
  --lumi-sys-color--accent-container: #192967;
  --lumi-sys-color--accent-fixed: #3186ff;
  --lumi-sys-color--primary: #9dd2ff;
  --lumi-sys-color--on-primary: #192967;
  --lumi-sys-color--black: #000000;
  --lumi-sys-color--white: #ffffff;
  --lumi-sys-color--outline: #9a9b9c;
  --lumi-sys-color--stroke-default: #2d2f38;

  --lumi-sys-color--code-background: #141414;
  --lumi-sys-color--code-primary-text: #ffffff;
  --lumi-sys-color--code-blue-text: #4fa0ff;
  --lumi-sys-color--code-green-text: #60d673;
  --lumi-sys-color--code-grey-text: #808080;
  --lumi-sys-color--code-pink-text: #ff96da;
  --lumi-sys-color--code-purple-text: #969dff;
  --lumi-sys-color--code-red-text: #ff5a59;
  --lumi-sys-color--code-yellow-text: #ffdb0f;

  --lumi-sys-color--chart-series-1: #9dd2ff;
  --lumi-sys-color--chart-series-2: #96a7d6;
  --lumi-sys-color--chart-series-3: #50e389;
  --lumi-sys-color--chart-series-4: #c8f585;
  --lumi-sys-color--chart-series-5: #f5f2e6;
  --lumi-sys-color--chart-series-6: #dcd8c0;
  --lumi-sys-color--chart-series-7: #82c7ff;
  --lumi-sys-color--chart-series-8: #f5d77f;
  --lumi-sys-color--chart-series-9: #d9ceff;
  --lumi-sys-color--chart-series-10: #ffa6d7;
}

/* ============================================================
 * 3b. OS-LEVEL DARK FALLBACK  (prefers-color-scheme)
 *     A prior refactor introduced this stylesheet and moved the dark tokens onto
 *     :root[data-theme="dark"], but dropped the @media (prefers-color-scheme:
 *     dark) trigger that widgets previously carried in their own <style>.
 *     Inline widgets whose host sends no set-theme / data-theme message therefore
 *     stayed on the light --surface (#fdfcfc), rendering white in dark mode.
 *     Re-apply the dark values on OS dark; an explicit host data-theme="light"
 *     still opts back to light. Keep in sync with the :root[data-theme="dark"]
 *     block above.
 * ============================================================ */
@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) {
    --body-bg: #0f0f0f;
    --lumi-sys-elevation--level1: 0 0 20px 0 rgba(0, 0, 0, 0.28);
    --lumi-sys-elevation--level2: 0 0 20px 0 rgba(0, 0, 0, 0.40);

    --lumi-sys-color--surface: #0f0f0f;
    --lumi-sys-color--surface-dim: #141414;
    --lumi-sys-color--surface-bright: #1c1c1c;
    --lumi-sys-color--surface-background: #0f0f0f;
    --lumi-sys-color--surface-accent: #14204f;
    --lumi-sys-color--surface-container: #141414;
    --lumi-sys-color--surface-container-high: #1c1c1c;
    --lumi-sys-color--on-surface: #e0e0e0;
    --lumi-sys-color--on-surface-default: #e0e0e0;
    --lumi-sys-color--on-surface-variant: rgba(255, 255, 255, 0.55);
    --lumi-sys-color--on-surface-de-emphasis: rgba(255, 255, 255, 0.55);
    --lumi-sys-color--on-surface-low: rgba(255, 255, 255, 0.12);
    --lumi-sys-color--positive: #0ebc5f;
    --lumi-sys-color--positive-container: #002220;
    --lumi-sys-color--on-positive-container: #0ebc5f;
    --lumi-sys-color--error: #ff4c45;
    --lumi-sys-color--error-container: #3c0202;
    --lumi-sys-color--on-error-container: #ff4c45;
    --lumi-sys-color--accent: #1f3b9b;
    --lumi-sys-color--accent-container: #192967;
    --lumi-sys-color--accent-fixed: #3186ff;
    --lumi-sys-color--primary: #9dd2ff;
    --lumi-sys-color--on-primary: #192967;
    --lumi-sys-color--black: #000000;
    --lumi-sys-color--white: #ffffff;
    --lumi-sys-color--outline: #9a9b9c;
    --lumi-sys-color--stroke-default: #2d2f38;

    --lumi-sys-color--code-background: #141414;
    --lumi-sys-color--code-primary-text: #ffffff;
    --lumi-sys-color--code-blue-text: #4fa0ff;
    --lumi-sys-color--code-green-text: #60d673;
    --lumi-sys-color--code-grey-text: #808080;
    --lumi-sys-color--code-pink-text: #ff96da;
    --lumi-sys-color--code-purple-text: #969dff;
    --lumi-sys-color--code-red-text: #ff5a59;
    --lumi-sys-color--code-yellow-text: #ffdb0f;

    --lumi-sys-color--chart-series-1: #9dd2ff;
    --lumi-sys-color--chart-series-2: #96a7d6;
    --lumi-sys-color--chart-series-3: #50e389;
    --lumi-sys-color--chart-series-4: #c8f585;
    --lumi-sys-color--chart-series-5: #f5f2e6;
    --lumi-sys-color--chart-series-6: #dcd8c0;
    --lumi-sys-color--chart-series-7: #82c7ff;
    --lumi-sys-color--chart-series-8: #f5d77f;
    --lumi-sys-color--chart-series-9: #d9ceff;
    --lumi-sys-color--chart-series-10: #ffa6d7;
  }
}

/* Dark mode slider thumb override */
:root[data-theme="dark"] .lumi-slider::-webkit-slider-thumb,
body.dark-mode .lumi-slider::-webkit-slider-thumb {
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='32' height='32' viewBox='0 0 32 32'%3E%3Crect x='14' y='6' width='4' height='20' rx='2' fill='%23ffffff'/%3E%3C/svg%3E");
}

@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) .lumi-slider::-webkit-slider-thumb {
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='32' height='32' viewBox='0 0 32 32'%3E%3Crect x='14' y='6' width='4' height='20' rx='2' fill='%23ffffff'/%3E%3C/svg%3E");
  }
}

/* ============================================================
 * 4. SHORT DIAGRAM / CHART ALIASES
 *    Legacy diagram.md and chart.jinja2 reference short names such as
 *    --surface, --on-surface, --chart-1..10, --primary, --r-full. These MUST
 *    resolve to the canonical --lumi-sys-color--* tokens (which flip in dark
 *    mode) — otherwise every diagram var() falls back to black (historical
 *    mass-regression bug #4). Light-hex fallbacks are a last resort only.
 * ============================================================ */
:root {
  /* surfaces */
  --surface: var(--lumi-sys-color--surface, #fdfcfc);
  --surface-dim: var(--lumi-sys-color--surface-dim, #f2f0f0);
  --surface-bright: var(--lumi-sys-color--surface-bright, #ffffff);
  --surface-container: var(--lumi-sys-color--surface-container, #f2f0f0);
  --surface-container-high: var(--lumi-sys-color--surface-container-high, #e6e6e6);
  --surface-container-lowest: var(--lumi-sys-color--surface, #ffffff);
  --surface-accent: var(--lumi-sys-color--surface-accent, #9dd2ff);
  /* foreground */
  --on-surface: var(--lumi-sys-color--on-surface, #000000);
  --on-surface-variant: var(--lumi-sys-color--on-surface-variant, rgba(0, 0, 0, 0.55));
  --on-surface-low: var(--lumi-sys-color--on-surface-low, rgba(0, 0, 0, 0.08));
  /* accents / brand */
  --primary: var(--lumi-sys-color--primary, #3186ff);
  --primary-container: var(--lumi-sys-color--accent-container, #dcf1ff);
  --accent: var(--lumi-sys-color--accent, #9dd2ff);
  --accent-container: var(--lumi-sys-color--accent-container, #dcf1ff);
  --accent-fixed: var(--lumi-sys-color--accent-fixed, #3186ff);
  /* status */
  --positive: var(--lumi-sys-color--positive, #008052);
  --positive-container: var(--lumi-sys-color--positive-container, #daf9d4);
  --error: var(--lumi-sys-color--error, #de2d29);
  --error-container: var(--lumi-sys-color--error-container, #ffdeec);
  /* structure */
  --outline: var(--lumi-sys-color--outline, #727676);
  --stroke-default: var(--lumi-sys-color--stroke-default, #e3e3e3);
  /* chart series 1..10 */
  --chart-1: var(--lumi-sys-color--chart-series-1, #2575fc);
  --chart-2: var(--lumi-sys-color--chart-series-2, #5b6e9e);
  --chart-3: var(--lumi-sys-color--chart-series-3, #228a49);
  --chart-4: var(--lumi-sys-color--chart-series-4, #62991b);
  --chart-5: var(--lumi-sys-color--chart-series-5, #1e564d);
  --chart-6: var(--lumi-sys-color--chart-series-6, #526a45);
  --chart-7: var(--lumi-sys-color--chart-series-7, #2780c4);
  --chart-8: var(--lumi-sys-color--chart-series-8, #997112);
  --chart-9: var(--lumi-sys-color--chart-series-9, #705ec2);
  --chart-10: var(--lumi-sys-color--chart-series-10, #c84288);
  /* code palette */
  --code-background: var(--lumi-sys-color--code-background, #000000);
  --code-primary-text: var(--lumi-sys-color--code-primary-text, #ffffff);
  /* spacing shorthands */
  --spacing-xs: var(--lumi-sys-spacing--xs, 4px);
  --spacing-s: var(--lumi-sys-spacing--s, 8px);
  --spacing-m: var(--lumi-sys-spacing--m, 12px);
  --spacing-l: var(--lumi-sys-spacing--l, 16px);
  --spacing-xl: var(--lumi-sys-spacing--xl, 20px);
  /* radius shorthands */
  --r-container: var(--lumi-sys-shape--xl-max, 40px);
  --r-xl: var(--lumi-sys-shape--xl, 28px);
  --r-l: var(--lumi-sys-shape--large-max, 24px);
  --r-m: var(--lumi-sys-shape--large, 16px);
  --r-s: var(--lumi-sys-shape--small, 8px);
  --r-full: var(--lumi-sys-shape--full, 999px);
}

/* ============================================================
 * 5. IN-SCOPE PRE-BAKED COMPONENT CLASSES
 *    Interactive controls + simple display components only (Decision D5).
 *    Complex components (timeline, sequence, stepper, pros-cons, hero, HUD,
 *    hotspot, media grid) are intentionally excluded.
 * ============================================================ */

/* Global font rendering quality + themed surface backdrop.
 * background/color MUST be set here (SSoT) so the widget backdrop follows the
 * light/dark surface token deterministically. Without this, a widget whose
 * model-generated markup forgets `background: var(--surface)` on its root
 * container falls back to the browser-default white body, producing a broken
 * dark mode (light header/chart area behind a dark card). Regression source:
 * batch1 PB-A02 dark. */
*, *::before, *::after {
  box-sizing: border-box;
}

html, body {
  background: var(--body-bg, transparent) !important;
  color: var(--on-surface) !important;
  /* Auto-resizing iframe: content grows the frame, never scrolls the document.
   * Model widgets already emit this; declared here as the SSoT default. */
  overflow-y: hidden;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-optical-sizing: auto;
  text-rendering: optimizeLegibility;
}

/* ============================================================
 * SCROLLBAR DISCIPLINE (single source of truth)
 *   Long lists/cards flow and let the iframe auto-resize (see the C++
 *   NeutralizeInnerScroll pass, which removes accidental tiny scroll boxes).
 *   For LEGITIMATE overflow that remains (wide tables, code, pan-containers,
 *   large >=240px viewports) render a slim, theme-aware scrollbar.
 *   One token carries the correct light/dark contrast (the auto-flipped
 *   stroke token is too dark on #0f0f0f), referenced once = SSoT.
 * ============================================================ */
:root { --lumi-scrollbar-thumb: rgba(0, 0, 0, 0.20); }
:root[data-theme="dark"], body.dark-mode { --lumi-scrollbar-thumb: rgba(255, 255, 255, 0.20); }
@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) { --lumi-scrollbar-thumb: rgba(255, 255, 255, 0.20); }
}
* {
  scrollbar-width: thin;
  scrollbar-color: var(--lumi-scrollbar-thumb) transparent;
}
::-webkit-scrollbar { width: 6px; height: 6px; }
::-webkit-scrollbar-track { background: transparent; }
::-webkit-scrollbar-thumb {
  background-color: var(--lumi-scrollbar-thumb);
  border-radius: var(--lumi-sys-shape--full, 999px);
}

/* --- Buttons --- */
.lumi-btn { display: inline-flex; align-items: center; justify-content: center; gap: var(--lumi-sys-spacing--s, 8px); min-height: 48px; padding: 0px 24px; font-family: var(--ff-sans, 'Google Sans Flex', 'Google Sans', sans-serif); font-size: 15px; font-weight: 400; line-height: 20px; border-radius: var(--lumi-sys-shape--full, 999px); border-width: medium; border-style: none; border-color: currentcolor; border-image: none; cursor: pointer; user-select: none; transition: background-color 0.15s, color 0.15s, border-color 0.15s, box-shadow 0.15s, transform 0.1s; text-decoration: none; box-sizing: border-box; white-space: nowrap; }
.lumi-btn:active, .lumi-btn.is-pressed { transform: scale(0.98); }
.lumi-btn--accent, .lumi-btn--primary { background-color: var(--lumi-sys-color--accent, #9dd2ff); color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-btn--accent:hover, .lumi-btn--primary:hover { background-color: var(--lumi-sys-color--accent-container, #dcf1ff); }
.lumi-btn--tonal { background-color: var(--lumi-sys-color--surface-dim, #f2f0f0); color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-btn--tonal:hover { background-color: var(--lumi-sys-color--surface-bright, #ffffff); }
.lumi-btn--bright { background-color: var(--lumi-sys-color--surface-bright, #ffffff); color: var(--lumi-sys-color--on-surface-default, #000000); border-width: medium; border-style: none; border-color: currentcolor; border-image: none; box-shadow: none; }
.lumi-btn--bright:hover { background-color: var(--lumi-sys-color--surface-dim, #f2f0f0); }
.lumi-btn--ghost, .lumi-btn--on-surface { background-color: var(--lumi-sys-color--on-surface-low, rgba(0, 0, 0, 0.04)); color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-btn--ghost:hover, .lumi-btn--on-surface:hover { background-color: var(--lumi-sys-color--on-surface-low, rgba(0, 0, 0, 0.08)); }
.lumi-btn--translucent { background-color: rgba(255, 255, 255, 0.25); backdrop-filter: blur(12px); color: var(--lumi-sys-color--on-surface-default, #000000); border-color: rgba(255, 255, 255, 0.3); }
.lumi-btn--translucent:hover { background-color: rgba(255, 255, 255, 0.35); }
.lumi-btn--small { min-height: 36px; padding: 0px 16px; font-size: 13px; line-height: 18px; gap: var(--lumi-sys-spacing--xs, 4px); }
.lumi-btn--xsmall { min-height: 24px; padding: 0px 10px; font-size: 11px; line-height: 16px; gap: 4px; }
/* Toggleable Buttons */
.lumi-btn.is-selected,
.lumi-btn.selected,
.lumi-btn[aria-pressed="true"] {
  background-color: var(--lumi-sys-color--accent-container, #dcf1ff);
  color: var(--lumi-sys-color--on-surface-default, #000000);
  border: none;
  box-shadow: none;
}
.lumi-btn.is-selected:hover,
.lumi-btn.selected:hover,
.lumi-btn[aria-pressed="true"]:hover {
  background-color: var(--lumi-sys-color--accent, #9dd2ff);
  color: var(--lumi-sys-color--on-surface-default, #000000);
}
.lumi-btn.is-selected:active,
.lumi-btn.selected:active,
.lumi-btn[aria-pressed="true"]:active {
  transform: scale(0.98);
}

:root[data-theme="dark"] .lumi-btn.is-selected,
:root[data-theme="dark"] .lumi-btn.selected,
:root[data-theme="dark"] .lumi-btn[aria-pressed="true"],
body.dark-mode .lumi-btn.is-selected,
body.dark-mode .lumi-btn.selected,
body.dark-mode .lumi-btn[aria-pressed="true"],
.lumi-theme-dark .lumi-btn.is-selected,
.lumi-theme-dark .lumi-btn.selected,
.lumi-theme-dark .lumi-btn[aria-pressed="true"] {
  background-color: var(--lumi-sys-color--accent-container, #004a77);
  color: var(--lumi-sys-color--on-surface-default, #ffffff);
  border: none;
  box-shadow: none;
}
:root[data-theme="dark"] .lumi-btn.is-selected:hover,
:root[data-theme="dark"] .lumi-btn.selected:hover,
:root[data-theme="dark"] .lumi-btn[aria-pressed="true"]:hover,
body.dark-mode .lumi-btn.is-selected:hover,
body.dark-mode .lumi-btn.selected:hover,
body.dark-mode .lumi-btn[aria-pressed="true"]:hover,
.lumi-theme-dark .lumi-btn.is-selected:hover,
.lumi-theme-dark .lumi-btn.selected:hover,
.lumi-theme-dark .lumi-btn[aria-pressed="true"]:hover {
  background-color: var(--lumi-sys-color--accent, #9dd2ff);
  color: #000000;
}

/* --- Switch --- */
.lumi-switch { display: inline-flex; align-items: center; gap: var(--lumi-sys-spacing--s, 8px); cursor: pointer; font-family: var(--ff-sans, 'Google Sans Flex', 'Google Sans', sans-serif); font-size: 15px; color: var(--lumi-sys-color--on-surface-default, #000000); user-select: none; }
.lumi-switch input[type="checkbox"] { position: absolute; opacity: 0; width: 0px; height: 0px; pointer-events: none; }
.lumi-switch__track { position: relative; display: inline-flex; align-items: center; width: 52px; height: 32px; background-color: var(--lumi-sys-color--surface-dim, #f2f0f0); border: 2px solid var(--lumi-sys-color--stroke-default, rgba(0, 0, 0, 0.12)); border-radius: var(--lumi-sys-shape--full, 999px); transition: background-color 0.2s, border-color 0.2s; flex-shrink: 0; box-sizing: border-box; }
.lumi-switch__thumb, .lumi-switch__track::after { content: ""; position: absolute; top: 50%; left: 6px; transform: translateY(-50%); width: 16px; height: 16px; border-radius: 50%; background-color: var(--lumi-sys-color--on-surface-variant, #757575); transition: 0.2s cubic-bezier(0.4, 0, 0.2, 1); display: flex; align-items: center; justify-content: center; box-sizing: border-box; }
.lumi-switch input[type="checkbox"]:checked + .lumi-switch__track { background-color: var(--lumi-sys-color--accent-fixed, #3186ff); border-color: transparent; }
.lumi-switch input[type="checkbox"]:checked + .lumi-switch__track .lumi-switch__thumb, .lumi-switch input[type="checkbox"]:checked + .lumi-switch__track::after { left: 22px; width: 24px; height: 24px; background-color: rgb(255, 255, 255); }
.lumi-switch input[type="checkbox"]:disabled + .lumi-switch__track { opacity: var(--lumi-sys-opacity-state--disabled, 0.38); cursor: not-allowed; }
.lumi-switch--small .lumi-switch__track, .lumi-switch--mini .lumi-switch__track { width: 32px; height: 20px; }
.lumi-switch--small .lumi-switch__thumb, .lumi-switch--small .lumi-switch__track::after, .lumi-switch--mini .lumi-switch__thumb, .lumi-switch--mini .lumi-switch__track::after { width: 12px; height: 12px; left: 2px; }
.lumi-switch--small input[type="checkbox"]:checked + .lumi-switch__track .lumi-switch__thumb, .lumi-switch--small input[type="checkbox"]:checked + .lumi-switch__track::after, .lumi-switch--mini input[type="checkbox"]:checked + .lumi-switch__track .lumi-switch__thumb, .lumi-switch--mini input[type="checkbox"]:checked + .lumi-switch__track::after { left: 12px; width: 16px; height: 16px; }

/* --- Checkbox --- */
.lumi-checkbox-label { display: inline-flex; align-items: center; gap: var(--lumi-sys-spacing--s, 8px); cursor: pointer; font-family: var(--ff-sans, 'Google Sans Flex', 'Google Sans', sans-serif); font-size: 15px; color: var(--lumi-sys-color--on-surface-default, #000000); user-select: none; }
.lumi-checkbox-label input[type="checkbox"] { position: absolute; opacity: 0; width: 0px; height: 0px; pointer-events: none; }
.lumi-checkbox { position: relative; width: 24px; height: 24px; border-radius: var(--lumi-sys-shape--small, 8px); border: 2px solid var(--lumi-sys-color--on-surface-variant, rgba(0, 0, 0, 0.55)); background-color: transparent; transition: background-color 0.15s, border-color 0.15s, box-shadow 0.15s; display: flex; align-items: center; justify-content: center; flex-shrink: 0; box-sizing: border-box; }
.lumi-checkbox-label:hover .lumi-checkbox { background-color: var(--lumi-sys-color--on-surface-low, rgba(0, 0, 0, 0.04)); border-color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-checkbox-label input[type="checkbox"]:checked ~ .lumi-checkbox, .lumi-checkbox-label input[type="checkbox"]:indeterminate ~ .lumi-checkbox, .lumi-checkbox.is-indeterminate { background-color: var(--lumi-sys-color--on-surface-default, #000000); border-color: transparent; }
.lumi-checkbox .lumi-checkmark { font-size: 18px; line-height: 1; color: var(--lumi-sys-color--surface, #ffffff); fill: var(--lumi-sys-color--surface, #ffffff); display: none; user-select: none; }
.lumi-checkbox-label input[type="checkbox"]:checked ~ .lumi-checkbox .lumi-checkmark, .lumi-checkbox-label input[type="checkbox"]:checked ~ .lumi-checkbox .lumi-checkbox__check { display: block; }
.lumi-checkbox-label input[type="checkbox"]:indeterminate ~ .lumi-checkbox .lumi-checkbox__indeterminate, .lumi-checkbox.is-indeterminate .lumi-checkbox__indeterminate { display: block; }
.lumi-checkbox-label input[type="checkbox"]:disabled ~ .lumi-checkbox, .lumi-checkbox-label input[type="checkbox"]:disabled ~ span { opacity: var(--lumi-sys-opacity-state--disabled, 0.38); cursor: not-allowed; }

/* --- Slider --- */
.lumi-slider-container { display: flex; align-items: center; gap: var(--lumi-sys-spacing--m, 16px); width: 100%; }
.lumi-slider-row { display: flex; flex-direction: column; gap: var(--lumi-sys-spacing--xs, 4px); width: 100%; }
.lumi-slider-label { font-family: var(--ff-sans, 'Google Sans Flex', 'Google Sans', sans-serif); font-size: 15px; font-weight: 400; color: var(--lumi-sys-color--on-surface-default, #000000); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
.lumi-slider { appearance: none; width: calc(100% + 28px); margin-left: -14px; margin-right: -14px; height: 40px; background: transparent; cursor: pointer; box-sizing: border-box; }
.lumi-slider:focus { outline: none; }
.lumi-slider::-webkit-slider-runnable-track { height: 4px; --thumb-center: calc(14px + (100% - 28px) * (var(--progress, 50%) / 100%)); --active-end: calc(var(--thumb-center) - 8px + (var(--progress, 50%) / 100%) * 6px); background-image: radial-gradient(circle at calc(100% - 18px) center, var(--lumi-sys-color--on-surface-variant, #757575) 2px, transparent 2.5px), linear-gradient( to right, transparent 0, transparent 14px, var(--lumi-sys-color--on-surface-default, #000000) 14px, var(--lumi-sys-color--on-surface-default, #000000) var(--active-end), transparent var(--active-end), transparent calc(var(--thumb-center) + 8px), var(--lumi-sys-color--stroke-default, rgba(0, 0, 0, 0.12)) calc(var(--thumb-center) + 8px), var(--lumi-sys-color--stroke-default, rgba(0, 0, 0, 0.12)) calc(100% - 16px), transparent calc(100% - 16px), transparent 100% ); border-radius: var(--lumi-sys-shape--full, 999px); border-width: medium; border-style: none; border-color: currentcolor; border-image: none; }
.lumi-slider::-webkit-slider-thumb { appearance: none; width: 32px; height: 32px; border-radius: 50%; background-color: transparent; background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='32' height='32' viewBox='0 0 32 32'%3E%3Crect x='14' y='6' width='4' height='20' rx='2' fill='%23000000'/%3E%3C/svg%3E"); background-size: 32px 32px; background-repeat: no-repeat; background-position: center center; border-width: medium; border-style: none; border-color: currentcolor; border-image: none; box-sizing: border-box; margin-top: -14px; cursor: pointer; transition: background-color 0.15s; }
.lumi-slider:hover::-webkit-slider-thumb { background-color: var(--lumi-sys-color--on-surface-low, rgba(0, 0, 0, 0.08)); }
.lumi-slider:active::-webkit-slider-thumb { background-color: var(--lumi-sys-color--on-surface-low, rgba(0, 0, 0, 0.12)); }
.lumi-slider:disabled { opacity: var(--lumi-sys-opacity-state--disabled, 0.38); cursor: not-allowed; }
.lumi-slider:disabled::-webkit-slider-thumb { cursor: not-allowed; box-shadow: none; }
.lumi-slider-value { display: flex; align-items: center; justify-content: center; min-width: 64px; height: 40px; padding: 0px 12px; background-color: var(--lumi-sys-color--surface-dim, #f2f0f0); border-radius: var(--lumi-sys-shape--medium, 16px); font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 15px; line-height: 20px; font-weight: 540; font-variation-settings: "wght" 540, "wdth" 92, "opsz" 15; font-variant-numeric: tabular-nums; color: var(--lumi-sys-color--on-surface-default, #000000); flex-shrink: 0; box-sizing: border-box; }

/* --- Text input --- */
.lumi-input-group { display: flex; flex-direction: column; gap: var(--lumi-sys-spacing--xs, 4px); width: 100%; }
.lumi-input-label { font-family: var(--ff-sans, 'Google Sans Flex', 'Google Sans', sans-serif); font-size: 14px; font-weight: 500; line-height: 20px; color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-input { appearance: none; width: 100%; min-height: 48px; padding: 0px 16px; font-family: var(--ff-sans, 'Google Sans Flex', 'Google Sans', sans-serif); font-size: 15px; font-weight: 400; line-height: 22px; color: var(--lumi-sys-color--on-surface-default, #000000); background-color: var(--lumi-sys-color--surface-bright, #ffffff); border: 1px solid var(--lumi-sys-color--stroke-default, rgba(0, 0, 0, 0.12)); border-radius: var(--lumi-sys-shape--large, 16px); background-clip: padding-box; outline: none; box-sizing: border-box; transition: border-color 0.15s, box-shadow 0.15s, background-color 0.15s; }
.lumi-input::placeholder { color: var(--lumi-sys-color--on-surface-variant, rgba(0, 0, 0, 0.55)); opacity: 0.7; }
.lumi-input:hover { border-color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-input:focus, .lumi-input:focus-visible { border-color: var(--lumi-sys-color--accent-fixed, #3186ff); box-shadow: 0 0 0 2px var(--lumi-sys-color--accent-container, rgba(49, 134, 255, 0.25)); }
textarea.lumi-input, .lumi-input--area { min-height: 100px; padding: 12px 16px; resize: vertical; line-height: 22px; }
.lumi-input.is-error, .lumi-input-group.is-error .lumi-input { border-color: var(--lumi-sys-color--error, #ff4c45); }
.lumi-input-helper { font-family: var(--ff-sans, 'Google Sans Flex', 'Google Sans', sans-serif); font-size: 12px; line-height: 16px; color: var(--lumi-sys-color--on-surface-variant, rgba(0, 0, 0, 0.55)); }
.lumi-input-group.is-error .lumi-input-helper, .lumi-input-helper--error { color: var(--lumi-sys-color--error, #ff4c45); }
.lumi-input:disabled, .lumi-input.is-disabled { opacity: var(--lumi-sys-opacity-state--disabled, 0.38); background-color: var(--lumi-sys-color--surface-dim, #f2f0f0); cursor: not-allowed; }

/* --- Focus ring --- */
:focus-visible { outline: 2px solid var(--lumi-sys-color--on-surface-default, #000000) !important; outline-offset: 2px !important; box-shadow: none !important; }
.lumi-btn:focus-visible, .lumi-switch input[type="checkbox"]:focus-visible + .lumi-switch__track, .lumi-checkbox-label input[type="checkbox"]:focus-visible ~ .lumi-checkbox, .lumi-slider:focus-visible::-webkit-slider-thumb, .lumi-input:focus-visible { outline: 2px solid var(--lumi-sys-color--on-surface-default, #000000); outline-offset: 2px; box-shadow: none; }

/* --- Typography: Display / Headline / Body / Label --- */
.lumi-display-l { font-family: var(--lumi-sys-typography-type-scale--display-l-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--display-l-font-size, 2.625rem); line-height: var(--lumi-sys-typography-type-scale--display-l-line-height, 3rem); letter-spacing: var(--lumi-sys-typography-type-scale--display-l-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--display-l-font-weight, 280); font-variation-settings: "wght" 280, "wdth" 100, "opsz" 42, "ROND" 100; }
.lumi-display-l-emphasized { font-family: var(--lumi-sys-typography-type-scale--display-l-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--display-l-font-size, 2.625rem); line-height: var(--lumi-sys-typography-type-scale--display-l-line-height, 3rem); letter-spacing: var(--lumi-sys-typography-type-scale--display-l-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--display-l-font-weight, 280); font-variation-settings: "wght" 280, "wdth" 100, "opsz" 42, "ROND" 100; }
.lumi-display-m { font-family: var(--lumi-sys-typography-type-scale--display-m-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--display-m-font-size, 2.25rem); line-height: var(--lumi-sys-typography-type-scale--display-m-line-height, 2.75rem); letter-spacing: var(--lumi-sys-typography-type-scale--display-m-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--display-m-font-weight, 320); font-variation-settings: "wght" 320, "wdth" 100, "opsz" 36, "ROND" 100; }
.lumi-display-m-emphasized { font-family: var(--lumi-sys-typography-type-scale--display-m-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--display-m-font-size, 2.25rem); line-height: var(--lumi-sys-typography-type-scale--display-m-line-height, 2.75rem); letter-spacing: var(--lumi-sys-typography-type-scale--display-m-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--display-m-font-weight, 320); font-variation-settings: "wght" 320, "wdth" 100, "opsz" 36, "ROND" 100; }
.lumi-display-s { font-family: var(--lumi-sys-typography-type-scale--display-s-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--display-s-font-size, 2rem); line-height: var(--lumi-sys-typography-type-scale--display-s-line-height, 2.375rem); letter-spacing: var(--lumi-sys-typography-type-scale--display-s-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--display-s-font-weight, 360); font-variation-settings: "wght" 360, "wdth" 100, "opsz" 32, "ROND" 100; }
.lumi-display-s-emphasized { font-family: var(--lumi-sys-typography-type-scale--display-s-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--display-s-font-size, 2rem); line-height: var(--lumi-sys-typography-type-scale--display-s-line-height, 2.375rem); letter-spacing: var(--lumi-sys-typography-type-scale--display-s-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--display-s-font-weight, 360); font-variation-settings: "wght" 360, "wdth" 100, "opsz" 32, "ROND" 100; }
.lumi-headline-l { font-family: var(--lumi-sys-typography-type-scale--headline-l-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--headline-l-font-size, 1.75rem); line-height: var(--lumi-sys-typography-type-scale--headline-l-line-height, 2.25rem); letter-spacing: var(--lumi-sys-typography-type-scale--headline-l-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--headline-l-font-weight, 350); font-variation-settings: "wght" 350, "wdth" 100, "opsz" 28, "ROND" 20; }
.lumi-headline-l-emphasized { font-family: var(--lumi-sys-typography-type-scale--headline-l-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--headline-l-font-size, 1.75rem); line-height: var(--lumi-sys-typography-type-scale--headline-l-line-height, 2.25rem); letter-spacing: var(--lumi-sys-typography-type-scale--headline-l-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--headline-l-font-weight, 350); font-variation-settings: "wght" 350, "wdth" 100, "opsz" 28, "ROND" 20; }
.lumi-headline-m { font-family: var(--lumi-sys-typography-type-scale--headline-m-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--headline-m-font-size, 1.5rem); line-height: var(--lumi-sys-typography-type-scale--headline-m-line-height, 1.75rem); letter-spacing: var(--lumi-sys-typography-type-scale--headline-m-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--headline-m-font-weight, 380); font-variation-settings: "wght" 380, "wdth" 100, "opsz" 24, "ROND" 20; }
.lumi-headline-m-emphasized { font-family: var(--lumi-sys-typography-type-scale--headline-m-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--headline-m-font-size, 1.5rem); line-height: var(--lumi-sys-typography-type-scale--headline-m-line-height, 1.75rem); letter-spacing: var(--lumi-sys-typography-type-scale--headline-m-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--headline-m-font-weight, 380); font-variation-settings: "wght" 380, "wdth" 100, "opsz" 24, "ROND" 20; }
.lumi-headline-s { font-family: var(--lumi-sys-typography-type-scale--headline-s-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--headline-s-font-size, 1.25rem); line-height: var(--lumi-sys-typography-type-scale--headline-s-line-height, 1.5rem); letter-spacing: var(--lumi-sys-typography-type-scale--headline-s-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--headline-s-font-weight, 470); font-variation-settings: "wght" 470, "wdth" 94, "opsz" 20, "ROND" 20; }
.lumi-headline-s-emphasized { font-family: var(--lumi-sys-typography-type-scale--headline-s-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--headline-s-font-size, 1.25rem); line-height: var(--lumi-sys-typography-type-scale--headline-s-line-height, 1.5rem); letter-spacing: var(--lumi-sys-typography-type-scale--headline-s-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--headline-s-font-weight, 470); font-variation-settings: "wght" 470, "wdth" 94, "opsz" 20, "ROND" 20; }
.lumi-body-l { font-family: var(--lumi-sys-typography-type-scale--body-l-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--body-l-font-size, 1.0625rem); line-height: var(--lumi-sys-typography-type-scale--body-l-line-height, 1.5rem); letter-spacing: var(--lumi-sys-typography-type-scale--body-l-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--body-l-font-weight, 400); font-variation-settings: "wght" 400, "wdth" 92, "opsz" 17; }
.lumi-body-l-emphasized { font-family: var(--lumi-sys-typography-type-scale--body-l-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--body-l-font-size, 1.0625rem); line-height: var(--lumi-sys-typography-type-scale--body-l-line-height, 1.5rem); letter-spacing: var(--lumi-sys-typography-type-scale--body-l-font-tracking, 0rem); font-weight: 540; font-variation-settings: "wght" 540, "wdth" 92, "opsz" 17; font-variant-numeric: tabular-nums; }
.lumi-body-m { font-family: var(--lumi-sys-typography-type-scale--body-m-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--body-m-font-size, 0.9375rem); line-height: var(--lumi-sys-typography-type-scale--body-m-line-height, 1.25rem); letter-spacing: var(--lumi-sys-typography-type-scale--body-m-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--body-m-font-weight, 400); font-variation-settings: "wght" 400, "wdth" 92, "opsz" 15; }
.lumi-body-m-emphasized { font-family: var(--lumi-sys-typography-type-scale--body-m-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--body-m-font-size, 0.9375rem); line-height: var(--lumi-sys-typography-type-scale--body-m-line-height, 1.25rem); letter-spacing: var(--lumi-sys-typography-type-scale--body-m-font-tracking, 0rem); font-weight: 540; font-variation-settings: "wght" 540, "wdth" 92, "opsz" 15; font-variant-numeric: tabular-nums; }
.lumi-body-s { font-family: var(--lumi-sys-typography-type-scale--body-s-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--body-s-font-size, 0.8125rem); line-height: var(--lumi-sys-typography-type-scale--body-s-line-height, 1.0625rem); letter-spacing: var(--lumi-sys-typography-type-scale--body-s-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--body-s-font-weight, 400); font-variation-settings: "wght" 400, "wdth" 92, "opsz" 13; }
.lumi-body-s-emphasized { font-family: var(--lumi-sys-typography-type-scale--body-s-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--body-s-font-size, 0.8125rem); line-height: var(--lumi-sys-typography-type-scale--body-s-line-height, 1.0625rem); letter-spacing: var(--lumi-sys-typography-type-scale--body-s-font-tracking, 0rem); font-weight: 540; font-variation-settings: "wght" 540, "wdth" 92, "opsz" 13; font-variant-numeric: tabular-nums; }
.lumi-label-l { font-family: var(--lumi-sys-typography-type-scale--label-l-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--label-l-font-size, 1.0625rem); line-height: var(--lumi-sys-typography-type-scale--label-l-line-height, 1.5rem); letter-spacing: var(--lumi-sys-typography-type-scale--label-l-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--label-l-font-weight, 370); font-variation-settings: "wght" 370, "wdth" 92, "opsz" 17; }
.lumi-label-l-emphasized { font-family: var(--lumi-sys-typography-type-scale--label-l-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--label-l-font-size, 1.0625rem); line-height: var(--lumi-sys-typography-type-scale--label-l-line-height, 1.5rem); letter-spacing: var(--lumi-sys-typography-type-scale--label-l-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--label-l-font-weight, 370); font-variation-settings: "wght" 370, "wdth" 92, "opsz" 17; }
.lumi-label-m { font-family: var(--lumi-sys-typography-type-scale--label-m-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--label-m-font-size, 0.9375rem); line-height: var(--lumi-sys-typography-type-scale--label-m-line-height, 1.25rem); letter-spacing: var(--lumi-sys-typography-type-scale--label-m-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--label-m-font-weight, 370); font-variation-settings: "wght" 370, "wdth" 92, "opsz" 15; }
.lumi-label-m-emphasized { font-family: var(--lumi-sys-typography-type-scale--label-m-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--label-m-font-size, 0.9375rem); line-height: var(--lumi-sys-typography-type-scale--label-m-line-height, 1.25rem); letter-spacing: var(--lumi-sys-typography-type-scale--label-m-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--label-m-font-weight, 370); font-variation-settings: "wght" 370, "wdth" 92, "opsz" 15; }
.lumi-label-s { font-family: var(--lumi-sys-typography-type-scale--label-s-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--label-s-font-size, 0.8125rem); line-height: var(--lumi-sys-typography-type-scale--label-s-line-height, 1.25rem); letter-spacing: var(--lumi-sys-typography-type-scale--label-s-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--label-s-font-weight, 370); font-variation-settings: "wght" 370, "wdth" 92, "opsz" 13; }
.lumi-label-s-emphasized { font-family: var(--lumi-sys-typography-type-scale--label-s-font-name, 'Google Sans Flex', sans-serif); font-size: var(--lumi-sys-typography-type-scale--label-s-font-size, 0.8125rem); line-height: var(--lumi-sys-typography-type-scale--label-s-line-height, 1.25rem); letter-spacing: var(--lumi-sys-typography-type-scale--label-s-font-tracking, 0rem); font-weight: var(--lumi-sys-typography-type-scale--label-s-font-weight, 370); font-variation-settings: "wght" 370, "wdth" 92, "opsz" 13; }

/* --- Typography: Monospace / Extended (Google Sans Code) --- */
.lumi-blockquote { font-family: var(--ff-mono, 'Google Sans Code', monospace); font-style: italic; font-size: 22px; line-height: 30px; font-weight: 300; font-variation-settings: "wght" 300, "opsz" 22, "MONO" 0; }
.lumi-takeaway { font-family: var(--ff-mono, 'Google Sans Code', monospace); font-style: italic; font-size: 17px; line-height: 24px; font-weight: 400; font-variation-settings: "wght" 400, "opsz" 17, "MONO" 0; }
.lumi-caption { font-family: var(--ff-mono, 'Google Sans Code', monospace); font-style: italic; font-size: 13px; line-height: 20px; font-weight: 400; font-variation-settings: "wght" 400, "opsz" 13, "MONO" 0; }
.lumi-code { font-family: var(--ff-mono, 'Google Sans Code', monospace); font-size: 15px; line-height: 20px; font-weight: 400; font-variation-settings: "wght" 400, "MONO" 1; }
.lumi-bullet { font-family: var(--ff-mono, 'Google Sans Code', monospace); font-size: 15px; line-height: 24px; font-weight: 650; font-variation-settings: "wght" 650, "MONO" 1; }

/* --- Cards & attribution --- */
.lumi-summary-card { padding: var(--lumi-sys-spacing--l, 16px); background-color: var(--lumi-sys-color--surface-bright, #ffffff); border-radius: var(--lumi-sys-shape--medium, 12px); color: var(--lumi-sys-color--on-surface-default, #000000); font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 15px; line-height: 20px; box-sizing: border-box; }
.lumi-link-card { display: flex; align-items: center; justify-content: space-between; padding: var(--lumi-sys-spacing--l, 16px); background-color: var(--lumi-sys-color--surface-bright, #ffffff); border-radius: var(--lumi-sys-shape--medium, 12px); text-decoration: none; color: var(--lumi-sys-color--on-surface-default, #000000); transition: background-color 0.15s; box-sizing: border-box; }
.lumi-link-card:hover { background-color: var(--lumi-sys-color--surface-container-high, #e6e6e6); }
.lumi-attribution-buffer { margin-top: var(--lumi-sys-spacing--xxl, 24px); font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 13px; color: var(--lumi-sys-color--on-surface-de-emphasis, rgba(0, 0, 0, 0.55)); }
.lumi-card { background-color: var(--lumi-sys-color--surface-bright, #ffffff); border-radius: var(--lumi-sys-shape--xl-max, 40px); padding: var(--lumi-sys-spacing--3xl, 28px); display: flex; flex-direction: column; gap: var(--lumi-sys-spacing--s, 8px); width: 100%; box-sizing: border-box; }
.lumi-card.is-prominent, .lumi-card--prominent, .lumi-card.surface-dim { background-color: var(--lumi-sys-color--surface-dim, #f2f0f0); }
.lumi-card--prominent .lumi-chip, .lumi-card.surface-dim .lumi-chip { background: var(--lumi-sys-color--surface-bright, #ffffff); }
.lumi-card-title { font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 20px; font-weight: 500; font-variation-settings: "wght" 470, "wdth" 94, "opsz" 20; color: var(--lumi-sys-color--on-surface, #000000); margin: 0px; }
.lumi-card-subtitle { font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 13px; font-weight: 400; font-variation-settings: "wght" 400, "wdth" 92, "opsz" 13; color: var(--lumi-sys-color--on-surface-variant, rgba(0, 0, 0, 0.55)); margin: 0px; }
.lumi-card-body { font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 15px; font-weight: 400; font-variation-settings: "wght" 400, "wdth" 92, "opsz" 15; color: var(--lumi-sys-color--on-surface, #000000); margin: var(--lumi-sys-spacing--xs, 4px) 0 0 0; }

/* --- Progress bar --- */
.lumi-progress-tracker { display: flex; flex-direction: column; gap: var(--lumi-sys-spacing--xs, 4px); width: 100%; }
.lumi-progress-bar { width: 100%; height: 8px; background-color: var(--lumi-sys-color--stroke-default, #e3e3e3); border-radius: var(--lumi-sys-shape--full, 999px); overflow: hidden; }
.lumi-progress-fill { height: 100%; background-color: var(--lumi-sys-color--accent-fixed, #3186ff); border-radius: var(--lumi-sys-shape--full, 999px); transition: width 0.3s; }

/* --- Accordion (card group variant) --- */
.lumi-accordion-group { display: flex; flex-direction: column; gap: var(--lumi-sys-spacing--s, 8px); }
.lumi-accordion-group .lumi-accordion-item { background-color: var(--lumi-sys-color--surface-container, #f2f0f0); border-radius: var(--lumi-sys-shape--medium, 12px); overflow: hidden; transition: background-color 0.15s; }
.lumi-accordion-group .lumi-accordion-header { padding: var(--lumi-sys-spacing--l, 16px); font-family: var(--ff-sans, sans-serif); font-size: 15px; font-weight: 540; cursor: pointer; user-select: none; display: flex; justify-content: space-between; align-items: center; color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-accordion-group .lumi-accordion-chevron { transition: transform 0.2s; font-size: 12px; }
.lumi-accordion-group .lumi-accordion-item.active .lumi-accordion-chevron { transform: rotate(180deg); }
.lumi-accordion-group .lumi-accordion-body { display: none; padding: 0 var(--lumi-sys-spacing--l, 16px) var(--lumi-sys-spacing--l, 16px) var(--lumi-sys-spacing--l, 16px); font-family: var(--ff-sans, sans-serif); font-size: 15px; color: var(--lumi-sys-color--on-surface-de-emphasis, rgba(0, 0, 0, 0.55)); line-height: 20px; }
.lumi-accordion-group .lumi-accordion-item.active .lumi-accordion-body { display: block; }

/* --- Accordion (borderless list variant) --- */
.lumi-accordion { display: flex; flex-direction: column; width: 100%; border-top: 1px solid var(--lumi-sys-color--on-surface-low, rgba(0, 0, 0, 0.08)); }
.lumi-accordion-item { display: flex; flex-direction: column; width: 100%; background: transparent; border-radius: 0px; border-bottom: 1px solid var(--lumi-sys-color--on-surface-low, rgba(0, 0, 0, 0.08)); }
.lumi-accordion-header { display: flex; justify-content: space-between; align-items: center; padding: var(--lumi-sys-spacing--xl, 20px) 0; cursor: pointer; user-select: none; }
.lumi-accordion-title { margin: 0px; color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-accordion-item.active .lumi-accordion-content { display: flex; flex-direction: column; gap: var(--lumi-sys-spacing--l, 16px); }
.lumi-accordion-content { display: none; padding-bottom: var(--lumi-sys-spacing--xxl, 24px); }
.lumi-accordion-field { display: flex; flex-direction: column; gap: var(--lumi-sys-spacing--xxs, 2px); }
.lumi-accordion-field-label { margin: 0px; color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-accordion-field-val { margin: 0px; color: var(--lumi-sys-color--on-surface-default, #000000); }

/* --- Segmented control --- */
.lumi-segmented-group { display: flex; background-color: var(--lumi-sys-color--surface-container, #f2f0f0); padding: 4px; border-radius: var(--lumi-sys-shape--full, 999px); gap: 4px; }
.lumi-segmented-btn { flex: 1 1 0%; padding: 8px 16px; border-width: medium; border-style: none; border-color: currentcolor; border-image: none; border-radius: var(--lumi-sys-shape--full, 999px); background-color: transparent; font-family: var(--ff-sans, sans-serif); font-size: 14px; font-weight: 510; cursor: pointer; color: var(--lumi-sys-color--on-surface-de-emphasis, rgba(0, 0, 0, 0.55)); transition: 0.2s; }
.lumi-segmented-btn.is-active, .lumi-segmented-btn.active, .lumi-segmented-btn.is-selected, .lumi-segmented-btn.selected, .lumi-segmented-btn[aria-selected="true"] { background-color: var(--lumi-sys-color--surface-bright, #ffffff); color: var(--lumi-sys-color--on-surface-default, #000000); box-shadow: var(--lumi-sys-elevation--level1); }

/* --- Tabs --- */
.lumi-tab-group { display: flex; flex-direction: column; gap: var(--lumi-sys-spacing--4xl, 36px); width: 100%; }
.lumi-tab-bar { display: flex; gap: var(--lumi-sys-spacing--l, 16px); padding-bottom: 0px; overflow-x: auto; scrollbar-width: none; }
.lumi-tab-bar::-webkit-scrollbar { display: none; }
.lumi-tab { height: 40px; padding: 0 var(--lumi-sys-spacing--xl, 20px); display: flex; align-items: center; justify-content: center; font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 17px; line-height: 24px; font-weight: 370; font-variation-settings: "wght" 370, "wdth" 92, "opsz" 17; color: var(--lumi-sys-color--on-surface-de-emphasis, rgba(0, 0, 0, 0.55)); background: transparent; border-width: medium; border-style: none; border-color: currentcolor; border-image: none; border-radius: var(--lumi-sys-shape--full, 999px); cursor: pointer; white-space: nowrap; transition: background-color 0.15s, color 0.15s; }
.lumi-tab:hover { color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-tab.active, .lumi-tab.is-active, .lumi-tab.is-selected, .lumi-tab.selected, .lumi-tab[aria-selected="true"] { background-color: var(--lumi-sys-color--surface-container-high, #f2f0f0); color: var(--lumi-sys-color--on-surface-default, #000000); font-weight: 510; font-variation-settings: "wght" 510, "wdth" 92, "opsz" 17; }
.lumi-tab-content { display: flex; flex-direction: column; gap: var(--lumi-sys-spacing--m, 12px); padding-top: 0px; padding-bottom: 0px; }
.lumi-tab-content .lumi-body-l-emphasized, .lumi-tab-content .lumi-headline-s { margin: 0px; }
.lumi-tab-content .lumi-body-l { margin: 0px; color: var(--lumi-sys-color--on-surface-default, #000000); }

/* --- Callout / pullquote --- */
.lumi-callout { display: flex; flex-direction: column; gap: var(--lumi-sys-spacing--xs, 4px); width: 100%; }
.lumi-callout .lumi-body-l-emphasized { margin: 0px; }
.lumi-pullquote { display: flex; gap: var(--lumi-sys-spacing--xl, 20px); width: 100%; margin: 0px; }
.lumi-pullquote-mark { width: 30px; height: 22px; flex-shrink: 0; margin-top: 4px; color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-pullquote-body { display: flex; flex-direction: column; gap: var(--lumi-sys-spacing--l, 16px); flex: 1 1 0%; min-width: 0px; }
p.lumi-pullquote-text, .lumi-pullquote-text { font-family: var(--ff-mono, 'Google Sans Code', monospace); font-style: italic; font-weight: 300; font-variation-settings: "wght" 300, "opsz" 22, "MONO" 0; color: var(--lumi-sys-color--on-surface-default, #000000); margin: 0px; font-size: 22px !important; line-height: 30px !important; }
.lumi-pullquote-cite { display: flex; flex-direction: column; font-style: normal; }
.lumi-pullquote-cite .lumi-de-emphasis { color: var(--lumi-sys-color--on-surface-de-emphasis, rgba(0, 0, 0, 0.55)); }

/* --- Data table (simple) --- */
.lumi-data-table-container { width: 100%; overflow-x: auto; border-radius: var(--lumi-sys-shape--medium, 12px); border: 1px solid var(--lumi-sys-color--stroke-default, rgba(0, 0, 0, 0.12)); }
.lumi-data-table { width: 100%; border-collapse: collapse; font-family: var(--ff-sans, sans-serif); font-size: 14px; text-align: left; }
.lumi-data-table th { padding: 12px 16px; font-weight: 600; background-color: var(--lumi-sys-color--surface-container, #f2f0f0); border-bottom: 1px solid var(--lumi-sys-color--stroke-default, rgba(0, 0, 0, 0.12)); color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-data-table td { padding: 12px 16px; border-bottom: 1px solid var(--lumi-sys-color--stroke-default, rgba(0, 0, 0, 0.12)); color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-data-table tr:last-child td { border-bottom-width: medium; border-bottom-style: none; border-bottom-color: currentcolor; }

/* --- Table widget (prose-style) --- */
.lumi-table-widget { display: flex; flex-direction: column; gap: var(--lumi-sys-spacing--xxl, 24px); width: 100%; }
.lumi-table-title { margin: 0px; color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-table { width: 100%; table-layout: fixed; border-collapse: collapse; font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); text-align: left; }
.lumi-table th { padding: 12px 16px 12px 0px; font-size: 17px; line-height: 24px; font-weight: 540; font-variation-settings: "wght" 540, "wdth" 92, "opsz" 17; color: var(--lumi-sys-color--on-surface-default, #000000); border-bottom: 1px solid var(--lumi-sys-color--on-surface-low, rgba(0, 0, 0, 0.08)); }
.lumi-table td { padding: 16px 16px 16px 0px; font-size: 17px; line-height: 24px; font-weight: 400; font-variation-settings: "wght" 400, "wdth" 92, "opsz" 17; color: var(--lumi-sys-color--on-surface-default, #000000); border-bottom: 1px solid var(--lumi-sys-color--on-surface-low, rgba(0, 0, 0, 0.08)); }
.lumi-table td:last-child, .lumi-table th:last-child { padding-right: 0px; }
/* Comparison: highlight the chosen column as ONE clean card — fill + rounded top/bottom, and stop the row rules at its edges (transparent bottom-border) so lines never slice the card. */
.lumi-table th.is-pick, .lumi-table td.is-pick { background: var(--surface-dim); border-bottom-color: transparent; padding-left: 16px; }
.lumi-table th.is-pick { border-radius: var(--r-s) var(--r-s) 0 0; }
.lumi-table tbody tr:last-child td.is-pick { border-radius: 0 0 var(--r-s) var(--r-s); }
.lumi-table .pick-col { color: var(--accent-fixed); }
.lumi-table tr.lumi-table-ellipsis-row td { padding: 16px 0px 0px; border-bottom-width: medium; border-bottom-style: none; border-bottom-color: currentcolor; color: var(--lumi-sys-color--on-surface-variant, rgba(0, 0, 0, 0.55)); }

/* --- Luminous Spec Table (Figma 8543-1878) --- */
.lumi-spec-table-container { width: 100%; overflow-x: auto; background: transparent; }
.lumi-spec-table { width: 100%; border-collapse: collapse; font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); text-align: left; background: transparent; }
.lumi-spec-table th { padding: 12px 28px 16px 0px; font-size: 17px; line-height: 24px; font-weight: 540; font-variation-settings: "wght" 540, "wdth" 100, "opsz" 17; color: var(--lumi-sys-color--on-surface-default, #000000); border-bottom: 1px solid var(--lumi-sys-color--on-surface-low, rgba(0, 0, 0, 0.08)); background: transparent; }
.lumi-spec-table td { padding: 16px 28px 16px 0px; border-bottom: 1px solid var(--lumi-sys-color--on-surface-low, rgba(0, 0, 0, 0.08)); vertical-align: top; background: transparent; }
.lumi-spec-table th:last-child, .lumi-spec-table td:last-child { padding-right: 0px; }
.lumi-spec-label { display: block; font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 13px; line-height: 17px; font-weight: 400; font-variation-settings: "wght" 400, "wdth" 92, "opsz" 13; color: var(--lumi-sys-color--on-surface-variant, rgba(0, 0, 0, 0.55)); margin-bottom: 2px; }
.lumi-spec-value { display: block; font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 15px; line-height: 20px; font-weight: 400; font-variation-settings: "wght" 400, "wdth" 92, "opsz" 15; color: var(--lumi-sys-color--on-surface-default, #000000); }
.lumi-spec-table-more { display: flex; align-items: center; justify-content: center; padding: 12px; color: var(--lumi-sys-color--on-surface-variant, rgba(0, 0, 0, 0.55)); font-size: 15px; line-height: 20px; cursor: pointer; }

/* --- Code block --- */
.lumi-code-block { background-color: var(--lumi-sys-color--code-background, #000000); border-radius: var(--lumi-sys-shape--xl-max, 40px); padding: 32px; display: flex; flex-direction: column; gap: var(--lumi-sys-spacing--l, 16px); width: 100%; box-sizing: border-box; }
.lumi-code-header { display: flex; justify-content: space-between; align-items: center; width: 100%; }
.lumi-code-lang { font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 15px; font-weight: 500; font-variation-settings: "wght" 540, "wdth" 92, "opsz" 15; color: var(--lumi-sys-color--code-primary-text, #ffffff); }
.lumi-code-copy { background: transparent; border-width: medium; border-style: none; border-color: currentcolor; border-image: none; color: var(--lumi-sys-color--code-primary-text, #ffffff); cursor: pointer; display: flex; align-items: center; justify-content: center; padding: 4px; border-radius: var(--lumi-sys-shape--full, 999px); transition: background-color 0.2s; }
.lumi-code-copy:hover { background-color: rgba(255, 255, 255, 0.1); }
.lumi-code-snippet { margin: 0px; overflow-x: auto; width: 100%; }
.lumi-code-snippet code { font-family: var(--ff-mono, 'Google Sans Code', monospace); font-size: 15px; line-height: 20px; color: var(--lumi-sys-color--code-primary-text, #ffffff); display: block; white-space: pre; }

/* --- Section / prose --- */
.lumi-section { display: flex; flex-direction: column; align-items: stretch; width: 100%; }
.lumi-section h1 { font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 28px; line-height: 36px; font-weight: 350; font-variation-settings: "wght" 350, "wdth" 100, "opsz" 28; color: var(--lumi-sys-color--on-surface, #000000); margin-top: var(--lumi-sys-spacing--m, 12px); margin-bottom: var(--lumi-sys-spacing--xxl, 24px); }
.lumi-section h1:first-child { margin-top: 0px; }
.lumi-section h2 { font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 24px; line-height: 28px; font-weight: 380; font-variation-settings: "wght" 380, "wdth" 100, "opsz" 24; color: var(--lumi-sys-color--on-surface, #000000); margin-top: var(--lumi-sys-spacing--m, 12px); margin-bottom: var(--lumi-sys-spacing--m, 12px); }
.lumi-section h2:first-child { margin-top: 0px; }
.lumi-section h3 { font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 20px; line-height: 24px; font-weight: 470; font-variation-settings: "wght" 470, "wdth" 94, "opsz" 20; color: var(--lumi-sys-color--on-surface, #000000); margin-top: var(--lumi-sys-spacing--m, 12px); margin-bottom: var(--lumi-sys-spacing--xs, 4px); }
.lumi-section h3:first-child { margin-top: 0px; }
.lumi-section p { font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 17px; line-height: 24px; font-weight: 400; font-variation-settings: "wght" 400, "wdth" 92, "opsz" 17; color: var(--lumi-sys-color--on-surface, #000000); margin-top: 0px; margin-bottom: var(--lumi-sys-spacing--m, 12px); }
.lumi-section p:last-child { margin-bottom: 0px; }
.lumi-section ul { list-style: none; padding: 0px; margin: 0 0 var(--lumi-sys-spacing--m, 12px) 0; width: 100%; }
.lumi-section ul:last-child { margin-bottom: 0px; }
.lumi-section li { position: relative; padding-left: 40px; padding-bottom: 12px; font-family: var(--ff-sans, 'Google Sans Flex', sans-serif); font-size: 17px; line-height: 24px; font-weight: 400; font-variation-settings: "wght" 400, "wdth" 92, "opsz" 17; color: var(--lumi-sys-color--on-surface, #000000); box-sizing: border-box; }
.lumi-section li:last-child { padding-bottom: 0px; }
.lumi-section li::before { content: "○"; position: absolute; left: 3.5px; top: 0px; width: 24px; height: 24px; display: flex; align-items: center; justify-content: center; font-family: var(--ff-mono, 'Google Sans Code', monospace); font-size: 15px; font-weight: 650; font-variation-settings: "MONO" 1, "wght" 650; color: var(--lumi-sys-color--on-surface, #000000); }
.lumi-section li ul { margin-top: 12px; margin-bottom: 0px; padding-left: 40px; }

/* --- Chart legend (1:1 series color match) --- */
.lumi-chart-header, .lumi-chart-title { margin-bottom: 32px; }
.lumi-chart-legend { display: flex; justify-content: center; align-items: center; gap: 24px; margin-top: 32px; padding-top: 0px; width: 100%; flex-wrap: wrap; }
.lumi-legend-item { display: inline-flex; align-items: center; gap: 8px; }
.lumi-legend-dot { width: 20px; height: 20px; display: inline-flex; align-items: center; justify-content: center; flex-shrink: 0; }
.lumi-legend-dot-swatch { width: 20px; height: 20px; border-radius: 50%; display: block; }
span.lumi-legend-dot[style*="background"] { width: 20px; height: 20px; border-radius: 50%; flex-shrink: 0; display: inline-block; }
.lumi-legend-label { font-family: var(--ff-mono, 'Google Sans Code', monospace); font-style: italic; font-size: 13px; font-weight: 400; line-height: 20px; color: var(--lumi-sys-color--on-surface, #000000); font-variation-settings: "wght" 400, "opsz" 13, "MONO" 0; font-feature-settings: "kern" 1, "liga" 1; white-space: nowrap; }

/* Canonical themed <select>. Uses element+class specificity (select.lumi-select)
   so it intentionally wins over any model hand-rolled `.lumi-select` rule: the
   runtime stylesheet is injected before widget <style> blocks, so a bare
   `.lumi-select` (same specificity, later) would otherwise override it. This
   provides appearance:none + a theme-neutral chevron so no native OS arrow leaks. */
select.lumi-select {
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  width: 100%;
  padding: var(--lumi-sys-spacing--s, 8px) 40px var(--lumi-sys-spacing--s, 8px)
    var(--lumi-sys-spacing--m, 12px);
  border: 1px solid var(--stroke-default);
  border-radius: var(--r-full, 999px);
  background-color: var(--surface);
  color: var(--on-surface);
  font-family: var(--ff-sans, 'Google Sans Flex', sans-serif);
  font-size: 15px;
  line-height: 20px;
  cursor: pointer;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 24 24' fill='none' stroke='%2380868b' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpolyline points='6 9 12 15 18 9'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 14px center;
  background-size: 14px;
}
select.lumi-select:focus-visible {
  outline: 2px solid var(--lumi-sys-color--accent-fixed, #3186ff);
  outline-offset: 2px;
}

/* Toggle / filter chip. Models frequently emit `<button class="lumi-chip">`
   (optionally `.is-active`/`.is-selected`) for toggle pills; without a
   canonical rule these fall back to native (retro) browser button chrome.
   Theme-aware via runtime tokens so it is correct in light and dark. */
.lumi-chip {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: var(--lumi-sys-spacing--s, 8px);
  min-height: 32px;
  padding: 0 16px;
  font-family: var(--ff-sans, 'Google Sans Flex', 'Google Sans', sans-serif);
  font-size: 14px;
  font-weight: 500;
  line-height: 20px;
  color: var(--lumi-sys-color--on-surface-default, #1f1f1f);
  background: var(--lumi-sys-color--surface-dim, #f2f0f0);
  border: 1px solid transparent;
  border-radius: var(--lumi-sys-shape--full, 999px);
  cursor: pointer;
  user-select: none;
  white-space: nowrap;
  box-sizing: border-box;
  transition: background-color 0.15s, color 0.15s, border-color 0.15s;
  -webkit-appearance: none;
  appearance: none;
}
.lumi-chip:hover {
  background: var(--lumi-sys-color--surface-container-high, #e6e6e6);
}
.lumi-chip.is-active,
.lumi-chip.active,
.lumi-chip.is-selected,
.lumi-chip.selected,
.lumi-chip[aria-pressed="true"],
.lumi-chip[aria-selected="true"] {
  color: var(--lumi-sys-color--accent-fixed, #3186ff);
  background: var(--lumi-sys-color--accent-container, rgba(49, 134, 255, 0.14));
  border-color: transparent;
  font-weight: 600;
}
.lumi-chip:focus-visible {
  outline: 2px solid var(--lumi-sys-color--accent-fixed, #3186ff);
  outline-offset: 2px;
}

/* ============================================================
 * DIAGRAM GUARD — SVG <text> is fill-only.
 *   An inherited group stroke (e.g. `.node:hover { stroke }` on a <g>)
 *   otherwise cascades into child <text>, thickening glyph outlines
 *   (fake-bold) and recoloring the label. Highlight strokes belong on
 *   shapes (rect/path); text never paints a stroke.
 * ============================================================ */
svg text { stroke: none; paint-order: fill; }


/* ============================================================
   COMPOSITE WIDGETS & LAYOUT (composed on top of core library)
   ============================================================ */
.lumi-time-content, .lumi-seq-content {
  display: flex;
  flex-direction: column;
  gap: 4px;
}
.lumi-display {
  font-family: var(--ff-sans, 'Google Sans Flex', sans-serif);
  font-size: 40px;
  line-height: 46px;
  font-weight: 320;
  font-variation-settings: "wght" 320, "wdth" 100, "opsz" 40, "ROND" 100;
  letter-spacing: -0.02em;
  color: var(--on-surface);
}
.lumi-dashboard-hud {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(155px, 1fr));
  gap: 16px;
  width: 100%;
  padding: 20px 0;
  border-top: 1px solid var(--surface-dim);
  border-bottom: 1px solid var(--surface-dim);
}
.lumi-card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 20px;
  width: 100%;
}
.lumi-tldr {
  font-family: var(--ff-sans, 'Google Sans Flex', sans-serif);
  font-size: 19px;
  line-height: 28px;
  font-weight: 380;
  color: var(--on-surface);
  max-width: 880px;
  margin: 0;
}
/* Comparison layout primitive (side-by-side, borderless) */
.lumi-comparison {
  display: flex;
  flex-direction: column;
  gap: var(--lumi-sys-spacing--xxl);
  width: 100%;
}
@media (min-width: 600px) {
  .lumi-comparison { flex-direction: row; }
}
.lumi-comp-column {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: var(--lumi-sys-spacing--s);
}
.lumi-comp-media-wrap {
  width: 100%;
  aspect-ratio: 1 / 1;
  background-color: var(--lumi-sys-color--surface-dim);
  border-radius: var(--lumi-sys-shape--corner-large, 16px);
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}
.lumi-comp-media { max-width: 90%; max-height: 90%; object-fit: contain; }
.lumi-comp-specs {
  display: flex;
  flex-direction: column;
  gap: var(--lumi-sys-spacing--m);
  margin-top: var(--lumi-sys-spacing--s);
}
.lumi-spec-row { display: flex; align-items: flex-start; gap: var(--lumi-sys-spacing--s); }
.lumi-spec-text { display: flex; flex-direction: column; }

.lumi-pros-cons {
  display: flex;
  flex-direction: column;
  gap: var(--lumi-sys-spacing--xxl);
  width: 100%;
}
@media (min-width: 600px) {
  .lumi-pros-cons { flex-direction: row; }
}
.lumi-pc-column, .lumi-pros-col, .lumi-cons-col {
  display: flex;
  flex-direction: column;
  gap: var(--lumi-sys-spacing--l);
}
.lumi-pc-list, .lumi-pros-list, .lumi-cons-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: var(--lumi-sys-spacing--s);
}
.lumi-pc-list .marker { font-size: 20px; margin-top: 2px; }
/* Component lists carry their own markers/rings; opt out of the generic prose bullet */
.lumi-pc-list li, .lumi-pros-list li, .lumi-cons-list li,
.lumi-seq-step, .lumi-sequence li, .lumi-timeline li, .lumi-timeline-item { padding-left: 0; }
.lumi-pc-list li::before, .lumi-pros-list li::before, .lumi-cons-list li::before,
.lumi-seq-step::before, .lumi-sequence li::before, .lumi-timeline li::before, .lumi-timeline-item::before { content: none; }
.lumi-pc-list li, .lumi-pros-list li, .lumi-cons-list li {
  display: flex;
  align-items: flex-start;
  gap: var(--lumi-sys-spacing--l);
  font-size: 15px;
  line-height: 22px;
  color: var(--on-surface);
}
.lumi-sequence {
  display: flex;
  flex-direction: column;
  width: 100%;
  list-style: none;
  padding: 0;
  margin: 0;
}
.lumi-seq-step {
  display: flex;
  align-items: flex-start;
  gap: var(--lumi-sys-spacing--l);
  position: relative;
  padding-bottom: var(--lumi-sys-spacing--l);
}
.lumi-seq-step:last-child { padding-bottom: 0; }
.lumi-seq-num {
  width: 20px;
  height: 20px;
  margin: 2px 2px 0 2px;
  border-radius: 50%;
  border: 1.3px solid var(--lumi-sys-color--on-surface);
  background-color: transparent;
  color: var(--lumi-sys-color--on-surface);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  box-sizing: border-box;
  z-index: 2;
}
.lumi-seq-num span {
  display: block;
  width: 100%;
  text-align: center;
  font-family: var(--ff-sans);
  font-size: 13px;
  line-height: 1;
  letter-spacing: 0;
  font-weight: 400;
  font-variation-settings: "wght" 400, "wdth" 92, "opsz" 13;
}
.lumi-seq-step:not(:last-child)::after {
  content: '';
  position: absolute;
  top: 30px;
  bottom: 6px;
  left: 11px;
  width: 2px;
  background-color: var(--lumi-sys-color--on-surface);
  -webkit-mask-image: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='2' height='4'><circle cx='1' cy='2' r='0.65' fill='black'/></svg>");
  -webkit-mask-repeat: repeat-y;
  -webkit-mask-size: 2px 4px;
  mask-image: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='2' height='4'><circle cx='1' cy='2' r='0.65' fill='black'/></svg>");
  mask-repeat: repeat-y;
  mask-size: 2px 4px;
  z-index: 1;
}
.lumi-seq-content {
  display: flex;
  flex-direction: column;
  gap: var(--lumi-sys-spacing--xs);
}
.lumi-process-flow {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 16px;
  width: 100%;
}
.lumi-flow-step {
  background: var(--surface);
  border: 1px solid var(--surface-dim);
  border-radius: 14px;
  padding: 18px;
  display: flex;
  flex-direction: column;
  gap: 8px;
}
.lumi-column {
  display: flex !important;
  flex-direction: column !important;
}
.lumi-row {
  display: flex !important;
  flex-direction: row !important;
  align-items: center;
}
.lumi-column > h1, .lumi-column > h2, .lumi-column > h3 {
  margin-bottom: 12px !important;
}
.lumi-cluster {
  display: flex;
  flex-wrap: wrap;
  gap: var(--spacing-l, 16px);
  align-items: center;
}
.lumi-stat-value {
  font-family: var(--ff-sans);
  font-size: 2rem;
  font-weight: 700;
  line-height: 1.15;
  letter-spacing: -0.01em;
  color: var(--on-surface);
}
.lumi-stat-label {
  font-size: 0.8125rem;
  color: var(--on-surface-variant);
}
.lumi-title {
  font-family: var(--ff-sans);
  font-size: clamp(2rem, 4vw, 2.75rem);
  font-weight: 700;
  line-height: 1.08;
  letter-spacing: -0.02em;
  color: var(--on-surface);
  margin: 0;
}
.lumi-subtitle {
  font-size: 1.125rem;
  color: var(--on-surface-variant);
  line-height: 1.5;
}
.lumi-kicker, .lumi-eyebrow {
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--on-surface-variant);
}
.lumi-page, .lumi-viewer-content, .lumi-article, .lumi-doc, .page-container {
  max-width: 720px;
  margin-inline: auto;
  padding: 56px 24px 96px;
  box-sizing: border-box;
}
.lumi-prose > p, .lumi-prose > ul, .lumi-prose > ol, .lumi-prose > blockquote {
  max-width: 68ch;
}
.lumi-page, .lumi-viewer-content, .lumi-article, .lumi-doc, .page-container {
  padding: 32px 18px 64px;
}

/* Timeline — golden (hollow ring marker + SVG-dotted connector; item = [marker][content] row) */
.lumi-timeline { display: flex; flex-direction: column; width: 100%; position: relative; }
.lumi-timeline-item { display: flex; align-items: flex-start; gap: 16px; position: relative; padding-bottom: 16px; }
.lumi-timeline-item:last-child { padding-bottom: 0; }
.lumi-time-marker { width: 24px; height: var(--lumi-sys-typography-type-scale--body-l-line-height, 1.5rem); flex-shrink: 0; position: relative; display: flex; align-items: center; justify-content: center; }
.lumi-time-marker::before { content: ''; width: 16px; height: 16px; border-radius: 50%; border: 1.3px solid var(--on-surface); background-color: transparent; z-index: 2; box-sizing: border-box; }
.lumi-timeline-item:not(:last-child)::after { content: ''; position: absolute; top: 28px; bottom: 4px; left: 11px; width: 2px; background-color: var(--on-surface); -webkit-mask-image: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='2' height='4'><circle cx='1' cy='2' r='0.65' fill='black'/></svg>"); -webkit-mask-repeat: repeat-y; -webkit-mask-size: 2px 4px; mask-image: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='2' height='4'><circle cx='1' cy='2' r='0.65' fill='black'/></svg>"); mask-repeat: repeat-y; mask-size: 2px 4px; z-index: 1; }
.lumi-time-content { display: flex; flex-direction: column; gap: 4px; }
/* Reset UA margins on widget content children so flex gap is the only vertical spacing (matches golden outside the previewer's .lumi-tab-content scope). */
.lumi-time-content > *, .lumi-seq-content > * { margin: 0; }

</style>

  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SOC N1 Operations Command & Technical Portfolio | Marcos César</title>
  
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Google+Sans+Code:ital,wght@0,400..700;1,400..700&family=Google+Sans+Flex:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200" rel="stylesheet">
  
  <!-- External Libraries -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js" onerror="console.warn('Chart.js fallback')"></script>
  
  <style>
    /* Custom Page Layout & Specific Component Overrides */
    :root {
      --ff-sans: 'Google Sans Flex', -apple-system, BlinkMacSystemFont, sans-serif;
      --ff-mono: 'Google Sans Code', monospace;
      
      /* Dark Theme Tokens Default Mapping */
      --body-bg: #0b0d12;
      --surface: #0f1219;
      --surface-dim: #151923;
      --surface-bright: #1f2533;
      --surface-container: #181d29;
      --on-surface: #e1e7f5;
      --on-surface-variant: #94a3b8;
      --on-surface-low: rgba(255, 255, 255, 0.08);
      
      --accent-fixed: #3186ff;
      --primary: #3186ff;
      --accent-container: rgba(49, 134, 255, 0.15);
      --positive: #0ebc5f;
      --positive-container: rgba(14, 188, 95, 0.15);
      --error: #ff4c45;
      --error-container: rgba(255, 76, 69, 0.15);
      --warning: #f59e0b;
      --warning-container: rgba(245, 158, 11, 0.15);
      
      --stroke-default: #262d3d;
      --outline: #384358;
      --r-s: 8px;
      --r-m: 12px;
      --r-l: 16px;
      --r-full: 999px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background-color: var(--body-bg);
      color: var(--on-surface);
      font-family: var(--ff-sans);
      font-size: 15px;
      line-height: 1.5;
      padding: 0;
      margin: 0;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    /* Top Navigation Bar */
    .top-nav {
      background-color: var(--surface);
      border-bottom: 1px solid var(--stroke-default);
      padding: 12px 24px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .brand-group {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .brand-badge {
      width: 36px;
      height: 36px;
      background: var(--accent-container);
      border: 1px solid var(--primary);
      border-radius: 8px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--primary);
      font-weight: 700;
    }

    .brand-info h1 {
      font-size: 16px;
      font-weight: 600;
      letter-spacing: -0.2px;
    }

    .brand-info p {
      font-size: 12px;
      color: var(--on-surface-variant);
      font-family: var(--ff-mono);
    }

    .status-pill {
      display: flex;
      align-items: center;
      gap: 8px;
      padding: 6px 12px;
      background: var(--positive-container);
      border: 1px solid rgba(14, 188, 95, 0.3);
      border-radius: var(--r-full);
      font-size: 12px;
      color: var(--positive);
      font-family: var(--ff-mono);
    }

    .pulse-dot {
      width: 8px;
      height: 8px;
      background-color: var(--positive);
      border-radius: 50%;
      box-shadow: 0 0 8px var(--positive);
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.4; transform: scale(0.8); }
      100% { opacity: 1; transform: scale(1); }
    }

    /* Main Container & Layout */
    .app-container {
      max-width: 1400px;
      margin: 0 auto;
      width: 100%;
      padding: 24px;
      flex: 1;
      display: flex;
      flex-direction: column;
      gap: 24px;
    }

    /* Header Profile Card */
    .profile-hero {
      background: linear-gradient(135deg, var(--surface) 0%, var(--surface-dim) 100%);
      border: 1px solid var(--stroke-default);
      border-radius: var(--r-l);
      padding: 24px;
      display: grid;
      grid-template-columns: 1fr auto;
      gap: 24px;
      align-items: center;
    }

    @media (max-width: 900px) {
      .profile-hero {
        grid-template-columns: 1fr;
      }
    }

    .hero-main h2 {
      font-size: 24px;
      font-weight: 600;
      margin-bottom: 6px;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .hero-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 12px;
    }

    .hero-tag {
      background: var(--surface-bright);
      border: 1px solid var(--stroke-default);
      padding: 4px 10px;
      border-radius: var(--r-s);
      font-size: 12px;
      color: var(--on-surface-variant);
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .hero-tag .material-symbols-outlined {
      font-size: 16px;
      color: var(--primary);
    }

    .stats-strip {
      display: flex;
      gap: 16px;
      flex-wrap: wrap;
    }

    .stat-box {
      background: var(--surface-dim);
      border: 1px solid var(--stroke-default);
      border-radius: var(--r-m);
      padding: 12px 18px;
      min-width: 120px;
      text-align: center;
    }

    .stat-val {
      font-size: 22px;
      font-weight: 700;
      font-family: var(--ff-mono);
      color: var(--primary);
    }

    .stat-lbl {
      font-size: 11px;
      color: var(--on-surface-variant);
      text-transform: uppercase;
      letter-spacing: 0.5px;
      margin-top: 2px;
    }

    /* Main Tab Navigation */
    .nav-tabs {
      display: flex;
      gap: 8px;
      border-bottom: 1px solid var(--stroke-default);
      padding-bottom: 0;
      overflow-x: auto;
    }

    .tab-btn {
      background: transparent;
      border: none;
      color: var(--on-surface-variant);
      padding: 12px 18px;
      font-size: 14px;
      font-family: var(--ff-sans);
      font-weight: 500;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 8px;
      border-bottom: 2px solid transparent;
      transition: all 0.2s ease;
      white-space: nowrap;
    }

    .tab-btn:hover {
      color: var(--on-surface);
      background: var(--surface-container);
      border-radius: var(--r-s) var(--r-s) 0 0;
    }

    .tab-btn.active {
      color: var(--primary);
      border-bottom-color: var(--primary);
    }

    .tab-content {
      display: none;
      flex-direction: column;
      gap: 20px;
    }

    .tab-content.active {
      display: flex;
    }

    /* Grid Layouts */
    .grid-2 {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 20px;
    }

    .grid-3 {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
    }

    .grid-1-2 {
      display: grid;
      grid-template-columns: 1fr 2fr;
      gap: 20px;
    }

    .grid-2-1 {
      display: grid;
      grid-template-columns: 2fr 1fr;
      gap: 20px;
    }

    @media (max-width: 960px) {
      .grid-2, .grid-3, .grid-1-2, .grid-2-1 {
        grid-template-columns: 1fr;
      }
    }

    /* Card Box Styling */
    .panel-card {
      background: var(--surface);
      border: 1px solid var(--stroke-default);
      border-radius: var(--r-m);
      padding: 20px;
      display: flex;
      flex-direction: column;
      gap: 16px;
    }

    .panel-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-bottom: 1px solid var(--on-surface-low);
      padding-bottom: 12px;
    }

    .panel-title {
      font-size: 16px;
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .panel-title .material-symbols-outlined {
      color: var(--primary);
      font-size: 20px;
    }

    /* Console & Log Terminal Mockup */
    .terminal-window {
      background: #06080c;
      border: 1px solid var(--outline);
      border-radius: var(--r-s);
      font-family: var(--ff-mono);
      font-size: 13px;
      overflow: hidden;
      display: flex;
      flex-direction: column;
    }

    .terminal-bar {
      background: #11151f;
      padding: 8px 12px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-bottom: 1px solid var(--stroke-default);
    }

    .terminal-dots {
      display: flex;
      gap: 6px;
    }

    .dot {
      width: 10px;
      height: 10px;
      border-radius: 50%;
    }

    .dot-red { background: #ff5f56; }
    .dot-yellow { background: #ffbd2e; }
    .dot-green { background: #27c93f; }

    .terminal-title {
      font-size: 11px;
      color: var(--on-surface-variant);
    }

    .terminal-body {
      padding: 14px;
      min-height: 220px;
      max-height: 380px;
      overflow-y: auto;
      color: #33ff77;
      line-height: 1.6;
      white-space: pre-wrap;
      word-break: break-all;
    }

    .log-line {
      margin-bottom: 4px;
    }

    .log-err { color: #ff5252; }
    .log-warn { color: #ffd740; }
    .log-info { color: #64b5f6; }
    .log-success { color: #69f0ae; }
    .log-dim { color: #607d8b; }

    /* Interactive Buttons */
    .action-btn {
      background: var(--primary);
      color: #ffffff;
      border: none;
      padding: 8px 16px;
      border-radius: var(--r-s);
      font-family: var(--ff-sans);
      font-size: 13px;
      font-weight: 500;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      transition: background 0.2s ease;
    }

    .action-btn:hover {
      background: #1d6edc;
    }

    .action-btn--secondary {
      background: var(--surface-bright);
      color: var(--on-surface);
      border: 1px solid var(--stroke-default);
    }

    .action-btn--secondary:hover {
      background: var(--surface-container);
    }

    .action-btn--danger {
      background: var(--error);
    }

    .action-btn--danger:hover {
      background: #c62828;
    }

    /* Code Snippet Box */
    .code-box {
      background: #07090e;
      border: 1px solid var(--stroke-default);
      border-radius: var(--r-s);
      padding: 14px;
      font-family: var(--ff-mono);
      font-size: 12px;
      color: #e2e8f0;
      overflow-x: auto;
      position: relative;
    }

    .copy-btn {
      position: absolute;
      top: 10px;
      right: 10px;
      background: var(--surface-bright);
      border: 1px solid var(--stroke-default);
      color: var(--on-surface-variant);
      padding: 4px 8px;
      border-radius: 4px;
      font-size: 11px;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 4px;
    }

    .copy-btn:hover {
      color: var(--on-surface);
      background: var(--surface-container);
    }

    /* Interactive Q&A Cards */
    .qa-card {
      background: var(--surface-dim);
      border: 1px solid var(--stroke-default);
      border-radius: var(--r-m);
      overflow: hidden;
      transition: border-color 0.2s ease;
    }

    .qa-card:hover {
      border-color: var(--outline);
    }

    .qa-header {
      padding: 16px;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: space-between;
      font-weight: 500;
    }

    .qa-body {
      padding: 0 16px 16px 16px;
      font-size: 14px;
      color: var(--on-surface-variant);
      display: none;
      border-top: 1px solid var(--on-surface-low);
      padding-top: 12px;
      line-height: 1.6;
    }

    .qa-card.open .qa-body {
      display: block;
    }

    .qa-badge {
      background: var(--accent-container);
      color: var(--primary);
      padding: 2px 8px;
      border-radius: 4px;
      font-size: 11px;
      font-family: var(--ff-mono);
    }

    /* Simulation Control Deck */
    .control-deck {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      padding: 12px;
      background: var(--surface-dim);
      border-radius: var(--r-s);
      border: 1px solid var(--stroke-default);
    }

    /* Footer */
    footer {
      border-top: 1px solid var(--stroke-default);
      padding: 20px 24px;
      text-align: center;
      font-size: 12px;
      color: var(--on-surface-variant);
      margin-top: auto;
      font-family: var(--ff-mono);
    }

    /* Table Customizations */
    .data-table {
      width: 100%;
      border-collapse: collapse;
      font-size: 13px;
    }

    .data-table th, .data-table td {
      padding: 10px 12px;
      text-align: left;
      border-bottom: 1px solid var(--stroke-default);
    }

    .data-table th {
      background: var(--surface-dim);
      color: var(--on-surface-variant);
      font-family: var(--ff-mono);
      font-weight: 500;
      font-size: 11px;
      text-transform: uppercase;
    }

    .data-table tr:hover {
      background: var(--surface-container);
    }

    .pill-badge {
      display: inline-block;
      padding: 2px 8px;
      border-radius: 12px;
      font-size: 11px;
      font-family: var(--ff-mono);
      font-weight: 500;
    }

    .pill-danger { background: var(--error-container); color: var(--error); }
    .pill-success { background: var(--positive-container); color: var(--positive); }
    .pill-warning { background: var(--warning-container); color: var(--warning); }
    .pill-info { background: var(--accent-container); color: var(--primary); }

  </style>
</head>
<body class="lumi-theme-dark">

  <!-- Top Navigation Header -->
  <header class="top-nav">
    <div class="brand-group">
      <div class="brand-badge">SOC</div>
      <div class="brand-info">
        <h1>SOC N1 Command Center &amp; Portfolio</h1>
        <p>Marcos César Inácio da Luz | Technical Case &amp; Operations Readiness</p>
      </div>
    </div>
    <div class="status-pill">
      <div class="pulse-dot"></div>
      <span>LAB ACTIVE | DEBIAN 13 SIEM &amp; WIREGUARD</span>
    </div>
  </header>

  <div class="app-container">

    <!-- Candidate Hero Banner -->
    <section class="profile-hero">
      <div class="hero-main">
        <h2>
          <span>Marcos César Inácio da Luz</span>
          <span class="material-symbols-outlined" style="color: var(--primary)">verified</span>
        </h2>
        <p style="color: var(--on-surface-variant); font-size: 14px; max-width: 780px;">
          Tecnólogo em Segurança da Informação (UNIP) com 10 anos de vivência em Liderança de Segurança Física. Especialista em resposta a incidentes inicial, triagem KQL no Elastic Stack, automação de coleta de logs e arquiteturas Zero Trust via WireGuard.
        </p>
        <div class="hero-tags">
          <div class="hero-tag">
            <span class="material-symbols-outlined">school</span>
            <span>UNIP TSI (Maio 2026)</span>
          </div>
          <div class="hero-tag">
            <span class="material-symbols-outlined">workspace_premium</span>
            <span>Hackers do Bem Blue Team (300h+)</span>
          </div>
          <div class="hero-tag">
            <span class="material-symbols-outlined">terminal</span>
            <span>Elasticsearch 8.x / Kibana KQL</span>
          </div>
          <div class="hero-tag">
            <span class="material-symbols-outlined">vpn_lock</span>
            <span>WireGuard Zero Trust</span>
          </div>
          <div class="hero-tag">
            <span class="material-symbols-outlined">shield</span>
            <span>IPTables Host Containment</span>
          </div>
        </div>
      </div>
      <div class="stats-strip">
        <div class="stat-box">
          <div class="stat-val">300h+</div>
          <div class="stat-lbl">Treinamento Prático</div>
        </div>
        <div class="stat-box">
          <div class="stat-val">10 Anos</div>
          <div class="stat-lbl">Gestão &amp; Liderança</div>
        </div>
        <div class="stat-box">
          <div class="stat-val">N1 Ready</div>
          <div class="stat-lbl">SOC Night Shift</div>
        </div>
      </div>
    </section>

    <!-- Navigation Tabs -->
    <nav class="nav-tabs">
      <button class="tab-btn active" onclick="switchTab('lab-sim')">
        <span class="material-symbols-outlined">terminal</span>
        <span>Simulador de Incidente (Live Lab)</span>
      </button>
      <button class="tab-btn" onclick="switchTab('topology')">
        <span class="material-symbols-outlined">hub</span>
        <span>Arquitetura de Rede &amp; VPN</span>
      </button>

      <button class="tab-btn" onclick="switchTab('interview')">
        <span class="material-symbols-outlined">record_voice_over</span>
        <span>Simulador de Entrevista (It4us N1)</span>
      </button>
      <button class="tab-btn" onclick="switchTab('github-repo')">
        <span class="material-symbols-outlined">code</span>
        <span>Documentação GitHub &amp; README</span>
      </button>
    </nav>

    <!-- TAB 1: Live Interactive Lab & Incident Simulator -->
    <div id="lab-sim" class="tab-content active">
      <div class="grid-2-1">
        
        <div class="panel-card">
          <div class="panel-header">
            <div class="panel-title">
              <span class="material-symbols-outlined">p2p</span>
              <span>Console de Simulação de Ataque &amp; Ingestão SIEM</span>
            </div>
            <span class="pill-badge pill-info">Filebeat auth.log Active</span>
          </div>

          <div class="control-deck">
            <button class="action-btn action-btn--danger" onclick="runAttackSimulation()">
              <span class="material-symbols-outlined">bolt</span>
              <span>1. Disparar Hydra SSH Brute Force (Kali 10.10.17.15)</span>
            </button>

            <button class="action-btn action-btn--secondary" onclick="applyFirewallBlock()">
              <span class="material-symbols-outlined">block</span>
              <span>2. Aplicar IPTables DROP Contenção (Debian)</span>
            </button>

            <button class="action-btn action-btn--secondary" onclick="testVpnTunnel()">
              <span class="material-symbols-outlined">vpn_key</span>
              <span>3. Validar Acesso Criptografado WireGuard (10.66.0.1)</span>
            </button>

            <button class="action-btn action-btn--secondary" onclick="clearConsoleLog()">
              <span class="material-symbols-outlined">cleaning_services</span>
              <span>Limpar Console</span>
            </button>
          </div>

          <!-- Console Terminal Output -->
          <div class="terminal-window">
            <div class="terminal-bar">
              <div class="terminal-dots">
                <div class="dot dot-red"></div>
                <div class="dot dot-yellow"></div>
                <div class="dot dot-green"></div>
              </div>
              <div class="terminal-title">server@debian:/var/log/auth.log — Elastic Ingestion Stream</div>
              <span style="font-size: 11px; color: var(--on-surface-variant)">TTY pts/1</span>
            </div>
            <div class="terminal-body" id="sim-terminal">
              <div class="log-line log-dim">[SYSTEM INIT] Elasticsearch 8.19.21 online on https://localhost:9200</div>
              <div class="log-line log-dim">[SYSTEM INIT] Filebeat system module active monitoring /var/log/auth.log</div>
              <div class="log-line log-success">[SYSTEM INIT] WireGuard wg0 interface active on 10.66.0.1/24 (ListenPort 51820)</div>
              <div class="log-line log-info">[SOC MONITOR] Aguardando eventos de autenticação ou simulação de ataque...</div>
            </div>
          </div>
        </div>

        <!-- Real-time Metrics & Incident Ticket Box -->
        <div style="display: flex; flex-direction: column; gap: 20px;">
          
          <div class="panel-card">
            <div class="panel-header">
              <div class="panel-title">
                <span class="material-symbols-outlined">analytics</span>
                <span>Telemetria em Tempo Real</span>
              </div>
            </div>
            <div style="height: 180px;">
              <canvas id="metricsChart"></canvas>
            </div>
          </div>

          <div class="panel-card">
            <div class="panel-header">
              <div class="panel-title">
                <span class="material-symbols-outlined">confirmation_number</span>
                <span>Ticket de Incidente SOC N1</span>
              </div>
              <span class="pill-badge pill-warning" id="ticket-status">EM ANÁLISE</span>
            </div>

            <div style="font-size: 12px; display: flex; flex-direction: column; gap: 8px;">
              <div style="display: flex; justify-content: space-between; border-bottom: 1px solid var(--on-surface-low); padding-bottom: 4px;">
                <span style="color: var(--on-surface-variant)">ID do Ticket:</span>
                <span style="font-family: var(--ff-mono)">INC-20260918-001</span>
              </div>
              <div style="display: flex; justify-content: space-between; border-bottom: 1px solid var(--on-surface-low); padding-bottom: 4px;">
                <span style="color: var(--on-surface-variant)">Ativo Alvo:</span>
                <span style="font-family: var(--ff-mono)">10.10.17.18:22 (Debian Server)</span>
              </div>
              <div style="display: flex; justify-content: space-between; border-bottom: 1px solid var(--on-surface-low); padding-bottom: 4px;">
                <span style="color: var(--on-surface-variant)">IP Origem Atacante:</span>
                <span style="font-family: var(--ff-mono)" id="ticket-attacker-ip">10.10.17.15 (Kali)</span>
              </div>
              <div style="display: flex; justify-content: space-between; border-bottom: 1px solid var(--on-surface-low); padding-bottom: 4px;">
                <span style="color: var(--on-surface-variant)">Vetor MITRE:</span>
                <span style="font-family: var(--ff-mono)">T1110 - Brute Force SSH</span>
              </div>
              <div style="display: flex; justify-content: space-between;">
                <span style="color: var(--on-surface-variant)">Contenção Ativa:</span>
                <span style="font-family: var(--ff-mono)" id="ticket-firewall-status">Pendente (IPTables)</span>
              </div>
            </div>
          </div>

        </div>

      </div>

      <!-- KQL Kibana Search Query Reference -->
      <div class="panel-card">
        <div class="panel-header">
          <div class="panel-title">
            <span class="material-symbols-outlined">search</span>
            <span>Consulta KQL Utilizada no Kibana Discover</span>
          </div>
          <span class="pill-badge pill-info">Kibana Syntax</span>
        </div>
        <div class="code-box">
          <button class="copy-btn" onclick="copyText('kql-code')">
            <span class="material-symbols-outlined" style="font-size: 14px">content_copy</span> Copy
          </button>
          <code id="kql-code">event.dataset: "system.auth" and event.outcome: "failure" and user.name: "root"</code>
        </div>
      </div>

    </div>

    <!-- TAB 2: Topology & WireGuard Zero Trust -->
    <div id="topology" class="tab-content">
      <div class="panel-card">
        <div class="panel-header">
          <div class="panel-title">
            <span class="material-symbols-outlined">schema</span>
            <span>Topologia de Rede do Laboratório: Datacenter Monitorado &amp; Acesso VPN Zero Trust</span>
          </div>
          <span class="pill-badge pill-success">WireGuard Tunnel Established</span>
        </div>

        <p style="color: var(--on-surface-variant); font-size: 14px;">
          Arquitetura corporativa virtualizada demonstrando o isolamento do servidor Debian, coleta de logs via Filebeat/Elasticsearch e o túnel criptografado ponto a ponto via WireGuard para o analista remoto.
        </p>

        <!-- SVG Interactive Topology Diagram -->
        <div style="width: 100%; overflow-x: auto; background: #080a0f; border-radius: var(--r-s); padding: 20px; border: 1px solid var(--stroke-default);">
          <svg viewBox="0 0 800 400" style="width: 100%; max-width: 800px; height: auto; display: block; margin: 0 auto;">
            <defs>
              <marker id="caret" viewBox="0 0 10 10" refX="7.5" refY="5" markerUnits="userSpaceOnUse" markerWidth="10" markerHeight="10" orient="auto">
                <path d="M 3 1.2 L 7.5 5 L 3 8.8" fill="none" stroke="var(--primary)" stroke-width="1.3" stroke-linecap="round" stroke-linejoin="round"/>
              </marker>
              <marker id="caret-red" viewBox="0 0 10 10" refX="7.5" refY="5" markerUnits="userSpaceOnUse" markerWidth="10" markerHeight="10" orient="auto">
                <path d="M 3 1.2 L 7.5 5 L 3 8.8" fill="none" stroke="var(--error)" stroke-width="1.3" stroke-linecap="round" stroke-linejoin="round"/>
              </marker>
            </defs>

            <!-- Boundary Box: Corporate Datacenter -->
            <rect x="20" y="30" width="460" height="340" rx="16" fill="rgba(21, 25, 35, 0.6)" stroke="var(--outline)" stroke-dasharray="4 4"/>
            <text x="35" y="55" fill="var(--on-surface-variant)" font-family="var(--ff-mono)" font-size="12" font-weight="600">CORP DATACENTER / SIEM MONITORING ZONE</text>

            <!-- Node 1: Debian Server (Target) -->
            <rect x="50" y="80" width="180" height="90" rx="12" fill="var(--surface-bright)" stroke="var(--primary)" stroke-width="2"/>
            <text x="140" y="105" text-anchor="middle" fill="var(--on-surface)" font-family="var(--ff-sans)" font-size="14" font-weight="600">Debian 13 (Server)</text>
            <text x="140" y="125" text-anchor="middle" fill="var(--primary)" font-family="var(--ff-mono)" font-size="12">IP: 10.10.17.18</text>
            <text x="140" y="145" text-anchor="middle" fill="var(--positive)" font-family="var(--ff-mono)" font-size="11">VPN IP: 10.66.0.1 (wg0)</text>

            <!-- Node 2: Elastic Stack / Kibana -->
            <rect x="270" y="80" width="180" height="90" rx="12" fill="var(--surface-bright)" stroke="var(--stroke-default)"/>
            <text x="360" y="105" text-anchor="middle" fill="var(--on-surface)" font-family="var(--ff-sans)" font-size="14" font-weight="600">Elastic Stack &amp; Kibana</text>
            <text x="360" y="125" text-anchor="middle" fill="var(--on-surface-variant)" font-family="var(--ff-mono)" font-size="12">Port 9200 / 5601</text>
            <text x="360" y="145" text-anchor="middle" fill="var(--on-surface-variant)" font-family="var(--ff-mono)" font-size="11">Filebeat / auth.log</text>

            <!-- Node 3: OpenSSH & IPTables -->
            <rect x="50" y="240" width="180" height="90" rx="12" fill="var(--surface-bright)" stroke="var(--stroke-default)"/>
            <text x="140" y="265" text-anchor="middle" fill="var(--on-surface)" font-family="var(--ff-sans)" font-size="14" font-weight="600">OpenSSH &amp; IPTables</text>
            <text x="140" y="285" text-anchor="middle" fill="var(--on-surface-variant)" font-family="var(--ff-mono)" font-size="12">Port 22 (SSH)</text>
            <text x="140" y="305" text-anchor="middle" fill="var(--error)" font-family="var(--ff-mono)" font-size="11">DROP 10.10.17.15 Rule</text>

            <!-- External Attacker Node: Kali Linux -->
            <rect x="560" y="240" width="200" height="90" rx="12" fill="var(--surface-bright)" stroke="var(--error)" stroke-width="2"/>
            <text x="660" y="265" text-anchor="middle" fill="var(--on-surface)" font-family="var(--ff-sans)" font-size="14" font-weight="600">Kali Linux (Attacker)</text>
            <text x="660" y="285" text-anchor="middle" fill="var(--error)" font-family="var(--ff-mono)" font-size="12">IP: 10.10.17.15</text>
            <text x="660" y="305" text-anchor="middle" fill="var(--on-surface-variant)" font-family="var(--ff-mono)" font-size="11">Hydra SSH Brute Force</text>

            <!-- Remote Analyst Workstation (Zero Trust) -->
            <rect x="560" y="80" width="200" height="90" rx="12" fill="var(--surface-bright)" stroke="var(--positive)" stroke-width="2"/>
            <text x="660" y="105" text-anchor="middle" fill="var(--on-surface)" font-family="var(--ff-sans)" font-size="14" font-weight="600">Analyst Workstation</text>
            <text x="660" y="125" text-anchor="middle" fill="var(--positive)" font-family="var(--ff-mono)" font-size="12">VPN Client: 10.66.0.2</text>
            <text x="660" y="145" text-anchor="middle" fill="var(--on-surface-variant)" font-family="var(--ff-mono)" font-size="11">Encrypted Tunnel (WireGuard)</text>

            <!-- Connections -->
            <!-- Debian -> Elastic -->
            <line x1="230" y1="125" x2="270" y2="125" stroke="var(--primary)" stroke-width="1.5" stroke-dasharray="0 4" stroke-linecap="round" marker-end="url(#caret)"/>
            
            <!-- Debian -> SSH/IPTables -->
            <line x1="140" y1="170" x2="140" y2="240" stroke="var(--stroke-default)" stroke-width="1.5" stroke-dasharray="0 4" stroke-linecap="round"/>

            <!-- Attacker Kali -> SSH (Attacking line) -->
            <path d="M 560 285 L 230 285" fill="none" stroke="var(--error)" stroke-width="1.5" stroke-dasharray="0 4" stroke-linecap="round" marker-end="url(#caret-red)"/>
            <rect x="330" y="275" width="130" height="20" rx="10" fill="var(--surface-dim)"/>
            <text x="395" y="289" text-anchor="middle" fill="var(--error)" font-family="var(--ff-mono)" font-size="10">Hydra Attack Vector</text>

            <!-- Analyst -> Debian (WireGuard VPN Tunnel) -->
            <path d="M 560 125 L 230 125" fill="none" stroke="var(--positive)" stroke-width="2" stroke-dasharray="0 4" stroke-linecap="round" marker-end="url(#caret)"/>
            <rect x="330" y="115" width="130" height="20" rx="10" fill="var(--positive-container)"/>
            <text x="395" y="129" text-anchor="middle" fill="var(--positive)" font-family="var(--ff-mono)" font-size="10" font-weight="600">WireGuard UDP:51820</text>

          </svg>
        </div>

        <!-- WireGuard Key Configuration Summary Table -->
        <div class="panel-header" style="margin-top: 10px;">
          <div class="panel-title">
            <span class="material-symbols-outlined">key</span>
            <span>Chaves de Autenticação WireGuard VPN</span>
          </div>
        </div>

        <table class="data-table">
          <thead>
            <tr>
              <th>Ativo</th>
              <th>IP Físico</th>
              <th>IP na VPN (wg0)</th>
              <th>Chave Pública (Public Key)</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><strong>Debian Server</strong></td>
              <td><code>10.10.17.18</code></td>
              <td><code>10.66.0.1/24</code></td>
              <td><code>NN8WcEfilfWGzZN9wHlRl2xs+oe4rQYihzYIMxMu5H4=</code></td>
            </tr>
            <tr>
              <td><strong>Kali Linux / Client</strong></td>
              <td><code>10.10.17.15</code></td>
              <td><code>10.66.0.2/24</code></td>
              <td><code>zjntTmm5QTIR66xSoBdYMGZjK+NVwYVRolEdsIoCqFc=</code></td>
            </tr>
          </tbody>
        </table>

      </div>
    </div>

    <!-- TAB 3: Interactive Interview Simulator for It4us SOC N1 -->
    <div id="interview" class="tab-content">
      <div class="panel-card">
        <div class="panel-header">
          <div class="panel-title">
            <span class="material-symbols-outlined">quiz</span>
            <span>Guia Estratégico de Entrevista — Analista SOC N1 (It4us Cyber Security)</span>
          </div>
          <span class="pill-badge pill-info">Roteiro Tático</span>
        </div>

        <p style="color: var(--on-surface-variant); font-size: 14px;">
          Respostas estruturadas que conectam 10 anos de liderança em segurança privada com o conhecimento técnico acadêmico (UNIP + Hackers do Bem) e a prática direta em SIEM / WireGuard.
        </p>

        <!-- Flashcards Stack -->
        <div style="display: flex; flex-direction: column; gap: 12px;">
          
          <div class="qa-card open" onclick="toggleQA(this)">
            <div class="qa-header">
              <span>1. Fale sobre você e sua trajetória profissional. Como ela se conecta com SOC N1?</span>
              <span class="qa-badge">Storytelling</span>
            </div>
            <div class="qa-body">
              "Iniciei na construção civil desenvolvendo disciplina de trabalho, atuei na indústria multinacional e trabalhei 10 anos na segurança privada, onde liderei equipes em cenários críticos. Essa bagagem me deu maturidade, atenção a detalhes e controle sob pressão. Migrei para cibersegurança de forma estruturada: concluí Tecnologia em Segurança da Informação pela UNIP e acumulei mais de 300 horas no Hackers do Bem (Especialização Blue Team). Hoje, uno essa postura de liderança e gestão de riscos físicos à prática digital em monitoramento SIEM."
            </div>
          </div>

          <div class="qa-card" onclick="toggleQA(this)">
            <div class="qa-header">
              <span>2. Como você atua ao receber um alerta crítico no turno noturno?</span>
              <span class="qa-badge">Metodologia N1</span>
            </div>
            <div class="qa-body">
              "Sigo o ciclo padronizado de SOC: 
              1. <strong>Triagem:</strong> Identifico a origem (IP), destino, usuário e horário exato.
              2. <strong>Validação:</strong> Verifico no SIEM se é um falso positivo ou um evento suspeito confirmado (ex: múltiplas falhas de autenticação seguidas de alteração em horário atípico).
              3. <strong>Documentação:</strong> Registro o ticket detalhado com evidências (logs brutos e hashes).
              4. <strong>Contenção/Escalonamento:</strong> Aplico a regra de contenção inicial autorizada (como isolamento de IP no firewall) e escalono para o N2/CSIRT conforme o playbook de severidade."
            </div>
          </div>

          <div class="qa-card" onclick="toggleQA(this)">
            <div class="qa-header">
              <span>3. Qual é sua experiência prática com ferramentas de SIEM (QRadar, Wazuh, Elastic)?</span>
              <span class="qa-badge">Laboratório Prático</span>
            </div>
            <div class="qa-body">
              "Em ambiente corporativo de produção estou buscando minha primeira oportunidade, mas possuo experiência direta montando e operando laboratórios de SOC. Configurei servidor Debian com Elasticsearch 8.x, Kibana e agentes Filebeat coletando logs de autenticação (`auth.log`). Disparei ataques de força bruta com Hydra a partir do Kali Linux, elaborei queries KQL para filtrar IoCs (`event.dataset: 'system.auth'`) e executei bloqueios com IPTables. A curva de adaptação ao QRadar ou Wazuh da operação será imediata."
            </div>
          </div>

          <div class="qa-card" onclick="toggleQA(this)">
            <div class="qa-header">
              <span>4. Como você lida com o trabalho em regime PJ, escala noturna e plantões de final de semana?</span>
              <span class="qa-badge">Disponibilidade</span>
            </div>
            <div class="qa-body">
              "Tenho total disponibilidade para início imediato e adaptação à escala noturna. Minha trajetória na segurança privada me acostumou com turnos, plantões e vigilância contínua durante a noite. Tenho postura profissional consolidada para atuar em regime PJ com suporte contábil e emissão de notas fiscais."
            </div>
          </div>

        </div>

      </div>
    </div>

    <!-- TAB 4: GitHub Documentation & README Tool -->
    <div id="github-repo" class="tab-content">
      <div class="panel-card">
        <div class="panel-header">
          <div class="panel-title">
            <span class="material-symbols-outlined">folder_zip</span>
            <span>Repositório GitHub do Laboratório (mcmcesar/soc-lab-elastic-kali)</span>
          </div>
          <span class="pill-badge pill-success">Public Repository</span>
        </div>

        <p style="color: var(--on-surface-variant); font-size: 14px;">
          Documentação completa formatada em Markdown para inclusão direta no GitHub e compartilhamento com recrutadores no LinkedIn.
        </p>

        <div class="code-box" style="max-height: 400px; overflow-y: auto;">
          <button class="copy-btn" onclick="copyText('readme-code')">
            <span class="material-symbols-outlined" style="font-size: 14px">content_copy</span> Copiar README.md
          </button>
<pre id="readme-code"># 🛡️ SOC Lab: Detecção, Resposta a Incidentes &amp; Conectividade Segura Zero Trust

Laboratório prático focado em operações de **Security Operations Center (SOC N1)**, cobrindo ingestão e análise de telemetria com Elastic Stack, contenção de ataques em nível de rede e implementação de canal seguro ponto a ponto via **WireGuard VPN**.

---

## 📌 Topologia do Ambiente

* **Servidor de Monitoramento / Alvo:** Debian GNU/Linux 13 (Trixie) - IP `10.10.17.18`
* **Estação de Ataque:** Kali Linux - IP `10.10.17.15`
* **SIEM &amp; Ingestão:** Elasticsearch 8.19.21 + Kibana (:5601) + Filebeat (`auth.log`)
* **Camada VPN Zero Trust:** WireGuard (Subrede `10.66.0.0/24`)

---

## 🔒 1. Camada de Acesso Seguro (WireGuard VPN)

Para simular o acesso remoto seguro corporativo a ativos críticos do datacenter:
* **Protocolo:** WireGuard integrado ao Kernel Linux.
* **Criptografia:** Chaves assimétricas Curve25519 e autenticação simétrica via `PresharedKey`.
* **Servidor Debian (`/etc/wireguard/wg0.conf`):** IP `10.66.0.1`
* **Cliente Kali (`/etc/wireguard/wg0.conf`):** IP `10.66.0.2`

---

## ⚔️ 2. Simulação de Ataque (SSH Brute Force)

A partir da estação Kali Linux (`10.10.17.15`), executou-se ataque automatizado de dicionário contra o serviço OpenSSH:

```bash
hydra -l root -P senhas.txt -t 4 10.10.17.18 ssh
```

---

## 🔍 3. Triagem e Investigação SIEM (KQL / Kibana)

Eventos de auditoria capturados pelo Filebeat em `/var/log/auth.log` foram analisados no Kibana Discover:

```kql
event.dataset: "system.auth" and event.outcome: "failure"
```

### Evidências Extraídas:
* **Origem do Ataque (`source.ip`):** `10.10.17.15`
* **Usuário Alvo (`user.name`):** `root`
* **Volume:** Múltiplas falhas consecutivas de credencial em intervalo inferior a 3 segundos.
* **Classificação MITRE ATT&CK:** T1110 (Brute Force).

---

## 🛑 4. Contenção e Resposta Ativa

Aplicação de bloqueio imediato na camada de rede com Netfilter/IPTables:

```bash
iptables -I INPUT -s 10.10.17.15 -j DROP
```

Após a aplicação da regra, novas tentativas sofreram descarte silencioso de pacotes (*Timeout*).
</pre>
        </div>

      </div>
    </div>

  </div>

  <footer>
    SOC N1 Operational Dashboard &amp; Portfolio | Desenvolvido para Marcos César Inácio da Luz | UNIP TSI
  </footer>

  <script>
    // Tab Switching Logic
    function switchTab(tabId) {
      document.querySelectorAll('.tab-btn').forEach(btn => btn.classList.remove('active'));
      document.querySelectorAll('.tab-content').forEach(content => content.classList.remove('active'));

      event.currentTarget.classList.add('active');
      document.getElementById(tabId).classList.add('active');
    }

    // QA Card Toggle Logic
    function toggleQA(cardEl) {
      cardEl.classList.toggle('open');
    }

    // Copy to Clipboard Utility
    function copyText(elementId) {
      const text = document.getElementById(elementId).innerText;
      navigator.clipboard.writeText(text).then(() => {
        alert('Texto copiado com sucesso!');
      }).catch(err => {
        console.error('Erro ao copiar: ', err);
      });
    }

    // Console Logging Helper for Simulator
    function logToTerminal(msg, type = 'info') {
      const term = document.getElementById('sim-terminal');
      const line = document.createElement('div');
      line.className = 'log-line';
      
      const time = new Date().toLocaleTimeString();
      let classType = 'log-info';
      if (type === 'error') classType = 'log-err';
      if (type === 'warn') classType = 'log-warn';
      if (type === 'success') classType = 'log-success';

      line.innerHTML = `<span class="log-dim">[${time}]</span> <span class="${classType}">${msg}</span>`;
      term.appendChild(line);
      term.scrollTop = term.scrollHeight;
    }

    function clearConsoleLog() {
      const term = document.getElementById('sim-terminal');
      term.innerHTML = '<div class="log-line log-dim">[SYSTEM RESET] Console limpo. Aguardando novas ações...</div>';
    }

    // Simulation Engine Functions
    let attackActive = false;
    let firewallActive = false;

    function runAttackSimulation() {
      logToTerminal("==================================================", 'warn');
      logToTerminal("DISPARANDO SIMULAÇÃO DE ATAQUE DE FORÇA BRUTA SSH", 'warn');
      logToTerminal("Comando: hydra -l root -P senhas.txt -t 4 10.10.17.18 ssh", 'dim');

      if (firewallActive) {
        setTimeout(() => {
          logToTerminal("[ATTACK REJECTED] [ERROR] could not connect to 10.10.17.18:22 - Connection timed out", 'error');
          logToTerminal("[SOC ALERT] Pacotes descartados pelo firewall IPTables (DROP rule 10.10.17.15)", 'success');
        }, 1000);
        return;
      }

      attackActive = true;
      let count = 0;
      const interval = setInterval(() => {
        count++;
        logToTerminal(`[KIBANA INGEST] PAM auth.log: Failed password for root from 10.10.17.15 port ${40000 + count} ssh2`, 'error');
        updateChart(1, 15);
        if (count >= 6) {
          clearInterval(interval);
          logToTerminal("[SOC ALERT] TRIAGEM KQL DETECTOU BRUTE FORCE DE 10.10.17.15 (INC-20260918-001)", 'warn');
          document.getElementById('ticket-status').innerText = 'CRÍTICO';
          document.getElementById('ticket-status').className = 'pill-badge pill-danger';
        }
      }, 500);
    }

    function applyFirewallBlock() {
      firewallActive = true;
      logToTerminal("==================================================", 'info');
      logToTerminal("[ACTION] Executando contenção no Debian: iptables -I INPUT -s 10.10.17.15 -j DROP", 'success');
      logToTerminal("[FIREWALL] Regra de descarte ativada para o IP 10.10.17.15 na porta de entrada.", 'success');
      document.getElementById('ticket-firewall-status').innerText = 'ATIVO (DROP Rule)';
      document.getElementById('ticket-firewall-status').style.color = 'var(--positive)';
      document.getElementById('ticket-status').innerText = 'CONTIDO';
      document.getElementById('ticket-status').className = 'pill-badge pill-success';
    }

    function testVpnTunnel() {
      logToTerminal("==================================================", 'info');
      logToTerminal("[WIREGUARD] Testando túnel seguro de 10.66.0.2 (Kali) -> 10.66.0.1 (Debian)", 'info');
      logToTerminal("[HANDSHAKE] Handshake completed 2 seconds ago. Transfer: 1.2 KiB sent, 1.4 KiB received", 'success');
      logToTerminal("[SSH LOG] ssh server@10.66.0.1 - Accepted password for server from 10.66.0.2 port 51820 ssh2", 'success');
    }

    // Chart.js Telemetry Chart Setup
    let metricsChart;
    function initChart() {
      const ctx = document.getElementById('metricsChart').getContext('2d');
      metricsChart = new Chart(ctx, {
        type: 'line',
        data: {
          labels: ['00:10', '00:11', '00:12', '00:13', '00:14', '00:15', '00:16'],
          datasets: [
            {
              label: 'Falhas SSH (10.10.17.15)',
              data: [0, 1, 0, 0, 12, 18, 0],
              borderColor: '#ff4c45',
              backgroundColor: 'rgba(255, 76, 69, 0.1)',
              fill: true,
              tension: 0.4
            },
            {
              label: 'Tráfego WireGuard (10.66.0.1)',
              data: [2, 3, 2, 4, 5, 8, 12],
              borderColor: '#0ebc5f',
              backgroundColor: 'transparent',
              tension: 0.4
            }
          ]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: {
            legend: {
              labels: { color: '#94a3b8', font: { family: 'Google Sans Flex', size: 11 } }
            }
          },
          scales: {
            x: { grid: { display: false }, ticks: { color: '#94a3b8', font: { size: 10 } } },
            y: { grid: { color: '#262d3d' }, ticks: { color: '#94a3b8', font: { size: 10 } } }
          }
        }
      });
    }

    function updateChart(vpnVal, errVal) {
      if (metricsChart) {
        const lastIdx = metricsChart.data.datasets[0].data.length - 1;
        metricsChart.data.datasets[0].data[lastIdx] += errVal;
        metricsChart.update();
      }
    }

    // Initialize Chart on Page Load
    document.addEventListener('DOMContentLoaded', () => {
      initChart();
    });
  </script>
</body>
</html>
```
