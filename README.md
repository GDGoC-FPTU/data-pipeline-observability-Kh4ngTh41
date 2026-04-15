[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23572319&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** kh4ngth41@example.com
**Name:** Kh4ngTh41

---

## Mô tả

Day 10 Lab: Xây dựng ETL Pipeline với Data Observability. Hoàn thành các hàm extract, validate, transform, load trong solution.py. Chạy experiment stress test với clean và garbage data để khảo sát chất lượng dữ liệu ảnh hưởng như thế nào đến Agent response.

---

## Cách chạy (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chạy ETL Pipeline
```bash
python solution.py
```

### Chạy Agent Simulation (Stress Test)
```bash
# Mô tả cách bạn chạy thí nghiệm Clean vs Garbage data
```

---

## Cấu trúc thư mục

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output của pipeline
├── experiment_report.md     # Báo cáo thí nghiệm
└── README.md                # File này
```

---

## Kết quả

Tổng hợp: 5 records input, 3 records valid (đã xử lý), 2 records bị loại (1 giá âm, 1 category rỗng). Pipeline đã tính discounted_price (giảm 10%) và thêm timestamp. Stress test cho thấy Agent trả lời đúng với clean data nhưng sai với garbage data (chọn outlier 999999).
