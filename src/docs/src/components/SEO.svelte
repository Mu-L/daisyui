<script>
  import { siteData } from "@src/lib/data.js"

  import { readEnv } from "$lib/util"

  export let title = ""
  export let desc = siteData.desc
  export let img = siteData.card

  $: formattedTitle = title ? `${title} — ${siteData.title}` : siteData.title
</script>

<svelte:head>
  <title>{formattedTitle}</title>
  <meta name="description" content={desc} />
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:title" content={formattedTitle} />
  <meta name="twitter:description" content={desc} />
  <meta name="twitter:image" content={readEnv("VITE_ROOT") + img} />
  <meta name="twitter:image:alt" content={formattedTitle} />
  <meta property="og:title" content={formattedTitle} />
  <meta property="og:description" content={desc} />
  <meta property="og:image" content={readEnv("VITE_ROOT") + img} />
</svelte:head>
