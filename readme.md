<h4 align="right"> 
<a href="README_cn.md">簡體中文</a> 
<a href="README.md" style="margin: 0 10px;" >English</a> 
<span href="README_tw.md">繁體</span>
</h4>  
<p align="center">
    <img src="https://raw.githubusercontent.com/Paulsxb/StageX/refs/heads/main/Logo_animat.svg" width=400/>
</p>
<h1 align="center">StageX</h1>  
<p align="center"><strong>向 Watchout 致敬，入門級多媒體播控軟件 StageX</strong>
</p>

<p align="center">
    <a href="https://github.com/Paulsxb/StageX/releases">
        <img src="https://img.shields.io/github/v/release/Paulsxb/StageX?style=flat-square&logo=github&color=blue" alt="Release">
    </a>
    <a href="https://github.com/Paulsxb/StageX/releases">
        <img src="https://img.shields.io/github/downloads/Paulsxb/StageX/total?style=flat-square&logo=github" alt="Downloads">
    </a>
    <a href="https://github.com/Paulsxb/StageX/stargazers">
        <img src="https://img.shields.io/github/stars/Paulsxb/StageX?style=flat-square&logo=github" alt="Stars">
    </a>
    <a href="https://github.com/Paulsxb/StageX/network/members">
        <img src="https://img.shields.io/github/forks/Paulsxb/StageX?style=flat-square&logo=github" alt="Forks">
    </a>
    <img src="https://img.shields.io/badge/Qt-6.x-41CD52?style=flat-square&logo=qt" alt="Qt Version">
    <img src="https://img.shields.io/badge/Platform-Windows-0078D4?style=flat-square&logo=windows" alt="Platform">
    <a href="https://github.com/Paulsxb/StageX/blob/main/LICENSE">
        <img src="https://img.shields.io/github/license/Paulsxb/StageX?style=flat-square" alt="License">
    </a>
</p>

<div align="left">StageX 是壹款輕量化的舞台播控工具，面向小型發布會、培訓會、教學場景，支持視頻、圖像、PDF、網頁及 PPT 五種媒體格式
     的外接屏播出控制。 </div>  
<br>

> 痛點😅：壹次偶然的機會，朋友要開壹個小型的個人演唱會，讓我負責播控。壹共20首4K的高清視頻，連續播放。我想把視頻嵌入PowerPoint，但是20個4K的視頻文件啊，PPT只能內嵌視頻，最終的PPT文件會有多大？還能跑的起來嗎？我又嘗試壹些視頻播放軟件，但是歌曲和歌曲之間的中場還需要切換演唱會背景、開場前還有循環播放的暖場視頻（歌曲視頻是單次播放），同時考慮到視頻與視頻之間的無縫切換，突然，我就萌生了要開發壹款入門級的簡單播控軟件……

## 軟件亮點

-   💎 5種多媒體源支持：視頻、圖片、PDF、網頁、PowerPoint
-   🎬️ 通過ACT幕的概念，將各種媒體文件串聯並播放
-   🎥 視頻支持：MP4 / MKV / AVI / M4V / TS / MOV
-   🖼️ 圖片支持：PNG / JPG / JPEG / BMP / GIF / SVG / WebP / 靜態SVG
-   💻️ PowerPoint 支持：PPTX / PPT。不是截圖渲染，而是完美支持PPT原生動畫
-   🎚️ 配備專業調音台模塊，讓導播人員全程掌控多視頻的音響度
-   📑 支持PDF單頁全屏或最大化顯示，並支持翻頁.
-   🛜 支持在線網站（包括 Youtube 等需要驗證登錄的網站），同時也支持本地網頁.
-   🌍️ 多語言支持：簡體、繁體、英文.
-   ⌨️ 全局鍵盤鈎子：支持USB及藍牙翻頁器控制，支持鍵盤 Page Up/ Down 導播控制，不搶焦點
-   📺️ 雙屏模式：主屏控制端 + 外屏純淨播出端（投影 / LED 牆 / 副屏）
-   💯 UI 設計參考剪映和OBS，界面簡潔，易于上手

<img src="https://raw.githubusercontent.com/Paulsxb/StageX/refs/heads/main/Stage_UI.png" width="100%" style="text-align: center"/>

## 軟件說明

-   前往 [Releases](https://github.com/Paulsxb/StageX/releases) 頁面下載最新安裝包.
-   本軟件需要ffmpeg、VLC、Office等環境支持，內存在8G以上，如果是4K甚至以上視頻，建議16G內存以上
-   此版本爲天使嘗鮮版，最多支持10個ACT幕
-   本軟件爲閉源軟件。詳見 LICENSE 文件（隨安裝包附帶）.
-   如有問題或建議，歡迎來信：<a href="mailto:paulsxb@gmail.com?subject=StageX_Feedback" target="_blank">paulsxb@gmail.com</a>

## 應用場景

### 場景壹：婚宴、生日派對、主題活動等

將多個視頻和圖片串聯起來，通過翻頁器直接控制播放

### 場景二：培訓會、分享會

以PPT文件爲主，但不再需要啓動PowerPoint，直接通過StageX軟件控制PPT的完美播放，所有PPT內嵌效果及動畫均能複現。並且還能播放視頻、圖片甚至是網頁端的操作演示。通過手中的翻頁器，主講人自己就能操控全程演示。每壹個ACT幕還能單獨添加備注作爲提示。

### 場景三：培訓及分享會小型活動、或發布會

同樣以PPT文件爲主，把需要展示的圖像、視頻包括PDF認證或調研文檔直接展示，除了主持人或發言人可以自行操控外，導播台的人員也能協助控制。在播放視頻、PPT或PDF時，導播員可以在本機上直觀地看到視頻文件當前播放時間，還有多久播放結束？PDF和PPT還有幾頁？整個播放過程盡在掌控之中。

## 支持 StageX

💖 如果StageX對妳的生活和工作有幫助，妳喜歡它的話，也請支持StageX，給我壹點鼓勵和認可，非常感謝！

<table style="text-align:center; width: 400px; border-collapse: collapse; border-spacing: 0; border: none;">
    <tr>
        <td style="padding: 0; margin: 0; border: none;"><img src="https://media.giphy.com/media/513lZvPf6khjIQFibF/giphy.gif"/></td>
        <td style="padding: 0; margin: 0; border: none;"><a href="https://ko-fi.com/stagex"><img src="https://raw.githubusercontent.com/Paulsxb/StageX/refs/heads/main/Buymeacoffee.png" width=200/></a></td>
    </tr>
</table>

## 開發日誌

| 版本 | 日期 | 內容 |
|------|------|------|
| v0.5.6 | 2026-06-02 | 色彩濾鏡（原始/黑白/紅綠藍濾 + 亮度/對比/飽和/色相） |
| v0.5.5 | 2026-06-02 | 裁切濾鏡 + 三濾鏡組合實時聯動 |
| v0.5.3 | 2026-06-02 | 縮放濾鏡（自適應/實際/拉伸/橫向/縱向/平鋪） |
| v0.5.2 | 2026-06-02 | 位置濾鏡（畫布左上角原點，X/Y像素偏移） |
| v0.5.1 | 2026-06-02 | PPT縮略圖文字顯示 + HighDPI獨立縮放 + CJK字體 |