# Crime-Drone-Prediction
Dự đoán khu vực có khả năng xảy ra tội phạm dựa trên bộ dữ liệu INDORE POLICE CRIME DATASET
## Phân tích dữ liệu
- Dataset: https://www.kaggle.com/datasets/quangjames/crime-drone-india-2018
	* Dòng: 2090 và Cột: 9
 	* Thông tin các trường:
		+ timestamp: Thời gian xảy ra tội phạm
		+ act379: Cướp
		+ act13: Đánh bạc
		+ act279: Tai nạn
		+ act323: Bạo lực
		+ act363: Bắt cóc
		+ act302: Giết người
- Dữ liệu không có giá trị null
## Tiền xử lý dữ liệu
- Phân tích trường **timestamp**:
	* Dữ liệu không cùng định dạng: '1/3/2018 14:30'; '3/1/2018 16:30'
	* Cần chuyển đổi sang cùng định dạng
		+ Đổi "." thành ":"
		+ Đổi "-" thành "/"
		+ Chuyển về định dạng datetime
- Tách timestamp thành các đặc trưng: year, month, day, hour, dayofyear, week, weekofyear, dayofweek, weekday, quarter
- Thêm đặc trưng phân loại "Crime Type" với các giá trị:
	* 'act379': 'Robbery'
	* 'act13': 'Gambling'
	* 'act279': 'Accident'
	* 'act323': 'Violence'
	* 'act363': 'Kidnapping'
	* 'act302': 'Murder'
- Tạo ma trận tương quan để xem xét mối quan hệ giữa các thuộc tính. Chọn các thuộc tính có tương quan thấp với nhau để giảm chiều dữ liệu.
- Thực hiện giảm chiều dữ liệu thủ công hoặc PCA
