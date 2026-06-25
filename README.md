# 🧹 Dự án Mô phỏng Agent Máy hút bụi thông minh (Vacuum Cleaner Agent)

Dự án phát triển một chương trình mô phỏng Agent máy hút bụi tự động tìm đường đi tối ưu để làm sạch các vết rác trên bản đồ ô lưới (Grid Map). Dự án sử dụng ngôn ngữ **Python** kết hợp thư viện đồ họa **Tkinter** để trực quan hóa quá trình tìm kiếm và di chuyển của Agent thông qua nhiều chiến lược giải thuật khác nhau.

---

## 🚀 Tính năng nổi bật
- **Bản đồ trực quan (GUI Tkinter):** Hiển thị Agent (máy hút bụi), các ô có rác, ô trống và các chướng ngại vật (vật cản).
- **Log lịch sử thời gian thực:** Hiển thị chi tiết từng bước đi, hành động (`UP`, `DOWN`, `LEFT`, `RIGHT`, `CLEAN`) và chi phí ước lượng của Agent trên giao diện.
- **Đa dạng giải thuật:** Tích hợp đầy đủ từ các thuật toán tìm kiếm mù (Uninformed Search) đến tìm kiếm có tri thức và tìm kiếm địa phương (Local Search).

---

## 🧠 Các Giải thuật Tìm kiếm triển khai trong Dự án

Dự án bao gồm 2 nhóm chiến lược tìm kiếm chính:

### 1. Chiến lược Tìm kiếm Không gian Trạng thái (Cơ bản)
- **BFS Kiểu 1 & Kiểu 2 (Breadth-First Search):** Tìm kiếm theo chiều rộng, đảm bảo tìm được chuỗi hành động ngắn nhất đến khi sạch sàn.
- **DFS (Depth-First Search):** Tìm kiếm theo chiều sâu, ưu tiên đi hết một nhánh trước khi quay lui.
- **UCS (Uniform Cost Search):** Tìm kiếm với chi phí đồng đều, tối ưu hóa theo tổng giá trị hành động.
- **A* Search:** Tìm kiếm có chứng thực sử dụng hàm Heuristic (ước lượng khoảng cách đến các ô rác) để định hướng đường đi tối ưu nhất.

### 2. Chiến lược Tìm kiếm Địa phương (Local Search - Nâng cao)
- **Simple Hill Climbing:** Leo đồi đơn giản, chọn bước đi đầu tiên tốt hơn trạng thái hiện tại.
- **Steepest Ascent Hill Climbing:** Leo đồi dốc nhất, quét toàn bộ lân cận và chọn bước đi tối ưu nhất (chi phí thấp nhất).
- **Stochastic Hill Climbing:** Leo đồi ngẫu nhiên, chọn ngẫu nhiên một trong số các trạng thái lân cận tốt hơn.
- **Random Restart Hill Climbing:** Leo đồi khởi động lại ngẫu nhiên. Nếu rơi vào cực tiểu cục bộ (kẹt), thuật toán tự động reset về vị trí ban đầu và bắt đầu lượt tìm kiếm mới (giới hạn theo `MAX_RESTART`).
- **Local Beam Search:** Tìm kiếm chùm cục bộ. Duy trì và phát triển song song một chùm gồm $k$ trạng thái tốt nhất ở mỗi bước lặp để tránh bị kẹt và mở rộng không gian tìm kiếm.

---

## 🛠️ Cấu trúc Trạng thái và Ràng buộc Bài toán
- **Trạng thái (State):** Được định nghĩa dưới dạng một bộ ba tuple `(x, y, grid)` bao gồm vị trí hiện tại của Agent `(x, y)` và trạng thái ma trận các ô rác/vật cản `grid`.
- **Hàm chi phí (`get_cost`):** Hàm heuristic đánh giá mức độ hiệu quả (số lượng rác còn lại trên bản đồ). Mục tiêu của Agent là đưa chi phí này về `0` (Goal Test thành công).
- **Ràng buộc hành động:** Để tối ưu hóa hiệu năng di chuyển, khi Agent đứng tại ô có rác (`grid[x][y] == 1`), hệ thống áp đặt ràng buộc bắt buộc Agent phải thực hiện hành động `CLEAN` trước khi thực hiện các bước di chuyển khác.

---

## 💻 Hướng dẫn Cài đặt và Chạy ứng dụng

### Yêu cầu hệ thống
- Máy tính đã cài đặt **Python 3.x**.
- Môi trường chạy mã nguồn **Jupyter Notebook** hoặc **Visual Studio Code** (đã cài extension Jupyter).

### Các thư viện sử dụng
Các thư viện cốt lõi đều là thư viện chuẩn của Python:
```bash
# Thư viện giao diện và cấu trúc dữ liệu nền tảng
tkinter
collections (deque)
heapq
random
time
