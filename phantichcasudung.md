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
    ![Diagram](https://www.planttext.com/plantuml/png/Z5CnRjim5DrvYWVjle078x3SfbuA0Ow7ZBIiHe8bAfM_37WiEWH59wCNi1i4ROCOxP1973mmo3ruWbwX46LBT18xtKZ-z_xZ-tpyApSdK-8PvKdCk4zf1kTzgBuBp29rAnpmATm1wwQv6FDi3cTuEUOKl4spnDI6VVP6K4HpE1wdA13aPUc7A0vCrVEOcmhAqhWkR_Tna5MzwwsbqK15uDCELwwVYlKuyH6VLcgzBcFk0AqEXlqspjLj3byNFt9Gnk5h-Ij7gEKtJ1zN66bv9KA8qYeRzj5gTU0EzbWYrCNw4XIgUt41YeGv5o1rbrWwfrgk8ymjDNMNO1BfOfEOpXtBv2lm1hYbbPuFSDYsN29xtJREcZu7RFQwDJRBvvZfucPtM4kTPRgunaGN6yB7l5oR-pqi7lzeUUtRehQh_w1PnZolZLEr4aS8dhURxskjjoCUjF4kqlAp08LQVZr2O3mcE6PS5EhYPbwFos50yx1kgEKN4MAgvPfZffRs2_Wc6oOYLFCPKDscDZXJonGF2oqN4SZeYmi6LEwEnc9FOA9-9Y-qEH2NyvUxL0GxCgwjCTRoD-98owlccp2W2OsDhWjFWZFJyjFUw0zVu7XydlCifoOMrRSSgLKvOBNFA3_jKeJmIqpzAiyoiltQfiSU8n1Znau2CSwJ-1y0003__mC0)
  - Biểu đồ lớp:\
    ![Diagram](https://www.planttext.com/plantuml/png/h99DJiCm48NtFeMNiEW5AXHLQeKK2KJ4tzuuap326LSpanNYP2mu4bT03WcD6q4tB3tlyxpd9t--Vsn47MlV1MDyS2BsOLyxXSl8dNqrrjf-E5TE4KWhZWq6E3jFYe1Z_xnGtgPDkVAzhQo151i4NjixPQGsJIjWYUH2IKtapYb6ciktA2ytpIF60EHXhkpGjHG5PJwyPt3Q0MbcmI2USPzsNqEDVd2HjRr2qOl3f4ZmDfBqGSSW0p4V3Kn9oh7kVHRs-EtRcAWGWF-fp9rJz-HaR7D8bjyf_hPfGKzwR2CHU3qH-9TDX--pMXLssODPDcEFo6G-mz8nPwOI9kYdb8mQOncp0QhJ1_y2003__mC0)
    
2. Quản lý thuốc và điều trị
 - Các lớp phân tích của ca sử dụng Quản lý thuốc và điều trị:
    - Boundary:
      - CreateForm: Giao diện mà nhân viên lâm sàng sử dụng để thêm các loại thuốc vào một đơn thuốc.
      - PatientConnect: Giao diện tương tác với hệ thống quản lý hồ sơ bệnh nhân khi nhân viên lâm sàng cần cập nhật hồ sơ bệnh nhân.
      - MedicineConnect: Giao diện tương tác với hệ thống quản lý hồ sơ bệnh nhân khi nhân viên lâm sàng cần tạo đơn thuốc cho bệnh nhân.
    - Control:
      - PrescriptionController: Điều phối quá trình tạo đơn thuốc cho bệnh nhân. Xử lý các yêu cầu tìm kiếm thuốc và thêm các loại thuốc vào một đơn từ FormPrescriptionUI. Dữ liệu sau khi được xử lý sẽ được lưu vào PatientDatabase.
    - Entity:
      - PatientDatabase: Lớp này đại diện cho hệ thống quản lý hồ sơ bệnh nhân, là cơ sơ dữ liệu chứa các hồ sơ bệnh nhân.
      - MedicineDatabase: Lớp này đại diện cho cơ sơ dữ liệu chứa các loại thuốc đã được phê duyệt bởi cơ quan y tế.
      - NoticeDatabase: Lớp này đại diện cho cơ sở dữ liệu chứa các thông báo và danh tính của nhân viên lâm sàng khi bỏ qua thông báo cảnh báo.
      - Medication: Lớp này đại diện cho các loại thuốc mà bệnh nhân đã và đang sử dụng.
  - Biểu đồ sequence:
    ![Diagram](https://www.planttext.com/plantuml/png/p5GzRjim6DrvYW_QUu4CHM3PJOFMHb0dGqT68Yp24kLGb06DHOSEHL5upbBN28gc2P2XapXaK91xy0IzGa59baGfTeHEzM1Bvdll-tly_iZxmqXWBkB0HzWH8GThucNV6InfTiqim17OKpG8O-PYde1bSu85UHNo83yxEqOZ9gX8m1eJbpfOqB1WZKV83fdWeG_M2IUHm-b27vP_-eGNujLh8qWkHHcnGyQ88xP0_Mo6eumCiS3dE295KE9EaqYGe25sWWKbJ3IrtX4dv6vRiGGQWiD1TJm91NNCS9FX025x2YzUmjdn0RpFhcDmLFeZ1f7T122yMCcLWywEDSAU6WZcgVHs0SBBVhCP2CegU2quAJ3Bx1iaflPMi-hU0HmfUKlRk5gqGfOyNNeFaePfHjNPvpWLiCKwvN42IvLUiIQacSifL-a6vYgz5t0HgtHJns-L-YIoAa_77Ht0KRPcyB1ISaL1FDufkM4pD1xbvxgvHHakPXv4sThnEbZTud9khwcI7_M4bFpSe204K4_BzfJyKesnCpKlkmxWOVMuPWYW6D_ED05qecRHRrLwbJJpRGMOwnm341nNKSoX6wutlDYcLiC4awHLXeE-rE5WYt-p0mI1afSK0I00x0km1af-OXwmV0ETvytMNqh-r7Ua85a8ye-MxrRLjKQ1RjNnvDtfibgsgcrJNjlpR1tgHcoObp-Nj5tEsSygV_96D7QmxiDNk8Xnax9jGjD_tNj9LNg_0A7abLFuhsBrMHy6mRJIfEK2__4kRgoo7QpT1cnSZeutdfnVnuVFAzHsFEs5xU-jVtLNFtyPCtl6LIMM-14nFJGlCVkjrCt6zk8a3-NfrNJ9Ph1KyWFCA0x1fVgsbfslh_t-PCskBvNyXK6ej4wTkMXRWB4DoWhSlVkWttp_bytHVrlebZ0N7HBcne7_5m00__y30000)
  - Biểu đồ lớp:\
    ![Diagram](https://www.planttext.com/plantuml/png/X5D1QiCm4Bph5Juc1t-W59CI9r1eWwbVi94swO8jfTBwK8fVraEVr2yKsN4isKbw4MXcThGhZNw_VrQEmN9JLqB82fnB2c12pJamxC5XyYMI97aXnu-lg4W2az6PQ0Tv1vB6M2yj0kF0BPQZVcUOv4KTY7iYbAuxV6jiFJFjkbWiFUeGh7oFq7OoozfeZP9xb-QaWF7C5DOSgCBGQSRCHetiRazQM7JIqiatjJQQhQagj3Ug_XbaHFlwSV-i7fAIBUcZntTGOxZFnnOYs3WuHi8dLPCcnxOpVJCDH_JMuaU3Mdw6OEcJauDN-jL36wrYe2I5cyC19RkmjBiF83rC4P7dYzkJFkP6ih5No6waae6RiRGL8eXCccRNNq3SU9WqpUAyt15Eed176UTTJ18vdZbLNFvJccR1Sul9oK4l5uSfC6Xw0x52hVn__mC00F__0m00)
    
3. Cung cấp thông tin về thuốc
 - Các lớp phân tích của ca sử dụng Cung cấp thông tin về thuốc và chẩn đoán:
    - Boundary:
      - PrescriptionForm: Giao diện mà nhân viên lâm sàng sử dụng tìm các loại thuốc để kê vào một đơn thuốc.
      - PrescriptionFormConnect: Giao diện tương tác với hệ thống quản lý thuốc được duyệt bởi cơ quan y tế.
    - Control:
      - PrescriptionController: Điều phối quá trình tìm đơn các loại thuốc trong cơ sở dữ liệu. Xử lý các yêu cầu tìm kiếm thuốc và thông tin chẩn đoán từ PrescriptionForm. PrescriptionFormConnect hỗ trợ hệ thống tìm kiếm thuốc từ MedicineDatabase.
    - Entity:
      - MedicineDatabase: Lớp này đại diện cho cơ sơ dữ liệu chứa các loại thuốc đã được phê duyệt bởi cơ quan y tế.
      - Medication: Lớp này đại diện cho các loại thuốc trong cơ sở dữ liệu.
  - Biểu đồ sequence:
    ![Diagram](https://www.planttext.com/plantuml/png/b9E_JiCm4CPtFyMzG5yWGuKe_mQGaEZ2QDoqjPhOnJbNoeWO69Zw10XL20bHqO4f7ZeKzJtk2VeAAA5LapI1ifxz_VnzT-ULcnz4o0tQC61Se3RG2gIIWWTNoBjTTgYjwd0JmwNn8s7a4ALM9zg4x5YXn1Wk_8uKFAsobbPeT52ukgu5lgb7jRHIli02KIh_Y2E_uP7F62juWaPp1-71ARcfX7ZnPa5Gyce15-yX32Gbyn2mRycD1IlBeD5e5WDxSBr5g3ubqo5WV_6fUe1IRK3PkSgUsD_RxvXTQysQHjPbhGgvLLKvMpV-Fy2SB2MMP-L1EwS4D5hrG2oV8IBt11ro7n18SW-MbPNPA2fm9eOH9I-gQAbINHklRIYPm8ZS7GmecIFSshIGsn1Mc_7FCUn3p8zX4pFxCnwSBsSMliRanX9mEICtKRsVUDc5oc2RfykoVTRxJ9AxJpUGt6FU-pS0003__mC0)
  - Biểu đồ lớp:\
    ![Diagram](https://www.planttext.com/plantuml/png/f5DBQiCm4Dth5BDC5hb0A24bJg3GbbAVO2ADKr5vb4fZYYazMHSzKgzGv93OYXCeT6EOD-_Dvutry_MzZ891cjeffHt620zahBPC1GfkCH9yA028X46_T3aKwtdoIksx3sOEfGJBkodSsoWtFM6XFhEA7NYerSTt9tt27x6cOLnGrC7k4p63VSHTHhmrjMKR9NH5dtqZMNeJwAqXrkqGBDFQ1IPc-YPepIO7IcjeNLMa9GwbAyyIqF9nYopv5BgfjvPtXTVYmuLajr8fA4qlFRarv6nygF_eVo8P6_SEsvwLRZAfit0-EjGKu7htbMScBOSX3hPLLNus0E2pom50yAw7BfPV9HkzSnJ-yukDx9hD5bVQPDn1ztF5OEzH-QCVINF-KjJewPnOtRnABObDKxjV0000__y30000)
