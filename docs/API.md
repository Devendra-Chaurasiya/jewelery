# API Integration Guide

## Endpoint Used by Frontend

- Method: `POST`
- Path: `/generate_image`
- Full URL: `<apiBaseUrl>/generate_image`

`<apiBaseUrl>` is entered from the Design Studio API URL input.

## Request

Headers:

```http
Content-Type: application/json
```

Body:

```json
{
  "prompt": "A stunning piece of jewelry: ..."
}
```

## Success Response

```json
{
  "image_base64": "iVBORw0KGgoAAA..."
}
```

The frontend converts this to:

`data:image/png;base64,<image_base64>`

## Error Behavior

- Non-2xx responses are treated as failures
- Response text is logged in browser console
- UI stops loading and does not show mock image fallback

## Backend CORS Requirements

Allow your frontend origin and preflight requests.

FastAPI example:

```python
from fastapi.middleware.cors import CORSMiddleware

app.add_middleware(
    CORSMiddleware,
    allow_origins=["http://localhost:5173", "http://127.0.0.1:5173"],
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)
```

## Troubleshooting

- `405` on `OPTIONS`: CORS/preflight is not configured correctly
- `422`: request body schema mismatch
- `500`: backend runtime/model issue (check backend logs)
- Empty image: ensure response includes `image_base64`