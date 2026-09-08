name: generate_testcases_skill
description: Kỹ năng sinh Manual Test Case chuyên nghiệp từ Senior QA (10+ năm kinh nghiệm). Đảm bảo bao phủ 100% tài liệu Yêu cầu (từ requiment_analist_skill), phân loại chế độ (QUICK, RISK-BASED), áp dụng các kỹ thuật thiết kế testcase chuẩn mực (EP, BVA, Decision Table, State Transition, Pairwise, Error Guessing) và tích hợp Self-Quality Gate trước khi xuất dữ liệu.

# Kỹ năng Sinh Manual Test Case (Generate Testcases Skill)

Skill này dùng để phân tích Requiment, User Story, Acceptance Criteria, Business Rule, UI/Figma hoặc API spec và tạo Manual Testcase một cách chuyên nghiệp.

## Nguyên tắc :

  - Hiểu requiment trước khi viết testcase
  - Ưu tiên business flow và risk quan trọng
  - Không tạo testcase trùng hoặc không có giá trị
  - Không tự suy đoán business rule khi tài liệu chưa xác định
  - Chỉ áp dụng kĩ thuật test phù hợp
  - Sau khi tạo testcase phải tự kiểm tra coverage và chất lượng.

## Chọn Mode : 

Skill cung cấp 2 chế độ để phù hợp với mọi quy nô yêu cầu :

| Mode | Khi nào dùng | Cách xử lý |
|------|-------------|-----------|
| **QUICK** | Module đơn giản, cần TC nhanh, requirements rõ ràng | Phân tích -> sinh TC -> Tự động check coverage, chất lượng|
| **FULL RBT** | Module phức tạp, cần phân tích rủi ro, hệ thống lớn | Phân tích -> làm rõ -> phân rã -> RBT -> sinh TC -> Tự động check coverage, chất lượng |

## Quy tắc chọn mode : 

- Ưu tiên đánh giá theo thứ tự : 
    - Scope : Scope càng lớn thì chọn FULL RBT
    - Business complexity : Business rule càng phức tạp thì chọn FULL RBT
    - Risk : Risk càng cao thì chọn FULL RBT
    - Dependency/Integration : càng nhiều dependency/integration thì chọn FULL RBT
    - Yêu cầu của user : Nếu user yêu cầu rõ mode nào thì ưu tiên theo yêu cầu của user
  
  # Mode 1 : QUICK 

  ## Mục đích 
  Sinh testcase nhanh với coverage đầy đủ trong phạm vi requirement và risk phù hợp, đồng thời tránh over-testing.
  
  ## Khi nào dùng :
  - Module đơn giản
  - Business rule đơn giản
  - Risk thấp
  - Không có dependency/integration
  - User yêu cầu mode QUICK
  
  ## Quy trình 
  1. Đọc và hie6yu3 requiment :
    - Xác định scope
    - Xác định input/output
    - Xác định expected behavior
  2. Xác định Business Rules :
    - Required/Optional.
    - Validation.
    - Min/Max.
    - Condition.
    - Status.
    - Permission.
    - Constraint.
  3. Xác định Test Scenarios : 
    - Happy Path
    - Negative path
    - Alternative Flow
    - Boundary/Edge Cases
    - Business Rules
  4. Áp dụng kỹ thuật thiết kế test case phù hợp :
  Chỉ chọn kỹ thuật phù hợp với từng loại test case , không áp dụng tất cả : 
  - Equivalence Partitioning
  - Boundary Value Analysis
  - Decision Table
  - State Transition Testing
  - Pairwise Testing
  - Error Guessing
  4. Identify Requirement Gap
   - Missing rule
   - Ambiguous behavior
   - Missing expected result
   - Missing validation
  **Lưu ý** : Nếu Gap không ảnh hưởng đến việc generate TC -> tiếp tục , Nếu Gap ảnh hưởng đến việc generate TC -> cần hỏi lại user
  
  5. Generate Test Case với định dạng chuẩn:
  | TC ID | Requirement ID | Risk Level | Test Title | Pre-conditions | Test Steps | Expected Result | Test Data | Automatable | Auto Type | Tags |
  | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
  | TC_AUTH_001 | FR-AUTH-01 | High | Đăng nhập thành công với Email & Pass đúng | Đã có tài khoản hợp lệ | 1. Truy cập /login<br>2. Nhập Email & Password<br>3. Nhấn "Đăng nhập" | 1. Hiển thị form đăng nhập<br>2. Dữ liệu hiển thị đúng<br>3. Chuyển hướng Dashboard, toast "Thành công" | Email: `user1@test.com`<br>Pass: `P@ssword123` | Yes | UI | `Smoke`, `Regression` |
  6. Auto-Check Coverage & Quality:
  - Requiment coverage
  - Business rule coverage
  - Positive/Negative/Boundary
  - Duplicate
  - Step/Expected rõ ràng
  - Test Data cụ thể
  - Không over-testing


# Mode 2 : Full Risk-Based (FULL RBT)

# Mục đích 
Sinh testcase từ tài liệu requiment một cách chuyên nghiệp 

# Khi nào dùng

  - Module phức tạp
  - Business rule phức tạp
  - Risk cao
  - Có dependency/integration
  - User yêu cầu mode FULL RBT

# Quy trình : 

## Step 1 : Context & Scope 
Mục đích : để hiểu rõ bối cảnh của hệ thống :
    - Project/module
    - Business objective
    - In scope
    - Out of scope
    - User/Role

## Step 2 : Analyze & Clarify Requirements - Phân tích & làm rõ requiment
    - Funtional requiment
    - Acceptance Criter
    - Business Rules
    - Happy Path
    - Negative Path
    - Alternative Flow
    - Boundary/Edge Cases
    - UI/UX Rules
    - Validation Rules
    - Error message
    - Data Constraint
**Lưu ý** : Nếu requiment rõ -> không hỏi user , Nếu requiment thiếu nhưng có thể test phần đã rõ -> Ghi requiment Gap av2 tiếp tục , Nếu requiment thiếu thông tin làm thay đổi Expected Result -> Dừng tại điểm bị ảnh hưởng và hỏi user, không tự suy diễn.

## Step 3 : Decomposition - Phân rã & Phân loại Test Case

 **Mục đích:** Chia tính năng phức tạp thành các Module / Sub-module nhỏ, dễ quản lý.

**Agent phải:**
1. Ưu tiên phân rã theo : 
    - Business capability
    - Business Flow
    - Feature/Sub-feature
    - UI component nếu cần.
2. Mô tả ngắn gọn chức năng từng Module

**Output:** Danh sách Modules/Sub-modules

## Step 4 : Dependency & Business Flow - Xác định luồng nghiệp vụ & Dependency

  **Mục đích:** Làm rõ luồng nghiệp vụ cốt lõi và mối quan hệ giữa các module để đảm bảo không bỏ sót kịch bản quan trọng.

  **Agent phải:**
    1. **Vẽ Business Flow/Sequence Diagram (nếu cần):**
        - Đối với luồng phức tạp: Tạo sơ đồ đơn giản mô tả cách các module tương tác.
        - Chỉ tập trung vào luồng nghiệp vụ cốt lõi (không vẽ chi tiết UI).
    2. **Xác định Dependencies:**
        - Module A ảnh hưởng đến Module B như thế nào?
        - Module C phải được thực hiện trước Module D?
        - Dữ liệu từ module nào ảnh hưởng đến module nào?

**Output** : Business low + Dependencies Map
      
## Step 5 : Risk Analysis & Prioritization - Phân tích rủi ro & Ưu tiên hóa

  **Mục đích**: Đánh giá mức độ ảnh hưởng của từng kịch bản đến nghiệp vụ và hệ thống
  **Lưu ý** : Risk không chỉ dùng để gán Priority cho Test Case. Risk phải quyết định Test Coverage, Test Depth và Test Scope.

  **Agent phải:**
    1. Xác định các rủi ro tiềm ẩn của từng module
    2. Phân loại rủi ro theo mức độ ảnh hưởng:
        - High: Ảnh hưởng đến nghiệp vụ cốt lõi, dữ liệu quan trọng
        - Medium: Ảnh hưởng đến nghiệp vụ phụ, dữ liệu không quan trọng
        - Low: Ảnh hưởng nhỏ, không ảnh hưởng đến nghiệp vụ
    3. Ưu tiên hóa test case dựa trên mức độ rủi ro 
    4. Xác định mức độ Test Coverage và Test Depth dựa trên Risk:
        - Risk High → Test Coverage rộng và Test Depth sâu.
        - Risk Medium → Test Coverage và Test Depth ở mức phù hợp.
        - Risk Low → Test Coverage và Test Depth ở mức cơ bản

    5. Ưu tiên Test Case dựa trên mức độ Risk:
        - High → ưu tiên thực hiện trước.
        - Medium → thực hiện sau High.
        - Low → thực hiện sau cùng hoặc có thể giảm phạm vi khi thời gian hạn chế.

## Step 6 : Test Strategy & Traceability - Xác định chiến lược & truy xuất nguồn gốc 

  **Mục đích:** Đảm bảo mọi nghiệp vụ đều được bao phủ bởi test case và giảm thiểu rủi ro bỏ sót.

  **Agent phải:**
    1. **Xác định phạm vi test (Test Scope):**
        - Module nào được test?
        - Module nào không được test?
    3. **Tạo Traceability Matrix (Ma trận truy xuất nguồn gốc):**
        - Liên kết từng Test Case với Requirement ID, Business Rule ID, Risk ID
        - Đảm bảo không có Requirement nào bị bỏ sót.

  ## Step 7 : Test Scenario Design - Thiết kế kịch bản kiểm thử

  **Mục đích:** Tạo các kịch bản kiểm thử chi tiết để đảm bảo mọi nghiệp vụ đều được bao phủ bởi test case.
    
  **Agent phải:**
    1. **Tạo Test Scenarios (Kịch bản kiểm thử):**
        - Liệt kê tất cả các kịch bản kiểm thử
        - Mô tả ngắn gọn kịch bản
        - Đánh số thứ tự cho từng Test Scenario 
    2. **Xác định Test Data (Dữ liệu kiểm thử):**
        - Xác định Test Data cần thiết cho từng Test Scenario 
        - Tạo Test Data với định dạng chuẩn
    3. **Xác định Expected Result (Kết quả mong đợi):**
        - Xác định Expected Result cho từng Test Scenario 
        - Đảm bảo Expected Result rõ ràng và dễ kiểm tra
        
## Step 8 : Test Case Generation - Sinh test cases  

  - Sinh testcase chi tiết theo định dạng Markdown

## Step 9 : Integration & E2E - Tích hợp & End-to-End 

  **Mục đích:** Đảm bảo các Module có thể hoạt động chính xác khi kết hợp với nhau và các luồng nghiệp vụ quan trọng hoạt động xuyên suốt từ đầu đến cuối.

**Agent phải:**

1.  **Xác định Integration Points:**
Xác định các Module/Component có tương tác với nhau.
Xác định dữ liệu được truyền giữa các Module.
Xác định API/Service/Database/External System liên quan.
Xác định các điểm có khả năng xảy ra lỗi khi tích hợp.

* Ví dụ :  User -> Order -> Payment -> Inventory

2. **Tạo Integration Test Cases:**
Kiểm tra dữ liệu từ Module A được truyền đúng sang Module B.
Kiểm tra Module B xử lý đúng dữ liệu từ Module A.
Kiểm tra trạng thái được đồng bộ chính xác giữa các Module.
Kiểm tra lỗi từ Module A được xử lý đúng tại Module B.
Kiểm tra timeout/retry nếu có.
Kiểm tra duplicate request/transaction nếu có.
Kiểm tra data consistency giữa các Module.
3. **Xác định Critical E2E Flows:**
Xác định các luồng nghiệp vụ quan trọng nhất đối với User/Business.
Ưu tiên các flow có Risk High/Critical.
Không tạo E2E testcase cho mọi UI flow nếu không cần thiết.
4. **Tạo E2E Test Scenarios:**
Kiểm tra Happy Path của Critical Flow.
Kiểm tra Negative/Exception Flow quan trọng.
Kiểm tra trạng thái dữ liệu sau khi hoàn thành toàn bộ flow.
Đảm bảo kết quả cuối cùng phù hợp với Business Rule.
5. **Trace Integration & E2E:**
Liên kết Integration/E2E Scenario với:
Requirement ID
Business Rule ID
Risk ID
Test Case ID
Đảm bảo các Risk High/Critical có Integration/E2E coverage khi cần.

**Output:** Danh sách Integration Test Scenarios + Critical E2E Flows + Integration/E2E Test Cases + Mapping với Requirement/Risk.

## Step 10 : Regression Impact Analysis - Phân tích ảnh hưởng Regression
**Mục đích:** Xác định các Module, Business Flow và Test Case có khả năng bị ảnh hưởng khi có thay đổi, từ đó xác định phạm vi Regression Testing phù hợp và tránh bỏ sót lỗi phát sinh.

**Agent phải:**

1. **Xác định Changed Area:**
Xác định Module/Feature được thay đổi.
Xác định Requirement/Business Rule được thay đổi.
Xác định API/Database/UI/Logic liên quan nếu có.
2. **Xác định Affected Modules:**
Kiểm tra Dependency giữa Changed Module và các Module khác.
Xác định Module trực tiếp bị ảnh hưởng.
Xác định Module gián tiếp có khả năng bị ảnh hưởng.
3. **Xác định Affected Test Cases:**
Tìm các Test Case liên quan trực tiếp đến Changed Module.
Tìm Test Case liên quan đến Business Rule bị thay đổi.
Tìm Test Case thuộc các Integration Flow bị ảnh hưởng.
Tìm Test Case thuộc Critical E2E Flow bị ảnh hưởng.
Ưu tiên Regression Test Case có Risk High/Critical.
4. **Phân loại Regression Scope:**
Direct Regression: Test trực tiếp chức năng bị thay đổi.
Related Regression: Test các chức năng có dependency với chức năng bị thay đổi.
Integration Regression: Test các điểm tích hợp bị ảnh hưởng.
E2E Regression: Test Critical Business Flow bị ảnh hưởng.
Full Regression: Chỉ áp dụng khi thay đổi có phạm vi ảnh hưởng lớn hoặc theo yêu cầu của Project.
5. **Ưu tiên Regression Test Case:**
Risk High/Critical → ưu tiên chạy trước.
Core Business Flow → ưu tiên cao.
Module có Dependency → ưu tiên cao.
Test Case liên quan trực tiếp đến Change → ưu tiên cao.
Low Risk/Low Impact → có thể chạy sau nếu thời gian hạn chế.

**Output:** Changed Areas + Affected Modules + Affected Business Flows + Regression Scope + Regression Test Cases + Regression Priority.

## Step 11 : Coverage & Quality Gate - Kiểm tra Coverage & chất lượng Test Case

**Mục đích:** Đảm bảo bộ Test Case đã bao phủ đầy đủ Requirement, Business Rule và Risk quan trọng, đồng thời loại bỏ Test Case trùng lặp, không cần thiết hoặc không thể thực thi.

**Agent phải:**

1. **Kiểm tra Requirement Coverage:**
Kiểm tra tất cả Functional Requirement đã có Test Case chưa.
Kiểm tra Acceptance Criteria đã được cover chưa.
Xác định Requirement chưa được kiểm thử.
Xác định Requirement chỉ được cover một phần.
2. **Kiểm tra Business Rule Coverage:**
Mỗi Business Rule phải có Test Scenario/Test Case phù hợp.
Đảm bảo Positive/Negative behavior của Business Rule được kiểm tra khi applicable.
Không bỏ sót Business Rule quan trọng.
3. **Kiểm tra Risk Coverage:**
Đảm bảo Risk High/Critical đã được Test Case cover.
Kiểm tra Test Depth có phù hợp với mức Risk hay không.
Risk càng cao → mức độ kiểm thử càng sâu.
Xác định các Risk chưa có Test Coverage.
4. **Kiểm tra Test Case Quality:**

Kiểm tra:

Test Case ID không trùng.
Test Scenario rõ ràng.
Pre-condition đầy đủ.
Test Data cụ thể.
Test Steps có thể thực thi.
Expected Result rõ ràng và có thể kiểm chứng.
Priority phù hợp với Risk.
Test Type phù hợp.
Không có Test Case duplicate.
Không có Test Case chỉ khác wording nhưng cùng behavior.
Không có Test Case nằm ngoài Scope.
5. **Kiểm tra Test Design Coverage:**

Xác định các kỹ thuật kiểm thử đã được áp dụng phù hợp:

Equivalence Partitioning.
Boundary Value Analysis.
Decision Table.
State Transition.
Error Guessing.
Positive/Negative Testing.

Không bắt buộc áp dụng tất cả kỹ thuật.

Chỉ sử dụng khi phù hợp với Requirement/Business Rule.

6. **Kiểm tra Integration & E2E Coverage:**
Critical Integration Point đã được cover chưa?
Critical Business Flow đã có E2E Test Case chưa?
Risk High/Critical có cần Integration/E2E nhưng chưa được cover không?
Kiểm tra Data Consistency giữa các Module.
7. **Kiểm tra Traceability:**
Xác định:

Requirement không có Test Case.
Risk không có Test Case.
Test Case không trace được về Requirement.
Test Case không thuộc Scope.
8. **Xác định Gap & Residual Risk:**

Nếu phát hiện thiếu coverage:

Xác định nguyên nhân.
Bổ sung Test Case nếu cần.
Ghi rõ Requirement Gap.
Ghi rõ Risk chưa được cover.
Ghi rõ Residual Risk nếu vẫn còn rủi ro sau khi thiết kế Test Case.

**Output** : Requiment coverage + Business Rule coverage + Risk coverage + Integration & E2E coverage + Regression Coverage + Duplicate Check + Testcase Quality Check + Requiment Gap + Residual Risk.

## 5. Định Dạng Output Standard (Template Markdown)

```markdown
# Bộ Test Cases: [Tên Module]
**Mode**: [QUICK / RISK-BASED] | **Tổng số TC**: [Số lượng] | **Coverage**: 100%

| TC ID | Requirement ID | Risk Level | Test Title | Pre-conditions | Test Steps | Expected Result | Test Data | Automatable | Auto Type | Tags |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_AUTH_001 | FR-AUTH-01 | High | Đăng nhập thành công với Email & Pass đúng | Đã có tài khoản hợp lệ | 1. Truy cập /login<br>2. Nhập Email & Password<br>3. Nhấn "Đăng nhập" | 1. Hiển thị form đăng nhập<br>2. Dữ liệu hiển thị đúng<br>3. Chuyển hướng Dashboard, toast "Thành công" | Email: `user1@test.com`<br>Pass: `P@ssword123` | Yes | UI | `Smoke`, `Regression` |
```

---

## 6. Quy Tắc Bắt Buộc

- **Luôn viết bằng Tiếng Việt chuyên ngành QA/QC.**
- **Không tự suy diễn nghiệp vụ**: Khi thiếu thông tin, liệt kê câu hỏi Q&A hỏi User trước khi tiếp tục.
