# Bài 3 - Dockerfile đóng gói trang HTML tĩnh

## Nội dung index.html
```html
<h1>Hello Docker Session 09!</h1>
```

## Nội dung Dockerfile
```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
```

## Build image
```
```

## Chạy container cổng 8081 + kiểm tra curl
```
<h1>Hello Docker Session 09!</h1>
```
