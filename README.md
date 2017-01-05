# disappearing-tilde

This is sample Hugo site to illustrate possible error in paginator URL creation. See <https://github.com/spf13/hugo/issues/2177>.

The error: When creating a site with a `baseurl` containing a tilde (`~`), the tilde is stripped from the paginator URLs.

## My setup

- Hugo v0.18, downloaded from <https://github.com/spf13/hugo/releases> (output from `hugo version`: `Hugo Static Site Generator v0.18 BuildDate: 2016-12-19T14:43:00-05:00`)
- OS X 10.10.5

## Steps to reproduce

Set up the site:

```sh
git clone https://github.com/marcliberatore/disappearing-tilde.git
cd disappearing-tilde
hugo server --watch
```

Then open <http://localhost:1313/~liberato/disappearing-tilde/>, scroll to the bottom, and check the link for the `Older >` button, generated by `{{ .Paginator.Next.URL }}` in the [pager partial](themes/hemingway/layouts/partials/pager.html). For me, it lacks the tilde (`~`) and is invalid.

## Other notes

The tilde does not disappear in all links.

The behavior seems to occurrs regardless of theme.
