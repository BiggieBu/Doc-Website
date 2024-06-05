---
sidebar_position: 1
---
## Markdown Lang
- markdown link creation using [link text](link-address)
    - links can be external urls and internal urls or file paths 
- font size follows follow # hierarchy
- ** **bolds text**
    - "-" means bullet points
```<language-name>
"```"creates code blocks
```
or 
```text title=<file name>
\\highlight-start
highlighted section
\\highlight-end
not highlighted
```

- `` ` comments/highlights text``
:::note 
`::note`creates note section
:::
:::tip 
`::tip`creates tip section
:::
:::danger 
`::tip`creates tip section
:::
- --- creates front matter/header of markdown:
    - slug: /my-custom-url
    - description: My document description
    - title: My document title
    - id: my-doc-id
- ![Docusaurus logo](/img/docusaurus.png)
```md
    ![<name>](img path)
```
- .mdx allows for more versaitlity. It creates and uses react components directly inside markdown


