---
layout: post
title: jeckyll mathjax blog post
date: 2023-12-06 12:10:10
description: A step-by-step guide to displaying math equations in Jekyll using MathJax.
tags: Jekyll MathJax
categories: posts
giscus_comments: true
related_posts: true
---


# Displaying Math Equations in Jekyll Using MathJax

## Introduction

In this blog post, we'll discuss how to display math equations in a Jekyll site using MathJax, a popular JavaScript library for rendering mathematical notation.

## Step-by-Step Guide

### Adding MathJax to Your Jekyll Site

1. **Insert MathJax Script**: 
   Add the following script to the `<head>` section of your HTML layout file (in `_layouts` or the default layout of your theme):

   ```html
   <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
   <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
   ```

2. **Configure MathJax** (Optional): 
   Customize MathJax, such as changing delimiters for inline and display math. Here's an example:

   ```html
   <script>
     MathJax = {
       tex: {
         inlineMath: [['$', '$'], ['\(', '\)']],
         displayMath: [['$$', '$$'], ['\[', '\]']]
       },
       svg: {
         fontCache: 'global'
       }
     };
   </script>
   ```

### Writing Math Equations

- **Inline Math**: Enclose your LaTeX code within `$...$` for inline equations (e.g., `$x + y = z$`).
- **Displayed Math**: Use `$$...$$` for equations that should be on their own line (e.g., `$$x + y = z$$`).

### Troubleshooting

If inline math isn't rendering:
- **Check Configuration**: Ensure MathJax is configured to recognize `$...$` as inline math.
- **Markdown Processing**: Add space around your inline math, like `$ x + y = z $`.
- **Escape Characters**: Try escaping the dollar signs (e.g., `\$x + y = z\$`).

### Conclusion

With these steps, you should be able to display beautiful mathematical equations in your Jekyll site.

---

*Thank you for reading!*
