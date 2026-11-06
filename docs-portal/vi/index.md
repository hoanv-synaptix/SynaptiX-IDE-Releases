# Cổng Tài liệu Kỹ thuật SynaptiX IDE (Technical Wiki)

<div class="doc-meta-bar">
  <span><strong>Mã tài liệu:</strong> SYNX-DOC-IDE-000</span>
  <span><strong>Nền tảng phần mềm:</strong> SynaptiX IDE (.NET 8 Desktop Engineering Environment)</span>
  <span><strong>Đối tượng:</strong> Kỹ sư Tích hợp Hệ thống, Tự động hóa &amp; IIoT</span>
  <span><strong>Tiêu chuẩn:</strong> IEC/IEEE 82079-1 &bull; ANSI/ISA-101</span>
</div>

Chào mừng bạn đến với cổng tài liệu kỹ thuật chính thức của **SynaptiX IDE** — môi trường kỹ thuật tích hợp trên máy tính dành riêng cho việc thiết kế logic điều khiển, cấu hình truyền thông công nghiệp, mô phỏng kiểm thử, nạp chương trình an toàn và giám sát thời gian thực cho **Hệ sinh thái Tự động hóa Biên & IIoT SynaptiX**.

Khác với các phần mềm cấu hình rời rạc tách biệt giữa điều khiển tại chỗ, đọc cảm biến RS-485 và đẩy dữ liệu đám mây, **SynaptiX IDE** hợp nhất toàn bộ quy trình từ thiết kế sơ đồ khối trực quan, kiểm soát chặt chẽ kiểu dữ liệu vật lý, mô phỏng chu kỳ chính xác không cần phần cứng, nạp Flash hai pha nguyên tử đến chẩn đoán trực tuyến 20 FPS trong một không gian làm việc duy nhất.

![Tổng quan Giao diện Kỹ thuật SynaptiX IDE](/images/synaptix_main_anatomy.png)

---

## Lộ trình Đọc & Tra cứu Tài liệu

Toàn bộ tài liệu được tổ chức xuyên suốt theo **6 chương tuần tự** trên cây thư mục bên trái, dẫn dắt kỹ sư đi đúng mạch từ kiến trúc nền tảng, cài đặt ban đầu, làm chủ từng không gian làm việc, tra cứu chi tiết từng khối hàm đến tích hợp hệ thống hoàn chỉnh:

<div class="wiki-chapter-grid">
  <a class="wiki-card" href="./concepts/ecosystem-overview">
    <span class="wiki-card-step">CHƯƠNG 01</span>
    <h3>Tổng quan &amp; Kiến trúc Cốt lõi</h3>
    <p>Tìm hiểu 7 cấu hình thiết bị SynaptiX định sẵn, kiến trúc vùng nhớ Tag vật lý (BOOL, INT32, REAL), cơ chế chống nhập sai dữ liệu và chu trình thực thi tất định.</p>
  </a>
  <a class="wiki-card" href="./getting-started/installation">
    <span class="wiki-card-step">CHƯƠNG 02</span>
    <h3>Cài đặt &amp; Khởi tạo Nhanh</h3>
    <p>Cài đặt SynaptiX IDE trên Windows 10/11, thiết lập cổng USB CDC &amp; mạng TCP, làm quen bố cục giao diện và hoàn thành dự án đầu tiên trong 10 phút.</p>
  </a>
  <a class="wiki-card" href="./workspaces/device-tab">
    <span class="wiki-card-step">CHƯƠNG 03</span>
    <h3>Không gian Làm việc (7 Tab)</h3>
    <p>Hướng dẫn chuyên sâu cho từng Tab chức năng (Ctrl+1 đến Ctrl+7): Device, Logic Graph, Tag Catalog, Rule Table, Blueprints, Deploy và Live Watch.</p>
  </a>
  <a class="wiki-card" href="./blocks/overview">
    <span class="wiki-card-step">CHƯƠNG 04</span>
    <h3>Từ điển Khối hàm (Blocks)</h3>
    <p>Đặc tả kỹ thuật chuẩn datasheet (1 khối = 1 trang riêng) cho toàn bộ 18 khối hàm: Chuỗi Luật Cốt lõi, Định thời, Bộ đếm, Tuyến tính hóa SCALE, Modbus RTU, Xuất xung/DO, MQTT, HTTP và TCP.</p>
  </a>
  <a class="wiki-card" href="./tools/rs485-and-scada-slave">
    <span class="wiki-card-step">CHƯƠNG 05</span>
    <h3>Kết nối, DTU Studio &amp; Công cụ</h3>
    <p>Cấu hình bus RS-485, tích hợp SCADA qua Bản đồ Modbus Slave cố định, thiết lập MQTT TLS &amp; Wi-Fi, vận hành DTU Gateway Studio, mô phỏng Offline và AI Copilot.</p>
  </a>
  <a class="wiki-card" href="./appendices/keyboard-shortcuts">
    <span class="wiki-card-step">CHƯƠNG 06</span>
    <h3>Phụ lục Tra cứu Nhanh</h3>
    <p>Bảng tra cứu tức thời tổ hợp phím tắt toàn cục &amp; căn chỉnh Canvas, từ điển biến Macro ({val1:N}, {ts}, {device}), giới hạn bộ nhớ và bảng mã lỗi chẩn đoán.</p>
  </a>
</div>

---

## Quy trình Kỹ thuật Đầu-Cuối trên SynaptiX IDE

```mermaid
flowchart LR
    A["1. Chọn Cấu hình Thiết bị<br/>(New Project / Tự động nhận diện)"] --> B["2. Khai báo Tag Vật lý &amp; Ảo<br/>(Tag Catalog · Ctrl+3)"]
    B --> C["3. Thiết kế Sơ đồ Khối &amp; IIoT<br/>(Logic Graph · Ctrl+2)"]
    C --> D["4. Mô phỏng Offline &amp; Biên dịch<br/>(Simulator F5 · Compile F7)"]
    D --> E["5. Nạp Giao dịch Nguyên tử 2 Pha<br/>(Deploy · Ctrl+F5)"]
    E --> F["6. Giám sát &amp; Nghiệm thu<br/>(Live Watch Ctrl+7 · Live Debug F8)"]
```

## Các Trụ cột Kỹ thuật Cốt lõi

| Trụ cột Thiết kế | Cam kết Kỹ thuật trong SynaptiX IDE | Tài liệu Chi tiết |
| :--- | :--- | :--- |
| **Sự thật Thị giác & Toàn vẹn Kiểu** | Mọi ô nhập liệu đều ràng buộc chặt chẽ với vùng nhớ vật lý (`BOOL`, `INT32`, IEEE-754 `REAL`), tự động chuẩn hóa định dạng hoặc hoàn nguyên tức thì khi nhập sai kiểu. | [Kiến trúc Bộ nhớ Tag & Kiểu Dữ liệu](./concepts/data-model-and-types) |
| **Động cơ Thực thi Lai Tất định** | Kết hợp chuỗi luật Sự kiện – Điều kiện – Hành động 4 giai đoạn (tối đa 100 luật) với các khối định thời, bộ đếm, hiệu chuẩn tuyến tính và tiến trình truyền thông bất đồng bộ không gây nghẽn chu kỳ quét. | [Chu trình Thực thi Tất định](./concepts/execution-pipeline) |
| **18 Khối Hàm Công nghiệp Chuyên biệt** | Không cần viết mã kịch bản phức tạp — tích hợp sẵn từ phát hiện sườn xung, lịch thời gian thực RTC, đọc/ghi Modbus RTU Master, điều khiển chân cứng DO/PWM/PTO đến đóng gói JSON MQTT, HTTP REST và luồng TCP thô. | [Tổng quan Danh mục Khối hàm](./blocks/overview) |
| **Kiểm thử Offline Không cần Phần cứng** | Trình mô phỏng chu kỳ thực (`F5`) và khung bơm gói tin JSON giả lập giúp kiểm chứng 100% logic điều khiển ngay trên bàn làm việc trước khi ra hiện trường. | [Mô phỏng Offline & Gỡ lỗi Trực tuyến](./tools/simulator-and-live-debug) |
| **Triển khai Nguyên tử An toàn** | Cơ chế nạp hai pha kèm kiểm tra tiền triển khai đảm bảo sự cố mất điện hoặc tuột cáp giữa chừng không bao giờ làm hỏng cấu hình đang chạy trên thiết bị biên. | [Không gian Triển khai — Deploy](./workspaces/deploy-tab) |

::: tip Chuyển đổi Song ngữ Tức thời
Cả phần mềm **SynaptiX IDE** lẫn cổng tài liệu kỹ thuật này đều hỗ trợ chuyển đổi song ngữ tức thời giữa **Tiếng Việt** và **English** (thông qua nút chọn ngôn ngữ ở góc trên bên phải).
:::
