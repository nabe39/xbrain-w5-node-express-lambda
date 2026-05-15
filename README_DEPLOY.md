# Báo cáo nộp bài Lab W5 - Node.js Express on Lambda (BYOL)

**Người nộp:** Duc
**Repository:** https://github.com/nabe39/xbrain-w5-node-express-lambda.git
**Giảng viên chấm bài:** Anh Huỳnh Nghĩa (nghia.huynh@techxcorp.com)

---

## 🚀 1. Link API Gateway URL đã deploy

Dưới đây là link API Gateway gốc đã được deploy thành công lên môi trường AWS Lambda (us-west-2):

- **Root URL:** https://qanbvr1wxd.execute-api.us-west-2.amazonaws.com
- **Test Endpoint (Hello):** https://qanbvr1wxd.execute-api.us-west-2.amazonaws.com/api/hello/Lan
- **Test Endpoint (Echo - POST):** https://qanbvr1wxd.execute-api.us-west-2.amazonaws.com/api/echo

Tất cả các endpoint đều hoạt động chính xác trả về đúng định dạng JSON giống hệt lúc chạy Local.

---

## ☁️ 2. Thông tin triển khai AWS

- **AWS Account ID:** `318662970982`
- **AWS Region:** `us-west-2`
- **Stack Name:** `byol-node-express-duc`
- **IAM User:** `Duc` (Workshop Participant)
- **Deployment Tool:** AWS CLI (CloudFormation Package & Deploy)

---

## 📝 3. Chi tiết Chiến lược & Đo đạc Cold Start (Trích xuất từ NOTES.md)

### Chiến lược đã chọn: Strategy A — `serverless-http` adapter

**Lý do chọn Strategy A (`serverless-http`):**

- Thay đổi code cực kỳ nhỏ (~3 dòng)
- Không cần sửa `app.js` — giữ nguyên hoàn toàn
- Thư viện phổ biến, được dùng rộng rãi
- Cold start ổn: 200–400ms

---

## 📂 4. Cấu trúc Source Code

- `lambda.js`: File Entrypoint mới dành riêng cho Lambda (Sử dụng `serverless-http`).
- `app.js` & `server.js`: Giữ nguyên bản gốc.
- `template.yaml`: Đã cấu hình Handler trỏ vào `lambda.js` và xử lý quyền triển khai.
- `NOTES.md`: Chứa các ghi chú gốc của quá trình thử nghiệm.

---

\*Cảm ơn anh Nghĩa đã review bài tập này
