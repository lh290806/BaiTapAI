# 🤖 Đồ Án Trí Tuệ Nhân Tạo (Artificial Intelligence Toolkit)

![Python Version](https://img.shields.io/badge/python-3.8%20%7C%203.9%20%7C%203.10%20%7C%203.11-blue?style=for-the-badge&logo=python)
![Framework](https://img.shields.io/badge/UI-Tkinter-orange?style=for-the-badge&logo=python)
![Academic Project](https://img.shields.io/badge/Project-UTEX%20Academic-red?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

Dự án là một tập hợp các ứng dụng mô phỏng và trực quan hóa các giải thuật Trí Tuệ Nhân Tạo kinh điển từ nền tảng lý thuyết đến thực hành đồ họa trực quan. Hệ thống được xây dựng bằng ngôn ngữ **Python** kết hợp với thư viện giao diện **Tkinter**, hỗ trợ đắc lực cho việc giảng dạy, học tập và nghiên cứu các chiến lược tối ưu hóa, tìm kiếm không gian trạng thái và lý thuyết trò chơi đối kháng.

---

## 🚀 Giao Diện Demo Trực Quan
*(Dưới đây là hình ảnh hoạt động thực tế của từng phân hệ thuật toán)*

### Phân Hệ 1: Tô Màu Bản Đồ (CSP)
> 📸 ****

### Phân Hệ 2: Trò Chơi Tic-Tac-Toe AI
> 📸 **[BẠN CHÈN LINK ẢNH HOẶC GIF DEMO TIC-TAC-TOE VÀO ĐÂY]**

### Phân Hệ 3: Agent Máy Hút Bụi Thông Minh
> 📸 ![Demo Máy Hút Bụi](https://github.com/user-attachments/assets/0cd17b8f-426c-4e40-b12b-3e5172ccbd34)

---

## 🧩 Khám Phá Các Phân Hệ Thuật Toán

### 1. Phân Hệ Tô Màu Bản Đồ TP.HCM (Constraint Satisfaction Problem - CSP)
Ứng dụng giải quyết bài toán Thỏa Mãn Ràng Buộc dựa trên bản đồ thu nhỏ gồm 7 quận/huyện trọng điểm tại TP.HCM (Phú Nhuận, Bình Thạnh, Quận 1, Quận 3, Quận 4, Quận 5, Quận 10). Mục tiêu là tô màu các quận sao cho không có hai quận lân cận nào trùng màu nhau bằng cách sử dụng tối đa 4 màu.
* **Tính năng chính:** Cho phép chọn thuật toán, theo dõi từng bước duyệt màu ngẫu nhiên/thử nghiệm, tự động cập nhật trạng thái "Hợp lệ", "Quay lui (Backtrack)" hoặc "Xung đột" lên màn hình theo thời gian thực.
* **Các thuật toán tích hợp:**
    * **Backtracking:** Thuật toán quay lui kiểm tra điều kiện ràng buộc thuần túy.
    * **Forward Checking:** Kỹ thuật nhìn kiểm tra trước để thu hẹp sớm miền giá trị của các biến lân cận chưa tô.
    * **Backtracking kết hợp AC-3:** Thuật toán duy trì tính nhất quán của cung (Arc Consistency) để tối ưu hóa không gian tìm kiếm.
    * **Min-Conflicts:** Thuật toán tìm kiếm địa phương tối ưu, lặp lại việc chọn ngẫu nhiên biến bị xung đột và gán giá trị làm giảm tối thiểu số lượng vi phạm ràng buộc.

### 2. Trình Giải Cờ Caro Tic-Tac-Toe (Adversarial Search)
Mô phỏng một trò chơi đối kháng kinh điển trên bàn cờ kích thước $3 \times 3$ giữa Người chơi (Quân O) và Trí tuệ nhân tạo (Quân X) từ một thế cờ khởi tạo có sẵn.
* **Tính năng chính:** Giao diện bàn cờ thân thiện, cơ chế khóa ô thông minh sau khi đánh, tự động thông báo kết quả Thắng/Thua/Hòa ngay khi đạt trạng thái kết thúc. Người dùng có thể linh hoạt chuyển đổi thuật toán để so sánh sức mạnh tính toán của AI.
* **Các thuật toán tích hợp:**
    * **Minimax:** Duyệt toàn bộ cây trò chơi để đưa ra quyết định tối ưu tuyệt đối cho AI.
    * **Alpha-Beta Pruning:** Tối ưu hóa thuật toán Minimax bằng cách cắt tỉa các nhánh không làm ảnh hưởng đến kết quả cuối cùng, tăng tốc độ xử lý một cách vượt trội.
    * **Expectimax:** Phù hợp cho môi trường có tính đến xác suất ngẫu nhiên hoặc hành vi không tối ưu từ phía đối thủ.

### 3. Hệ Thống Mô Phỏng Agent Máy Hút Bụi (Advanced Search Algorithms)
Một nền tảng giả lập cao cấp, trực quan hóa cách thức di chuyển và xử lý của một Robot thông minh (Agent) thực hiện nhiệm vụ quét dọn toàn bộ các ô rác trên lưới ma trận $3 \times 3$.
* **Tính năng điều khiển:** Bảng điều khiển tích hợp toàn diện gồm: Tạo sàn ngẫu nhiên, Bắt đầu mô phỏng, Tạm dừng/Tiếp tục, Hủy chạy, cấu hình giới hạn độ sâu cắt (Cutoff) và khu vực hiển thị Log hành động chi tiết (`UP`, `DOWN`, `LEFT`, `RIGHT`, `CLEAN`) theo từng bước thời gian.
* **Hệ thống thuật toán đồ sộ tích hợp:**
    * **Tìm kiếm mù (Uninformed Search):** Định dạng BFS (Kiểu 1 & 2), DFS (Kiểu 1 & 2), Tìm kiếm sâu dần IDS (Kiểu 1 & 2) và Tìm kiếm chi phí đồng nhất UCS.
    * **Tìm kiếm có thông tin (Informed Search):** Tìm kiếm tham lam (Greedy Search) và Thuật toán tối ưu A*, IDA* dựa trên khoảng cách Manhattan đến các ô có rác.
    * **Tìm kiếm cục bộ (Local Search):** Các biến thể Leo Đồi (Simple Hill Climbing, Steepest Ascent HC, Stochastic HC, Random Restart HC), Tìm kiếm chùm cục bộ (Local Beam Search), và thuật toán Mô phỏng Luyện Kim (Simulated Annealing).
    * **Môi trường đặc biệt (Belief & Nondeterministic):** Tìm kiếm trong không gian niềm tin toàn phần/một phần (Belief Space Search) áp dụng khi Agent không có thông tin hoàn hảo về vị trí, và thuật toán Tìm kiếm đồ thị AND-OR trong điều kiện môi trường bất định.

---

## 📂 Cấu Trúc Mã Nguồn

```text
├── .idea/
├── Visualizer/
├── README.md
├── bfs_8_puzzle.ipynb
├── main.py
├── model_8_puzzle.ipynb
├── model_vaccum.ipynb
├── simple_8_puzzle.ipynb
├── simple_vacuum.ipynb
└── vacuum.ipynb
