# AI Agent Study — Public Demo

Static, standalone demo pages reproducing the two AI-assistance conditions of
the study — an **inline autocomplete** agent and a **conversational chatbot**
agent — for reviewers and readers of the paper to try out.

These are the **actual experiment pages**, copied verbatim from the study's Flask
templates. The only changes are:

- Google reCAPTCHA is stubbed out (no site key, no external Google call).
- Every backend request (`/generate-user-id`, `/verify-captcha`,
  `/save-response`, `/save-thank-you-time`, …) is intercepted client-side, so
  **nothing is saved, transmitted, or recorded**.
- The final redirect to the LimeSurvey questionnaire is replaced by an in-page
  placeholder that explains the questionnaire step and offers a clear link to
  continue to the debriefing page (`debriefing-demo.html`), matching the real
  study's flow (questions → LimeSurvey profile questionnaire → debriefing).
- The "Finish and Return to Prolific" buttons (shown on consent-declined,
  attention-check-failed, and unsupported-device screens) point to
  `prolific-placeholder.html` instead of the real Prolific submission URL.
- A "Demonstration only" banner is added at the top of each page.

The experiment logic itself — consent form, instructions, the agent behavior,
attention checks, confidence rating, timing — is **unmodified**.

## Files

- `index.html` — landing page linking to both demos
- `autocomplete-demo.html` — inline autocomplete agent (route `/copilot` in the study)
- `chatbot-demo.html` — conversational chatbot agent (route `/chatgpt` in the study)
- `debriefing-demo.html` — the post-study debriefing page (route `/debriefing-test`)
- `prolific-placeholder.html` — placeholder shown where the study returns to Prolific
- `.nojekyll` — tells GitHub Pages to serve the files as-is (skip Jekyll processing)


