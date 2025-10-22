# How to Add New Blog Posts

This guide explains how to add new blog posts to your personal website.

## Quick Steps

1. **Copy the template**
2. **Edit the content**
3. **Update the blog index**
4. **Update the RSS feed**

---

## Detailed Instructions

### Step 1: Create Your New Post

1. Navigate to the year folder (e.g., `my-thoughts/2025/`)
   - If the year folder doesn't exist yet, create it: `mkdir my-thoughts/YYYY/`

2. Copy the template file to create your new post:
   ```bash
   cp my-thoughts/2025/first-post.html my-thoughts/2025/your-post-slug.html
   ```

   **Naming convention:** Use lowercase letters, numbers, and hyphens only
   - ✅ Good: `marketing-automation-tips.html`
   - ❌ Bad: `Marketing Automation Tips.html`

### Step 2: Edit Your Post File

Open your new post file and update these sections:

#### In the `<head>` section:

1. **Title tag** (line 6):
   ```html
   <title>Your Actual Post Title | My Thoughts | Brian Franklin</title>
   ```

2. **Meta description** (line 7):
   ```html
   <meta name="description" content="A compelling 1-2 sentence summary of your post.">
   ```

3. **Open Graph title** (line 13):
   ```html
   <meta property="og:title" content="Your Actual Post Title">
   ```

4. **Open Graph description** (line 14):
   ```html
   <meta property="og:description" content="A compelling 1-2 sentence summary of your post.">
   ```

5. **Open Graph URL** (line 12):
   ```html
   <meta property="og:url" content="https://brianfranklin.me/my-thoughts/YYYY/your-post-slug.html">
   ```

6. **Published date** (line 16):
   ```html
   <meta property="article:published_time" content="YYYY-MM-DD">
   ```

7. **Twitter card title** (line 22):
   ```html
   <meta property="twitter:title" content="Your Actual Post Title">
   ```

8. **Twitter card description** (line 23):
   ```html
   <meta property="twitter:description" content="A compelling 1-2 sentence summary of your post.">
   ```

9. **Twitter card URL** (line 21):
   ```html
   <meta property="twitter:url" content="https://brianfranklin.me/my-thoughts/YYYY/your-post-slug.html">
   ```

10. **Canonical URL** (line 28):
    ```html
    <link rel="canonical" href="https://brianfranklin.me/my-thoughts/YYYY/your-post-slug.html">
    ```

#### In the `<body>` section:

1. **Post title** (around line 46):
   ```html
   <h1 class="post-title">Your Actual Post Title</h1>
   ```

2. **Post date** (around line 50):
   ```html
   <i class="far fa-calendar"></i> May 15, 2025
   ```

3. **Post content** (starting around line 55):
   Replace all the placeholder content with your actual blog post content.

### Step 3: Update the Blog Index

Open `my-thoughts/index.html` and add your post to the list:

```html
<li class="post-item">
    <div class="post-date">May 15, 2025</div>
    <h2 class="post-title"><a href="2025/your-post-slug.html">Your Actual Post Title</a></h2>
    <p class="post-excerpt">A brief 1-2 sentence summary that entices readers to click...</p>
    <a href="2025/your-post-slug.html" class="read-more">Read more</a>
</li>
```

**Important:** Add new posts at the TOP of the list (newest first).

### Step 4: Update the RSS Feed

Open `my-thoughts/feed.xml` and:

1. Update the `<lastBuildDate>` (line 10):
   ```xml
   <lastBuildDate>Day, DD Mon YYYY HH:MM:SS GMT</lastBuildDate>
   ```
   Example: `Wed, 15 May 2025 00:00:00 GMT`

2. Add your new post as an `<item>` (add at the top, after line 11):
   ```xml
   <item>
     <title>Your Actual Post Title</title>
     <link>https://brianfranklin.me/my-thoughts/2025/your-post-slug.html</link>
     <guid>https://brianfranklin.me/my-thoughts/2025/your-post-slug.html</guid>
     <pubDate>Wed, 15 May 2025 00:00:00 GMT</pubDate>
     <description>A brief 1-2 sentence summary of your post.</description>
     <author>Brian Franklin</author>
   </item>
   ```

**Important:** Add new posts at the TOP of the feed (newest first).

### Step 5: Commit and Push

```bash
git add .
git commit -m "Add new blog post: Your Post Title"
git push
```

---

## Tips for Writing Good Posts

### SEO Tips
- Keep titles under 60 characters
- Keep meta descriptions between 150-160 characters
- Use descriptive, keyword-rich titles
- Make excerpts compelling and actionable

### Content Tips
- Use headings (`<h2>`, `<h3>`) to break up long sections
- Keep paragraphs short (3-4 sentences max)
- Use bullet points for lists
- Use blockquotes for important callouts
- Include examples and specific details

### URL Slug Tips
- Keep it short (3-5 words max)
- Use keywords from your title
- Use hyphens to separate words
- Don't include dates in the slug (dates are in the folder)

---

## Example Workflow

Let's say you want to write a post titled "5 Marketing Automation Tips" on May 20, 2025:

1. **Create the file:**
   ```bash
   cp my-thoughts/2025/first-post.html my-thoughts/2025/marketing-automation-tips.html
   ```

2. **Edit the file:** Update all meta tags and content as described above

3. **Update index.html:** Add the post entry at the top of the list

4. **Update feed.xml:** Add the post item at the top

5. **Commit:**
   ```bash
   git add .
   git commit -m "Add blog post: 5 Marketing Automation Tips"
   git push
   ```

---

## Newsletter Integration Ideas

Your RSS feed at `https://brianfranklin.me/my-thoughts/feed.xml` can be connected to:

- **Substack** - Import RSS feed to auto-post to newsletter
- **Buttondown** - RSS-to-email automation
- **ConvertKit** - RSS feed automation
- **Mailchimp** - RSS campaigns
- **Feedburner** - RSS management and analytics

Most of these services can automatically email your subscribers when you publish a new post!

---

## Need Help?

If you want to add features like:
- Comments
- Search
- Tags/categories
- Reading time estimates
- Related posts
- Social sharing buttons

Let me know and I can help add those!
