# OLM Panel by NTH — Bản phát hành

Repo này **chỉ chứa file đã build** để tải về. **Không chứa source code.**

| | |
|---|---|
| Source (private) | [`qnthanh210/Extension_OLM`](https://github.com/qnthanh210/Extension_OLM) |
| Remote config (public, chỉ JSON) | [`qnthanh210/olm-ext-remote-config`](https://github.com/qnthanh210/olm-ext-remote-config) |

---

## Cài đặt

Extension này **không** đăng Chrome Web Store, nên không cài bằng 1 click được.

### Bước 1 — tải file ZIP

Vào tab **Releases** của repo này, tải `olm-ext-v<phiên-bản>.zip`.

### Bước 2 — giải nén

Giải nén ra **một thư mục con** chứa file `manifest.json`.

> ⚠️ Nếu giải nén phẳng (thấy `manifest.json` ngay ngoài cùng mà không có thư mục con),
> Chrome sẽ báo lỗi. Phải có cấu trúc:
> ```
> olm-ext-vX.Y.Z/
>   ├── manifest.json      ← file này phải nằm ở đây
>   ├── background.js
>   ├── content.js
>   └── ...
> ```

### Bước 3 — nạp vào Chrome

1. Mở `chrome://extensions`
2. Bật **Developer mode** (góc trên bên phải)
3. Bấm **Load unpacked**
4. Chọn đúng thư mục con ở Bước 2

### Bước 4 — dùng

Mở <https://olm.vn> và nhập license key trong panel.

**Không cần nhập lại key khi cập nhật** — extension giữ license trong
`chrome.storage.local`.

---

## Yêu cầu

* **Chrome 111 trở lên** (cần content script `world: "MAIN"`)
* Chỉ chạy trên `https://olm.vn/*`
* Máy tính. **Không dùng được trên điện thoại** — Chrome Android không hỗ trợ extension.

---

## Cách cập nhật

Extension **không tự cập nhật** (không có Web Store để nhận bản mới).

```
1. Tải ZIP bản mới từ Releases
2. Giải nén ĐÈ lên đúng thư mục cũ (giữ nguyên vị trí)
3. chrome://extensions → bấm nút ⟳
```

Xoá cache đi khi có bản mới: xem thẻ **Sửa lỗi** trong `chrome://extensions`.

---

## Lệnh tắt

Sau khi cài, gõ `olm` vào ô địa chỉ Chrome rồi **nhấn dấu cách**:

| Lệnh | Tác dụng |
|---|---|
| `olm ` | mở menu nhập key + trạng thái |
| `olm status` | license + phiên bản config |
| `olm update` | ép kiểm tra cập nhật config |
| `olm on` / `olm off` | bật / tắt panel + highlight |
| `olm rollback` | quay lại phiên bản config trước |

> Chrome bắt buộc có **dấu cách** sau keyword. Gõ `olm` không có space sẽ bị coi
> là từ khoá tìm kiếm.

---

## Phiên bản

Xem tab **Releases** để có danh sách đầy đủ.

| Phiên bản | Thay đổi chính |
|---|---|
| 1.4.3 | Sửa lỗi đổi màu highlight |
| 1.4.2 | Sửa quét DOM liên tục gây nặng máy |
| 1.4.1 | Thêm mục trợ giúp trong menu |
| 1.4.0 | Remote Config engine |

---

## Liên hệ

Cần key license hoặc gặp lỗi: mở issue ở repo
[`Extension_OLM`](https://github.com/qnthanh210/Extension_OLM/issues).
