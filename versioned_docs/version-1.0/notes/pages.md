---
sidebar_position: 3
---
# Pages
- all pages are stored in 'src/pages'
- pages can be in react or in markdown
- eg. index.js is homepage
- Pages are routed to their file names:
    - `src/pages/index.js` → `localhost:3000/`
    - `src/pages/foo.md` → `localhost:3000/foo`
    - `src/pages/foo/bar.js` → `localhost:3000/foo/bar`

# Documents
Group of pages connected through:
- a sidebar
- prev next nav
- versioning 
covered in docs.md

# Sidebar
metadata for sidebar also includes sidebar_label(default=first line) apart from sidebar_position
Sidebar can also be created explicitly(sidebars.js)

# Blogs
Blog posts are organized in a descending by date order in the blog section.

Slug names the url for the blog. There are other fields to template blogs and pages too.