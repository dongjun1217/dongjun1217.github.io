# Dot Kik

![Djshin](https://github.com/rundocs/jekyll-rtd-theme/workflows/CI/badge.svg?branch=develop)
![jsDelivr](https://data.jsdelivr.com/v1/package/gh/rundocs/jekyll-rtd-theme/badge)

### 안녕하세요! DevOps의 모든 것을 다루는 DevOps ToolKit In Korea, AKA. Dot KIK 입니다.

데브옵스는 단순히 개발(Dev)과 운영(Ops)의 합성어를 넘어서, 

지속적인 통합, 배포, 모니터링, 

그리고 피드백을 통해 더 빠르고 안정적인 소프트웨어 릴리스를 가능하게 하는 문화와 실천입니다.

이 블로그는 데브옵스의 모든 측면을 탐구하며, 

이 분야의 최신 동향, 도구, 최고의 실천법, 그리고 실제 사례 연구를 공유합니다.




## 그래서 어떤 걸 할껀데?

이곳은 기술의 최전선에서 일하는 개발자, 운영 팀, 그리고 데브옵스에 열정을 가진 모든 이들을 위한 공간입니다.

여기서는 초보자부터 전문가까지, 모든 레벨의 독자가 자신의 지식을 넓히고, 

데브옵스 여정에서 마주치는 다양한 도전을 극복할 수 있는 통찰력을 얻을 수 있습니다. 

우리는 다음과 같은 주제들을 다룰 예정입니다

- [@primer/css](https://github.com/primer/css)
- [github-pages](https://github.com/github/pages-gem) ([dependency versions](https://pages.github.com/versions/))

## Quick start

```yml
remote_theme: rundocs/jekyll-rtd-theme
```

You can [generate](https://github.com/rundocs/starter-slim/generate) with the same files and folders from [rundocs/starter-slim](https://github.com/rundocs/starter-slim/)

## Usage

Documentation that can guide how to create with Github pages, please refer to [rundocs.io](https://rundocs.io) for details

## Features

- Shortcodes (Toasts card, mermaid)
- Pages Plugins (emoji, gist, avatar, mentions)
- Auto generate sidebar
- [Attribute List Definitions](https://kramdown.gettalong.org/syntax.html#attribute-list-definitions) (Primer/css utilities, Font Awesome 4)
- Service worker (caches)
- SEO (404, robots.txt, sitemap.xml)
- Canonical Link (Open Graph, Twitter Card, Schema data)

## Options

| name          | default value        | description       |
| ------------- | -------------------- | ----------------- |
| `title`       | repo name            |                   |
| `description` | repo description     |                   |
| `url`         | user domain or cname |                   |
| `baseurl`     | repo name            |                   |
| `lang`        | `en`                 |                   |
| `direction`   | `auto`               | `ltr` or `rtl`    |
| `highlighter` | `rouge`              | Cannot be changed |

```yml
# folders sort
readme_index:
  with_frontmatter: true

meta:
  key1: value1
  key2: value2
  .
  .
  .

google:
  gtag:
  adsense:

mathjax: # this will prased to json, default: {}

mermaid:
  custom:     # mermaid link
  initialize: # this will prased to json, default: {}

scss:   # also _includes/extra/styles.scss
script: # also _includes/extra/script.js

translate:
  # shortcodes
  danger:
  note:
  tip:
  warning:
  # 404
  not_found:
  # copyright
  revision:
  # search
  searching:
  search:
  search_docs:
  search_results:
  search_results_found: # the "#" in this translate will replaced with results size!
  search_results_not_found:

plugins:
  - jemoji
  - jekyll-avatar
  - jekyll-mentions
```

## The license

The theme is available as open source under the terms of the MIT License
