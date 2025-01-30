[WebRTC book](https://webrtcforthecurious.com/docs/webrtc-for-the-curious.pdf)
# WebRTC
## **1. WebRTC là gì?**  
- **WebRTC** (Web Real-Time Communication) là công nghệ giúp truyền dữ liệu thời gian thực giữa các trình duyệt mà không cần máy chủ trung gian.  
- Kết nối trong WebRTC là **peer-to-peer (P2P)**, giúp truyền dữ liệu nhanh chóng và tiết kiệm tài nguyên.  

## **2. Vai trò của máy chủ trong WebRTC**  
- **Máy chủ không tham gia vào việc truyền dữ liệu**, nhưng **cần thiết trong giai đoạn thiết lập kết nối**.  
- **Signaling Server** (máy chủ báo hiệu) được sử dụng để giúp hai thiết bị trao đổi thông tin cần thiết ban đầu.  

## **3. Cách WebRTC thiết lập kết nối**  

### **Bước 1: Trao đổi thông tin phiên (SDP - Session Description Protocol)**  
- **Client 1** tạo một **offer** chứa thông tin phương tiện (SDP).  
- **Signaling Server** gửi offer này đến **Client 2**.  
- **Client 2** lưu trữ offer và gửi **answer** chứa thông tin SDP của nó ngược lại.  
- Sau bước này, cả hai client đều biết được **cấu hình phương tiện** của nhau (âm thanh, video).  

### **Bước 2: Trao đổi thông tin mạng (ICE Candidates)**  
- **ICE Candidates** được tạo ra từ các **STUN và TURN servers** để xác định địa chỉ mạng có thể kết nối.  
- ICE Candidates của từng client được gửi qua **Signaling Server** để đối phương nhận được thông tin mạng.  
- Khi cả hai client có đủ thông tin ICE của nhau, chúng có thể **thiết lập kết nối P2P trực tiếp**.  

## **4. Kết nối và truyền dữ liệu P2P**  
- Sau khi hoàn tất trao đổi thông tin phiên và mạng, hai client kết nối trực tiếp mà không cần máy chủ trung gian.  
- Mọi dữ liệu truyền qua WebRTC sẽ là **P2P**, giúp giảm độ trễ và tăng hiệu suất truyền tải.  

# Digram 

![image](https://github.com/user-attachments/assets/e61c0593-e7af-4f1c-b9ab-8ebd40873a7d)


## **1. Giải thích sơ đồ**
1. **Giai đoạn Signaling (Trao đổi SDP và ICE Candidates)**
   - Hai trình duyệt (Client 1 và Client 2) sử dụng Signaling Server để trao đổi SDP (Session Description Protocol) và ICE Candidates.
   - SDP chứa thông tin phương tiện (âm thanh/video) mà mỗi bên hỗ trợ.
   - ICE Candidates giúp xác định địa chỉ mạng để kết nối trực tiếp.

2. **Giai đoạn Kết nối P2P**
   - Sau khi hoàn tất trao đổi ICE Candidates, hai client có thể thiết lập kết nối ngang hàng (P2P).
   - Dữ liệu (âm thanh/video/file) được truyền trực tiếp mà không qua Signaling Server.

3. **STUN & TURN Servers**
   - STUN Server giúp xác định địa chỉ mạng của client.
   - TURN Server chỉ được dùng khi kết nối P2P trực tiếp không khả thi (ví dụ: NAT chặn kết nối).  


## **2. Lợi ích của mô hình WebRTC**
- **Giảm độ trễ**: Dữ liệu truyền trực tiếp giữa các client.  
- **Tiết kiệm tài nguyên**: Không cần máy chủ trung gian để xử lý dữ liệu.  
- **Bảo mật cao**: Dữ liệu có thể được mã hóa để đảm bảo an toàn.  






