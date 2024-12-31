1. Cập nhật hồ sơ bệnh nhân
  - Các lớp phân tích của ca sử dụng Cập nhật hồ sơ bệnh nhận:
    - Boundary:
      - UpdateForm: Giao diện mà nhân viên lâm sàng sử dụng để tra cứu và cập nhật hồ sơ của bệnh nhân nếu cần. Giao diện sẽ hiển thị thông tin của bệnh nhân, lịch sử các cuộc tư vấn và ghi lại các phương pháp điều trị và thuốc đã kê đơn.
      - PatientConnect: Giao diện tương tác với hệ thống quản lý hồ sơ bệnh nhân khi nhân viên lâm sàng cần cập nhật hồ sơ bệnh nhân.
    - Control:
      - PatientController: Điều phối quá trình cập nhật hồ sơ bệnh nhân. Xử lý các yêu cầu để cập nhật hồ sơ của bệnh nhân từ UpdateForm. Dữ liệu sau khi được xử lý sẽ được lưu vào PatientDatabase.
    - Entity:
      - PatientProfile: Lớp này đại diện cho hồ sơ bệnh nhân gồm các thông tin như mã định danh bệnh nhân duy nhất, thông tin cá nhân, đánh giá rủi ro về tự gây hại/bạo lực, chẩn đoán các tình trạng, phương pháp điều trị, các loại thuốc đã kê đơn, các cuộc tư vấn, giới thiệu.
      - PatientDatabase: Lớp này đại diện cho hệ thống quản lý hồ sơ bệnh nhân, là cơ sơ dữ liệu chứa các hồ sơ bệnh nhân.
  - Biểu đồ sequence:
    ![Diagram](https://www.planttext.com/plantuml/png/Z5CnRjim5DrvYWVjle078x3SfbuA0Ow7ZBIiXe8bAfKf0nwB345HT31w0Rj1q2QeqGwTnC43ZTo39-WL2bAgJ2Tnt4tKV-y_llyV_yZDoLJGN1HfGcWeiXpUMwQ-SinYTSyzq2dy0Ubc1H_JV0vlU3cc8dgTvQcj3Vla5HUncCCBg8WZBe8yUnSdaQq60V4pBl8iQShrEOdogdTpT3HsK1w5uX_EV3yMwr51HtHQgVMwXFW3j3eOzjlmcPQVEKAcvLq8lhtY5n0vHQZbNK66VRHQ7VY3DixLVO5GbzyASARBzIK4KxyDEkRsFuTGFrAdzQcMwnZp7S_KCObrkKbjvuxZwmXy1wnfnkO13gdB1jdhjd6swmEcvHTC7rOOQNdD6RXP8kbr6snUp37JvMtrqzKwotLvWuakDmBl2_DjBxXTFFpIyYRSgJxozH-ynbghWo1eurIj-0kC8B18C-DZpPq5lecrlE8GJCjFBp08JGGyEpF1T7axRsRc4M0_E1yvmrJBDSLCBTqrX3OWDYUYuHEWsdfZSQQM6ROBBHSnXDNd5mGm_evaOqzWehwdpxGva9dpvxjK13Stlginrl8dabZBwy8rr6kIuwBhmjFqpBJyi3VxGpSucg6dH3T4DXhLynofbPcnsgUOnxla3A71r8kfS-Bo3bCYFYOd4HyNQV8N003__mC0)
  - Biểu đồ lớp:\
    ![Diagram](https://www.planttext.com/plantuml/png/h96n3S8m44Nxcy8b55a1HKg4H9S21ZYS0o8vDh8lLPJ9A1Y95IB761oveA4y_QVtzUtNurawHij3hm2aGkV4wTuYqzxONemWX1YMkq7kI7DZpQLJjDdwn15QUSkIAPhMYHYpf3AQhL6Ax9-gQcGye_DTNrsW3pg6mNWb_gchZDOaETXaE8ucyKm0oNCLnIvV1ldMDUUb2RGK9aHiYyXdOiAy5m2Kf5l_bJC0003__mC0)
    
    UpdateForm Class
+updatePatientProfile():
Phương thức này được gọi khi người dùng muốn cập nhật hồ sơ bệnh nhân. Nó có thể chứa logic để thu thập thông tin mới từ giao diện người dùng và gửi yêu cầu cập nhật tới controller (ví dụ: PatientController).
+searchPatientProfile():
Phương thức này được gọi khi người dùng muốn tìm kiếm hồ sơ bệnh nhân. Nó có thể thực hiện tìm kiếm từ giao diện người dùng và gửi yêu cầu tìm kiếm tới controller để tìm kiếm trong cơ sở dữ liệu.
2. PatientProfile Class
Lớp này không có phương thức nào trong sơ đồ của bạn. Tuy nhiên, về lý thuyết, lớp này sẽ đại diện cho đối tượng "hồ sơ bệnh nhân", lưu trữ thông tin chi tiết về bệnh nhân như tên, tuổi, lịch sử bệnh lý, v.v. Các phương thức trong lớp này sẽ giúp truy cập và thay đổi thông tin của bệnh nhân.
3. PatientController Class
+updatePatientProfile():

Phương thức này xử lý logic liên quan đến việc cập nhật hồ sơ bệnh nhân. Khi người dùng gửi yêu cầu cập nhật từ UpdateForm, PatientController sẽ nhận yêu cầu, kiểm tra dữ liệu và gọi các phương thức của các lớp khác (ví dụ: PatientConnect, PatientDatabase) để thực hiện cập nhật.
+searchPatientProfile():

Phương thức này xử lý logic tìm kiếm hồ sơ bệnh nhân. Khi người dùng gửi yêu cầu tìm kiếm, PatientController sẽ nhận yêu cầu, thực hiện các bước kiểm tra (nếu có) và gọi các lớp khác (ví dụ: PatientConnect, PatientDatabase) để tìm kiếm hồ sơ bệnh nhân.
4. PatientDatabase Class
+updateProfileInDatabase():

Phương thức này sẽ thực hiện công việc cập nhật thông tin hồ sơ bệnh nhân trong cơ sở dữ liệu. Sau khi nhận yêu cầu từ PatientController, nó sẽ thực hiện cập nhật trong cơ sở dữ liệu (chẳng hạn như sửa thông tin của một bệnh nhân).
+getPatientProfile():

Phương thức này được gọi khi muốn lấy thông tin hồ sơ bệnh nhân từ cơ sở dữ liệu. PatientController sẽ gọi phương thức này để truy xuất dữ liệu về bệnh nhân từ cơ sở dữ liệu.
5. PatientConnect Class
+connectToDatabase():
Phương thức này có nhiệm vụ thiết lập kết nối giữa hệ thống và cơ sở dữ liệu. Lớp này đóng vai trò như một lớp trung gian, giúp các lớp khác (như PatientDatabase) kết nối với cơ sở dữ liệu và thực hiện các thao tác như lưu, cập nhật, truy vấn dữ liệu.
    
2. Quản lý thuốc và điều trị
 - Các lớp phân tích của ca sử dụng Quản lý thuốc và điều trị:
    - Boundary:
      - CreateForm: Giao diện mà nhân viên lâm sàng sử dụng để thêm các loại thuốc vào một đơn thuốc.
      - PatientConnect: Giao diện tương tác với hệ thống quản lý hồ sơ bệnh nhân khi nhân viên lâm sàng cần cập nhật hồ sơ bệnh nhân.
      - MedicineConnect: Giao diện tương tác với hệ thống quản lý hồ sơ bệnh nhân khi nhân viên lâm sàng cần tạo đơn thuốc cho bệnh nhân.
    - Control:
      - PrescriptionController: Điều phối quá trình tạo đơn thuốc cho bệnh nhân. Xử lý các yêu cầu tìm kiếm thuốc và thêm các loại thuốc vào một đơn từ CreateForm. Dữ liệu sau khi được xử lý sẽ được lưu vào PatientDatabase.
    - Entity:
      - PatientDatabase: Lớp này đại diện cho hệ thống quản lý hồ sơ bệnh nhân, là cơ sơ dữ liệu chứa các hồ sơ bệnh nhân.
      - MedicineDatabase: Lớp này đại diện cho cơ sơ dữ liệu chứa các loại thuốc đã được phê duyệt bởi cơ quan y tế.
      - NoticeDatabase: Lớp này đại diện cho cơ sở dữ liệu chứa các thông báo và danh tính của nhân viên lâm sàng khi bỏ qua thông báo cảnh báo.
      - Medication: Lớp này đại diện cho các loại thuốc mà bệnh nhân đã và đang sử dụng.
  - Biểu đồ sequence:
    ![Diagram](https://www.planttext.com/plantuml/png/p5QxRjim5Dtv5HVQ-mCUYi2ocmQjZQ1EXewCH5Y4BIgXA0CQYmmTYgBmdAMk4HH96o139t78eC3_mI_eBnIKP4cKOaVjL0-sR9vp7-SUNlYtV3W81UOYykS8EoBWO8szz1k31KrlcGKu17k2-a74NCnZi6nEi22l0kvdPwT7QCW45J5O8-9I1miQvApH4Da14poOWtNCIUXmUguFYn_dXEV1ow-r95aeoeWTC4OSiGNgPpCTPMI01Jx38ScJ4dSIXuBujM37M532H3tME-84t6r6B816m46_F1u7WZfckl6WZv0zWHSluVIe1xQdv6S6ZgVaZGFiyP9DGQG_VH1UfEJIGQT76cfFUl0-lOt0KSdt29Ydahjp45xwI-CfA-5Lv76EMQHV8QwOElOsPYbZ3mwLlADDN1MqH1OyhK47aePfHYdnSvmIs62Ty2Y6XKgkMHrIh-M4gsGDCvKy2BY8LBAkyZTQVH9PjgVp3djmcAuOF2wLN58GctibrsoAHiFiN8kRj-5Yva6OhXolXTKI5tDxJPMyr1DIybEDWX10omU54AsfUUcj3u_BpOeXW7nyEyi4q8MQJRzLoNLShxUHOAPhz45mN6OnXsxOt_1YareE4qoIZZBeTwKE-blycnqWy9MyeWW00U2v0Aklv4Vc0SjMqLacjdvJyaRVaPna8SXUEdoxgxOrSdIZZoVlJflLi5Lbc-BQdgMhG0knPbxsND1sEMS_g_Z8XAWjOwt35xY8S9so5Q7kl_Qzf2fvE0UXvBMJ-wzaTLaV1i6qqhZXWldcFggjiXsitGQiNOwMDvwSNyk7pqUex7ZI2TlTM__ghcx-wkwf0adc8J4TD2im-utKhiNseZXBvUd5TCMci53o0qmf3i2b-guMkbUNVd-nfkOB9NzW42gfIcSksZPWx8AY0tVlDkWstVzbR_pLNBKm1uIv-l_Q7m000F__0m00)
  - Biểu đồ lớp:\
    ![Diagram](https://www.planttext.com/plantuml/png/X9D1RW8n34NtEKMMi9Wh8AIfsBNY2YRZGgIG8CUi42VheaVg5QfCm4mI1fRpRJ_Rtvc_dzzrP20-7vrIna6CUWjiqVC7CEmWehuehVKU-QPlANnRXujbai-d0HYRoFNE-iJ16kknX1b2OBp7CccFN0ePFT44-XNOcgV8716WV4ffFwPj0XsRIO1jyBaq8f0v5AeGRhlsmNiqd2apBWZflJy5hh7dqPmm6hAdD5GVF5Dm3cdUr2UBj5wLmunv-fBKYLbTjvffhcPcwb95uTMhpCg7LwdbzLLrZqdREaKUZ3GSTrNr3QRp2ADvo1L4hT4FwIVw1m00__y30000)

PatientDatabase Class:

Lớp này có thể đại diện cho cơ sở dữ liệu chứa thông tin về bệnh nhân, nhưng trong sơ đồ này bạn chưa chỉ rõ các phương thức trong lớp này. Nếu lớp này chỉ lưu trữ dữ liệu, bạn có thể thêm các phương thức như getPatientProfile() hoặc updatePatientProfile() để làm rõ hơn.
MedicineDatabase Class:

+createMedicine(): Phương thức này sẽ tạo mới một loại thuốc trong cơ sở dữ liệu của thuốc. Đúng như mong đợi, phương thức này chỉ được định nghĩa trong MedicineDatabase, nơi thực hiện các thao tác với dữ liệu thuốc.
NoticeDatabase Class:

+createNotice(): Phương thức này sẽ tạo một thông báo mới trong cơ sở dữ liệu. Tuy nhiên, bạn chưa chỉ rõ việc tạo thông báo này có liên quan đến cái gì, ví dụ như thông báo về đơn thuốc, hoặc thông báo cho bệnh nhân.
CreateForm Class:

+createMedication(): Phương thức này có thể là nơi người dùng nhập liệu để tạo đơn thuốc mới.
+searchMedication(): Phương thức này có thể tìm kiếm thuốc trong cơ sở dữ liệu thuốc.
PatientConnect Class:

+updatePatientProfile() và +searchPatientProfile(): Các phương thức này có thể cập nhật hoặc tìm kiếm hồ sơ bệnh nhân, như đã giải thích trong sơ đồ trước đó.
MedicineConnect Class:

+createMedicine(): Phương thức này thực hiện công việc tạo thuốc trong cơ sở dữ liệu thuốc (được gọi từ MedicineConnect).
PrescriptionController Class:

+createMedicine() và +searchMedication(): Các phương thức này sẽ xử lý logic liên quan đến việc tạo thuốc và tìm kiếm thuốc, tương tác với các lớp MedicineConnect và CreateForm.
Medication Class:

Lớp này có thể đại diện cho đối tượng "Thuốc", lưu trữ thông tin chi tiết về thuốc như tên thuốc, liều lượng, cách sử dụng, v.v.
    
3. Cung cấp thông tin về thuốc
 - Các lớp phân tích của ca sử dụng Cung cấp thông tin về thuốc và chẩn đoán:
    - Boundary:
      - PrescriptionForm: Giao diện mà nhân viên lâm sàng sử dụng tìm các loại thuốc để kê vào một đơn thuốc.
      - PrescriptionConnect: Giao diện tương tác với hệ thống quản lý thuốc được duyệt bởi cơ quan y tế.
    - Control:
      - PrescriptionController: Điều phối quá trình tìm đơn các loại thuốc trong cơ sở dữ liệu. Xử lý các yêu cầu tìm kiếm thuốc và thông tin chẩn đoán từ PrescriptionForm. PrescriptionConnect hỗ trợ hệ thống tìm kiếm thuốc từ MedicineDatabase.
    - Entity:
      - MedicineDatabase: Lớp này đại diện cho cơ sơ dữ liệu chứa các loại thuốc đã được phê duyệt bởi cơ quan y tế.
      - Medication: Lớp này đại diện cho các loại thuốc trong cơ sở dữ liệu.
  - Biểu đồ sequence:
    ![Diagram](https://www.planttext.com/plantuml/png/b98zJiD048NxFSLS81Tm4KMOlm8G4caebxKJhsAFmtetKagKWW9Hv0G8HGY1Y4X1vIrI9CezvWHS0Ta4OYUn2EtCl4zlvisddJOIpPKsKSYuqB42DvGe1GylD6-rs5viqEEg3-VAJuIINIrZF8nLnDmOjOh3KcDP2trLBNHZH5zeTe1QwZwS-fuKF6kMAXBzVQxv5KzynbZ94zJg6r07t83iFO88oBu8mFa0sw1dRn5R7uLQhLvUqe7BsQi1GUcp0Gme7NT11xEFZ20HT6383aNUns_c3dxETk5iUgjNtDE18x9Z2VsLqupm0sNRLTkiBU__7s11bX7N0tAWML22LZ6sGImU8I7x01xPTmWbsLl3rfLv5bjmolIXH-aJbZrLo_C7Sk1aCJ4m7v8TIj2B2TaHjjbg89-ll4TJKJg27jaRw50wrN1jiaBke2CfdMxczNkKFtFRXLZCRUjFxOwgUlHZINQGlIBPkoA8iOQFded2Bm000F__0m00)
  - Biểu đồ lớp:\
    ![Diagram](https://www.planttext.com/plantuml/png/f99D2W8n38NtFKMMCmil82B2Y2i5GIzGEq6BdLQIY8XuCXSUoIj8HtJ-651S9dd9ztZaSRjFM3J9iN1A6QUPOO6vDTRZL8lUQ4QuA01Wr6HsvKoB3JxPu_aKA1_2IiZwRGfpopAg16DrRLmict2fkaj2DcGFiJyBL7p9YQBSyi7fSwMAxAHebCEEeHIWdvu5xz78ouHv5UlmpY0fiLkKwXp_aa2TbWKl59n3-YVPJdg3mRW7qz3MwEsDMWoTy-zuuaxxGLJdOpwgqgzI4_Hv_B0d0000__y30000)
    MedicineDatabase Class:

+searchMedication(keyword: String) List<Medication>: Phương thức này tìm kiếm thuốc dựa trên từ khóa (keyword) và trả về một danh sách các đối tượng Medication phù hợp với từ khóa đó. Điều này đúng với mục đích của MedicineDatabase là lưu trữ và tìm kiếm các thông tin thuốc trong cơ sở dữ liệu.
Medication Class:

Đây là lớp đại diện cho đối tượng thuốc, có thể chứa các thuộc tính như tên thuốc, công dụng, liều lượng, v.v. Tuy nhiên, trong sơ đồ này, lớp Medication chưa có phương thức nào được định nghĩa. Bạn có thể thêm các thuộc tính hoặc phương thức để làm rõ hơn về chức năng của lớp này.
PrescriptionForm Class:

+searchMedication(keyword: String): Phương thức này cho phép người dùng tìm kiếm thuốc từ giao diện của PrescriptionForm, và gọi phương thức searchMedication() từ PrescriptionController.
+displayMedicationList(medicationList: List<Medication>): Phương thức này hiển thị danh sách thuốc được tìm thấy sau khi tìm kiếm. Nó có thể nhận đầu vào là một danh sách các đối tượng Medication và hiển thị chúng trong giao diện.
PrescriptionFormConnect Class:

Lớp này không có phương thức nào được định nghĩa trong sơ đồ của bạn. Đây có thể là lớp kết nối giữa PrescriptionForm và cơ sở dữ liệu (hoặc các lớp khác) để truy xuất thông tin thuốc. Nếu vậy, bạn có thể thêm phương thức như connectToDatabase() hoặc getMedications() để thể hiện rõ chức năng của lớp này.
PrescriptionController Class:

+searchMedication(keyword: String) List<Medication>: Phương thức này sẽ xử lý logic tìm kiếm thuốc và trả kết quả về dưới dạng danh sách Medication. Phương thức này có thể gọi tới MedicineDatabase để lấy thông tin thuốc.
