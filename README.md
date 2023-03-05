# Label-studio for wsl docker<br>(Docker for windows)

<!-- <img src="https://user-images.githubusercontent.com/12534576/192582340-4c9e4401-1fe6-4dbb-95bb-fdbba5493f61.png"/> -->

![GitHub](https://img.shields.io/github/license/heartexlabs/label-studio?logo=heartex) ![label-studio:build](https://github.com/heartexlabs/label-studio/workflows/label-studio:build/badge.svg) ![GitHub release](https://img.shields.io/github/v/release/heartexlabs/label-studio?include_prereleases)

[Website](https://labelstud.io/) • [Docs](https://labelstud.io/guide/) • [Twitter](https://twitter.com/labelstudiohq) • [Join Slack Community <img src="https://app.heartex.ai/docs/images/slack-mini.png" width="18px"/>](https://slack.labelstudio.heartex.com/?source=github-1)


## What is Label Studio?

<!-- <a href="https://labelstud.io/blog/release-130.html"><img src="https://github.com/heartexlabs/label-studio/raw/master/docs/themes/htx/source/images/release-130/LS-Hits-v1.3.png" align="right" /></a> -->

Label Studio is an open source data labeling tool. It lets you label data types like audio, text, images, videos, and time series with a simple and straightforward UI and export to various model formats. It can be used to prepare raw data or improve existing training data to get more accurate ML models.

## Quick start

### Mount WSL folder

`\\wsl$`にアクセスしてネットワークドライブに追加します．

![](https://i.imgur.com/5U89qau.png)

そのネットワークドライブ上でリポジトリを`clone`してきます．

### change permissions

権限を変更します．

```bash
maki@maki-hp:~/prj/label-studio-170$ sudo chmod 777 mydata/ postgres-data/
[sudo] password for maki: 
maki@maki-hp:~/prj/label-studio-170$ ls -al
total 200
drwxr-xr-x 13 maki maki  4096 Mar  5 19:04 .
drwxr-xr-x  3 maki maki  4096 Mar  5 18:59 ..
-rw-r--r--  1 maki maki    60 Mar  5 19:00 .black
-rw-r--r--  1 maki maki   424 Mar  5 19:00 .codespellrc
drwxr-xr-x  2 maki maki  4096 Mar  5 19:00 .devcontainer
-rw-r--r--  1 maki maki   269 Mar  5 19:00 .dockerignore
drwxr-xr-x  8 maki maki  4096 Mar  5 19:03 .git
-rw-r--r--  1 maki maki    69 Mar  5 19:00 .gitattributes
drwxr-xr-x  5 maki maki  4096 Mar  5 19:00 .github
-rw-r--r--  1 maki maki  1125 Mar  5 19:00 .gitignore
-rw-r--r--  1 maki maki   113 Mar  5 19:00 .gitleaks.toml
-rw-r--r--  1 maki maki 17047 Mar  5 19:00 .pylintrc
-rw-r--r--  1 maki maki  1407 Mar  5 19:00 CODE_OF_CONDUCT.md
-rw-r--r--  1 maki maki  4884 Mar  5 19:00 CONTRIBUTING.md
-rw-r--r--  1 maki maki  3100 Mar  5 19:00 Dockerfile
-rw-r--r--  1 maki maki   100 Mar  5 19:00 Dockerfile.cloudrun
-rw-r--r--  1 maki maki   180 Mar  5 19:00 Dockerfile.heroku
-rw-r--r--  1 maki maki  2148 Mar  5 19:00 Dockerfile.redhat
-rw-r--r--  1 maki maki 11341 Mar  5 19:00 LICENSE
-rw-r--r--  1 maki maki  1152 Mar  5 19:00 MANIFEST.in
-rw-r--r--  1 maki maki  1332 Mar  5 19:00 Makefile
-rw-r--r--  1 maki maki   199 Mar  5 19:00 NOTICE
-rw-r--r--  1 maki maki  2029 Mar  5 19:02 README.md
-rw-r--r--  1 maki maki 10848 Mar  5 19:00 README_origin.md
-rw-r--r--  1 maki maki   957 Mar  5 19:00 app.json
-rw-r--r--  1 maki maki  3800 Mar  5 19:00 azuredeploy.json
-rw-r--r--  1 maki maki   283 Mar  5 19:00 azuredeploy.parameters.json
-rw-r--r--  1 maki maki    29 Mar  5 19:00 codecov.yml
drwxr-xr-x  5 maki maki  4096 Mar  5 19:00 deploy
-rw-r--r--  1 maki maki   499 Mar  5 19:00 docker-compose.mysql.yml
-rw-r--r--  1 maki maki  1879 Mar  5 19:00 docker-compose.yml
drwxr-xr-x  5 maki maki  4096 Mar  5 19:00 docs
-rw-r--r--  1 maki maki    79 Mar  5 19:00 heroku.yml
drwxr-xr-x  3 maki maki  4096 Mar  5 19:00 images
drwxr-xr-x 18 maki maki  4096 Mar  5 19:00 label_studio
drwxr-xr-x  2 maki maki  4096 Mar  5 19:00 licenses
drwxrwxrwx  4 root root  4096 Mar  5 19:10 mydata
drwxrwxrwx 19  999 root  4096 Mar  5 19:10 postgres-data
-rw-r--r--  1 maki maki  2089 Mar  5 19:00 roadmap.md
drwxr-xr-x  2 maki maki  4096 Mar  5 19:00 scripts
-rw-r--r--  1 maki maki  1554 Mar  5 19:00 setup.py
maki@maki-hp:~/prj/label-studio-170$
```


### Run with Docker Compose
Docker Compose script provides production-ready stack consisting of the following components:

- Label Studio
- [Nginx](https://www.nginx.com/) - proxy web server used to load various static data, including uploaded audio, images, etc.
- [PostgreSQL](https://www.postgresql.org/) - production-ready database that replaces less performant SQLite3.

To start using the app from `http://localhost` run this command:
```bash
docker-compose up
```

[README_origin.md](README_origin.md)


## License

This software is licensed under the [Apache 2.0 LICENSE](/LICENSE) © [Heartex](https://www.heartex.com/). 2020-2022

<img src="https://user-images.githubusercontent.com/12534576/192582529-cf628f58-abc5-479b-a0d4-8a3542a4b35e.png" title="Hey everyone!" width="180" />
