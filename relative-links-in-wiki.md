GitHub supports relative links in markup files. 

This means your documentation can now easily stand on its own, without always pointing to GitHub.

You can link directly between different documentation files, whether you view the documentation on GitHub itself, or locally, using a different markup renderer.

You want examples of link definitions and how they work? Here's some Markdown for you.
Instead of an absolute link:

    [a link](https://github.com/user/repo/blob/branch/other_file.md)

    …you can use a relative link:

    [a relative link](other_file.md)

and github makes sure it gets linked to user/repo/blob/branch/other_file.md.

If you were using a workaround like [a workaround link](repo/blob/master/other_file.md), you'll have to update your documentation to use the new syntax.
