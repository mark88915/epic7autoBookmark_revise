# 此為 Fork 專案

原專案：https://github.com/steven010116/epic7autoBookmark
原作者已退坑(專案已經不維護)，後續有新問題或 Bug 可以在此專案上提 Issue 或發 PR 進行修正 (但不接受提需求)

> 此專案的修正為修正因為網路延時造成可能漏買書籤的 bug、優化代碼、移除派遣內容，但基本邏輯與代碼與原專案相同，UI、以及使用方式也都相同，若有疑慮仍可以繼續使用舊版

# epic7autoBookmark

第七史詩刷商店的小工具

![image](https://github.com/steven010116/epic7autoBookmark/assets/24381832/526e78b9-df97-4500-9758-55f514eed883)

目前這個版本不支援國服，如果有國服的使用需求可以參考這位大佬維護的專案 [epic7auto](https://github.com/Wrong-pixel/epic7auto)

## 一、環境

0. windows10 / MacOS (Apple 晶片也行)
1. Bluestack / Bluestack Air (Mac) / 任一可啟用 Adb 的模擬器
   i. 版本：理論上全版本通用  
   ii. 顯示：橫向、1920x1080、240DPI or 320DPI
2. 第七史詩  
   i. 裝置詳細設定和遊戲詳細設定最好都不勾，如果覺得畫面太醜，高畫質套件測試過也是能正常運行  
   ii. 推薦：只勾高級設定
3. python 3.9.6 ~ 3.9.10 中任一版本
4. config.json
   ![預覽](https://i.imgur.com/2sAobaw.png)  
   i. adb_addr 填 adb 路徑  
   ii. e7_language 填 e7 裡的語系(繁中: zh-TW, 簡中: zh-CN, 英文: en-US)

   > 繁中版以外語系請參考繁中語系的圖片透過模擬器進行截圖並替換掉對應語系的圖片，否則辨識會失敗，若有特殊需求可以發 Issue 詢問

## 二、使用方式

### Windows

先將 bluestack 和第七史詩的設定調整的如上方環境相同。  
adb 功能在設定=>進階=>Android 調試橋(ADB)，勾選後會看到路徑。  
英文路徑在 settings=>Advanced=>Android Debug Bridge(ADB)。

![預覽](https://i.imgur.com/eSamCR3.png)

確認第七史詩語系是不是與 config.json 裡使用的相同(預設為繁中)。

0. 綠色按鈕 code > download zip 整包下載後解壓縮放在同一個資料夾下，路徑最好為英數避免有其他問題。
1. 參考上面的環境，確認 config.json 內的參數都是對的。
2. 開啟遊戲，進到秘密商店後，畫面會長得像下面這樣。

![預覽](https://i.imgur.com/KxeSpWM.png)

3. 安裝 python 並在安裝時將 python 加進 PATH(環境變數)
4. 打開 cmd(命令提示列)並移動到資料夾底下然後依序執行以下指令

```
python -m venv venv (若環境變數為python3則用python3替代python)
venv\Scripts\activate
pip install -r requirements.txt
python main.py
```

---

若要打包為執行檔(.exe)

```
pip install pyinstaller
pyinstaller -F -w -i main.ico main.py
```

### MacOS (不打包，以開發模式進行)

1. 裝 bluestack air 並在模擬器內設定啟用 adb 然後將解析度調到 1920\*1080
   > 這一步同安卓，mac 版的模擬器 2G+遊戲 200 Ｍ請自行評估容量
2. homebrew 裝 adb 以及 python 3.9.6~3.9.10 之間任一版本
   > 需將 python 設定環境變數
3. 綠色按鈕 code > download zip 整包下載後解壓縮放在同一個資料夾下，路徑最好為英數避免有其他問題。
4. 打開 terminal(終端機)並移動到資料夾底下然後依序執行以下指令

```
python -m venv venv (若環境變數為python3則用python3替代python)
source venv/bin/activate
pip install -r requirements.txt
python main.py
```

## 三、特別感謝

Raven9527 - 自動點擊派遣功能

## 四、更新資訊

2025/07/12 - 優化代碼，將重複性代碼抽共用並提高可讀性、修正因為網路延時造成可能漏買書籤的 bug、移除派遣相關內容、更新繁中版圖片、更新 README.md
