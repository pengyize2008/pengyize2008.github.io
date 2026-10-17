---
title: "{{ replace .File.ContentBaseName "-" " " | title }}"
# slug 决定网址，建议用英文/数字，例如 my-first-diary
slug: "{{ .File.ContentBaseName }}"
description: ""
date: {{ .Date }}
# 日记统一归到「日记」分类
categories:
    - 日记
tags:
    []
draft: false
---
