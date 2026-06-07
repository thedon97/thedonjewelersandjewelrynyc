# The Don Jewelers & Jewelry

Vercel-ready static jewelry website with a serverless Labgrown Diamond inventory proxy.

## Deploy on Vercel

1. Upload or push this project to GitHub.
2. Import the repository into Vercel.
3. Add these Vercel environment variables:
   - `LGD_API_KEY`
     - This must be added in Vercel Project Settings > Environment Variables for Production.
     - After adding it, redeploy the site. Environment variables do not apply to an already-built deployment.
   - `LGD_API_URL` set to `https://lgdusallc.com/developer-api/diamond`
   - `DIAMOND_CACHE_TTL_MS` set to `900000`
4. Use the default Vercel build settings. The build command is `npm run build`.

## Notes

- Do not commit a real `.env` file or private API key.
- Static files and images are served from the project root: `index.html`, `main.js`, `styles.css`, and image files.
- The live diamond feed is served through `/api/diamonds` so the private vendor API key stays server-side.
- `/api/diamonds` supports `?type=certified&page=1` for white certified diamonds and `?type=certified_color&page=1` for certified color diamonds.
- Checkout uses the configured Stripe Buy Button/payment link in `main.js`.
- Stripe Pay Now currently points to `https://buy.stripe.com/14A5kEeX9aYgfrKfCw5kk00`.
