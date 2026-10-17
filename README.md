<img align="right" width="150" alt="logo" src="https://user-images.githubusercontent.com/5889006/190859553-5b229b4f-c476-4cbd-928f-890f5265ca4c.png">

# Hugo Theme Stack Starter Template

This is a quick start template for [Hugo theme Stack](https://github.com/CaiJimmy/hugo-theme-stack). It uses [Hugo modules](https://gohugo.io/hugo-modules/) feature to load the theme.

It comes with a basic theme structure and configuration. GitHub action has been set up to deploy the theme to a public GitHub page automatically. Also, there's a cron job to update the theme automatically everyday.

## Video Tutorial

In case you got lost during the setup process, here's a video tutorial that setups a new Hugo site using this template, and deploys it to GitHub Pages: https://www.youtube.com/watch?v=8qDdQQ6Ifxo

## Get started

1. Click *Use this template*, and create your repository as `<username>.github.io` on GitHub. (You can also use a different repository name, but then the resulting website will be available at `https://<username>.github.io/<repository-name>`. )
![Step 1](https://user-images.githubusercontent.com/5889006/156916624-20b2a784-f3a9-4718-aa5f-ce2a436b241f.png)

2. Once the repository is created, create a GitHub codespace associated with it.
![Create codespace](https://user-images.githubusercontent.com/5889006/156916672-43b7b6e9-4ffb-4704-b4ba-d5ca40ffcae7.png)

3. While waiting for the codespace to be created, go to `Settings` -> `Pages` of your newly created repository, and set `Build and deployment` -> `Source` to `GitHub Actions`.
![Change build and deployment source](https://github.com/user-attachments/assets/192459bf-25d8-441e-8029-c108d789e449)

4. After the codespace is created, you can test that the site is built successfully by running `hugo server` in the terminal and see your new site in action. 

5. Check `config` folder for the configuration files. You can edit them to suit your needs. Make sure to update the `baseurl` property in `config/_default/config.toml` to your site's URL. For example, if your new repository is named `my-blog`, then the `baseurl` should be `https://<username>.github.io/my-blog/`.

6. Once you're done editing the site, just commit it and push it. GitHub action will deploy the site automatically to GitHub page asociated with the repository.

---

In case you don't want to use GitHub codespace, you can also run this template in your local machine. **You need to install Git, Go and Hugo extended locally.** For more information, check official Hugo documentation: https://gohugo.io/installation/

## Update theme manually

Run:

```bash
hugo mod get -u github.com/CaiJimmy/hugo-theme-stack/v4
hugo mod tidy
```

> This starter template has been configured with `v4` version of theme. Due to the limitation of Go module, once the `v4` or up version of theme is released, you need to update the theme manually. (Modifying `config/module.toml` file)

## Deploy to another static page hostings

Check official Hugo documentation: https://gohugo.io/host-and-deploy/

---

## 这个站点怎么用

站点根目录：`D:\qinna`（Hugo + Stack 主题，主题通过 Hugo Modules 自动管理）。

### 写一篇日记

```bash
hugo new content post/diary/2026-10-16-日记标题.md
```

生成的文件在 `content/post/diary/`，用任意编辑器写 Markdown 正文即可。
front matter 里的 `categories` 已默认填好「日记」，方便在侧边栏按分类筛选。

### 本地预览

```bash
hugo server -D
```

打开 <http://localhost:1313>，保存文件后页面会自动刷新。`-D` 表示连草稿一起显示。

### 发布上线

```bash
hugo            # 生成静态文件到 public/
git add -A
git commit -m "新日记"
git push
```

推到 GitHub 后，`.github/workflows/deploy.yml` 会自动构建并发布到
<https://pengyize2008.github.io/>。

### 界面语言

主题的翻译文件是 `i18n/zh.toml`，因此 `config/_default/languages.toml` 里的
语言标识必须写 `zh`；侧边栏菜单的中文名在 `content/_index.md` 与
`content/page/archives/index.md` 的 front matter 里设置。

