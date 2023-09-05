# Epic Stack with Fathom Analytics

[Fathom Analytics](https://usefathom.com/ref/CDDARA) is the recommanded [analytics service](https://github.com/epicweb-dev/epic-stack/blob/11defa5cdd787c8b07a4d103f0b1bd79accdfa83/docs/features.md?plain=1#L48) by the Epic Stack (not definitive).

Fathom Analytics uses simple embed script tag to work.

## Steps

You can get all your the changes required on [this commit](https://github.com/xstevenyung/epic-stack-with-fathom-analytics/commit/2626fe1af922f2094ed63cbbb5e8f88e12e08a9f)

## Prepare for production

1. Create your new project on [Fathom Analytics website](https://usefathom.com/ref/CDDARA)
2. Once your project is created, add in your `.env` your `FATHOM_ANALYTICS_SITE_ID` (don't forget to replicate your change in your `.env.example` for good mesure) or add in on Fly.io for production using `fly secrets set FATHOM_ANALYTICS_SITE_ID=your-site-id`
