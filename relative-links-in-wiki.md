# Relative links

GitHub supports relative links in markup files. 

This means your documentation can now easily stand on its own, without always pointing to GitHub.

You can link directly between different documentation files, whether you view the documentation on GitHub itself, or locally, using a different markup renderer.

You want examples of link definitions and how they work? Here's some Markdown for you.
Instead of an absolute link:

    [a link](https://github.com/user/repo/blob/branch/other_file.md)

…you must use a relative link:

    [a relative link](other_file.md)

and github makes sure it gets linked to user/repo/blob/branch/other_file.md.

If you were using a workaround like [a workaround link](repo/blob/master/other_file.md), you'll have to update your documentation to use the new syntax.

Well it is not the end of the story more is possible , but it is a start toward better standards, and movable content.

# Images

<img src="../raw/master/photos/mavlab_logo.png" width="50%" />

The above image was inserted into the Wiki with:

  `<img src="../raw/master/photos/mavlab_logo.png" width="50%" />`

Note that with Github the Prieview function of a page does not work a 100% with image relative links. If you save the page, all is well.

# Tips
Read e.g.  https://stackoverflow.com/questions/7653483/github-relative-link-in-markdown-file
