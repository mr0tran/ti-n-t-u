**Tác giả**: tuan0tran  
**Repository**: [https://github.com/mr0tran/ti-n-t-u.git](https://github.com/mr0tran/ti-n-t-u.git)

## Cấu trúc Layout

### 1. Màn hình Start (`activity_main.xml`)
- **Chức năng**: Nhập tên người chơi (từ 2 người trở lên)
- **Thành phần chính**:
  - Header với tiêu đề và mô tả
  - TextInputLayout để nhập tên người chơi
  - Nút "Thêm người chơi"
  - RecyclerView hiển thị danh sách người chơi
  - Nút "Bắt đầu chơi"

### 2. Màn hình Game (`activity_game.xml`)
- **Chức năng**: Hiển thị lượt chơi và bốc bài
- **Thành phần chính**:
  - Header hiển thị người chơi hiện tại
  - CardView chứa lá bài và nhiệm vụ
  - Nút "Bốc bài" và "Người tiếp theo"
  - Nút "Kết thúc" game

### 3. Màn hình Kết thúc (`activity_result.xml`)
- **Chức năng**: Tổng kết lượt uống của từng người chơi
- **Thành phần chính**:
  - Header "Kết thúc game"
  - CardView chứa tổng kết từng người chơi
  - Tổng số lượt uống
  - Nút "Chơi lại" và "Về màn hình chính"

## Layout Items

### `item_player.xml`
- Item cho RecyclerView danh sách người chơi
- Hiển thị tên người chơi và nút xóa

### `item_player_summary.xml`
- Item cho RecyclerView tổng kết
- Hiển thị tên và số lượt uống của từng người

## Drawables

### `card_background.xml`
- Background cho lá bài với gradient và border

### `drink_count_background.xml`
- Background cho số lượt uống với màu accent

### `ic_remove.xml`
- Icon X cho nút xóa người chơi

## Màu sắc (colors.xml)
- **Primary**: #FF6B35 (Cam chủ đạo)
- **Accent**: #FFD93D (Vàng nhấn)
- **Background**: #FFF8F0 (Nền kem nhạt)
- **Card Background**: #FFFFFF (Trắng)
- **Text Primary**: #2C3E50 (Xanh đậm)
- **Text Secondary**: #7F8C8D (Xám)

## Tính năng Responsive
- Sử dụng **ConstraintLayout** làm layout chính
- **LinearLayout** cho các thành phần con
- **CardView** với corner radius và elevation
- **MaterialButton** với styling nhất quán
- **TextInputLayout** cho input fields
- **RecyclerView** cho danh sách động

## Hướng dẫn sử dụng

### 1. Tích hợp vào Activity
```java
// Trong MainActivity
setContentView(R.layout.activity_main);

// Trong GameActivity  
setContentView(R.layout.activity_game);

// Trong ResultActivity
setContentView(R.layout.activity_result);
```

### 2. Xử lý RecyclerView
```java
// Adapter cho danh sách người chơi
PlayerAdapter playerAdapter = new PlayerAdapter(players);
rvPlayers.setAdapter(playerAdapter);
rvPlayers.setLayoutManager(new LinearLayoutManager(this));

// Adapter cho tổng kết
PlayerSummaryAdapter summaryAdapter = new PlayerSummaryAdapter(playerSummaries);
rvPlayerSummary.setAdapter(summaryAdapter);
rvPlayerSummary.setLayoutManager(new LinearLayoutManager(this));
```

### 3. Xử lý sự kiện
```java
// Nút bốc bài
btnDrawCard.setOnClickListener(v -> {
    // Logic bốc bài và hiển thị nhiệm vụ
});

// Nút thêm người chơi
btnAddPlayer.setOnClickListener(v -> {
    String playerName = etPlayerName.getText().toString();
    if (!playerName.isEmpty()) {
        // Thêm người chơi vào danh sách
    }
});
```

## Git Workflow

### Nhánh đã tạo
- **Nhánh**: `tuan0tran`
- **Commit messages**:
  - "Add Tiên Tửu game layouts and resources - Created by tuan0tran"
  - "Add complete game layouts - activity_game.xml and activity_result.xml"

### Cách merge
1. Tạo nhánh mới: `git checkout -b tuan0tran`
2. Thêm file: `git add .`
3. Commit: `git commit -m "message"`
4. Push nhánh: `git push origin tuan0tran`
5. Merge vào main: `git checkout main && git merge tuan0tran`
6. Push main: `git push origin main`

## Lưu ý
- Đảm bảo đã thêm Material Design dependencies trong `build.gradle.kts`
- Sử dụng theme Material3 để có giao diện đẹp nhất
- Các layout đã được tối ưu cho responsive design
- Có thể tùy chỉnh màu sắc trong `colors.xml` theo ý muốn
- File `.gitignore` đã được cấu hình để loại trừ các file build không cần thiết

## Tình trạng dự án
✅ **Hoàn thành**: Layout XML cho 3 màn hình chính  
✅ **Hoàn thành**: Màu sắc và chuỗi cần thiết  
✅ **Hoàn thành**: Git workflow và merge code  
🔄 **Đang chờ**: Logic game và Activity implementation  
🔄 **Đang chờ**: Adapter cho RecyclerView  
🔄 **Đang chờ**: Testing và optimization

