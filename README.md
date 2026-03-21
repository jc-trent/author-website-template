# The Indie Author Website Template

A free, no-code website for serial fiction authors. Built for LitRPG, progression fantasy, sci-fi, and anyone writing a multi-book series.

Your readers want to know three things: *When is the next book? How many books are planned? Is the series still active?* This site answers all of them in one place — no Discord archaeology required.

**What you need:** A free GitHub account and about an hour. That's it.

**What you don't need:** Any coding knowledge, any software to download, or any money. GitHub Pages hosts your site for free, forever.

---

## Before You Start: How This Works

If you've never touched anything like this before, here's the 30-second mental model.

Your website is made of simple text files. Some of them are configuration files that control how the site looks and behaves (think of them as settings). Others are content files where you type your actual words — book descriptions, your bio, blog posts.

All of these files live in a **repository** on GitHub. A repository is just a folder of files that GitHub stores for you online. When you edit a file and save it, GitHub automatically rebuilds your website. You never have to upload anything to a server or worry about hosting. You edit text, you click save, your site updates. That's the whole process.

You will encounter two types of files:

**`.yml` files** (pronounced "yammel") are settings files. They use a simple format: a label on the left, a colon, and a value on the right. Like this:

```yaml
title: "My Pen Name"
email: "me@example.com"
```

The only rule that matters: **indentation is sacred.** These files use spaces (not tabs) to show structure, and if the spacing is wrong, the site won't build. If something breaks after you edit a `.yml` file, check your spacing first.

**`.md` files** (Markdown) are content files. This is where you write your actual words. Markdown is just plain text with a few simple tricks: `**bold**` makes text **bold**, `*italic*` makes text *italic*, and `#` at the start of a line makes a heading. If you can write an email, you can write Markdown.

At the top of every `.md` file, you'll see a block of text between two lines of three dashes (`---`). This block is called **front matter** and it's where you put structured data about that page — things like the book title, the release date, and the blurb. Below the front matter is where freeform text goes.

One more concept: the `#` symbol. In these files, putting a `#` at the start of a line turns that line into a **comment** — the site ignores it completely. This is how you turn features on and off. If you don't have an audiobook yet, you don't delete the audiobook line — you just put a `#` in front of it. When you're ready, remove the `#` and it appears on your site.

```yaml
# This line is ignored by the site (it's "commented out")
audio_date: "June 2026"   # This line is active
```

That's everything you need to know. The rest is just following the steps below.

---

## Step 1: Create Your Site

1. If you don't have one, create a free account at [github.com](https://github.com).
2. Come back to this page and click the green **"Use this template"** button near the top right. Select **"Create a new repository."**
3. Name your repository **`yourusername.github.io`** — replace `yourusername` with your actual GitHub username. This specific name is what tells GitHub to turn this folder into a website.
4. Set it to **Public** and click **Create repository**.

You now have your own copy of all these files. Everything you change here only affects your site.

---

## Step 2: Turn On GitHub Pages

This tells GitHub to actually publish your site to the internet.

1. In your new repository, click the **Settings** tab at the top.
2. In the left sidebar, click **Pages**.
3. Under "Build and deployment," make sure the Source is set to **Deploy from a branch**.
4. Under "Branch," select **`main`** and click **Save**.

In about two minutes, your site will be live at `https://yourusername.github.io`. It'll look like a template with placeholder text — that's expected. Next step is making it yours.

---

## Step 3: Learn the One Skill You Need

Every change you make to your site follows the same three steps:

1. **Click on a file** to open it.
2. **Click the pencil icon** (top right of the file contents) to edit it.
3. **Make your changes**, then click the green **"Commit changes..."** button.

"Commit" is GitHub's word for "save." Every time you commit, GitHub rebuilds your site. Changes usually appear within a minute or two.

That's the only mechanical skill required. Everything else in this guide is "open this file, change this text."

---

## Step 4: Make It Yours

You only need to touch four files. **Do not edit the `.html` files** — those are the engine that runs the site. You're just filling in the content.

### 4a. Your Settings — `_config.yml`

This is the command center. Open it and you'll see clearly labeled sections:

```yaml
title: "John Author"
author:
  name: "John Author"
  email: "author@yourdomain.com"
  newsletter_url: "https://yournewsletter.substack.com"
  amazon_url: "https://www.amazon.com/author/yourid"
```

Change these values to your own. The site uses them everywhere — your name in the header, your email in the footer, your newsletter link on buttons. Update them once here, and they update everywhere.

**If you don't have something yet** (no Amazon page, no newsletter), just leave the value as an empty string: `newsletter_url: ""`. The site will automatically hide any buttons that would link to nowhere.

This file also controls which book appears on your homepage:

```yaml
featured_series: "example-series"
featured_book: 1
```

The `featured_series` value must exactly match the `slug` in your series file (explained below). The `featured_book` number tells it which book in that series to feature.

**Important:** After editing `_config.yml`, your site may take an extra minute to rebuild. This file is special — it controls the entire site, so GitHub takes a moment to process changes.

### 4b. Your Colors — `assets/css/style.css`

Open this file. At the very top (the first 10 lines), you'll see the color settings:

```css
--accent: #b8862d;
--accent-glow: #d4993a;
```

These are hex color codes. If you want your buttons and accent colors to match your book covers, swap in your own hex codes. (Search "hex color picker" on Google to find one — you click a color and it gives you the code.)

You don't need to touch anything else in this file.

### 4c. Your Bio — `about.md`

Open this file and replace the placeholder text with your actual author bio. Write normally — Markdown handles the formatting. Use `*italic*` for book titles, leave a blank line between paragraphs, and that's about it.

### 4d. Your Books — `_series/example-series.md`

This is the most important file. Open it and you'll see structured data describing a series and its books.

**First, rename the file.** Click on it, click the pencil to edit, and you'll see the filename at the top of the editor. Change `example-series.md` to something that matches your series — like `my-series-name.md`. Use lowercase letters and dashes instead of spaces.

**Then update the `slug` field inside the file to match the new filename** (without the `.md`). This is how the homepage knows which series to feature.

```yaml
title: "My Awesome Series"
slug: my-series-name       # Must match the filename
```

Now fill in the rest. Every field has a comment next to it explaining what it does. Here's the key insight: **almost every field is optional.** The site adapts to whatever you provide.

Have comp titles? Fill them in. Don't? Delete the line or put a `#` in front of it. The site won't show an empty box — it just skips that section entirely. Same goes for audiobook dates, Goodreads links, word counts, and everything else. Start with just a title and blurb, and add more as you have it.

**To add more books to a series**, copy the entire block for Book 1 (everything from the `-` before `title:` down to the last field), paste it below, and change the details. The `-` at the start is important — it tells the system "this is the next book in the list."

**To add a second series**, create a new file in the `_series` folder. Click into `_series`, click **Add file > Create new file**, name it `your-second-series.md`, and paste in the structure from your first series file as a starting point. Change the `slug`, `order` (set it to `2` so it sorts after your first series), and fill in the new series data.

---

## Step 5: Adding Book Covers

If you don't have cover art yet, do nothing. Leave the `cover:` line in your series file commented out with a `#` and the site will show a clean placeholder.

When you're ready:

1. Go to the `assets` folder, then `img`.
2. Click **Add file > Upload files**. Drag your cover image onto the page (JPG or PNG, ideally around 1600 x 2560 pixels for a standard book ratio).
3. Click **Commit changes** to save it.
4. Go back to your series file and update the cover line:

```yaml
cover: "/assets/img/my-cover.jpg"    # filename must match exactly
```

Make sure there's no `#` in front of the line — that would comment it out and hide it.

---

## Step 6: Writing Update Posts

The Updates page shows posts in reverse chronological order — newest first. Use it for milestone announcements: "Book 3 is with the editor," "Series extended from 5 to 7 books," "Audio for Book 1 is now available."

To create a post:

1. Go to the `_posts` folder.
2. Click **Add file > Create new file**.
3. Name it with the date first, followed by a short name: `2026-10-31-book-three-update.md`. The date format matters — it must be `YYYY-MM-DD`.
4. Add front matter at the top:

```yaml
---
layout: post
title: "Book 3 Status Update"
description: "A short summary that appears on the Updates page."
date: 2026-10-31
---
```

5. Write your post below the second `---`. Plain text, Markdown formatting.
6. Click **Commit changes**.

The post will automatically appear on your Updates page.

---

## Step 7: Custom Domain (Optional)

Your site works fine at `yourusername.github.io`. But if you want a professional URL like `www.yourpenname.com`, you can set one up for about $10–15 per year.

1. Buy a domain from a registrar like Namecheap, Porkbun, or Cloudflare.
2. In your registrar's DNS settings, add A records pointing to GitHub's IP addresses. Search "GitHub Pages custom domain setup" for the current IPs — they update occasionally.
3. In your repository, go to **Settings > Pages**. Under "Custom domain," type your new URL and click Save.
4. GitHub will create a file called `CNAME` in your repository. Don't delete it — it's what connects your domain to your site.
5. Once DNS propagates (can take up to an hour), check the **Enforce HTTPS** box in your Pages settings.

---

## Troubleshooting

Something broke? Don't panic. It's almost always a typo.

**The most common mistake** is breaking the spacing in a `.yml` or `.md` file. These files are picky about indentation. If your site stops building after an edit, look at what you just changed and check for missing quotes, extra spaces, or lines that aren't aligned with the ones above them.

**To see what you changed**, go to your repository's main page and look at the recent commits. Each one shows exactly what text was added or removed. If you can spot the mistake, edit the file and fix it. If you can't, undo the change by copying the original text from the commit history.

**The fastest fix** for confusing errors is to copy the error message and the file you were editing, paste them into an AI (ChatGPT, Gemini, Claude — any of them work), and ask: *"I'm editing a Jekyll site on GitHub Pages. I changed this file and got this error. What did I break?"* It will almost always tell you the exact line.

**If you're truly stuck** after trying the above, you can reach out. No guarantees on response time — my priority is writing books, not tech support — but I'll help if I can.

---

## Why This Exists

I write in the progression fantasy and LitRPG space. If you've spent any time in this community, you've seen the pattern: someone asks "when is the next book coming out?" and the answer is "the author said something in a Patreon post eight months ago, but I think plans changed since then." The information exists, it's just scattered across Discord pins, Reddit threads, and locked posts that become impossible to find.

I wanted a single page where a reader could see: how many books are planned, when each one comes out, whether the series is on track, and whether audio is available. No hunting, no secondhand information, no asking on Reddit and hoping someone remembers.

I built this for my own site, and I'm sharing it because the whole community would benefit if more authors did this. The template is free, the hosting is free, and the time investment is about an hour. If it helps even a few authors communicate better with their readers, it was worth open-sourcing.

Use it, modify it, make it yours. No attribution required (though there's an optional template credit link in the nav if you want to leave it on and help other authors find it).
# author-website-template
