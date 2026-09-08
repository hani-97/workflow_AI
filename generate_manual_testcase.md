description Workflow này dùng để sinh ra manual testcase từ requirement 
name : generate_manual_testcase_workflow

## Các bước thực hiện 

## Step 1 : Phân tích yêu cầu
1. Hiểu requiment đang yêu cầu hệ thống làm gì dựa vào skill 'requiment_analist_skill' 
2. Xác định ai thực hiện và điều kiện trước khi thực hiện
3. Bóc tách toàn bộ business flow chính và các trường hợp ngoại lệ 
4. Xác định Happy path, Alternative & Exception Flow
5. Xác định input/output
6. Xác định các quy tắc hợp lệ
7. Identify boundary conditions
8. Identify permission/authorization
9. Identify state transitions
10. Identify dependencies/integrations. 
11. Xác định Analyze Input & Validati
12. Phát hiện Ambiguity & Missing Requirements
13. Xác định các yêu cầu mâu thuẫn

## Step 2 : Q&A / Clarification
1. Nếu requirement không có ambiguity -> Continue
2. Nếu có ambiguity -> Xác định điểm mơ hồ :
→ Giải thích tác động
→ Đặt câu hỏi (Q1/Q2/Q3...)
→ DỪNG LẠI
→ Chờ người dùng
→ Cập nhật phân tích
→ Tiếp tục
## Step 3 : System Decomposition
1. Module
   ↓
Sub-module
   ↓
Function
   ↓
Business Rule
   ↓
Testable Condition

## Step 4 : Test Condition & Scenario Design
1. Dựa vào các skill 'Equivalence Partitioning , Boundary Value Analysis, Decision Table , State Transition, Pairwise , Error Guessing' để nhóm thành Scenario.

## Step 5: Đảm bảo độ bao phủ (Traceability)
1. Requiment -> module -> Business Rule -> Test Condition ->Test Scenario -> Test Case 

## Step 6: Risk-Based Prioritization
1. Xác định mức độ ưu tiên: Business Impact + Likelihood + Technical Complexity + Dependency + Historical Risk = Risk Level
2. Sau đó xác định Test Case có Risk Level cao hay thấp và ưu tiên thực hiện các Test Case có Risk Level cao trước

## Step 7 : TestCae Generation
1. Mỗi testcase nên có tối thiểu : Test Case ID, Requirement ID, Module, Function, Business Rule, Test Condition, Test Scenario, Test Case, Pre-condition, Test Step, Input Data, Expected Result, Actual Result, Status, Risk Level
2. Áp dụng các kỹ năng Test Data Generation, Equivalence Partitioning, Boundary Value Analysis, Decision Table, State Transition, Pairwise, Error Guessing để sinh ra testcase
3. Test Data phải cụ thể 
4. Nếu quá nhiều -> sinh từng module , hỏi user để tiếp tục

## Step 8: Chuẩn hóa Format & Metadata (Template Mapping)
1. Đóng gói toàn bộ test cases vào bảng Markdown chuẩn đầy đủ metadata cho Automation:
   `| TC ID | Module | Risk Level | Test Title | Pre-Condition | Test Steps | Expected Result | Priority | Test Data | Automatable | Auto Type | Tags |`
2. **Chạy Self-Quality Gate (5 tiêu chí):** Unique TC ID, 1-to-1 Step-Expected matching, Concrete Test Data, Field Validation Coverage, và Automation Metadata Ready.
3. Xuất dưới dạng Artifact (`test_cases_<module>.md`).

## Output

- Bảng testcase Mardown hoàn chỉnh,  sẵn sàng copy sang Excel/Jira/TestRail hoặc sync trực tiếp vào Google Sheets
- Traceability Matrix
- Danh sách Ambiguities đã giải quyết
- Báo cáo Self-Quality Gate Verification
