# table of contents

## Architecture
```mermaid
flowchart LR
    subgraph Authoring["Authoring"]
        A["Any device / editor"]
        N["Notion<br/>(optional)"]
    end

    subgraph Source["Source of Truth"]
        M["Markdown"]
        G["GitHub Repository"]
    end

    subgraph Build["Build"]
        GA["GitHub Actions"]
        H["Hugo"]
    end

    subgraph Hosting["Production"]
        S["Static HTML / CSS / JS"]
        P["Static Hosting"]
    end

    A --> M
    N -. "sync / export" .-> M
    M --> G

    G --> GA
    GA --> H
    H --> S
    S --> P

    P --> R["Reader"]
```

## Downloading the tools
1. hugo
`brew install hugo`

## Starting the service locally
1. `hugo server -D` (`-D` includes drafts)
2. open http://localhost:1313/blog/

## Writing a post
1. `hugo new content posts/my-post.md`
2. write in Markdown, add `tags`
3. set `draft = false` to publish

## Layout
- `hugo.toml`: site title, author, menu
- `content/`: posts and the about page
- `layouts/`: HTML templates
- `assets/css/main.css`: all styles (light and dark)
