**Execution of JavaScript Programs**:
- *Deferred execution*:
Thuộc tính `defer` khiến trình duyệt web trì hoãn việc thực thi tập lệnh cho đến khi tài liệu được tải và phân tích cú pháp. Điều này áp dụng các tập tin bên ngoài. Khi trình phân tích cú pháp gặp tập lệnh bị trì hoãn, nó sẽ tiếp tục phân tích cú pháp tài liệu và đồng thời tải xuống tệp.  
Cuối cùng, các tập lệnh có thuộc tính trì hoãn được thực thi theo thứ tự mà chúng được đặt trong tập lệnh.

```javascript
<script scr="js/file.js" defer></script>
```

- *Asynchronous execution*:
Thuộc tính `async` khiến tập lệnh được thực thi ngay khi có sẵn nhưng nó không chặn phân tích cú pháp tài liệu. Trình duyệt tiếp tục phân tích cú pháp tài liệu và đồng thời tải tệp.  
Các tập lệnh có thuộc tính `async` được thực thi ngay sau khi chúng được tải, do đó chúng có thể bị lỗi trật tự.

```javascript
<script scr="js/file2.js" async></script>
```