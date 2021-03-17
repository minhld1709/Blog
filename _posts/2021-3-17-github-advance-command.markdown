---
layout: post
title: Github Advance
date: 2020-05-23 19:32:20 +0300
description: This article show short command line github usually use
img: 2021-3-17-github-basic/Git_icon.png
fig-caption: # Add figcaption (optional)
tags: [GIT]
---
# **Giới thiệu**
Xin chào tất cả các bạn, nếu như các bạn đã đọc qua về bài viết cũ của mình về Git thì chắc hẳn các bạn đã nắm sơ qua một chút khái niệm và một vài câu lệnh Git cơ bản hay dùng trong dự án.
Ngày hôm nay, mình sẽ bổ sung thêm một số câu lệnh Git hơi khó hơn một chút nhưng cũng thường xuyên được sử dụng trong các dự án.

Ngày trước chúng ta đã biết về **git checkout**, **git branch**, **git add**, **git commit**, **git push** và **git pull** cùng với **git merge**.


Vậy hôm nay chúng ta sẽ tìm hiểu về các lệnh **git log**, **git reflog**, **git rebase**, **git cherry-pick** nhé.

# **Github log**
Lệnh này nhìn qua thôi chắc là các bạn hiểu ngay rùi, nó dùng để hiển thị Log của branch, hay chính xác hơn là hiển thị các commit trong branch đó và các thông số liên quan.
Ví dụ:
```
git log

commit 2d6b856ca149e90763ec6b5c9d0708bae44b5131 (HEAD -> B)
Author: github_name <github_mail>
Date:   Sun May 23 16:26:01 2021 +0700

    a1

commit d7dcd7b4292e7bf1b9d4cd120af86791c6891e06
Author: github_name <github_mail>
Date:   Sun May 23 16:26:41 2021 +0700

    b

commit 36b6843f1c1eaf69902fde0b424ef9cd2ee3f67e (origin/Main, master, develop, Main)
Author: github_name <github_mail>
Date:   Thu Mar 18 06:08:28 2021 +0700

    first commit
```

Chúng ta có thể thấy các thông số cơ bản của một commit như
Tên commit, mã commit hay author và created date của commit đó

Và thông thường khi check phần nhiều mọi người quan tâm đến tên commit là chính
Vậy nên chúng ta thường hay sử dụng lệnh tắt dưới đây cho dễ

```
git log --oneline -5
```
Result:
```
2d6b856 (HEAD -> B) a1
d7dcd7b b
36b6843 (origin/Main, master, develop, Main) first commit
```
* **--oneline** : Hiển thị tóm tắt thông tin commit trong 1 dòng
* **-5** : Hiển thị 5 commit đầu tiên

# **Github reflog**
Cùng với **git log** chúng ta cũng thường sử dụng **git reflog** để sử dụng trong dự án.

Khác với **git log**, **git reflog** sử dụng để theo dõi thao tác của chúng ta với github trong dự án
**Example:**
```
git reflog

2d6b856 (HEAD -> B) HEAD@{0}: commit (cherry-pick): a1
d7dcd7b HEAD@{1}: commit: b
36b6843 (origin/Main, master, develop, Main) HEAD@{2}: checkout: moving from develop to B
36b6843 (origin/Main, master, develop, Main) HEAD@{3}: checkout: moving from A to develop
b1685cd (A) HEAD@{4}: commit: a2
3abe031 HEAD@{5}: commit: a1
36b6843 (origin/Main, master, develop, Main) HEAD@{6}: checkout: moving from develop to A
36b6843 (origin/Main, master, develop, Main) HEAD@{7}: reset: moving to 36b6843
```
**git reflog** cho phép bạn theo dõi các thao tác của chúng ta như, chúng ta checkout từ branch nào, hay tạo commit nào, hay chúng ta xoá branch nào, hay cherry-pick hoặc rebase

Ứng dụng:
phần nhiều **git reflog** được sử dụng để truy vết các commit hoặc các branch bị lỡ tay xoá, hay các thao tác nhầm (như **merge** nhầm hay **rebase** nhầm) khi cho bạn muốn **reset** trở lại commit trước khi thao tác. Khi đó **git reflog** sẽ giúp chúng ta kiểm tra được **commit** mình muốn trở lại là commit nào.


# **Github cherry-pick**
Đây là một lệnh khá phổ biến khi bạn muốn lấy một commit từ branch khác sang branch hiện tại

**Thực tế dự án:**
Ban đầu khi bạn code chức năng **A** vậy nên bạn checkout từ branch develop (coi develop là branch phát triển đi) và bạn có 2 commit là **a1** và **a2**
Sau đó, từ branch develop, bạn lại checkout sang branch **B** để phát triển chức năng B và có một commit **b**
Và đến khi bạn muốn test khi gộp chức năng của **b** với **a1** thôi, thì chúng ta sẽ làm như thế nào?

Rất đơn giản, bạn chỉ cần đứng ở Branch **B** và cherry-pick commit của **a1** vậy là xong? ^^

Xem các commit của Branch A
```
git log --oneline -5 A
b1685cd (A) a2
3abe031 a1
```

Xem các commit của Branch B
```
git log --oneline -5 B
d7dcd7b (HEAD -> B) b
```

Cherry-pick commit **a1** sang Branch **B** và kiểm tra
```
git checkout B
git cherry-pick 3abe031

Result:
git log --oneline -5 B
2d6b856 (HEAD -> B) a1
d7dcd7b b
```

Qua ví dụ trên ta nhận thấy.
nội dung thay đổi commit của **a1** đã được copy qua branch **B** 
nhưng lưu ý thêm mã commit ủa **a1** đã được thay mới.
Vậy nên ta có thể hiểu **git cherry-pick** giúp chúng ta cập nhật thêm thay đổi của commit đó và đồng thời sẽ ghi lại mã commit cho commit mới.

Bổ sung:
Cách dùng này rất tiện lợi, trong trường hợp bạn muốn chọn lựa để test một vài chức năng nhất định, hoặc chỉ định một vài chức năng thay đổi để deploy lên server.

# **Github rebase**
Trong các công cụ của **Git**, có lẽ **rebase** được coi là một trong những công cụ đa dạng và nhiều **option** nhất

giờ chúng ta sẽ chạy thử một lệnh và xem nó nhé
```
git rebase -i HEAD~2
```
Result:
```
pick d7dcd7b b
pick 2d6b856 a1

# Rebase 36b6843..2d6b856 onto 36b6843 (2 commands)
#
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup <commit> = like "squash", but discard this commit's log message
# x, exec <command> = run command (the rest of the line) using shell
# b, break = stop here (continue rebase later with 'git rebase --continue')
# d, drop <commit> = remove commit
# l, label <label> = label current HEAD with a name
# t, reset <label> = reset HEAD to a label
# m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
# .       create a merge commit using the original merge commit's
# .       message (or the oneline, if no original merge commit was
# .       specified). Use -c <commit> to reword the commit message.
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
```

nhìn nhiều option như vậy nhưng thực sự cho đến giờ mình cũng mới chỉ xài có mấy option dưới đây


* **pick** : Giữ lại commit này
* **reword** : Đổi tên commit
* **edit** : Dừng và sửa đổi nội dung thay đổi của commit chỉ định
* **drop** : Bỏ qua commit chỉ định

Ngoài ra, rebase còn giúp chúng ta có thể thay đổi lại thứ tự commit
Before
```
pick d7dcd7b b
pick 2d6b856 a1
```
Chúng ta chỉ cần đổi lại vị trí 2 commit
```
pick 2d6b856 a1
pick d7dcd7b b
```
Và chúng ta **:q** nếu đang sử dụng Vim.

Thấy không, rất đơn giản và làm được nhiều thứ ^^

# **Kết luận:**
Sau khi xem qua vài viết này, chắc hẳn các bạn đã có thêm chút công cụ giúp cho mình có thể thao tác và quản lý code của mình tốt hơn rùi phải không nào ^^
Theo cá nhân mình, kiến thức về git chỉ cần tầm này là các bạn đã có thể hoàn toàn kiểm soát toàn bộ code dự án của mình rùi.

Còn lại chỉ cần bổ sung ít kinh nghiệm thực chiến nữa thôi ^^
Bài viết của mình hơi đơn giản nên có gì các bạn góp ý thêm nhé

Rất cám ơn mọi người đã dành thời gian đọc bài viết của mình ^^

Vậy chúng ta sẽ gặp lại ở bài viết sau nhé, cám ơn đã dành thời gian quan tâm và hẹn gặp lại

Hãy comment bên dưới để có gì chúng ta cùng trao đổi thêm nhé ^_^
