# CodeMitra frontend deployment

The frontend is a static single-page app and can stay on GitHub Pages at no hosting cost.

## GitHub Pages

1. Merge the reviewed frontend pull request into `main` when ready.
2. In repository Settings → Pages, select **Deploy from a branch**, branch `main`, folder `/ (root)` (or retain the repository's existing Pages workflow if one is configured).
3. Wait for the Pages deployment to finish, then open https://kayrootyt.github.io/codemitra-app/.

## Connect the Oracle-hosted backend

1. Open CodeMitra → Settings.
2. Set **Backend server URL** to the HTTPS hostname configured for the API, for example `https://api.example.com` (no trailing slash is needed).
3. Save and run the backend health check.
4. Ensure the backend's `ALLOWED_ORIGINS` contains exactly `https://kayrootyt.github.io`.

The backend URL is saved in the current browser's local storage. It is not a build-time secret and should not contain API keys. Never put NVIDIA, Hugging Face, or ElevenLabs credentials in this frontend repository.

## Smoke test

- Health check succeeds.
- A Hindi and an English chat response stream to completion.
- Attach a small image, text file and ZIP and confirm the backend receives them.
- Generate a project ZIP and verify the archive opens.
- Test Hindi male and female speech.
- Test on mobile and after refreshing the page.

The static frontend can be served publicly; all provider credentials and privileged operations must remain on the backend.
