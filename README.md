# Ssb – simple static blogger

Ssb is a suckless static site generator and blogging anti-framework written as a
single file shell script. It is useful for creating very simplistic blogs based
on Markdown writing. If you're looking for a blogging tool that takes nearly no
time to set up and just want to start writing with Markdown, then ssb is a
perfect program for the task.

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

## Installation

You can either download the source code release and manually place it in your
PATH (or better use `install(1)`), or use the homebrew release:
`brew install maciejzj/ssb/ssb`.

POSIX compliant shell and a markdown renderer (pandoc by default) are the only
requirements. If using homebrew packaging pandoc is installed as a dependency.

## Jump start

1. Run `ssb -g` to generate html and css templates. Adjust the header and
   the footer to your liking, you can customize the stylesheet, use a css theme,
   or your favourite style for Markdown.
2. Write your `index.md` page and some Markdown posts in `posts` directory.
3. Run `ssb index.md` to generate `html` files. Ssb will append the header, the
   list of posts and the footer to each file.
4. The timestamps near posts titles are generated from modification dates of
   Markdown files. If you wish to change them use the `touch` command (.e.g.
   `touch -t YYMMDDhhmm`).
5. Publish your blog.

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
ssb - simple static blogger.

Translates input markdown files to html pages. Attaches html header and
footer to each output. Files from the posts directory are appended to a
blog list at the end of each html.

Usage: ssb [-d|-g|-h|-r] [-e HEADER_PATH] [-f FOOTER_PATH][-m MD_RENDERER]
                         [-o OUTPUT_DIR] [-p POSTS_DIR] <MARKDOWN_FILES ...>

Positional arguments:
  MARKDOWN_FILES - Paths to arbitrary number of markdown files that will be
  translated into html files but not appended to the posts list (but will still
  display it at the bottom). It is intended to pass index.md here.

Options:
  -d Don't attach posts list to each html file.
  -g Generate html templates for header, footer and stylesheet.
  -h Show this help message.
  -r Recurse the posts directory.
  -v Be verbose (print each command being executed).

  -e HEADER_PATH Path to a header html file (header.html by default).
  -f FOOTER_PATH Path to a footer html file (footer.html by default).
  -m MD_RENDERER Markdown renderer command name. Must be able to read
     markdown form stdin and output html to stdout (pandoc by default).
  -o OUTPUT_DIR Output directory for html files (. by default).
  -p POSTS_DIR Path to a directory with markdown posts (posts by default).

Usage tips:

The timestamps near posts titles are generated from modification dates of
Markdown files.

If you wish to change them use the touch command (touch -t YYMMDDhhmm).

Credentials: https://github.com/maciejzj/ssb
```

## Other tips

Stylesheets for theming can be found
[here](https://github.com/maciejzj/ssb-themes).

You can grab the following Makefile starter to use ssb in a more comfortable
way:

```makefile
markdown_pages := index.md

posts_dir := posts
output_dir := docs

markdown_posts := $(wildcard $(posts_dir)/*.md)

# Main markdown pages
generated_files := $(foreach page,$(markdown_pages),$(patsubst %.md,$(output_dir)/%.html,$(page)))
# Append posts pages
generated_files += $(foreach post,$(markdown_posts),$(patsubst $(posts_dir)/%.md,$(output_dir)/%.html,$(post)))

.DEFAULT: compile

compile: $(generated_files)

$(generated_files): $(markdown_pages) $(markdown_posts)
	ssb -p $(posts_dir) -o $(output_dir) $(markdown_pages)

.PHONY: clean

clean:
	rm -f $(generated_files)
```

## Acknowledgements

Thanks to [Bartosz Pacia](https://github.com/bartekpacia) for an idea for
homebrew installation and initial package setup.
