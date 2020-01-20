---
title: "{{ replace .Name "-" " " | title }}"
author: "{{.GitInfo.AuthorName}}"
date: {{ .Date }}
draft: true
description: ""
subtitle: ""
tags:
 - tag1
 - tag2
image:""
images:
 - ""
 - ""
---
<amp-story-page id="cover">
  <amp-story-grid-layer template="fill">
    <amp-img src=""
        width="720" height="1280"
        layout="responsive">
    </amp-img>
  </amp-story-grid-layer>
</amp-story-page>