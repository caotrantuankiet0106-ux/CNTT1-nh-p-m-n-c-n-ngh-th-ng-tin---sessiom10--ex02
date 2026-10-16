 Markdown
# Báo cáo Phân tích & Source Code Markdown (Trang trại Lan)

## 1. Phân tích I/O (Input / Output)
* **Input (Thô):** Các ký tự mã lệnh đặc biệt như backtick đơn (`` ` ``), ba backtick kèm tên ngôn ngữ (`` `python` ``), ký tự bảng (`|`), và task list (`[ ]`).
* **Output (Render):** Giao diện chuyên nghiệp phân tách rõ Inline Code (lệnh ngắn), Code Block (có màu cú pháp), Bảng so sánh kỹ thuật và Task List tương tác.

## 2. Source Code chuẩn (`huong-dan-cam-bien.md`)
```markdown
# Hướng dẫn cài đặt cảm biến độ ẩm Lan

## 1. Cấu hình hệ thống
Chạy lệnh cập nhật `sudo apt update` và cài đặt thư viện bằng `pip install RPi.GPIO`.

## 2. Mã nguồn Python
```python
import RPi.GPIO as GPIO
import time

SENSOR_PIN = 17
PUMP_PIN = 22

GPIO.setmode(GPIO.BCM)
GPIO.setup(SENSOR_PIN, GPIO.IN)
GPIO.setup(PUMP_PIN, GPIO.OUT)

def kiem_tra():
    if GPIO.input(SENSOR_PIN) == 1:
        GPIO.output(PUMP_PIN, GPIO.HIGH)
    else:
        GPIO.output(PUMP_PIN, GPIO.LOW)

try:
    while True:
        kiem_tra()
        time.sleep(5)
except KeyboardInterrupt:
    GPIO.cleanup()
3. Bảng so sánh cảm biến
Tiêu chí	Cảm biến cũ	Cảm biến mới
Độ chính xác	Thấp	Cao (Chống nhiễu)
Kết nối	Qua mạch ADC	Chân GPIO trực tiếp
4. Task List kiểm tra thiết bị
[x] Kiểm tra nguồn điện bo mạch

[x] Cắm dây tín hiệu GPIO 17

[ ] Kiểm tra hệ thống nước

[ ] Chạy thử chương trình Python
