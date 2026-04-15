# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600289
**Name:** Thái Tuấn Khang
**Date:** 2026-04-15

---

## 1. Kết quả thí nghiệm

Chạy `agent_simulation.py` với 2 bộ dữ liệu và ghi lại kết quả:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 10 | Correct - returns valid electronics product with reasonable price |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 3 | Incorrect - picks extreme outlier (999999) instead of valid product |

---

## 2. Phan tich & nhan xet

### Tại sao Agent trả lời sai khi dùng Garbage Data?

Garbage data chứa nhiều vấn đề về chất lượng dữ liệu. Duplicate IDs (id=1 xuất hiện 2 lần) khiến Agent có thể xử lý sai trọng tâm. Wrong data types (price là "ten dollars" thay vì số) có thể gây lỗi parsing. Extreme outliers (Nuclear Reactor giá 999999) khiến Agent đưa ra quyết định sai lầm nghiêm trọng khi nó chọn sản phẩm có giá cao nhất mà không kiểm tra tính hợp lý. Null values (id=None, price=0, category=None) làm Agent không thể xử lý hoặc bỏ qua records. Tất cả các vấn đề này ảnh hưởng trực tiếp đến chất lượng đầu ra của Agent - nếu dữ liệu đầu vào chứa "rác", Agent sẽ học và phản hồi những thông tin sai lệch.

---

## 3. Kết luận

**Quality Data > Quality Prompt?**

Đồng ý. Nếu prompt được viết tốt nhưng dữ liệu đầu vào chứa nhiều lỗi (duplicates, outliers, null values, sai datatype) thì Agent vẫn sẽ đưa ra kết quả sai. Chất lượng dữ liệu là nền tảng - nó quyết định Agent có thể học và phản hồi đúng hay không. Một prompt tốt chỉ có thể tối ưu hóa cách Agent sử dụng dữ liệu, nhưng không thể biến dữ liệu rác thành chính xác.
