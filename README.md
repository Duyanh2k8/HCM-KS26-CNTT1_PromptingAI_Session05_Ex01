# [Bài thực hành 1] Lập kế hoạch tài chính cá nhân bằng Chain-of-Thought
## Prompt cho AI
### C – Context
Bạn là một cá nhân có thu nhập thay đổi theo từng tháng, hiện đang có một số khoản nợ cần thanh toán. Bạn muốn quản lý tài chính tốt hơn, cân đối giữa chi phí sinh hoạt, trả nợ, tiết kiệm và xây dựng quỹ dự phòng.

### R – Request
Hãy lập một kế hoạch tài chính cá nhân hàng tháng dựa trên dữ liệu tôi cung cấp. Phân bổ ngân sách hợp lý, đảm bảo không chi tiêu vượt quá thu nhập và ưu tiên thanh toán các khoản nợ đúng hạn.
### E – Explanation
Bài toán có nhiều dữ liệu và phép tính liên quan đến thu nhập, chi phí, nợ và tiết kiệm. Vì vậy, hãy áp dụng kỹ thuật Chain-of-Thought (CoT), chia quá trình xử lý thành từng bước logic để hạn chế sai sót.

**Quy trình tính toán:**

Bước 1: Tính toán tổng thu nhập khả dụng sau khi trừ thuế và chi phí cố định bắt buộc.
- Thu nhập bình quân = (T1 + T2 + T3)/3
- Thu nhập ròng = Thu nhập bình quân - Thuế/bảo hiểm
- Số tiền còn lại sau chi phí cố định = Thu nhập ròng - Chi phí cố định

Bước 2: Phân bổ khoản tiền trả nợ tối thiểu.
- Tổng nợ tối thiểu = cộng từng khoản nợ.
- Còn lại sau trả nợ = Kết quả bước 1c - Tổng nợ tối thiểu
- Nếu kết quả âm hoặc quá nhỏ, DỪNG và nêu cảnh báo cùng đề xuất điều chỉnh (cắt giảm, tăng thu nhập, đàm phán nợ) trước khi làm tiếp.

Bước 3: Trích lập quỹ tiết kiệm theo tỷ lệ cam kết.
- Tiết kiệm bắt buộc = 20% x thu nhập ròng (viết rõ phép nhân)
- Chia khoản này thành Quỹ dự phòng và Tiết kiệm mục tiêu theo tỷ lệ 50/50, trừ khi tôi nêu khác.
- Số còn lại để chi tiêu linh hoạt = kết quả Bước 2b - tiết kiệm bắt buộc

Bước 4: Chia phần còn lại cho chi tiêu linh hoạt theo quy tắc 50/30/20 cải tiến.
- 50% Chi tiêu thiết yếu linh hoạt
- 30% Chi tiêu cá nhân
- 20% Trả nợ vượt mức hoặc bổ sung quỹ dự phòng
   Tính từng phần bằng phép nhân hiển thị đầy đủ.
### A – Action
Thực hiện các phép tính cộng, trừ, nhân, chia cụ thể ở từng bước. Trình bày công thức, số liệu đầu vào và kết quả để người dùng có thể kiểm tra.

Sau đó, lập bảng phân bổ ngân sách cuối cùng bằng Markdown Table với các cột:
|Hạng mục|Số tiền (VNĐ)|Tỷ lệ (%)| Ghi chú|
|---|---|---|---|
|Chi phí cố định||||
|Trả nợ||||
|Tiết kiệm||||
|Quỹ dự phòng||||
|Chi tiêu thiết yếu||||
|Chi tiêu linh hoạt||||
|Tổng cộng||100%||
### T – Tone
Sử dụng ngôn ngữ đơn giản, dễ hiểu, chuyên nghiệp nhưng gần gũi. Giải thích ngắn gọn, tránh sử dụng quá nhiều thuật ngữ tài chính phức tạp.
### E – Extras
- Không tự ý tạo ra dữ liệu khi người dùng chưa cung cấp.
- Nếu thiếu thông tin quan trọng, hãy hỏi lại trước khi tính toán.
- Ưu tiên trả nợ đúng hạn và tránh phát sinh nợ mới.
- Đảm bảo tỷ lệ phân bổ ngân sách bằng chính xác 100% sau khi làm tròn.
- Nếu không đủ tiền đáp ứng các mục tiêu, phải chỉ rõ nguyên nhân và đề xuất phương án điều chỉnh.
- Không sử dụng Python, Pydantic hoặc công cụ lập trình.
- Chỉ trình bày các bước tính toán và kết quả trung gian có thể kiểm chứng, không yêu cầu tiết lộ suy luận nội bộ.

**DỮ LIỆU ĐẦU VÀO:**
- Thu nhập hàng tháng: [Nhập số tiền]
- Thuế và bảo hiểm: [Nhập số tiền]
- Chi phí cố định: [Nhập số tiền]
- Các khoản nợ: [Số tiền, lãi suất, thời hạn]
- Mục tiêu tiết kiệm: [Số tiền hoặc tỷ lệ]
- Quỹ dự phòng hiện có: [Nhập số tiền]

**ĐỊNH DẠNG ĐẦU RA:**
- Phần 1: Nhật ký suy luận logic (Reasoning Steps) chỉ ra công thức tính toán và số liệu trung gian.
- Phần 2: Bảng phân bổ ngân sách cuối cùng bằng Markdown Table với các cột: Hạng mục, Số tiền, Tỷ lệ %, Ghi chú.
## Phần 1: Nhật ký suy luận logic (Reasoning Steps) chỉ ra công thức tính toán và số liệu trung gian.
### Bước 1: Tính thu nhập khả dụng
Dữ liệu đầu vào:
- Thu nhập tháng 1: 10.500.000 VNĐ
- Thu nhập tháng 2: 12.000.000 VNĐ
- Thu nhập tháng 3: 11.570.000 VNĐ
- Thuế và bảo hiểm: 670.000 VNĐ/tháng
- Tiền thuê nhà: 3.500.000 VNĐ
- Điện, nước: 400.000 VNĐ
- Internet: 150.000 VNĐ
#### 1.1. Thu nhập bình quân:
(10.500.000 + 12.000.000 + 11.570.000)/3

=11.356.666,67 VNĐ
#### 1.2. Thu nhập ròng:
11.356.666,67 - 670.000 = 10.686.666,67 VNĐ
#### 1.3. Tổng chi phí cố định:
3.500.000 + 400.000 + 150.000 = 4.050.000 VNĐ
#### 1.4. Tiền còn lại sau chi phí cố định:
10.686.666,67 - 4.050.000 = 6.636.666,67 VNĐ
### Bước 2: Phân bổ tiền trả nợ
Dữ liệu khoản nợ:
|Khoản nợ	|Số tiền thanh toán	Thời hạn|
|---|---|
|Nợ A	|1.000.000 VNĐ/tháng	|Ngày 15|
|Nợ ngân hàng	|15.000.000 VNĐ/năm|	Ngày 3|
#### 2.1. Quy đổi khoản nợ ngân hàng theo tháng:
15.000.000/12 = 1.250.000 VNĐ
#### 2.2. Tổng tiền trả nợ tối thiểu mỗi tháng:
1.000.000 + 1.250.000 = 2.250.000 VNĐ
#### 2.3. Tiền còn lại sau trả nợ:
6.636.666,67 - 2.250.000 = 4.386.666,67 VNĐ
### Bước 3: Trích lập tiết kiệm
Mục tiêu tiết kiệm là 20% thu nhập ròng.
#### 3.1. Tổng tiền tiết kiệm:
10.686.666,67 x 20% = 2.137.333,33 VNĐ
#### 3.2. Chia thành hai khoản theo tỷ lệ 50/50:
- Quỹ dự phòng:

2.137.333,33 x 50% = 1.068.666,67 VNĐ
- Tiết kiệm mục tiêu:
2.137.333,33 x 50% = 1.068.666,67 VNĐ
#### 3.3. Tiền còn lại để chi tiêu linh hoạt:
4.386.666,67 - 2.137.333,33 = 2.249.333,34 VNĐ
### Bước 4: Phân bổ chi tiêu linh hoạt theo tỷ lệ 50/30/20
Tổng tiền để phân bổ: 2.249.333,34 VNĐ.
#### 4.1. Chi tiêu thiết yếu – 50%:
2.249.333,34 x 50% = 1.124.666,67 VNĐ

Dùng cho ăn uống, đi lại và các nhu cầu thiết yếu khác.
#### 4.2. Chi tiêu cá nhân – 30%:
2.249.333,34 x 30% = 674.800 VNĐ

Dùng cho giải trí và nhu cầu cá nhân.
#### 4.3. Trả nợ vượt mức – 20%:
2.249.333,34 x 20% = 449.866,67 VNĐ

Ưu tiên dùng khoản này để trả thêm nợ, hạn chế phát sinh lãi.

**Tổng ngân sách trả nợ mỗi tháng:**
2.250.000 + 449.866,67 = 2.699.866,67 VNĐ
## Phần 2: Bảng phân bổ ngân sách cuối cùng bằng Markdown Table với các cột: Hạng mục, Số tiền, Tỷ lệ %, Ghi chú.
Tổng thu nhập ròng dùng để phân bổ là 10.686.667 VNĐ sau khi làm tròn.
|Hạng mục	|Số tiền (VNĐ)	|Tỷ lệ (%)	|Ghi chú|
|---|---|---|---|
|Chi phí cố định	|4.050.000	|37,90%	|Tiền nhà, điện nước, internet|
|Trả nợ	|2.699.867	|25,26%	|Trả tối thiểu và trả thêm|
|Tiết kiệm	|1.068.667	|10,00%	|Tiết kiệm mục tiêu|
|Quỹ dự phòng	|1.068.666	|10,00%|	Dành cho trường hợp phát sinh|
|Chi tiêu thiết yếu|	1.124.667|	10,53%|	Ăn uống, đi lại|
|Chi tiêu linh hoạt|	674.800|	6,31%	|Giải trí, nhu cầu cá nhân|
|Tổng cộng	|10.686.667	|100,00%	|Không vượt thu nhập ròng|
