# Personal Site

This a personal site. Built using jekyll.

To create a new post:

```bash
bundle exec jekyll post "POST_TITLE"
```

To run a server:

```bash
jekyll s --livereload 
```

This runs server at http://localhost:4000/

The `--livereload` makes sure new posts and changes to them are available without restarting the server. Doesn't apply to config file though.

Minima theme has been imported to customize.

### Deploy

Just push the code to `main` branch, github pages takes care of the rest.