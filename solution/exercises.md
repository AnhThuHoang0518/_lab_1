# Ngày 1 — Bài Tập & Phản Ánh
## Nền Tảng LLM API | Phiếu Thực Hành

**Thời lượng:** 1:30 giờ  
**Cấu trúc:** Lập trình cốt lõi (60 phút) → Bài tập mở rộng (30 phút)

---

## Phần 1 — Lập Trình Cốt Lõi (0:00–1:00)

Chạy các ví dụ trong Google Colab tại: https://colab.research.google.com/drive/172zCiXpLr1FEXMRCAbmZoqTrKiSkUERm?usp=sharing

Triển khai tất cả TODO trong `template.py`. Chạy `pytest tests/` để kiểm tra tiến độ.

**Điểm kiểm tra:** Sau khi hoàn thành 4 nhiệm vụ, chạy:
```bash
python template.py
```
Bạn sẽ thấy output so sánh phản hồi của GPT-4o và GPT-4o-mini.

---

## Phần 2 — Bài Tập Mở Rộng (1:00–1:30)

### Bài tập 2.1 — Độ Nhạy Của Temperature
Gọi `call_openai` với các giá trị temperature 0.0, 0.5, 1.0 và 1.5 sử dụng prompt **"Hãy kể cho tôi một sự thật thú vị về Việt Nam."**
Temperature 0.0: Một sự thật thú vị về Việt Nam là đất nước này có một hệ thống hang động lớn nhất thế giới, đó là hang Sơn Đoòng. Hang Sơn Đoòng nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng, tỉnh Quảng Bình. Hang được phát hiện vào năm 1991 bởi một người dân địa phương tên là Hồ Khanh, nhưng mãi đến năm 2009 mới được công bố rộng rãi sau khi một đoàn thám hiểm người Anh do Howard Limbert dẫn đầu tiến hành khảo sát. Hang Sơn Đoòng có kích thước khổng lồ với chiều dài hơn 5 km, cao 200 m và rộng 150 m, đủ lớn để chứa cả một tòa nhà chọc trời 40 tầng. Bên trong hang còn có hệ sinh thái riêng với rừng cây, sông ngầm và các loài động thực vật độc đáo. 

Temperature 0.5: Một sự thật thú vị về Việt Nam là đất nước này có hang động lớn nhất thế giới, được gọi là Hang Sơn Đoòng. Hang động này nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng ở tỉnh Quảng Bình. Hang Sơn Đoòng được phát hiện vào năm 1991 bởi một người dân địa phương tên là Hồ Khanh, nhưng mãi đến năm 2009, một nhóm thám hiểm người Anh mới chính thức khảo sát và công bố sự tồn tại của nó. Hang động này có kích thước khổng lồ, với chiều dài khoảng 9 km, chiều cao đạt tới 200 mét và rộng 150 mét. Bên trong hang có cả một hệ sinh thái riêng biệt với rừng cây và sông ngầm. Hang Sơn Đoòng đã thu hút sự quan tâm của nhiều nhà thám hiểm và du khách từ khắp nơi trên thế giới. 

Temperature 1.0: Một sự thật thú vị về Việt Nam là quốc gia này sở hữu hệ thống hang động lớn nhất thế giới, Hang Sơn Đoòng. Hang Sơn Đoòng nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng ở tỉnh Quảng Bình. Hang động này được hình thành khoảng 2-5 triệu năm trước, và nó được phát hiện lần đầu tiên vào năm 1991 bởi một người dân địa phương tên Hồ Khanh. Tuy nhiên, mãi đến năm 2009, hang động mới được công nhận là hang động lớn nhất thế giới sau một cuộc thám hiểm do Hiệp hội Hang động Hoàng gia Anh thực hiện. Hang Sơn Đoòng có kích thước khổng lồ với chiều cao có thể chứa được cả một tòa nhà 40 tầng và rộng đủ để một chiếc Boeing 747 bay qua. 

Temperature 1.5: Một sự thật thú vị về Việt Nam là hệ thống hang Sơn Đoòng, nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng, tỉnh Quảng Bình, được coi là hang động lớn nhất thế giới. Hang Sơn Đoòng có kích thước đủ để chứa cả một tòa nhà chọc trời 40 tầng và bên trong có cả một hệ sinh thái riêng biệt với rừng, sông và thời tiết riêng. Hang được khám phá lần đầu tiên vào năm 1991 bởi một người dân địa phương và chính thức được các nhà khoa học khám phá vào năm 2009. Đây là một địa điểm du lịch mạo hiểm nổi tiếng, thu hút những người yêu thích khám phá thiên nhiên từ khắp nơi trên thế giới.

**Bạn nhận thấy quy luật gì qua bốn phản hồi?** (2–3 câu)
> Temp càng cao phản hồi càng sáng tạo và đa dạng, nhưng cũng có thể kém chính xác hơn. Temp thấp cho phản hồi ổn định và tập trung hơn, nhưng có thể thiếu sự mới mẻ.

**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**
> Chatbot hỗ trợ KH nên đặt temp ở mức thấp. Nếu temp cao quá, phản hồi có thể trở nên không nhất quán hoặc sai lệch, gây nhầm lẫn cho khách hàng. Temp thấp giúp đảm bảo phản hồi chính xác và đáng tin cậy, điều quan trọng trong dịch vụ khách hàng.

---

### Bài tập 2.2 — Đánh Đổi Chi Phí
Xem xét kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người thực hiện 3 lần gọi API, mỗi lần trung bình ~350 token.

**Ước tính xem GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này:**
> 10.000 users * 3 calls/user * 350 tokens/call = 10.500.000 tokens
Cost GPT-4o: 10.500.000 tokens / 1.000 * $0.010 = $105
Cost GPT-4o-mini: 10.500.000 tokens / 1.000 * $0.0006 = $6.3
GPT-4o đắt hơn GPT-4o-mini khoảng 16.67 lần cho workload này

**Mô tả một trường hợp mà chi phí cao hơn của GPT-4o là xứng đáng, và một trường hợp GPT-4o-mini là lựa chọn tốt hơn:**
> GPT-4o xứng đáng khi cần phản hồi chất lượng cao, phức tạp hoặc sáng tạo, như trong ứng dụng viết nội dung hoặc phân tích dữ liệu. GPT-4o-mini phù hợp cho các tác vụ đơn giản, lặp đi lặp lại hoặc khi ngân sách hạn chế, như chatbot hỗ trợ khách hàng cơ bản hoặc phân loại văn bản.

---

### Bài tập 2.3 — Trải Nghiệm Người Dùng với Streaming
**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì non-streaming lại phù hợp hơn?** (1 đoạn văn)
> Streaming quan trọng khi người dùng cần phản hồi nhanh và có thể chấp nhận phản hồi dần dần, như trong chatbot hoặc ứng dụng tương tác thời gian thực. Non-streaming phù hợp hơn khi phản hồi cần được hoàn chỉnh và chính xác trước khi hiển thị, như trong báo cáo phân tích hoặc nội dung dài, nơi việc hiển thị một phần có thể gây hiểu lầm hoặc mất tập trung.


## Danh Sách Kiểm Tra Nộp Bài
- [ ] Tất cả tests pass: `pytest tests/ -v`
- [ ] `call_openai` đã triển khai và kiểm thử
- [ ] `call_openai_mini` đã triển khai và kiểm thử
- [ ] `compare_models` đã triển khai và kiểm thử
- [ ] `streaming_chatbot` đã triển khai và kiểm thử
- [ ] `retry_with_backoff` đã triển khai và kiểm thử
- [ ] `batch_compare` đã triển khai và kiểm thử
- [ ] `format_comparison_table` đã triển khai và kiểm thử
- [ ] `exercises.md` đã điền đầy đủ
- [ ] Sao chép bài làm vào folder `solution` và đặt tên theo quy định 
