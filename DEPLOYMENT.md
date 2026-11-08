# CodeMitra frontend deployment

The frontend is a static single-page app and can stay on GitHub Pages at no hosting cost.

## GitHub Pages

1. Merge the reviewed frontend pull request into `main` when ready.
2. In repository Settings → Pages, select **Deploy from a branch**, branch `main`, folder `/ (root)` (or retain the repository's existing Pages workflow if one is configured).
3. Wait for the Pages deployment to finish, then open https://kayrootyt.github.io/codemitra-app/.

## Connect the no-card Render backend

1. Deploy the backend using the instructions in [the backend Render guide](https://github.com/KayrootYT/codemitra-backend/blob/feature/codemitra-quality-upgrade/DEPLOYMENT_RENDER.md).
2. Copy its HTTPS `onrender.com` URL.
3. Open CodeMitra → Settings.
4. Set **Backend server URL** to that URL (no trailing slash is needed), save, and run the backend health check.
5. Ensure backend `ALLOWED_ORIGINS` contains `https://kayrootyt.github.io`.

The backend URL is saved in the current browser's local storage. It is not a build-time secret and should not contain API keys. Never put NVIDIA, Hugging Face, or ElevenLabs credentials in this frontend repository.

## Smoke test

- Health check succeeds.
- A Hindi and an English chat response stream to completion.
- Attach a small image, text file and ZIP and confirm the backend receives them.
- Generate a project ZIP and verify the archive opens.
- Test Hindi male and female speech.
- Test on mobile and after refreshing the page.

The static frontend can be served publicly; all provider credentials and privileged operations must remain on the backend.
