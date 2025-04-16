<<<<<<< HEAD
# ecb-plugin-core
Plugin Core Trait Wordpress
=======

# ECB Core

ECB Core là một plugin nền dùng cho các plugin khác trong hệ thống WordPress do bạn phát triển. Plugin này chứa các Trait, Helper, Class và định nghĩa cần thiết để tái sử dụng, giảm lặp code, và giúp bạn xây dựng các plugin chuyên nghiệp theo hướng OOP.

---

## 📁 Cấu trúc thư mục

```
ecb-core/
├── ecb-core.php                # File khởi động plugin chính
│
├── trait/                      # Chứa các Trait dùng lại
│   ├── ECB_Notice_Trait.php         # Hiển thị admin notice
│   ├── ECB_Validator_Trait.php      # Các hàm kiểm tra dữ liệu đầu vào
│   └── ECB_File_Trait.php           # Xử lý tệp (upload, kiểm tra, v.v.)
│
├── classes/                    # Các class chức năng dùng chung
│   └── ECB_Logger.php               # Ghi log lỗi hoặc hành động
│
├── config/                     # File cấu hình và hằng số
│   └── constants.php
│
└── functions/                  # Các hàm global hỗ trợ nhỏ
    └── general.php
```

---

## 🧩 Chức năng chính

| Thành phần                  | Mô tả                                                                 |
|----------------------------|----------------------------------------------------------------------|
| `trait/ECB_Notice_Trait.php`    | Gồm các hàm hiển thị thông báo trong trang quản trị (`notice-success`, `error`, v.v.) |
| `trait/ECB_Validator_Trait.php` | Gồm các hàm kiểm tra định dạng email, số, chuỗi rỗng...          |
| `trait/ECB_File_Trait.php`      | Hỗ trợ kiểm tra file hợp lệ, xử lý đường dẫn, upload...         |
| `classes/ECB_Logger.php`        | Hỗ trợ ghi log ra file, dạng timestamp, dùng debug              |
| `config/constants.php`          | Định nghĩa hằng số toàn cục (plugin version, path, prefix...)    |
| `functions/general.php`         | Các hàm tiện ích (ex: `ecb_generate_random_string()`)           |

---

## 🔗 Cách sử dụng trong plugin khác

```php
// Tích hợp ECB Core bằng cách yêu cầu plugin này
require_once WP_PLUGIN_DIR . '/ecb-core/trait/ECB_Notice_Trait.php';

class My_Custom_Plugin {
    use ECB_Notice_Trait;

    public function show_message() {
        $this->display_admin_notice('Xin chào từ plugin chính!', 'notice-success');
    }
}
```

---

## ⚠️ Yêu cầu khi sử dụng

- Đảm bảo plugin này đã được cài và kích hoạt trước khi sử dụng ở các plugin khác.
- Nên kiểm tra bằng `class_exists()` hoặc `trait_exists()` để tránh lỗi.

---

## 📌 Tác giả

- Author: KhanhECB
- Version: 1.0.0

---
>>>>>>> e18a5e5 (first commit)
