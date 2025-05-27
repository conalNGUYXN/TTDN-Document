# Hướng dẫn cài đặt Winlogbeat trên Windows Server 2019
## 1. Kiểm tra kết nối đến ELK Server
```bash
ping dia_chi_elasticsearch
```
## 2. Tải và giải nén Winlogbeat

- Truy cập trang chính thức: [https://www.elastic.co/downloads/beats/winlogbeat](https://www.elastic.co/downloads/beats/winlogbeat)
- Tải bản `.zip` tương ứng với Windows.
- Giải nén vào thư mục: `C:\Program Files\Winlogbeat`.

## 3. Cấu hình Winlogbeat

## 4. Thiết lập các log cần thu thập

## 5. Tải index template và dashboards

## 6. Cài Winlogbeat dưới dạng dịch vụ Windows

## 7. Kiểm tra trạng thái dịch vụ

## 8. Kiểm tra dữ liệu trong Elasticsearch

```bash
curl -XGET http://<ĐỊA_CHỈ_ELASTICSEARCH>:9200/_cat/indices?v
```

---