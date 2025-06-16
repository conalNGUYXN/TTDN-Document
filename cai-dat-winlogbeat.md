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

Mở file cấu hình bằng Powershell dưới quyền Administrator:

```powershell
notepad "C:\Program Files\Winlogbeat\winlogbeat.yml"
```
Chỉnh sửa phần Kibana host:

```yaml
#Kibana Host
host: "ĐỊA_CHỈ_ELASTICSEARCH:5601"
```
Chỉnh sửa phần output:

```yaml
output.elasticsearch:
  hosts: ["http://<ĐỊA_CHỈ_ELASTICSEARCH>:9200"]
```

## 4. Tải index template và dashboards

Chạy PowerShell dưới quyền Administrator:

```powershell
cd 'C:\\Program Files\\Winlogbeat'
.\winlogbeat.exe setup -e
```

## 5. Cài Winlogbeat dưới dạng dịch vụ Windows

```powershell
.\install-service-winlogbeat.ps1
```

Khởi động dịch vụ:

```powershell
Start-Service winlogbeat
```

---
## 6. Kiểm tra trạng thái dịch vụ

```powershell
Get-Service winlogbeat
```

---
## 7. Kiểm tra dữ liệu trong Elasticsearch

```bash
curl -XGET http://<ĐỊA_CHỈ_ELASTICSEARCH>:9200/_cat/indices?v
```

---