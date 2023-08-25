# Epic Stack with Fathom Analytics

Fathom Analytics is the recommanded [analytics service](https://github.com/epicweb-dev/epic-stack/blob/11defa5cdd787c8b07a4d103f0b1bd79accdfa83/docs/features.md?plain=1#L48) by the Epic Stack (not definitive).

Fathom Analytics uses simple embed script tag to work.

## Steps

1. Create your new project on [Fathom Analytics website](https://usefathom.com)
2. Once your project is created, add in your `.env` your `FATHOM_ANALYTICS_SITE_ID` (don't forget to replicate your change in your `.env.example` for good mesure) or add in on Fly.io for production using `fly secrets set FATHOM_ANALYTICS_SITE_ID=your-site-id`
3. add Fathom Analytics site ID as an env variable in your `app/utils/env.server.ts`. don't forget to include it in your `schema` and your `getEnv` to expose the site ID to the client-side
4. add the script tag given by Fathom Analytics in `app/root.tsx` in the component `Document` but add `nonce` like below.
5. add `cdn.usefathom.com` in `server/index.ts` for `img-src`

```tsx
function Document({
  children,
  nonce,
  theme = 'light',
  env = {},
}: {
  children: React.ReactNode
  nonce: string
  theme?: 'dark' | 'light'
  env?: Record<string, string>
}) {
  return (
    <html lang="en" className={`${theme} h-full overflow-x-hidden`}>
      <head>
        <script
          type="text/javascript"
          nonce={nonce}
          src="https://cdn.usefathom.com/script.js"
          data-site={env.FATHOM_ANALYICS_SITE_ID}
          defer
        />
      </head>
    </html>
  )
}
```
