---
# see https://learn.getgrav.org/17/cookbook/general-recipes#display-different-robots-
routes:
  default: /robots.txt
process:
  markdown: false
dev:
  - 'User-agent: *'
  - 'Disallow: /'
---
User-agent: *
Disallow: /