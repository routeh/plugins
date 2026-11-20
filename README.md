# plugins

The feed of routeh plugins, served at <https://routeh.github.io/plugins/>:
`index.json`, its signature `index.json.sig`, and every bundle in
`blobs/<sha256>`.

Nothing here is written by hand but `feed.toml`. A plugin proposes its
bundles by pushing to the branch `plugin/<id>`; the workflow (routeh-plugin's
`feed.yml`) signs them into `blobs/`, rebuilds the index from every blob and
`feed.toml`, commits to `main` and deploys Pages. How it works:
routeh-plugin's `docs/RELEASE.md`.

```toml
# feed.toml
[awg]
keep = 3                       # the newest versions per architecture and kernel
yank = ["3.1.20261113.2-r1"]   # not shown; the blob stays
```
