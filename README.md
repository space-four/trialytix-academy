# trialytix-academy

## Specifica of `Hugo Book` Theme

### About the Theme

- Link on Hugo Themes Lib: <https://themes.gohugo.io/themes/hugo-book/>
- Link to Theme Github Repo: <https://github.com/alex-shpak/hugo-book>
  - Themes in Hugo are Github Repos
- Theme has been included as Git Submodule

### Project Specifica

- `docs` contains the Pages with all handbook/academy entries
- `posts` is not used but could realize a _very_ basic blog

- In `_index.md` on any level of the hierarchy, you can set `bookCollapseSection` to true
  - If set to true, nested menu-items will collapse
  - We set elements of first hierarchy to `true`

### SCSS File Structure

- To manipulate theme styles it is recommend to not do this in themes/...
  - Instead create copies of theme-scss-files in main project dir and manipulate styles there
  - Should potentially safe us in case of theme update

- `_fonts.scss` => Handle local hosting of fonts and set project-wide body font(s)
  - font-files rest in `static\fonts\{font-family-name}\`
- `_default.scss` => Handle basics brand/project-specific styles
- `_main.scss` => Maintain styles of general application
- `_markdown.scss` => Maintain styles of markdown-elemens on the pages (content-area)
- `utils.scss` => General Utility Classes
  - ~ aka "the posts" are styled here

### Layout File Structure

- As with the SCSS Files, it is strongly recommended to copy them to the general project directory before manipulating

- `/default` => `baseof.html` => Entire Page Layout
- `partials` => Here smaller pieces of Content are maintained, e.g. the brand display to the upper left or what comes after a table of contents

### config.toml

- `config.toml` maintains general configuration input for application
  - Path to Logo File
  - dark/light theme of website

## Hugo Basics

### Create Content

- To create text content work in the `content` directory
- `hugo new {myfile.md}` will create a md file in the content directoy
- `hugo new docs/{hierarchy}/{myfile.md}` will create directory `hierarchy` in `docs` and create {myfile.md} there
  - In thise case you need to `hugo new doc/{hierarchy.md}/_index.md` 

### Hugo Server

- Start a hugo WebServer with `hugo server`
- To also view content that is flagged `draft` invoke `hugo server -D`
