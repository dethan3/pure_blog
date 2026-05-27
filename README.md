# pure_blog

A tiny personal blog built with plain web files: HTML, CSS, JavaScript, and JSON.

No backend. No framework. No package manager. No build step.

## Structure

```text
pure_blog/
  index.html              # Home page and post list
  post.html               # Single post template
  style.css               # Shared visual design
  posts/
    index.json            # Post index and metadata
    hello-pure-blog.json  # One post per JSON file
    simple-web.json
```

## How it works

- `index.html` reads `posts/index.json` and renders the article list.
- `post.html?slug=hello-pure-blog` reads `posts/index.json`, finds the matching post, then loads the linked post JSON file.
- `style.css` controls the whole site's appearance.
- Each article is data, not a separate handcrafted HTML page.

## How to publish a new post

Create a new file in `posts/`, for example:

```text
posts/2026-05-27-my-new-post.json
```

Use this shape:

```json
{
  "slug": "my-new-post",
  "title": "My New Post",
  "date": "2026-05-27",
  "summary": "A one sentence summary.",
  "tags": ["notes"],
  "content": [
    { "type": "p", "text": "First paragraph." },
    { "type": "h2", "text": "A section" },
    { "type": "p", "text": "Second paragraph." },
    { "type": "quote", "text": "A quote." },
    { "type": "ul", "items": ["One", "Two"] }
  ]
}
```

Then add one entry to `posts/index.json`:

```json
{
  "slug": "my-new-post",
  "title": "My New Post",
  "date": "2026-05-27",
  "summary": "A one sentence summary.",
  "file": "posts/2026-05-27-my-new-post.json",
  "tags": ["notes"]
}
```

The article will be available at:

```text
post.html?slug=my-new-post
```

## Supported content blocks

- `{ "type": "p", "text": "..." }`
- `{ "type": "h2", "text": "..." }`
- `{ "type": "h3", "text": "..." }`
- `{ "type": "quote", "text": "..." }`
- `{ "type": "ul", "items": ["..."] }`
- `{ "type": "ol", "items": ["..."] }`
- `{ "type": "code", "language": "text", "text": "..." }`
- `{ "type": "hr" }`

## Recommended writing workflow

Write naturally in Markdown first. When publishing, convert the Markdown into the JSON block format above.

In this repository's intended workflow, Ethan can write the post in ChatGPT, then ask ChatGPT to publish it to `pure_blog`; ChatGPT converts it into JSON and updates the repository.

## How to publish with GitHub Pages

1. Open this repository on GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select branch `main` and folder `/root`.
5. Save.

After GitHub Pages finishes deploying, the site should be available from the URL shown in the Pages settings.

## Design principle

Keep it small. Keep it readable. Keep it easy to reopen years later.
