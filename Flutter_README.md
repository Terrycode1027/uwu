# Futter
---

##  目錄

1. [Flutter 是什麼？](#1-flutter-是什麼)
2. [系統需求確認](#2-系統需求確認)
3. [安裝 Flutter SDK](#3-安裝-flutter-sdk)
4. [安裝 Android Studio](#4-安裝-android-studio)
5. [設定 Android 模擬器](#5-設定-android-模擬器)
6. [安裝 VS Code（推薦編輯器）](#6-安裝-vs-code推薦編輯器)
7. [用 flutter doctor 診斷環境](#7-用-flutter-doctor-診斷環境)
8. [建立你的第一個專案](#8-建立你的第一個專案)
9. [認識專案結構](#9-認識專案結構)
10. [執行程式](#10-執行程式)
11. [修改你的第一行程式碼](#11-修改你的第一行程式碼)
12. [常見錯誤與解決方式](#12-常見錯誤與解決方式)
13. [下一步學習資源](#13-下一步學習資源)

---

## 1. Flutter 是什麼？

**Flutter** 是 Google 開發的開源 UI 框架，讓你只需要寫一份程式碼，就能同時發佈到：

- Android
- iOS
- 網頁（Web）
- Windows / macOS / Linux

Flutter 使用 **Dart** 語言，語法類似 Java / C#

---

## 2. 系統需求確認

在開始之前，請先確認你的電腦符合以下條件：

### Windows

| 項目 | 需求 |
|------|------|
| 作業系統 | Windows 10 或更新版本（64 位元） |
| 記憶體（RAM） | 至少 8 GB（建議 16 GB） |
| 硬碟空間 | 至少 10 GB 可用空間 |
| PowerShell | 5.0 或以上 |

### macOS

| 項目 | 需求 |
|------|------|
| 作業系統 | macOS 12（Monterey）或更新版本 |
| 記憶體（RAM） | 至少 8 GB |
| 硬碟空間 | 至少 10 GB 可用空間 |


---

## 3. 安裝 Flutter SDK

### Windows 安裝步驟

**步驟 1：下載 Flutter SDK**

打開git bash輸入:git clone -b stable https://github.com/flutter/flutter.git
電腦就會自己去找Flutter官方發布的最新穩定版本並下載到當前資料夾。
```
檔案位置通常在C:\User\flutter
```

>  不要放在 `C:\Program Files\`（需要管理員權限，容易出問題）  
>  不要放在含有中文或空白的路徑（例如 `C:\我的資料夾\flutter`）

**步驟 2：設定環境變數（Path）**

這個步驟讓你在任何地方都能使用 `flutter` 指令。

1. 按 `Win + S`，搜尋「環境變數」
2. 點選「進階」
3. 在右下角點選「環境變數」按鈕
4. 在「使用者變數」區域，找到 `Path`，雙擊開啟
5. 點選「新增」
6. 輸入你的 Flutter 路徑，例如：
   ```
   C:\flutter\bin
   ```
7. 一路點「確定」儲存

**步驟 4：驗證安裝**

開啟新的**命令提示字元（CMD）**或 **PowerShell**，輸入：

```bash
flutter --version
```

如果看到類似以下輸出，代表安裝成功 ：

```
Flutter 3.x.x • channel stable
Dart 3.x.x
```

---


## 4. 安裝 Android Studio

Android Studio 提供了 **Android SDK** 和 **模擬器**，是執行 Flutter Android App 的必要工具。

**步驟 1：下載 Android Studio**

 https://developer.android.com/studio

下載並安裝（保持所有預設選項即可）

**步驟 2：完成初始設定精靈**

第一次開啟 Android Studio 時，它會引導你安裝：
- Android SDK
- Android SDK Platform-Tools
- Android 模擬器

全部選「Next」接受預設安裝。

**步驟 3：接受 Android 授權**

回到命令列，執行：

```bash
flutter doctor --android-licenses
```

會出現一連串授權合約，全部輸入 `y` 並按 Enter 接受。

---

## 5. 設定 Android 模擬器

**步驟 1：開啟 Android Studio**

**步驟 2：前往 Virtual Device Manager**

點選選單 `Tools` → `Device Manager`（或 `AVD Manager`）

**步驟 3：建立新虛擬裝置**

1. 點「**Create Device**」
2. 選擇一款手機，例如 **Pixel 7**，點「Next」
3. 選擇系統映像（System Image）：選最新的 **API 版本**（帶有 `Recommended` 標籤），點「Download」下載後選取，點「Next」
4. 點「Finish」完成建立

**步驟 4：啟動模擬器**

在裝置清單中，點選 ▶️ 啟動模擬器，等待它開機（第一次會比較慢）。

> 💡 **小技巧：** 模擬器很吃效能。如果你有 Android 手機，可以用 USB 線連接電腦，開啟手機的「開發者模式」，這樣直接在真實手機上跑，速度更快！

---

## 6. 安裝 VS Code（推薦編輯器）

VS Code 輕量且好用，是開發 Flutter 最受歡迎的編輯器之一。

**步驟 1：下載 VS Code**

👉 https://code.visualstudio.com/

**步驟 2：安裝 Flutter 擴充套件**

1. 開啟 VS Code
2. 按 `Ctrl + Shift + X`（macOS：`Cmd + Shift + X`）開啟擴充功能面板
3. 搜尋「**Flutter**」
4. 安裝 **Flutter**（由 Dart Code 開發）→ 它會自動一併安裝 **Dart** 套件

---

## 7. 用 flutter doctor 診斷環境

`flutter doctor` 是 Flutter 內建的環境診斷工具，會告訴你哪些東西設定好了、哪些還有問題。

在終端機（Terminal）輸入：

```bash
flutter doctor
```

### 看懂輸出結果

```
Doctor summary (to see all details, run flutter doctor -v):
[✓] Flutter (Channel stable, 3.x.x)
[✓] Windows Version
[✓] Android toolchain - develop for Android devices
[✓] Chrome - develop for the web
[✓] Visual Studio - develop Windows apps
[✓] Android Studio (version x.x)
[✓] VS Code (version x.x)
[✓] Connected device (x available)
```

| 符號 | 意思 |
|------|------|
| ✅ `[✓]` | 這個項目設定完成，沒問題 |
| ⚠️ `[!]` | 有警告，建議修復但不一定影響運作 |
| ❌ `[✗]` | 有錯誤，需要解決 |

> 目標是讓 **Flutter、Android toolchain、Android Studio、VS Code** 都是 `[✓]`。

---

## 8. 建立你的第一個專案

### 方法一：使用 VS Code（圖形介面）

1. 按 `Ctrl + Shift + P`（macOS：`Cmd + Shift + P`）開啟命令面板
2. 輸入 `Flutter: New Project`，選取它
3. 選擇「**Application**」
4. 選擇你要儲存專案的資料夾（例如 `C:\Projects` 或 `~/Projects`）
5. 輸入專案名稱，例如 `my_first_app`（**注意：只能用小寫英文和底線，不能有空白或中文**）
6. 按 Enter，等待 VS Code 建立專案

### 方法二：使用命令列

```bash
# 切換到你想放專案的資料夾
cd C:\Projects

# 建立新專案
flutter create my_first_app

# 進入專案資料夾
cd my_first_app
```

---

## 9. 認識專案結構

建立完成後，你會看到以下資料夾結構：

```
my_first_app/
│
├── android/          ← Android 平台的原生設定（通常不需要動）
├── ios/              ← iOS 平台的原生設定（Mac 才能用）
├── lib/              ← ⭐ 你主要寫程式碼的地方！
│   └── main.dart     ← ⭐ 程式的入口點，從這裡開始
├── test/             ← 測試程式碼放這裡
├── pubspec.yaml      ← ⭐ 專案設定檔，管理套件依賴
└── README.md         ← 專案說明文件
```

### 最重要的檔案：`lib/main.dart`

打開它，你會看到 Flutter 自動產生的示範程式碼。先別怕，我們一行一行來看關鍵部分：

```dart
// 匯入 Flutter UI 套件（必備）
import 'package:flutter/material.dart';

// 程式的起點，就像 C 語言的 main()
void main() {
  runApp(const MyApp()); // 啟動 App
}

// 這是整個 App 的根元件
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      home: MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}
```

> 💡 **觀念：** 在 Flutter 裡，畫面上的所有東西都叫做 **Widget（元件）**。
> 文字是 Widget、按鈕是 Widget、整個畫面也是 Widget。就像積木一樣，一層一層疊起來。

---

## 10. 執行程式

### 確認模擬器或裝置已啟動

在 VS Code 右下角，你會看到一個裝置選擇器，例如：

```
sdk gphone64 x86 64 (android-x64)
```

如果顯示「No Device」，請先啟動 Android 模擬器（參考第 5 節）。

### 方法一：VS Code 執行（推薦）

按 `F5`，或點選選單 `Run` → `Start Debugging`

VS Code 會自動編譯並在模擬器上執行你的 App。

### 方法二：命令列執行

```bash
# 在專案資料夾內執行
flutter run
```

如果有多個裝置，它會問你要用哪一個，輸入對應的數字選擇。

### 第一次執行會比較慢

第一次編譯需要 1～3 分鐘，這是正常的。之後修改程式碼時，**Hot Reload** 功能會讓更新幾乎是即時的！

### 你應該看到這個畫面 🎉

模擬器上會出現一個畫面，顯示「You have pushed the button this many times:」和一個計數器。點擊右下角的浮動按鈕，數字會增加！

---

## 11. 修改你的第一行程式碼

讓我們來改一個簡單的地方，感受 **Hot Reload** 的魔力！

### 修改標題文字

找到 `lib/main.dart`，找到這一行：

```dart
title: 'Flutter Demo Home Page',
```

改成你想要的文字，例如：

```dart
title: '我的第一個 App！',
```

儲存檔案（`Ctrl + S`），然後：

**Hot Reload（熱重載）：** 按 `r`（在執行中的終端機）或按 VS Code 工具列的 ⚡ 圖示

畫面幾乎立即更新，**不需要重新啟動 App**！

### 修改計數器顏色

找到這一段：

```dart
floatingActionButton: FloatingActionButton(
  onPressed: _incrementCounter,
  tooltip: 'Increment',
  child: const Icon(Icons.add),
),
```

在 `FloatingActionButton(` 後面加上：

```dart
backgroundColor: Colors.red, // 改成紅色
```

儲存，Hot Reload，按鈕變紅色了！

---

## 12. 常見錯誤與解決方式

### ❌ `flutter` 指令找不到（not recognized）

**原因：** 環境變數沒設定好。

**解決：**
1. 確認 `flutter\bin` 路徑已加入 `Path` 環境變數
2. **重新開啟** 終端機（舊的終端機不會讀取新的環境變數）

---

### ❌ `flutter doctor` 顯示 Android toolchain 有問題

**解決：**

```bash
flutter doctor --android-licenses
```

全部輸入 `y` 接受授權即可。

---

### ❌ 模擬器開不起來 / 很慢

**原因：** 需要啟用 BIOS 的虛擬化技術（Virtualization / Hyper-V）。

**解決：**
1. 重開機進入 BIOS（通常按 `Del` 或 `F2`）
2. 找到「Intel Virtualization Technology」或「AMD-V」，設定為 **Enabled**
3. 儲存並重開機

或者，直接用 USB 連接實體 Android 手機代替模擬器。

---

### ❌ `Dart` 版本錯誤

**解決：** 確保你安裝的是最新穩定版 Flutter，舊版的 Dart 可能不相容：

```bash
flutter upgrade
```

---

### ❌ `pubspec.yaml` 套件安裝失敗

**解決：**

```bash
flutter pub get
```

如果還是失敗，嘗試：

```bash
flutter clean
flutter pub get
```

---

### ❌ Hot Reload 沒有反應

**解決：** 嘗試 **Hot Restart**（完整重啟但不重建）：

- 按 `R`（大寫）在終端機
- 或 VS Code 工具列的 🔄 圖示

---

## 13. 下一步學習資源

恭喜你！🎊 你已經成功安裝並執行了你的第一個 Flutter App！

以下是繼續學習的好資源：

### 官方資源（英文）

| 資源 | 連結 | 說明 |
|------|------|------|
| Flutter 官方文件 | https://docs.flutter.dev | 最完整的參考資料 |
| Flutter Codelabs | https://docs.flutter.dev/codelabs | 互動式教學，適合初學者 |
| Widget 目錄 | https://docs.flutter.dev/ui/widgets | 所有內建元件的說明 |
| DartPad | https://dartpad.dev | 線上練習 Dart 語法，不需安裝 |

### 建議學習路徑

```
第一週：熟悉 Dart 基本語法（變數、函式、類別）
    ↓
第二週：學習基本 Widget（Text、Column、Row、Container、Button）
    ↓
第三週：學習 StatefulWidget（讓畫面會動）
    ↓
第四週：學習頁面導航（Navigator）和 ListView
    ↓
之後：學習狀態管理（Provider 或 Riverpod）、連接 API
```

### 快速參考：常用指令

```bash
flutter create <專案名稱>    # 建立新專案
flutter run                  # 執行 App
flutter build apk            # 打包成 Android APK
flutter pub get              # 安裝套件
flutter pub add <套件名稱>   # 新增套件
flutter clean                # 清除快取（遇到奇怪錯誤時用）
flutter upgrade              # 升級 Flutter 到最新版本
flutter doctor               # 診斷環境
```

---

> 🌟 **最後的鼓勵：** 學習 Flutter 初期可能會遇到很多環境問題，這是每個開發者都經歷過的！遇到問題先用 `flutter doctor` 診斷，再去 [Stack Overflow](https://stackoverflow.com) 或 [Flutter GitHub Issues](https://github.com/flutter/flutter/issues) 搜尋錯誤訊息，通常都能找到解答。加油！💪

---

*文件版本：Flutter 3.x | 最後更新：2026 年 3 月*
