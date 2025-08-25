# Hướng dẫn khắc phục lỗi Android Studio

## Lỗi thường gặp và cách khắc phục

### 1. Lỗi Gradle Wrapper
**Lỗi**: `gradlew.bat is not recognized`

**Khắc phục**:
1. Mở Android Studio
2. Vào `File > Settings > Build, Execution, Deployment > Gradle`
3. Chọn "Use Gradle from: 'gradle-wrapper.properties' file"
4. Nhấn "OK" và sync lại project

### 2. Lỗi SDK
**Lỗi**: `compileSdk version XX not found`

**Khắc phục**:
1. Vào `File > Settings > Appearance & Behavior > System Settings > Android SDK`
2. Tab "SDK Platforms" > Cài đặt "Android 14.0 (API 34)"
3. Tab "SDK Tools" > Cài đặt "Android SDK Build-Tools 34.0.0"

### 3. Lỗi AGP Version
**Lỗi**: `Android Gradle Plugin version not compatible`

**Khắc phục**:
1. Đảm bảo Android Studio version mới nhất
2. Sync project với Gradle files
3. Clean và rebuild project

### 4. Lỗi Dependencies
**Lỗi**: `Could not resolve dependencies`

**Khắc phục**:
1. Vào `File > Settings > Build, Execution, Deployment > Gradle`
2. Kiểm tra "Offline work" không được check
3. Sync project

### 5. Lỗi Java Version
**Lỗi**: `Java version not compatible`

**Khắc phục**:
1. Vào `File > Project Structure`
2. Tab "SDK Location" > Chọn JDK 11 hoặc 17
3. Apply và OK

## Các bước khắc phục nhanh

### Bước 1: Clean Project
```
Build > Clean Project
```

### Bước 2: Invalidate Caches
```
File > Invalidate Caches and Restart
```

### Bước 3: Sync Gradle
```
File > Sync Project with Gradle Files
```

### Bước 4: Rebuild Project
```
Build > Rebuild Project
```

## Cấu hình tối ưu

### Gradle Settings
- **Gradle JDK**: 11 hoặc 17
- **Build and run using**: Gradle
- **Run tests using**: Gradle

### Memory Settings
- **Gradle VM options**: `-Xmx2048m -XX:MaxPermSize=512m`

## Liên hệ hỗ trợ

Nếu vẫn gặp lỗi, hãy:
1. Chụp màn hình lỗi
2. Gửi log từ `Build > View > Tool Windows > Build`
3. Mô tả chi tiết lỗi
