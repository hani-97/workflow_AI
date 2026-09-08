name : requiment_analist_skill
description: Kỹ năng phân tích tài liệu/giao diện dự án để bóc tách luồng nghiệp vụ, phát hiện ra những điểm mờ và sinh r tài liệu Yêu cầu chuẩn mực.

# Kỹ năng phân tích Yêu cầu ( Requiments Analyzer)

Kỹ năng này cung cấp các hướng dẫn chi tiết để AI có thể chuyển đổi giao diên UI hoặc cấu trúc DOM/HTML của một trang web thành các tài liệu yêu cầu nghiệp vụ rõ ràng , chi tiết phục vụ trực tiếp cho QA, Tester, Dev, Business Analyst. Đặc biệt là sinh Test Case cho Automation Test, Manual Test.

## 1. Mục tiêu chính :
- Hiểu rõ ràng về UI/UI hoặc cấu trúc DOM/HTML của một trang web.
- xây dựng tài liệu yêu cầu bám sát thực tế hệ thống đang chạy.
- Đảm bảo tính nhất quán, tính bao quát cho toàn bộ yêu cầu nghiệp vụ.
- Phát hiện sớm các điểm mơ hồ, không rõ ràng trong UI hoặc logic nghiệp vụ để yêu cầu làm rõ.
- Định dạng xuất ra một cách chuyên nghiệp (Sử dụng cấu trúc Artifact).

## 2. Quy trình trích xuất thông tin
Khi được yêu cầu tạo Requiment từ giao diện UI, hãy thực hiện tuần tự các bước sau :
1. Phân tích UI/DOM : Xác định các thành phần UI chính, nút, trường nhập, menu, điều hướng và cấu trúc tổng thể.
2. Xác định mục đích và nghiệp vụ : Tìm hiểu rõ ràng về UI/UI hoặc cấu trúc DOM/HTML của một trang web.
3. Bóc tách các luồng nghiệp vụ : Dựa vào UI để phân tích và bóc tách các luồng nghiệp vụ chính của hệ thống.
4. Phát hiện điểm mờ và câu hỏi cần làm rõ 
5. Xác định các quy tắc xử lý 
6. Xử lý dữ liệu Input và Output.
7. Trích xuất luồng công việc ( Workflows) :
- Sự phụ thuộc giữa các thành phần (VD: Nút Submit chỉ enable khi đã tích chọn Checkbox "Tôi đồng ý") .

## 3. Quy trình xuất dữ liệu dạng Artifact
1. Tạo ra một file Markdown chuẩn với cấu trúc Artifact.
2. Mỗi Artifact nên có các thông tin sau :

## 2.1. Tổng quan hệ thống : 
Mô tả tóm tắt tính năng và mục đích của trang web/module.

## 2.2. Business Process : 
- Tạo ra sơ đồ quy trình làm việc từ UI và các luồng nghiệp vụ được xác định.
- Sử dụng Mermaid (hoặc định dạng sơ đồ tương đương) để biểu diễn quy trình một cách trực quan.
- Xác định các bước trong quy trình, các điểm rẽ nhánh, và các điều kiện đi kèm.
- Lưu ý: Nếu không có UI thì dựa vào kinh nghiệm của AI     

## 2.3. Functional Requirements : 
- Mỗi một funtional requiment thường có : 
    - ID : FR-001
    - Requiment Name
    - Description
    - Actor
    - Preconditions
    - Trigger
    - Main flow
    - Alternative Flow
    - Exception Flow
    - Business Rule
    - Input
    - Output
    - Acceptance Criteria

## 2.4. Busisness Rule : 
- Ghi rõ ràng các business rule được phát hiện.
- Có thể dùng định dạng RuleId, BR_01, BR_02,... 
- Mỗi Business Rule có cấu trúc : 
    - RuleId
    - Business Rule Name
    - Description
    - Condition
    - Action

## 2.5. Validation Rule : 
- Đây là các rules Validation Input và Output Data  , các rule này sẽ được dùng để sinh ra testcase.
- RuleId
- Validation Name
- Description
- Condition
- Action    

## 2.6. Acceptance Criteria :
- Đây là các tiêu chí dùng để đánh giá một Test Case đã được chấp nhận hay chưa. Hoặc là các tiêu chí để xác định xem một yêu cầu đã được thực hiện thành công hay chưa. 
- Mỗi Acceptance Criteria thường có : 
    - ID : AC-001
    - Acceptance Criteria Name
    - Description
    - Condition
    - Action

## 4. bắt buộc : 
- Luôn viết bằng Tiếng Việt
- Không tự suy diễn logic hoặc nghiệp vụ của dự án . Nếu không chắc chắn hãy liệt kê tất cả câu hỏi vào mục "câu hỏi/ Làm rõ với BA/Stakeholder" để người dùng có thể trả lời và làm rõ requirement trước khi đưa vào sử dụng.

                                                                                