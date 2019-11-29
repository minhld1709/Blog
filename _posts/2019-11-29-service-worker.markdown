---
layout: post
title: Service Worker
date: 2019-11-29 08:32:20 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: 2019-11-29-service-worker/layout.png
fig-caption: # Add figcaption (optional)
tags: [PWA]
---
# **Giới thiệu**
Mấy năm gần đây khái niệm **PWA** đã và đang là một từ khóa rất hot trong giới native. Vậy hôm nay chúng ta sẽ cùng tìm hiểu sơ qua **PWA** là gì, và ra đời khi nào, và tại sao nó lại hot tới vậy 

# **PWA là gì? nó ra đời khi nào? và mục đích của nó là gì?**
Sau khi tham khảo các tài liệu và định nghĩa của một số bạn thì mình thấy đây là định nghĩa dễ hiểu nhất.
Progressive Web App (**PWA**) là một `nhóm các kĩ thuật` với mục đích tạo ra trải nghiệm tốt hơn đối với các `Application` trên nền tảng `Web`

Họ nâng cao khả năng trải nghiệm bằng cách:
  - cung cấp khả năng ngoại tuyến (**offline**)
  - đẩy thông báo (**push notification**)
  - giao diện và tốc độ tương đương ứng dụng Native
  - lưu trữ cục bộ các nguồn tài nguyên (**local caching**)

Ví dụ rõ ràng nhất mà các bạn hay gặp là **[https://m.facebook.com/](https://m.facebook.com/)**

Vậy một trang web **PWA** cần thoả mãn những điều kiện sau:
  - [x] - **Progressive** : có thể chạy trên mọi trình duyệt
  
  - [x] - **Response** : phù hợp với tất cả các kích cỡ màn hình

  - [x] - **Connectivity independent** : khả năng kết nối tăng cường hay nói đơn giản hơn là có thể hoạt động kể cả khi offline hoặc chất lượng mạng thấp

  - [x] - **App like** : hiển thị giống app để người dùng tương tác

  - [x] - **Fresh** : luôn được cập nhật mới nhờ service worker

  - [x] - **Safe** : bảo mật nhờ sử dụng HTTPS để ngăn chặn snooping và đảm bảo nội dung không bị làm giả

  - [x] - **Discoverable** : dễ dàng nhận diện, phục vụ cho mục đích SEO

  - [x] - **Re-engageable** : kết nối với người dùng dễ dàng hơn với tính năng.

  - [x] - **Installable** : cho phép người dùng đánh dấu ứng dụng web trên màn hình điện thoại để tiện truy cập sau đó

  - [x] - **Linkable** : dễ dàng chia sẻ thông qua URL (vượt trội hơn so với app)

**PWA** được giới thiệu lần đầu bởi Google vào năm 2015 và được sử dụng khá phổ biến trên `Android`, tuy nhiên phải mãi đến phiên bản 11.3, Apple mới cho phép **PWA** trên hệ điều hành `IOS`.

# Trải nghiệm
Sau khi đi lục lọi một chút thì mình nghĩ đây là bản demo dễ hiểu nhất, các bạn có thể trải nghiệm các chức năng và những điểm mạnh của **PWA** thông qua demo dưới đây

[https://demopwa.surge.sh/](https://demopwa.surge.sh/)

![Demo Screen]({{site.baseurl}}/assets/img/2019-11-24-pwa-introduction/demo_screen.png)

# **Kết luận**
Sau khi được trải nghiệm qua **PWA**, tôi tin chắc các bạn làm **Web Developer** đã có thêm một sự lựa chọn tuyệt vời để gia tăng trải nghiệm người dùng hỗ trợ trên **Mobile**, vô cùng đơn giản và đầy hiệu quả phải không nào ^_^

## Ở bài tiếp theo, chúng ta sẽ thử tự tạo một bản PWA của riêng mình nha ^_^

## **Reference:**
  * [https://fullstackstation.com/su-anh-huong-progressive-web-app-pwa-den-tuong-lai-nganh-lap-trinh-web/](https://fullstackstation.com/su-anh-huong-progressive-web-app-pwa-den-tuong-lai-nganh-lap-trinh-web/)
  * [https://viblo.asia/p/progressive-web-app-xoa-nhoa-khoang-cach-giua-web-va-mobile-apps-924lJY2mZPM](https://viblo.asia/p/progressive-web-app-xoa-nhoa-khoang-cach-giua-web-va-mobile-apps-924lJY2mZPM)

## Các bạn muốn góp ý hay trao đổi gì xin hãy commen ở phần bên dưới nhé ^_^

# Thankyou and See you 