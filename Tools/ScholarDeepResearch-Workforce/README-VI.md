# ScholarDeepResearch-Workforce

> **Hệ Thống Đa Tác Tử Nghiên Cứu Học Thuật Quy Mô Doanh Nghiệp**
> 22 Worker | 528 Agent | 8 Tầng HierarchicalSwarm | Tự Động Lưu Theo Nhiệm Vụ v2.0.0

---

## 🎯 Tổng Quan

ScholarDeepResearch-Workforce là hệ thống agent nghiên cứu tự động toàn diện cho việc khám phá, phân tích và tổng hợp tài liệu học thuật. Hệ thống cung cấp quyền truy cập hơn 350 triệu bài báo học thuật với 10 Phương Pháp Đọc Phê Bình và tự động lưu kết quả.

---

## 📋 Mục Lục

1. [Khả Năng Chính](#khả-năng-chính)
2. [Kiến Trúc](#kiến-trúc)
3. [Cài Đặt & Thiết Lập](#cài-đặt--thiết-lập)
4. [Hướng Dẫn Sử Dụng](#hướng-dẫn-sử-dụng)
5. [Tham Khảo Lệnh](#tham-khảo-lệnh)
6. [10 Ví Dụ Thực Tế](#10-ví-dụ-thực-tế)
7. [Tiêu Chuẩn Chất Lượng](#tiêu-chuẩn-chất-lượng)
8. [Xử Lý Sự Cố](#xử-lý-sự-cố)

---

## 🔧 Khả Năng Chính

| Khả Năng | Mô Tả |
|----------|-------|
| **350M+ Bài Báo** | Truy cập cơ sở dữ liệu học thuật toàn diện |
| **10 Phương Pháp Đọc Phê Bình** | Phân tích tài liệu chuyên sâu |
| **Tìm Kiếm Đa Nguồn** | Scholar, ArXiv, PubMed, bioRxiv, Patents, Web |
| **Phân Tích Đa Phương Thức** | Xử lý tài liệu dựa trên thị giác |
| **Phân Tích Dữ Liệu** | Phân tích thống kê với Python |
| **Xác Thực Trích Dẫn** | Đảm bảo không có ảo giác |
| **Tự Động Lưu v2.0.0** | 💾 Kết quả lưu theo thư mục động theo nhiệm vụ |

---

## 🏗️ Kiến Trúc

### 8-Tier HierarchicalSwarm

| Tầng | Tên | Workers | Chức Năng | Auto-Save |
|------|-----|---------|-----------|-----------|
| 1 | Query & Intelligence | 3 | Phân tích truy vấn | 💾 phase-01 |
| 2 | Search Strategy | 2 | Kỹ thuật từ khóa | 💾 phase-02 |
| 3 | Search Acquisition | 4 | Tìm kiếm đa nguồn | 💾 phase-03 |
| 4 | Content Extraction | 2 | Trích xuất toàn văn | 💾 phase-04 |
| 5 | Critical Reading | 4 | Áp dụng 10 phương pháp | 💾 phase-05 |
| 6 | Analysis & Synthesis | 3 | Thống kê, trực quan hóa | 💾 phase-06 |
| 7 | Quality Validation | 2 | Xác thực trích dẫn | 💾 phase-07 |
| 8 | Delivery & Evolution | 2 | Tạo báo cáo | 💾 phase-08 |

---

## ⚙️ Cài Đặt & Thiết Lập

### Yêu Cầu

- Truy cập công cụ ScholarGPT (advancedScholarSearch, arxivSearch, v.v.)
- Môi trường Python cho code_interpreter
- Khả năng Vision cho xử lý đa phương thức

### Bắt Đầu Nhanh

```bash
# Di chuyển đến thư mục workforce
cd D:\AGENTS\_Workforce\ScholarDeepResearch-Workforce

# Xem cấu trúc
tree /F

# Bắt đầu phiên nghiên cứu
# Chỉ cần cung cấp câu hỏi nghiên cứu để kích hoạt workforce
```

---

## 📖 Hướng Dẫn Sử Dụng

### Bước 1: Gửi Truy Vấn Nghiên Cứu

Cung cấp câu hỏi nghiên cứu bằng ngôn ngữ tự nhiên. Workforce tự động:

1. Làm rõ và định hướng truy vấn
2. Phân loại lĩnh vực học thuật
3. Tạo chiến lược tìm kiếm tối ưu

### Bước 2: Xử Lý Tự Động

Pipeline 8 tầng thực thi với **tự động lưu động v2.0.0**:

- **MỚI**: Mỗi phiên tạo thư mục riêng theo nội dung nhiệm vụ
- Định dạng: `{YYYY-MM-DD}_{slug_chủ_đề}`
- Ví dụ: `2026-01-31_ai_trong_giao_duc_2024_2026/`
- Tất cả 8 phase output lưu vào thư mục này
- Có thể khôi phục hoàn toàn nếu bị gián đoạn

### Bước 3: Xem Kết Quả

Nhận báo cáo nghiên cứu toàn diện với:

- Tóm tắt nguồn (≥50 từ mỗi nguồn)
- Phân tích phê bình với 10 phương pháp
- Trích dẫn đã xác thực (100% chính xác)
- Biểu đồ và sơ đồ

### Bước 4: Quản Lý Phiên

```bash
/save-all          # Lưu phiên hiện tại
/recall <session>  # Khôi phục phiên trước
/list-memory       # Xem các phiên đã lưu
/search <query>    # Tìm kiếm trong kết quả
```

---

## 🔍 Tham Khảo Lệnh

| Lệnh | Mô Tả | Ví Dụ |
|------|-------|-------|
| `/search` | Tìm kiếm kết quả | `/search "machine learning" --scope results` |
| `/recall` | Khôi phục phiên | `/recall session-001` |
| `/save-all` | Lưu phiên | `/save-all --name "AI-Review-2026"` |
| `/list-memory` | Liệt kê phiên | `/list-memory --type sessions --limit 10` |

---

## 📚 10 Ví Dụ Thực Tế

### Ví Dụ 1: Tổng Quan Nghiên Cứu Hệ Thống

**Truy vấn**: "Thực hiện tổng quan hệ thống về ứng dụng AI trong y tế từ 2020-2026"

**Workflow**:

1. Tầng 1: Phân tích → Lĩnh vực: Y học + AI
2. Tầng 2: Chiến lược → Từ khóa: AI, ML, y tế, chẩn đoán
3. Tầng 3: Tìm kiếm → PubMed (chính), Scholar, ArXiv
4. Tầng 5: Áp dụng đọc phê bình tuân thủ PRISMA
5. Tầng 8: Tạo báo cáo tổng quan

**Đầu ra**: Sơ đồ PRISMA, tổng hợp chủ đề, kết quả meta-analysis

---

### Ví Dụ 2: Phân Tích Bối Cảnh Công Nghệ

**Truy vấn**: "Phân tích tiến bộ gần đây trong Large Language Models (2024-2026)"

**Workflow**:

1. Tầng 1: Lĩnh vực → Khoa học Máy tính / NLP
2. Tầng 3: ArXiv (chính), Scholar, Patents
3. Tầng 5: Ánh xạ Cấu trúc + Phân tích Đối chiếu
4. Tầng 6: Trực quan hóa timeline, so sánh khả năng
5. Tầng 8: Báo cáo bối cảnh công nghệ

**Đầu ra**: Timeline tiến hóa, bảng so sánh model, khoảng trống nghiên cứu

---

### Ví Dụ 3: Nghiên Cứu Liên Ngành

**Truy vấn**: "Khám phá giao điểm giữa biến đổi khí hậu và machine learning"

**Workflow**:

1. Tầng 1: Phân loại đa lĩnh vực (Môi trường + CS)
2. Tầng 3: Tìm kiếm song song qua tất cả database
3. Tầng 5: Áp dụng tất cả 10 phương pháp đọc phê bình
4. Tầng 6: Tổng hợp liên ngành
5. Tầng 8: Báo cáo liên ngành với biểu đồ

**Đầu ra**: Sơ đồ chồng lấn lĩnh vực, phân loại ứng dụng, hướng tương lai

---

### Ví Dụ 4: Nghiên Cứu Y Sinh Chuyên Sâu

**Truy vấn**: "Nghiên cứu mới nhất về công nghệ vaccine mRNA"

**Workflow**:

1. Tầng 1: Lĩnh vực → Y sinh / Miễn dịch học
2. Tầng 3: PubMed + bioRxiv (chính), Scholar
3. Tầng 4: Trích xuất dữ liệu thử nghiệm lâm sàng
4. Tầng 5: Phương pháp Truy Vấn Phê Bình + Kiểm Tra Sự Thật
5. Tầng 8: Tổng hợp bằng chứng lâm sàng

**Đầu ra**: Sơ đồ cơ chế, dữ liệu hiệu quả, tóm tắt an toàn

---

### Ví Dụ 5: Nghiên Cứu Bối Cảnh Bằng Sáng Chế

**Truy vấn**: "Phân tích bằng sáng chế cho hệ thống nhận dạng xe tự lái"

**Workflow**:

1. Tầng 1: Lĩnh vực → Kỹ thuật / Bằng sáng chế
2. Tầng 3: PatentSearch (chính), Scholar, Web
3. Tầng 5: Ánh xạ Cấu trúc cho patent claims
4. Tầng 6: Trực quan hóa xu hướng patent
5. Tầng 8: Báo cáo bối cảnh IP

**Đầu ra**: Xu hướng nộp patent, chủ sở hữu chính, cụm công nghệ

---

### Ví Dụ 6: Đánh Giá Công Nghệ Giáo Dục

**Truy vấn**: "Hiệu quả của hệ thống gia sư AI trong giáo dục K-12"

**Workflow**:

1. Tầng 1: Lĩnh vực → Giáo dục + AI
2. Tầng 3: Scholar, PubMed (kết quả học tập)
3. Tầng 5: Tóm Tắt & Đặt Câu Hỏi + Xác Định Giả Định
4. Tầng 6: Phân tích effect size
5. Tầng 8: Khuyến nghị dựa trên bằng chứng

**Đầu ra**: Meta-analysis kết quả học tập, hướng dẫn triển khai

---

### Ví Dụ 7: Tình Báo Cạnh Tranh

**Truy vấn**: "So sánh đầu ra nghiên cứu của các phòng thí nghiệm AI hàng đầu"

**Workflow**:

1. Tầng 1: Trích xuất thực thể → Tập trung tổ chức
2. Tầng 3: ArXiv, Scholar với bộ lọc tác giả
3. Tầng 5: Phân Tích Đối Chiếu + Nghiên Cứu Quan Điểm
4. Tầng 6: Chỉ số xuất bản, phân tích trích dẫn
5. Tầng 8: Báo cáo tình báo cạnh tranh

**Đầu ra**: So sánh xuất bản, lĩnh vực tập trung, mạng lưới hợp tác

---

### Ví Dụ 8: Nghiên Cứu Phương Pháp Chuyên Sâu

**Truy vấn**: "Thực hành tốt nhất cho tối ưu hóa kiến trúc Transformer"

**Workflow**:

1. Tầng 1: Lĩnh vực → Phương pháp ML
2. Tầng 3: ArXiv (chính) với code repositories
3. Tầng 5: Làm Rõ Khái Niệm Chính + Trích Dẫn Phản Chiếu
4. Tầng 6: Tổng hợp benchmark hiệu năng
5. Tầng 8: Hướng dẫn phương pháp kỹ thuật

**Đầu ra**: Bảng kỹ thuật tối ưu, so sánh benchmark, mẫu code

---

### Ví Dụ 9: Khám Phá Chủ Đề Mới Nổi

**Truy vấn**: "Tình trạng hiện tại của quantum machine learning là gì?"

**Workflow**:

1. Tầng 1: Lĩnh vực → Máy tính Lượng tử + ML
2. Tầng 3: ArXiv, Scholar, bài báo hội nghị gần đây
3. Tầng 5: Tạo Sơ Đồ + Ánh Xạ Cấu Trúc
4. Tầng 6: Đánh giá khả năng
5. Tầng 8: Báo cáo mức độ sẵn sàng công nghệ

**Đầu ra**: Phân loại Quantum ML, hạn chế hiện tại, lộ trình nghiên cứu

---

### Ví Dụ 10: Nghiên Cứu Liên Quan Chính Sách

**Truy vấn**: "Các phương pháp quản lý AI ở các khu vực pháp lý khác nhau"

**Workflow**:

1. Tầng 1: Lĩnh vực → Chính sách + Công nghệ
2. Tầng 3: Scholar, Web (nguồn chính phủ), Patents
3. Tầng 5: Phân Tích Đối Chiếu giữa các khu vực
4. Tầng 6: Trực quan hóa so sánh chính sách
5. Tầng 8: Báo cáo bối cảnh quy định

**Đầu ra**: Bảng so sánh khu vực, timeline quy định, phân tích khoảng trống

---

## 📊 Tiêu Chuẩn Chất Lượng

| Chỉ Số | Ngưỡng | Mô Tả |
|--------|--------|-------|
| Đa dạng Nguồn | ≥3 database | Độ phủ database tối thiểu |
| Nguồn Học Thuật | ≥8 bài báo | Số nguồn học thuật tối thiểu |
| Chất Lượng Tóm Tắt | ≥50 từ | Độ dài tóm tắt mỗi nguồn |
| Tính Hợp Lệ Trích Dẫn | 100% | Tất cả trích dẫn đã xác thực |
| Điểm E-O | ≥0.85 | Điểm Efficiency-Optimization |

---

## 🔧 Xử Lý Sự Cố

| Vấn Đề | Giải Pháp |
|--------|-----------|
| Tìm kiếm không có kết quả | Mở rộng truy vấn, thử database khác |
| Phiên bị gián đoạn | Dùng `/recall last` để tiếp tục |
| Xác thực trích dẫn thất bại | Kiểm tra định dạng DOI, thử lại |
| Không đạt quality gate | Xem lại nguồn, thêm database |

---

## 📂 Cấu Trúc Thư Mục

```
ScholarDeepResearch-Workforce/
├── Context-Layer/
│   ├── Knowledge-Base/    (28 files: PLAYBOOKS, SKILLS, EXPERIENCE)
│   ├── Second-Brain/      (Brain, Memory, Command)
│   ├── Research-Integration/
│   └── Retrieval/
├── Workers/               (22 thư mục worker)
├── Team Orchestration/    (8 file điều phối)
└── Tools/
```

---

## 📚 Tham Khảo

- **Blueprint**: vnBuilderPro_MAS2026 v2.2.0
- **Efficiency**: arXiv:2601.14192v1
- **Standard**: WorkforceGenerator-MAS v1.3.2

---

*ScholarDeepResearch-Workforce v2.0.0 | Hệ Thống MAS Nghiên Cứu Học Thuật | Tự Động Lưu Động*
