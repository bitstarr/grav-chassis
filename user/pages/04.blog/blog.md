---
title: Blog
content:
    items: '@self.children'
    limit: 2
    order:
        by: date
        dir: desc
    filter:
        published: true
    pagination: true
    url_taxonomy_filters: true
feed:
    description: 'Sample Blog'
    limit: 10
pagination: true
taxonomy:
  navarea: ['main', 'footer']
---