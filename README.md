<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

Một phần mã của trang web là mã nguồn mở, hoan nghênh bạn đã giúp tối ưu hóa bản dịch.

## mã đầu cuối

* [mã đầu cuối](https://github.com/xxai-art/web)
* [Gói ngôn ngữ cho toàn bộ trang web](https://github.com/xxai-art/web/tree/main/i18n)
* [Gói ngôn ngữ cho các mô-đun đăng nhập](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Trang web Tài liệu đa ngôn ngữ](https://github.com/xxai-doc)

Ngôn ngữ lập trình giao diện người dùng là [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , bổ sung một số tính năng dựa trên cú pháp coffeescript, xem [./coffee_plus.md](./coffee_plus.md) .

## Quốc tế hóa các trang web và tài liệu

Xây dựng trên 3 dự án sau

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Hậu tố là `.mdt` , bạn có thể sử dụng cú pháp tương tự như `<+ ./coffee_plus/import.js>` để chỉ các tệp bên ngoài và tạo đánh dấu bằng hậu tố `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Bản dịch Markdown sẽ không dịch mã và liên kết, đồng thời sẽ lưu vào bộ đệm các câu đã dịch. Nếu bản dịch được sửa đổi nhưng văn bản gốc không bị sửa đổi, thì việc thực hiện lại bản dịch đó sẽ không ghi đè lên phần sửa đổi của bản dịch.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Các tệp ngôn ngữ để dịch các trang web được tạo bằng `yaml` .
