# HnCC Learn (hLearn)
<!--
[Docsy](https://github.com/google/docsy) is a Hugo theme for technical documentation sites, providing easy site navigation, structure, and more. This **Docsy Example Project** uses the Docsy theme, as well as providing a skeleton documentation structure for you to use. You can either copy this project and edit it with your own content, or use the theme in your projects like any other [Hugo theme](https://gohugo.io/themes/installing-and-using-themes/).

This Docsy Example Project is hosted at [https://example.docsy.dev/](https://example.docsy.dev/).

You can find detailed theme instructions in the Docsy user guide: https://docsy.dev/docs/

This is not an officially supported Google product. This project is currently maintained.
-->



HnCC Learn(hLearn) is a curated list for the community to learn anything from design to devleopment. The resources/content is community maintained. Anyone can contribute to this project.

HnCC Learn is by the community for the community.

## Contributing articles 

#### Non git way
Create an [issue here](https://github.com/hnccbits/learn.hnccbits.com/issues/new)

#### git way
Contents are written in markdown (.md). Visit [here](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) to get some idea about markdown.

Now What can you add?
This is a curated list for resources to learn anything from design to development. Just create some article or some curated list such as courses/materials link inside that particular section in [https://learn.hnccbits.com/docs/](https://learn.hnccbits.com/docs/).

Add contents inside `article_directory/` directory inside `/content/docs/en/`
For a main content section create `_index.md` and for articles create `article_directory/_index.md` OR `article_name.md`

Feel free to ask anything. We look forward to your first pull request with us :) 

## Cloning the HnCC Learn (Docsy Example) Project in your local system

The following will give you a project that is set up and ready to use (don't forget to use `--recurse-submodules` or you won't pull down some of the code you need to generate a working site). The `hugo server` command builds and serves the site. If you just want to build the site, run `hugo` instead.

To install Hugo :
- Linux: Try with your custom package manager (apt, pacman, yu etc) or [Homebrew on linux](https://gohugo.io/getting-started/installing/)

- Windows : Follow the official [guide](https://gohugo.io/getting-started/installing/)

- macOS : Follow the official [guide](https://gohugo.io/getting-started/installing/)

```bash
git clone --recurse-submodules --depth 1 https://github.com/hnccbits/learn.hnccbits.com.git
cd learn.hnccbits.com
hugo server
```
<!--
```bash
git clone --recurse-submodules --depth 1 https://github.com/google/docsy-example.git
cd docsy-example
hugo server
```
-->

The theme is included as a Git submodule:

```bash
▶ git submodule
 a053131a4ebf6a59e4e8834a42368e248d98c01d themes/docsy (heads/master)
```

If you want to do SCSS edits and want to publish these, you need to install `PostCSS` (not needed for `hugo server`):

```bash
npm install
```

<!--### Cloning the Example from the Theme Project


```bash
git clone --recurse-submodules --depth 1 https://github.com/docsy.git
cd tech-doc-hugo-theme/exampleSite
HUGO_THEMESDIR="../.." hugo server
```


Note that the Hugo Theme Site requires the `exampleSite` to live in a subfolder of the theme itself. To avoid recursive duplication, the example site is added as a Git subtree:

```bash
git subtree add --prefix exampleSite https://github.com/google/docsy.git  master --squash
```

To pull in changes, see `pull-deps.sh` script in the theme.-->

## Running the website locally

Once you've cloned the site repo, from the repo root folder, run:

```
hugo server
```
**If you are interested, you can read our journey of starting this site [here](#) .**

Maintainers:    
- [Suraj Kumar Mahto](https://github.com/suraj-sloth)

With ❤︎ from HnCC Web Team.