# bye
import requests

# Thông tin Zalo OA
ACCESS_TOKEN = "YOUR_ACCESS_TOKEN"
USER_ID = "USER_ID_CUA_NGUOI_NHAN"

# Nội dung tin nhắn
message_data = {
    "recipient": {
        "user_id": USER_ID
    },
    "message": {
        "text": "Chào tạm biệt! Hẹn gặp lại sau nhé! 😊"
    }
}

# Gửi tin nhắn qua API Zalo
url = "https://openapi.zalo.me/v2.0/oa/message"
headers = {
    "Content-Type": "application/json",
    "access_token": ACCESS_TOKEN
}

response = requests.post(url, json=message_data, headers=headers)

# Kiểm tra kết quả
if response.status_code == 200:
    print("Gửi tin nhắn thành công!")
else:
    print("Lỗi khi gửi tin nhắn:", response.json())
