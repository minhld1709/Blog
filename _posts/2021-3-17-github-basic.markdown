---
layout: post
title: Github Basic
date: 2020-01-11 19:32:20 +0300
description: This article show short command line github usually use
img: 2021-3-17-github-basic/Git_icon.png
fig-caption: # Add figcaption (optional)
tags: [GIT]
---
# **Giới thiệu**
Xin chào tất cả các bạn như các bạn đã biết, đối với một dân Dev thì việc có thể làm việc nhóm và vận hành trơn tru dự án là một trong những điều cần thiết và tất yếu. Và trong các kĩ năng cá nhân về ngôn ngữ lập trình thì khả năng quản lý source dự án cũng là một trong những điều vô cùng cần thiết.

Có thể các bạn đã nghe đến những cái trên như **SVN**, **github**, **gitlab** hay **bitbucket**, chúng đều là những công cụ quản lý vô cùng mạnh mẽ

Và phổ biến nhất hiện nay chắc hẳn là **github**, vậy nên hôm nay mình sẽ giới thiệu sơ qua cho các bạn về công cụ này, và một vài thao tác cơ bản nhất để mình có thể sử dụng trong dự án nhé.

# **Github là gì?**
Theo như định nghĩa từ Google
> What is GitHub? GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere. This tutorial teaches you GitHub essentials like repositories, branches, commits, and Pull Requests

Vậy Github là một nền tảng lưu trữ và quản lý version và những người cộng tác, giúp mọi người có thể làm việc cùng nhau trên một dự án

Vậy làm sao mà **Github** có thể giúp chúng ta làm việc cùng nhau? và chúng ta làm việc cùng nhau như thế nào?

Trước khi trả lời câu hỏi trên, chúng ta cần biết một số định nghĩa cơ bản của Github để có cái nhìn rõ ràng hơn về nó nhé.

# **Các khái niệm cơ bản của Github**

![GithubWorkflow]({{site.baseurl}}/assets/img/2021-3-17-github-basic/github_workflow.png)

### Có 3 khái niệm chính sẽ sử dụng trong Github

Thông qua hình trên mình sẽ giải thích một chút
* **Resource** : nơi lưu trữ source code, và nó sẽ được lưu trữ chính trên github
* **Commit** : đóng gói các thay đổi để update trên Resource
* **Branch** : nơi tập hợp các commit muốn thay đổi để update trong một lần

Để rõ ràng hơn, chúng ta sẽ tiếp cận chúng dưới các lệnh để có thể hiểu rõ hơn nhé!

# **Các lệnh cơ bản trong Github**
### Về cơ bản trong Git chủ yếu là dùng các lệnh như

* **git clone** : Kéo source code từ github về local
* **git add** : Lưu trữ các file vào bộ nhớ tạm
* **git commit** : Đóng gói các file trong bộ nhớ tạm
* **git push** : Đẩy các commit từ **Local** lên **Resource**
* **git merge** : Xác nhập các thay đổi vào branch chỉ định
* **git pull** : Cập nhật code mới được thay đổi từ **Resource** về **Local**

### Ngoài ra, cao hơn chút chúng ta sẽ sử dụng thêm một số lệnh như

* **git rebase** : Xử lý khéo léo các commit trong branch hiện tại
* **git cherry-pick** : Kéo một commit từ một branch khác về branch hiện tại
* **git reset** : Di chuyển HEAD của branch hiện tại đến một vị trí khác
* **git log --oneline** : Xem thông tin các commit của branch hiện tại hoặc branch được chỉ định
* **git reflog** : Xem lịch sử thao tác Github của bạn

Về cơ bản chỉ cần các lệnh cơ bản ở trên là các bạn đã có thể hoàn toàn tham dự vào phát triển các dự án rùi, vậy tạo sao chúng ta không thực hành cho nóng nhỉ ^^

# **Áp dụng Git cơ bản cho dự án cá nhân**

Trước tiên chúng ta tạo một Project dưới Local có tên là **demo-project** có cấu trúc file như sau:
```
.
└── demo.html
```
Sau đó chúng ta sẽ làm theo [**hướng dẫn cơ bản này**](https://docs.github.com/en/github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line) để tạo một Resource trên github có tên là **demo-project** và push source từ dưới local lên.

### Để push Project mới lên chúng ta làm từng bước sau

1. **git init** : Khai báo initial Git
2. **git add -A** : Lưu toàn bộ các file hiện tại vào bộ nhớ tạm
3. **git commit -m "first commit"** : Đóng gói các file trong bộ nhớ tạm và đặt tên là "first commit"
4. **git branch -m Main** : Đổi tên Branch hiện tại sang thành Main
5. **git remote add origin https://github.com/{github name}/demo-project.git"** : Định nghĩa đường Link resrouce là **origin**
6. **git push origin Main** : Đẩy commit từ Branch Main lên origin

Sau khi push thành công
```
➜  demo-project git:(Main) git push origin Main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 205 bytes | 205.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/minhld1709/demo-project.git
 * [new branch]      Main -> Main
```

Và chúng ta có được kêt quả
![Github project Screen]({{site.baseurl}}/assets/img/2021-3-17-github-basic/github_project_screen.png)

### Để update source chúng ta làm thế nào

Theo như cách phát triển các dự án thông thường
Branch để phát triển thường được dùng có thể đặt tên là **main** hoặc **develop** hoặc **master**
Trong trường hợp này, chúng ta sử dụng **Main** làm branch để phát triển

Và workflow thông thường sẽ từ branch **Main**

1. **git checkout BE123** : Checkout sang một branch chức năng mới có tên BE123
2. **Sửa code theo chức năng mới**
3. **git add -A**
4. **git commit -m "[BE123] add screen html"** 
5. **git push origin BE123** :  đẩy Branch BE123 từ Local lên Resrouce
6. **ở trên Resource chúng ta tạo pullrequest từ Brach BE123 to Main**
6. **ở trên Resource chúng ta merge pullrequest đó**
7. **git checkout Main** : Di chuyển từ branch BE123 về Branch Main dưới local
8. **git pull origin Main** : Kéo code mới được cập nhật từ Branch Main trên Resouce về Branch Main dưới Local

# **Kết luận:**
Sau khi xem qua bài viết này chắc hẳn các bạn đã có thể nắm bắt sơ bộ cách để sử dụng git cho dự án cá nhân rùi nhỉ, ở trên là một bài viết cơ bản và vẫn còn một số vấn đề phát sinh khi sử dụng vào dự án

Vậy chúng ta sẽ gặp lại ở bài viết sau nhé, cám ơn đã dành thời gian quan tâm và hẹn gặp lại

Hãy comment bên dưới để có gì chúng ta cùng trao đổi thêm nhé ^_^
