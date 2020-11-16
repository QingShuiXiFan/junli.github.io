---
title: 【Git】How to clone from GitHub faster in China
tag: [Git, EN]
category: IT
thumbnail: https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1605159460363&di=6070e55e7586c3bc4daa5477389dc47f&imgtype=0&src=http%3A%2F%2Fku.90sjimg.com%2Felement_origin_min_pic%2F00%2F86%2F40%2F1756eb4af1504bf.jpg
---

Sometimes it's bloody slow to clone a repository from GitHub in China mainland, so follow the following way to clone the repos from GitHub Chinese mirror site:

Steps:

1. Just replace `www.github.com` with `www.github.com.cnpmjs.org`, like the following example:

    ```shell
    git clone https://github.com.cnpmjs.org/QingShuiXiFan/mysite.git
    ```