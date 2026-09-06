# aiagentvn-templates-api

API JSON công khai chứa metadata của các template motion graphic Remotion và các video mẫu trên Google Drive.

Nguồn template chuẩn là `TEMPLATE_REGISTRY` trong repo
[premium-text-to-video](https://github.com/Agoobi/premium-text-to-video). Danh sách video mẫu
được đối chiếu từ `.tmp/video-catalog.csv`; các dòng có ID cũ được chuẩn hóa theo registry thật.
Thư mục Drive ưu tiên được dùng để đối chiếu nguồn template:
https://drive.google.com/drive/u/2/folders/1C7_lXQ2lZNdWigDTqH6rScpHMJQWCvVn

## Endpoint

```
GET https://agoobi.github.io/aiagentvn-templates-api/templates.json
```

## Response shape

```json
{
  "source": "premium-text-to-video",
  "generatedAt": "2026-09-06T00:00:00.000Z",
  "count": 45,
  "templates": [
    {
      "id": "news/tech-light",
      "name": "Tech News Light",
      "category": "news",
      "behavior": "fixed",
      "description": "Mô tả template bằng tiếng Việt.",
      "aspectRatio": "9:16",
      "videoDriveLinks": [
        {
          "topic": "Công nghệ",
          "url": "https://drive.google.com/file/d/...",
          "updatedAt": "2026-08-27"
        }
      ]
    }
  ]
}
```

`videoDriveLinks` là mảng vì một template có thể có nhiều video mẫu. Template chưa có
video trong catalog vẫn được giữ trong API với mảng rỗng; không tạo link giả.
