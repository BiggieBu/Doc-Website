---
sidebar_position: 2
---
# Docs
## Markdown
- header section: (sidebar_position: x), specifies relative sidebar position
- body: simple markdown file
- all ## and lower entries display a link when mouse hovers on the side
- markdown files only contain the content. It doesn't contain:
    - path address(all pages contain th  is)
    - edit option
        - Only present in markdown files and not dropdown folders
        - auto-generated and hooked to base address
        - currently doesn't work because it's hooked to docusaurus github repo
    - navigation button
        - all pages contain them
        - They are auto generated

## Website 
- the structure of page also contains a section that highlights heading on scroll on top right of the screen
- There is also a side bar on the left and a footer with necessary links
- routes for each of the pages and dropdowns 

## Dropdowns
- The documentation dropdown hierarchy is created via simple folder hierarchy specified using a _category_.json file
- docs folder in the repo folder is the root for hierarchy. Therefore, intro.md is the first doc file.
- It's displayed as title/label, description and pages link buttons(displaying there title and desc) 

### _category_.json
- Label: displayed at sidebar dropdown
- position: sidebar index
- link
    - ? type:Eg- generated index ?
    - description: dropdown description