---
title: "Hello World - My First Post"
date: "2024-01-15"
author: "John Doe"
tags: ["introduction", "blogging", "github"]
category: "general"
published: true
excerpt: "Welcome to my blog powered by GitHub as a CMS! Learn how this works."
coverImage: "/assets/images/posts/hello-world-cover.jpg"
slug: "hello-world"
---

# Hello World

Welcome to my blog! This is my first post using **Mini CMS** with GitHub as the database.

## Why GitHub as a CMS?

Using GitHub as a content management system provides several benefits:

- ✅ **Version Control** - Track all changes to your content
- ✅ **Free Hosting** - No database costs
- ✅ **Markdown Support** - Easy to write and read
- ✅ **Collaboration** - Use pull requests for content reviews

## How It Works

The architecture is simple:

1. Content is stored as Markdown files in GitHub
2. Frontend fetches content via GitHub's raw file URLs
3. Markdown is parsed and rendered in the browser

## Code Example

Here's a simple TypeScript example:

```typescript
interface Post {
  title: string;
  date: string;
  content: string;
}

const fetchPost = async (filename: string): Promise<Post> => {
  const response = await fetch(`https://raw.githubusercontent.com/.../${filename}`);
  const content = await response.text();
  return parseMarkdown(content);
};