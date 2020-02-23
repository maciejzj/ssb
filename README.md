# Ssb – simple static blogger

Ssb is a suckless static site generator and blogging anti-framework.
It is useful for creating very simplistic blogs based on markdown writing.
If you're looking for a blogging tool that takes nearly no time to setup and
learn to use and want to just start writing with markdown ssb is perfect for
the task.

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
2. Download ssb and place it in your `PATH` or inside your blog directory.
3. Run `ssb -g` to generate html and css templates. Adjust the header and
   the footer to your liking, you can customize the stylesheet, use a css theme,
   or your favourite style for markdown.
4. Write your index.md page and posts in `posts` directory.
5. Run `ssb index.md` to generate `html` files. Ssb will append header, list of
   posts and footer to each file.
6. The timestamps near posts titles are generated from modification dates of
   markdown files. 
   If you wish to change them use `touch -d` command on them.
7. Publish your blog.

## Features and non-features

* Ssb is a single POSIX compliant script that requires only a markdown renderer
  to create blogs.
* It is not a *real framework*, just a hackable script to automate blogging
  and save your time.
* No tags, no artifacts, no javascript, no learning, no lengthy setup.
* If you want a simple and effortless blogging engine ssb is perfect for you,
  whether you want something more features you can hack it, or use something
  more advanced like Jekyll or Hugo.
  
## Help
```
./ssb -h
Usage: ./ssb [-d|-g|-h|-r] [-e HEADER_PATH] [-f FOOTER_PATH] [-m MD_RENDERER]
                           [-o OUTPUT_DIR] [-p POSTS_DIR]
```
