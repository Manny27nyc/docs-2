---
title: Stitch Connect
permalink: /stitch-connect/
sidebar: overview
layout: connect

content-type: "connect-overview"

toc: false
summary: false
feedback: false

toolkit:
  - title: "{{ api.name }}"
    icon: "{{ api.icon }}"
    url: "{{ api.section | flatify }}"
    description: "{{ api.description | flatify }}"

  - title: "{{ js.name }}"
    icon: "{{ js.icon }}"
    url: "{{ js.section | flatify }}"
    description: "{{ js.description | flatify }}"
---