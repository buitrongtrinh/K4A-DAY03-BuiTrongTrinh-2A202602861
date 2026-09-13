# 📊 BÁO CÁO THU HOẠCH NGHIỆM THU BÀI LAB 3 (BƯỚC 3 — SUBMISSION ARTIFACT)

> **Họ và Tên Học viên:** Bùi Trọng Trịnh
> **Mã Sinh Viên / Mã Học viên:** 2A202602861
> **Chủ đề Lựa chọn:** Trợ lý Học vụ & Tra cứu Lịch thi VinUni: tra cứu GPA, lịch thi và đặt lịch tư vấn học vụ với Cố vấn.

---

## 1. BẢNG CHẤM ĐIỂM AGENTIC FIT SCORING MATRIX (ĐÁNH GIÁ CHỦ ĐỀ)

| Tiêu chí Đánh giá | Mức độ (1 - 5) | Giải trình chi tiết lý do chọn điểm |
| :--- | :---: | :--- |
| **1. Multi-step Reasoning** | 5 / 5 | Agent cần phân rã yêu cầu như: tra cứu hồ sơ sinh viên, xác định GPA/lịch thi/cố vấn, sau đó sử dụng dữ liệu này để tư vấn hoặc đặt lịch hẹn. |
| **2. Tool Interaction** | 5 / 5 | Hệ thống sử dụng MCP Server để gọi các công cụ tra cứu học vụ, tra cứu lịch thi và đặt lịch tư vấn với cố vấn học tập. |
| **3. Dynamic Decision** | 4 / 5 | Hành động tiếp theo phụ thuộc Observation từ tool: ví dụ chỉ đặt lịch khi tra cứu thấy sinh viên tồn tại và dùng đúng tên cố vấn trả về. |
| **4. Long Horizon Goal** | 3 / 5 | Agent giữ mục tiêu hỗ trợ sinh viên hoàn tất yêu cầu học vụ xuyên suốt một phiên, nhưng số bước xử lý thường ngắn. |
| **TỔNG ĐIỂM AGENTIC FIT** | **17 / 20** | *Tổng điểm > 12/20: Bài toán rất phù hợp triển khai Agentic System.* |

---

## 2. TRÍCH XUẤT KẾT QUẢ WATERFALL TRACE LOG (SAU KHI CHẠY TEST SUITE TRÊN API THẬT)

> ✅ **Trạng thái nghiệm thu LLM thật:** Đã cấu hình `GEMINI_API_KEY`, chạy bằng môi trường `lab-vin-env` và hoàn thành 5 test cases với Gemini API. File trace bên dưới lưu lại Thought, Native Tool Calling, Observation từ MCP Server và Final Answer.

Đoạn trích xuất Waterfall Trace tiêu biểu từ file `docs/trace_waterfall.json`:

```json
[
  {
    "step": 1,
    "action_type": "TOOL_EXECUTION",
    "thought": "Gemini quyết định gọi công cụ 'schedule_appointment' với tham số: {\"datetime_str\": \"09:00 16/09/2026\", \"advisor_name\": \"PGS.TS Nguyễn Văn A\", \"student_id\": \"SV2026001\"}",
    "tool_name": "schedule_appointment",
    "arguments": {
      "student_id": "SV2026001",
      "datetime_str": "09:00 16/09/2026",
      "advisor_name": "PGS.TS Nguyễn Văn A"
    },
    "observation": {
      "status": "SUCCESS",
      "student_id": "SV2026001",
      "booking_id": "BK-SV2026001-99",
      "datetime": "09:00 16/09/2026",
      "advisor": "PGS.TS Nguyễn Văn A"
    },
    "latency_ms": 1179.08
  }
]
```

---

## 3. TỔNG KẾT KẾT QUẢ NGHIỆM THU & NỘP BÀI

- [x] Đã điền API Key thật trong `.env` và xác nhận Agent chạy mượt mà trên Gemini API.
- **Tổng số Test Cases đã chạy thành công:** 5 / 5 test cases.
- **Số lượt gọi Tool qua MCP Server chính xác:** 5 lượt.
- **Kết quả đẩy Repo nộp bài:** [x] Đã commit và push mã nguồn thành công lên GitHub cá nhân.

---

> ✅ **HOÀN TẤT NỘP BÀI:** Sao chép đường link GitHub Repository cá nhân của bạn và dán vào ô nộp bài trên hệ thống LMS VLearn để hoàn tất Bài Lab 3!
