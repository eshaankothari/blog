# Blog

Posts live in `posts/<study>/` as `post.md` + `data/*.csv` → `index.html`; `posts/index.html` is the home page. Built with `blog_module` (`~/Desktop/blog_module`) on the blog_style identity (`~/Desktop/blog_style`).

**Procedure for a new or updated post: use the `blog-post` skill** (`/blog-post posts/<study>`). It is the whole recipe — outline + CSVs in, finished post out, his text verbatim, checked on desktop and phone. Start there before touching a post.

Quick commands:
```
blog_module new posts/<study>            # outline.md + data/
blog_module data posts/<study>           # what's in the CSVs
blog_module build posts/<study>/post.md  # → index.html, refreshes posts/index.html (add --watch)
blog_module verify posts/<study>         # his outline paragraphs vs post.md, word for word
blog_module preview posts/<study>/post.md  # .preview/desktop.png + phone.png — look at both
```
