# Remove private data when adding files to git

## Info

git provides filters which you can access via
your `attributes` and `config` files.

This is how to set up a simple clean filter.

## Context

More info here:

http://git-scm.com/book/ch7-2.html
https://github.com/gilesbowkett/git-smudge-and-clean

## How It Works

The files `git.config.sample` and
`git.attributes.sample` show lines you should
add to your `config` and `attributes` files in
order to make this work. Those files live at
either `.git/info/attributes` (project-local)
or `.gitattributes` (global), for `attributes`,
and either `.git/config` (project-local) or
`.gitconfig` (global), for `config`.

You will also need to put the full path of this
clean script in your git config section.

## Example

Your code looks something like this.
```
#GIT_CLEAN 555-555-5555 xxx-xxx-xxx
phone=555-555-5555
#GIT_CLEAN "secret string" xxxx
secet="secret string"
```

When added to your staging area, you will see.
```
phone=xxx-xxx-xxxx
secet="xxxx"
```

