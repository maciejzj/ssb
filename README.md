# Ssb – simple static blogger

Ssb is a suckless static site generator and blogging anti-framework.
It is useful for creating very simplistic blogs based on Markdown writing.
If you're looking for a blogging tool that takes nearly no time to set up
and just want to start writing with Markdown, then ssb is a perfect script
for the task.

Ssb is heavily inspired and based on
[this](https://benedicthenshaw.com/static_site.html)
post.

## Generated site structure

```
+------------------------------+
| Header and navbar            |
+------------------------------+
|                              |
|                              |
| Body written in Markdown     |
|                              |
|                              |
+------------------------------+
|                              |
| List of posts                |
|                              |
+------------------------------+
| Footer                       |
+------------------------------+
```

## Jump start

1. A POSIX compliant shell and your favourite markdown renderer (pandoc by
   default) are required.
2. Download `ssb` and place it in your `PATH` or inside your blog directory.
3. Run `ssb -g` to generate html and css templates. Adjust the header and
   the footer to your liking, you can customize the stylesheet, use a css theme,
   or your favourite style for Markdown.
4. Write your `index.md` page and posts in `posts` directory.
5. Run `ssb index.md` to generate `html` files. Ssb will append header, list of
   posts and footer to each file.
6. The timestamps near posts titles are generated from modification dates of
   Markdown files. 
   If you wish to change them use the `touch` command.
7. Publish your blog.

## Features and non-features

* Ssb is a single POSIX compliant script that requires only a Markdown renderer
  to create blogs.
* It is not a *real framework*, just a hackable script to automate blogging
  and save your time.
* No tags, no artifacts, no javascript, no learning, no lengthy setup.
* If you want a simple and effortless blogging engine ssb is perfect for you,
  whether you want something with more features you can hack it, or use
  frameworks like Jekyll or Hugo.

## Help

```
$ ssb -h 
ssb - simple static blogger.

Translates input markdown files to html pages. Attaches html header and footer
to each output. Files from the posts directory are appended to a blog list at
the end of each html.

Usage: ../ssb/ssb [-d|-g|-h|-r] [-e HEADER_PATH] [-f FOOTER_PATH][-m MD_RENDERER]
                                [-o OUTPUT_DIR] [-p POSTS_DIR] <file ...>

Options:
 -d Don't attach posts list to each html file.
 -g Generate html templates for header, footer and stylesheet.
 -h Show this help message.
 -r Recurse the posts directory.

 -e HEADER_PATH Path to a header html file (header.html by default).
 -f FOOTER_PATH Path to a footer html file (footer.html by default).
 -m MD_RENDERER Markdown renderer command name. Must be able to read
    markdown form stdin and output html to stdout (pandoc by default).
 -o OUTPUT_DIR Output directory for html files (. by default).
 -p POSTS_DIR Path to a directory with markdown posts (posts by default).
```

## Other

Stylesheets for theming can be found
[here](https://github.com/maciejzj/ssb-themes).
