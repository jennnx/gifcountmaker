# Follower count gif maker

![followers_movie](/static/followers.gif)

I use this to make fancy follower/revenue videos for my own Twitter account!

I don't know After Effects, and I don't want to pay $15/month for something this simple.

## TLDR

### Step 1

```bash
npm install
```

### Step 2

```bash
npm run dev -- --open
```

### Step 3

Use something like OBS or QuicktimePlayer and take a video. Upload it to Twitter for free money.

## Details

- The text, numbers, timing, colors (gradients), etc. can all be adjusted in `src/routes/+page.svelte`

- The icon can be adjusted by adding a custom `<svg>` element. Replace `src/routes/followers.svelte` with it and import it accordingly.
  
  - Set `stroke-width="1.5"` and `height="1em" width="1em"` on the new svg.

- All the styling is in pure CSS. No need to have any svelte knowledge!