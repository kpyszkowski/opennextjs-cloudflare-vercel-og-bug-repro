# OpenNext - Cloudflare: `@vercel/og` bug reproduction repository

I prepared API route `/api/og-image`.

It accepts optional `text` search parameter. Fallback text is rendered if
parameter is not provided.

Route works on NextJS development environment. However fails when attempting to
build for Worker crashing the process. The solution would be to patch the bundle
by replacing `@vercel/og` files with
[`workers-og`](https://github.com/kvnang/workers-og) library which is (almost)
1:1 reimplementation that works on Cloudflare Workers.

More context: https://github.com/opennextjs/opennextjs-cloudflare/issues/133
