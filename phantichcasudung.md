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
    ![Diagram](https://www.planttext.com/plantuml/png/h99DJiCm48NtFeMNiEW5AXHLQeKK2KJ4tzuuap326LSpanNYP2mu4bT03WcD6q4tB3tlyxpd9t--Vsn47MlV1MDyS2BsOLyxXSl8dNqrrjf-E5TE4KWhZWq6E3jFYe1Z_xnGtgPDkVAzhQo151i4NjixPQGsJIjWYUH2IKtapYb6ciktA2ytpIF60EHXhkpGjHG5PJwyPt3Q0MbcmI2USPzsNqEDVd2HjRr2qOl3f4ZmDfBqGSSW0p4V3Kn9oh7kVHRs-EtRcAWGWF-fp9rJz-HaR7D8bjyf_hPfGKzwR2CHU3qH-9TDX--pMXLssODPDcEFo6G-mz8nPwOI9kYdb8mQOncp0QhJ1_y2003__mC0)
    
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
    ![Diagram](https://www.planttext.com/plantuml/png/p5OxRjj04Ett50FskO2Am12bE4PYmOZi8kMQN8WBYqEPN0fW6RX84GI1QZTH12EmOmCkKd4B5nHyZpr1hX0iIV4hoKIgg90exNjlTcRU3FH7FXq4WleYTAU4MiBpmHWvoG-4EK_kq00QW3acVIz4c_eH6ARFg61lFDzDpywEo1055n4Onypc5XNSorZ7Gs9wA7nl2iQ9pmBBvpDzcFyuPNucNdoj14cbE3BJGsIMs03rSpqSHpQWWfxJW6L1cJsE0i7SYjW95PoXg6fzO9Rdsqt575WJ7FIBuv4dk5KFDnhq2J77yEerd1trm7IK_8fWEKhUMe3hAvo0IEvT44wevC8YPqSQQevxy36v2y5IySyGq57nmmo4a_pMU8u5l5GUPPXvyXsYagcrDvf56NjmgEG3R-9AqGAPytGDEf0qJ3EA4h_4AO0DrgaVHZ1NyGrM8TMxdFegNi65Yfy4N8OgNfNn6wbkHHRfwRZ37XmcIuJrGia51_7ygEGA9-Huc9xhucPfs1GT29AbvRImkiHvtzvo9QzqXvJyKg4G0j3oGLw8LjUSvCw5zU9vYGGWQz_EQmBeYzQJVg_YcwXwtqQ02tr75uHFYoZrfjViN_DYareq4-eahJBeTwKE-XlyknqWS9MyvWI00D2f0AElv6Tq0DDLT9uMMxyfUQjd92CP1DANbczdrRP6XcxaiNLssgo6hKhRv6DxdYmzNOWLEkbpJjlbdFsi_2CjH6KPwpfyWykGLYcR8bJzrvvBhkAd6GWbRwpCVmMho_ge4UfM6ZLSC7r-32khR0Thjm4hmz7onjR-jNpuia9fnzDEsExU-bTtTVDN3cRJWDLzSP5ZzjkZ7S5qmYWrfQFNpJLEOAxa9vXmwe7DzGJcrIn7UR-jrxLApfNyHK6ekBmwscIJG6t2ympsptYtdlqlsq0dYZOvO6Zh_rP_0G00__y30000)
  - Biểu đồ lớp:\
    ![Diagram](https://www.planttext.com/plantuml/png/X5D1QiCm4Bph5Juc1t-W59CI9r1eWwbVi94swO8jfTBwK8fVraEVr2yKsN4isKbw4MXcThGhZNw_VrQEmN9JLqB82fnB2c12pJamxC5XyYMI97aXnu-lg4W2az6PQ0Tv1vB6M2yj0kF0BPQZVcUOv4KTY7iYbAuxV6jiFJFjkbWiFUeGh7oFq7OoozfeZP9xb-QaWF7C5DOSgCBGQSRCHetiRazQM7JIqiatjJQQhQagj3Ug_XbaHFlwSV-i7fAIBUcZntTGOxZFnnOYs3WuHi8dLPCcnxOpVJCDH_JMuaU3Mdw6OEcJauDN-jL36wrYe2I5cyC19RkmjBiF83rC4P7dYzkJFkP6ih5No6waae6RiRGL8eXCccRNNq3SU9WqpUAyt15Eed176UTTJ18vdZbLNFvJccR1Sul9oK4l5uSfC6Xw0x52hVn__mC00F__0m00)
    
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
    ![Diagram](https://www.planttext.com/plantuml/png/f5DBQiCm4Dth5BDC5hb0A24bJg3GbbAVO2ADKr5vb4fZYYazMHSzKgzGv93OYXCeT6EOD-_Dvutry_MzZ891cjeffHt620zahBPC1GfkCH9yA028X46_T3aKwtdoIksx3sOEfGJBkodSsoWtFM6XFhEA7NYerSTt9tt27x6cOLnGrC7k4p63VSHTHhmrjMKR9NH5dtqZMNeJwAqXrkqGBDFQ1IPc-YPepIO7IcjeNLMa9GwbAyyIqF9nYopv5BgfjvPtXTVYmuLajr8fA4qlFRarv6nygF_eVo8P6_SEsvwLRZAfit0-EjGKu7htbMScBOSX3hPLLNus0E2pom50yAw7BfPV9HkzSnJ-yukDx9hD5bVQPDn1ztF5OEzH-QCVINF-KjJewPnOtRnABObDKxjV0000__y30000)
