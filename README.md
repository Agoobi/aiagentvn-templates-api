# aiagentvn-templates-api

Public JSON API cho metadata các Remotion motion graphic template, dùng cho agent/tool
khác gọi tới để biết template nào đang có sẵn.

Nguồn dữ liệu: `src/templates/registry.ts` trong repo private
[aiagentvn-motion-graphic-template](https://github.com/Agoobi/aiagentvn-motion-graphic-template),
được sync thủ công qua git submodule `templates-api` — xem `AGENTS.md` ở repo đó để biết quy trình
cập nhật khi thêm/sửa/xoá template.

## Endpoint

```
GET https://agoobi.github.io/aiagentvn-templates-api/templates.json
```

## Response shape

```json
{
  "source": "aiagentvn-motion-graphic-template",
  "generatedAt": "2026-08-18T23:56:17.808Z",
  "count": 31,
  "templates": [
    {
      "id": "creative/free-style",
      "name": "Free Style",
      "category": "creative",
      "behavior": "creative",
      "description": "...",
      "aspectRatio": "9:16"
    }
  ]
}
```
