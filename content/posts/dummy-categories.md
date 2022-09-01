---
title: "dummy category"
date: 2018-10-06T19:25:55+05:30
draft: true
categories: ["web-hosting",  "pcs-and-laptops", "mobiles-tablets"]
tags: ["shared-hosting", "vps-hosting", "wordpress-hosting", "cloud-hosting"]
featuredImage: "img/webhosting1.jpg"
---

### What is Hugo

Hugo is a Static Site Generator that is as much popular like Jekyll. It is based on Go Programming language made by google.
This is a new site content

{{< highlight html>}}
<section id="main">
  <div>
   <h1 id="title">{{ .Title }}</h1>
    {{ range .Pages }}
        {{ .Render "summary"}}
    {{ end }}
  </div>
</section>
{{< /highlight >}}