# UNIFIX deployment

The Git repository root is the deployment root. The Vite application lives in `cambo/` as an npm workspace; run `npm install`, `npm run dev`, `npm run build`, or `npm run lint` from this repository root.

## Deployment

Vercel and Netlify configurations are included at the repository root. They build the `cambo` workspace and publish `cambo/dist`, with a single-page-app fallback to `index.html`.

Set these variables in the deployment provider's project environment settings before building:

- `VITE_SUPABASE_URL`
- `VITE_SUPABASE_PUBLISHABLE_KEY`

The local `cambo/src/.env.local` file is ignored by Git and will not be uploaded during deployment. Redeploy after setting or changing environment variables. Only use a Supabase publishable/anon key in a client-side app; never put a service-role secret in a `VITE_` variable.
