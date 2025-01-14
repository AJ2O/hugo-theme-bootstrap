+++
title = "評論小部件"
date = 2021-11-27T19:54:29+08:00
featured = false
comment = true
toc = true
reward = true
categories = [
  "評論",
  "小部件"
]
tags = [
  "Disqus",
  "Utterances",
  "Giscus"
]
series = [
  "文檔"
]
images = []
aliases = [
  "/zh-tw/posts/widgets/comments"
]
authors = ["RazonYang"]
[menu.footer]
  parent = "features"
  weight = 7
  pre = '<i class="fas fa-fw fa-comments me-1"></i>'
+++

[Disqus](https://disqus.com/)、[Utterances](https://utteranc.es/) 和 [Giscus](https://giscus.app/) 評論小部件都是開箱即用的。本文將展示如何配置它們，甚至自定義你自己的評論小部件。

<!--more-->

## Disqus

[Disqus](https://disqus.com/) 評論小部件由 Hugo 支持。

```toml
disqusShortname = "yourdiscussshortname"
```

> 請注意：`disqusShortname` 是站點配置，而非參數。將其放在 `params` 是行不通的。

## Utterances

[Utterances](https://utteranc.es/) 是一個基於 GitHub issue 的輕量級評論小部件。

```toml
[utterances]
  repo = "user/repo"
  #issueTerm = "pathname" # pathname, url, title, og:title.
  #label = "comment" # Optional.
  #theme = ""
```

> 不同於 Disqus，Utterances 是一個參數。請將其放置在 `params`。

### 參數

| 名稱 | 類型 | 默認值 | 描述 |
|:---|:---|:---|:---
| `utterances.repo` | String | - | GitHub 倉庫。
| `utterances.issueTerm` | String | `pathname` | 文章和 issue 之間的映射： `pathname` | `pathname`, `url`, `title` 和 `og:title`。
| `utterances.label` | String | - | 此標籤會分配給 Utterances 創建的 issue。
| `utterances.theme` | String | - | 如果未設置任何主題，亮色和暗色模式會分別使用 `github-light` 和 `github-dark`。 可選值： `github-light`, `github-dark`, `preferred-color-scheme`, `github-dark-orange`, `icy-dark`, `dark-blue` 和 `photon-dark`。

### 故障排查

- 確保倉庫是公開的，否則讀者無法查看評論。
- 確保倉庫已經安裝了 [utterances app](https://github.com/apps/utterances)，否則用戶無法發表評論。
- 如果你的倉庫是尅隆的，請在設定中確保已經啟用了 issues 功能。

## Giscus

[Giscus](https://giscus.app/) is a lightweight comments widget built on GitHub discussions.

```toml
[giscus]
  repo = "user/repo"
  repoId = ""
  category = ""
  categoryId = ""
```

### Parameters

| Name | Type | Default | Description |
|:---|:---|:---|:---
| `giscus.repo` | String | - | GitHub repository. Required.
| `giscus.repoId` | String | - | GitHub repository ID. Required.
| `giscus.category` | String | - | Discussions category. Required.
| `giscus.categoryId` | String | - | Discussions category ID. Required.
| `giscus.theme` | String | - | Left it empty if you want to follow the theme mode.
| `giscus.mapping` | String | `pathname` | The mapping between blog posts and GitHub discussions: `pathname`, `url`, `title` and `og:title`.
| `giscus.inputPosition` | String | `top` | The input position: `top` or `bottom`.
| `giscus.reactions` | Boolean | `true` | Turn on/off the reactions.
| `giscus.metadata` | Boolean | `false` | Emit discussion metadata.
| `giscus.lang` | String | - | Specify language, default to site language.
| `giscus.lazyLoading` | Boolean | `true` | Enable lazy loading.

## 自定義評論小部件

我們不打算支持所有的評論小部件，但別擔心，你完全可以自定義評論小部件。

> 在創建自己的評論小部件之前，需要禁用其他評論小部件。

```bash
mkdir -p layouts/partials/post/comments
echo "MY COMMENTS WIDGET" > layouts/partials/post/comments/custom.html
```

期間，你很可能需要引入協力廠商資源，不過這可以通過 [自定義資源]({{< ref "/docs/advanced/custom-assets" >}}) 或 [鉤子]({{< ref "/docs/advanced/hooks" >}}) 輕鬆解决。
