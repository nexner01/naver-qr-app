# 네이버 QR코드 생성기 안드로이드 앱 (Naver QR Creator Android App)

`https://qr.naver.com/create` 페이지를 전체 화면 웹뷰(WebView)로 보여주는 안드로이드 앱 프로젝트입니다.
컴퓨터에 안드로이드 스튜디오(Android Studio)가 없어도 **GitHub Actions**를 통해 GitHub상에서 자동으로 APK를 빌드하고 다운로드받을 수 있도록 설정되어 있습니다.

---

## 📱 앱 특징
1. **전체 화면 웹뷰 (Full-screen WebView)**: 상단/하단 시스템 바를 숨긴 몰입형 전체 화면 UI.
2. **네이버 QR코드 생성 웹 완벽 지원**:
   - JavaScript, DOM Storage, Database 활성화
   - 이미지 첨부 및 파일 업로드 지원 (`WebChromeClient` + `FileChooser`)
   - 당겨서 새로고침 (`SwipeRefreshLayout`) 지원
   - 뒤로가기 버튼 처리 (`canGoBack` 검사)
3. **커스텀 앱 아이콘**: AI로 제작된 네온 글로우 스타일 QR 앱 아이콘 적용 (`mipmap-mdpi ~ xxxhdpi`).

---

## 🚀 GitHub Actions로 APK 빌드 및 다운로드 방법

1. **GitHub에 코드 푸시(Push)**:
   ```bash
   git init
   git add .
   git commit -m "Initial commit for Naver QR WebView App"
   git branch -M main
   git remote add origin https://github.com/사용자아이디/리포지토리이름.git
   git push -u origin main
   ```

2. **GitHub Actions에서 APK 다운로드**:
   - GitHub 리포지토리 페이지 상단의 **Actions** 탭으로 이동합니다.
   - 자동으로 실행 중이거나 완료된 **Build Android APK** 워크플로우를 클릭합니다.
   - 페이지 하단의 **Artifacts** 섹션에서 **`NaverQR-Debug-APK`**를 클릭하여 다운로드받습니다.
   - 압축 해제 후 나오는 `app-debug.apk` 파일(또는 스마트폰에 전송한 파일)을 안드로이드 기기에 설치하여 사용합니다.

---

## 🛠 Project Structure
```
receipt33/
├── .github/
│   └── workflows/
│       └── build.yml               # GitHub Actions 빌드 워크플로우
├── app/
│   ├── build.gradle.kts           # 앱 모듈 빌드 설정
│   └── src/
│       └── main/
│           ├── AndroidManifest.xml # 앱 권한, 액티비티, 테마 설정
│           ├── java/com/naver/qrmaker/
│           │   └── MainActivity.kt # 웹뷰 및 파일로드/뒤로가기 로직
│           └── res/               # 레이아웃, 커스텀 아이콘 및 스타일
├── build.gradle.kts               # 프로젝트 루트 빌드 설정
├── settings.gradle.kts            # 리포지토리 및 모듈 설정
├── gradlew                        # Linux/macOS용 Gradle 래퍼
├── gradlew.bat                    # Windows용 Gradle 래퍼
└── README.md
```
