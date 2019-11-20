---
layout: post
title: So Easy Build Github Page
date: 2019-11-20 13:32:20 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: 2019-11-20-github-pages/githubpage.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [GithubPages, Portpolio, BuildFast]
---
# **Giới thiệu**
Thời nay, khái niệm về portfolio đã quá đỗi quen thuộc với bất kể bợn trẻ nào trong design, và trong IT cũng vậy, github pages đã và đang được coi là portfolio đối với những developer trong thời điểm hiện nay. Vậy làm sao để chúng ta có được 1 portfolio nhanh, đơn giản nhưng đầy hiệu quả.
Và đây là một cách đơn giản nhất để tạo 1 github pages nhanh và hiệu quả.

# **Các bước để tạo Github Pages của riêng mình**
## 1) Chọn theme mình thích
Hãy tìm kiếm một trang Theme bạn thích trong list [này](https://jekyllthemes.io/github-pages-themes)

Và tôi chọn một themes mình vừa ý ví dụ themes [này](https://github.com/artemsheludko/flexible-jekyll) đi

![I and My friends]({{site.baseurl}}/assets/img/2019-11-20-github-pages/home-page.jpg)

## 2) Setup theme thành Github Pages
Chúng ta sẽ `fork` nó về account github của mình

![Fork to My Account]({{site.baseurl}}/assets/img/2019-11-20-github-pages/fork_account.png)

Sau đó, chúng ta kéo code về và sửa thêm đoạn dưới đây vào `Gemfile`
{% highlight ruby %}
gem 'github-pages'
{% endhighlight %}

### Tiếp theo, chúng ta chạy lệnh **Bundle** trên **Console**
{% highlight console %}
bundle install
{% endhighlight %}

Sau đó đóng commit và `push` lên `master`
{% highlight ruby %}
git add -A
git commit -m "Commit gem github pages"
git push origin master
{% endhighlight %}

## 3) Setup source trên Github
Tiếp sau đây, chúng ta chỉ cần setup `source` là `master branch` trên `github` là xong

![Setup Repository]({{site.baseurl}}/assets/img/2019-11-20-github-pages/setup_repository.png)

Bạn có thể xem kêt quả bằng cách vào theo link format dưới đây

[https://{github_name}.github.io/flexible-jekyll](https://{github_name}.github.io/flexible-jekyll)

## 4) Setup thành link ~.github.io/blog

Chúng ta chỉ cần làm đơn giản là cập nhật `baseurl` trong `_config.yml` thành `blog`
{% highlight yml %}
baseurl: "/blog" # the subpath of your site, e.g. /blog
{% endhighlight %}

Và `Push` thay đổi lên `master`, sau đó, chúng ta sẽ `rename repository` sang `blog`

![Rename Repository]({{site.baseurl}}/assets/img/2019-11-20-github-pages/githubpages_rename.png)

Và cuối cùng chúng ta có kết quả

[https://{github_name}.github.io/blog](https://{github_name}.github.io/blog)

# **Kết luận**

Với sự support của **jekyll**, chỉ cần vài bước đơn giản là chúng ta đã có một **Portpolio** tuyệt vời của riêng mình rùi, thật đơn giản phải không nào ^_^

## **Reference:**
 * [https://jekyllrb.com/](https://jekyllrb.com/)
 * [https://medium.com/20percentwork/creating-your-blog-for-free-using-jekyll-github-pages](https://medium.com/20percentwork/creating-your-blog-for-free-using-jekyll-github-pages-dba37272730a)

## Các bạn muốn góp ý hay trao đổi gì xin hãy commen ở phần bên dưới nhé ^_^

# Thankyou and See you 