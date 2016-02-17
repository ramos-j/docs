##### Maker on SLACK - join us
------
[![Slack Status](http://slack.makerdao.com/badge.svg)](https:/slack.makerdao.com)


# docs
documentation that doesn't belong somewhere more specific


## Contents

- [Usage](#usage)
- [Development](#development)
- [Contributing](#Contribute)


## Usage

### Install dependencies

```bash
$ bundle install
```


## Development

### Running locally

To see your Jekyll site with Poole applied, start a Jekyll server. In Terminal, from `/docs` (or whatever your Jekyll site's root directory is named):

```bash
$ jekyll serve
```

Open <http://localhost:4000> in your browser, and voilà.


## Contribute

Poole has two branches, but only one is used for active development.

- `master` for contributing.  **All pull requests should be to submitted against `master`.**
- `gh-pages` for our hosted site, which includes our analytics tracking code. **Please avoid using this branch.**

CSS is handled via Jeykll's built-in Sass compiler. Source Sass files are located in `_sass/`, included into `styles.scss`, and compile to `styles.css`.
