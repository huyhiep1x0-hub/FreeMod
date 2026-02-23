# Static files for remote content

Thu muc `html/` dung de luu noi dung tinh de app doc tu Git (raw URL):

- `updates.html`: noi dung tab `Cap nhat`
- `notices.html`: noi dung tab `Thong bao`
- `menu-visible.txt`: file `true/false` de an/hien menu header tu xa
- `header-visibility.json`: bat/tat hien thi menu/header tu xa

## 1) Cau hinh URL trong `client-ui`

Dat bien moi truong (vi du `.env.production`):

```env
VITE_UPDATES_STATIC_URL=https://raw.githubusercontent.com/<user>/<repo>/main/html/updates.html
VITE_NOTICES_STATIC_URL=https://raw.githubusercontent.com/<user>/<repo>/main/html/notices.html
VITE_REMOTE_HEADER_VISIBLE_URL=https://raw.githubusercontent.com/<user>/<repo>/main/html/menu-visible.txt
VITE_REMOTE_HEADER_VISIBLE_POLL_MS=30000
```

## 2) Dinh dang `menu-visible.txt` (khuyen dung)

Noi dung file chi can:

```txt
true
```

hoac

```txt
false
```

## 3) Dinh dang file `header-visibility.json` (tuy chon)

```json
{
  "headerVisible": true,
  "updatedAt": "2026-02-22T00:00:00Z",
  "note": "Set false de an menu/header tu xa"
}
```

App ho tro ca:
- JSON key: `headerVisible`, `showHeader`, `menuVisible`, `features.headerVisible`
- Text thuong: `true/false`, `1/0`, `show/hide`, `visible/hidden`
