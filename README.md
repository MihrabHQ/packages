# Mihrab packages

The apt and dnf repositories for [Mihrab](https://github.com/MihrabHQ/Mihrab)
on Linux, served at **https://mihrabhq.github.io/packages**, and the publisher
of the AUR package `mihrab-bin`.

Nothing is built here. Every hour [`publish.yml`](.github/workflows/publish.yml)
looks at Mihrab's latest release; when it carries a new version's `.deb` and
`.rpm`, it builds both repositories with that release's own
[`desktop/packaging/build-repos.sh`](https://github.com/MihrabHQ/Mihrab/blob/main/desktop/packaging/build-repos.sh),
signs them, deploys them to this repository's Pages site, and pushes the new
PKGBUILD to the AUR. Only the latest version is served.

Install instructions are on the site. The workflow's two secrets,
`PACKAGES_SIGNING_KEY` and `AUR_SSH_KEY`, are made by
[`desktop/packaging/make-keys.sh`](https://github.com/MihrabHQ/Mihrab/blob/main/desktop/packaging/make-keys.sh).
