<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

Bạn nên cài đặt nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) trước, sau đó `direnv allow` sau khi vào thư mục ( [.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) sẽ được thực thi tự động sau khi vào thư mục).

Ý nghĩa là: Dịch tiếng Trung sang tiếng Nhật, tiếng Hàn, tiếng Anh, dịch tiếng Anh sang tất cả các ngôn ngữ khác. Nếu bạn chỉ muốn hỗ trợ tiếng Trung và tiếng Anh, bạn chỉ cần viết `zh: en` .

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

### Hướng dẫn tự động dịch tài liệu

Xem kho mã [xxai-art/doc](https://github.com/xxai-art/doc)

Bạn nên cài đặt nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) trước, sau đó `direnv allow` sau khi vào thư mục ( [.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) sẽ được thực thi tự động sau khi vào thư mục).

Để tránh cơ sở mã lớn được dịch sang hàng trăm ngôn ngữ, tôi đã tạo một cơ sở mã riêng cho từng ngôn ngữ và tạo một tổ chức để lưu trữ cơ sở mã

Đặt biến môi trường `GITHUB_ACCESS_TOKEN` rồi chạy [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) sẽ tự động tạo kho lưu trữ mã.

Tất nhiên, bạn cũng có thể đặt nó trong một cơ sở mã.

Tham khảo tập lệnh dịch [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Mã kịch bản được diễn giải như sau:

[bunx](https://bun.sh/docs/cli/bunx) là sự thay thế cho npx, nhanh hơn. Tất nhiên, nếu bạn chưa cài đặt bun, bạn có thể sử dụng `npx` để thay thế.

`bunx mdt zh` hiển thị `.mdt` trong thư mục zh là `.md` , xem 2 tệp được liên kết bên dưới

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` là mã cốt lõi để dịch (nếu bạn chỉ cài đặt `nodejs` , nhưng chưa cài đặt `bun` và `direnv` , bạn cũng có thể chạy `npx i18n` để dịch).

Nó sẽ phân tích [cú pháp i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , cấu hình của `i18n.yml` trong tài liệu này như sau:

```
en:
zh: ja ko en
```

Ý nghĩa là: Dịch tiếng Trung sang tiếng Nhật, tiếng Hàn, tiếng Anh, dịch tiếng Anh sang tất cả các ngôn ngữ khác. Nếu bạn chỉ muốn hỗ trợ tiếng Trung và tiếng Anh, bạn chỉ cần viết `zh: en` .

Cuối cùng là [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) trích xuất nội dung giữa tiêu đề chính và phụ đề đầu tiên của `README.md` của mỗi ngôn ngữ để tạo mục nhập `README.md` . Code rất đơn giản, bạn có thể tự xem.

Google API được sử dụng để dịch miễn phí. Nếu bạn không thể truy cập Google, vui lòng định cấu hình và đặt proxy, chẳng hạn như:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Tập lệnh dịch sẽ tạo bộ đệm dịch trong thư mục `.i18n` , vui lòng kiểm tra nó với `git status` và thêm nó vào kho lưu trữ mã để tránh dịch lặp lại.

Vui lòng chạy `bunx i18n` mỗi khi bạn sửa đổi bản dịch để cập nhật bộ đệm.

Nếu chỉnh sửa đồng thời cả văn bản gốc và bản dịch thì cache sẽ bị lẫn lộn, nếu muốn chỉnh sửa chỉ có thể chỉnh sửa một cái, sau đó chạy `bunx i18n` để cập nhật cache.
