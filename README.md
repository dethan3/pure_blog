# pure_blog

A tiny personal blog made with the simplest possible web stack: one `index.html` file, plain HTML, plain CSS, no framework, no build step, no JavaScript.

## How to edit

Open `index.html` and edit the text directly.

To add a new post:

1. Add one item to the article list inside `<ul class="note-list">`.
2. Copy an existing `<article>` block.
3. Give it a new `id`, date, title, and body.
4. Make the list item link to that `id`, for example `href="#my-new-post"`.

## How to publish with GitHub Pages

1. Open this repository on GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select branch `main` and folder `/root`.
5. Save.

After GitHub Pages finishes deploying, the site should be available from the URL shown in the Pages settings.

## Design principle

Keep it small. Keep it readable. Keep it easy to reopen years later.
