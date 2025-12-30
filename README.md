# ⚡ CLI Power Tools: Mac 终端效率神器清单

> "为什么我要下载几百 MB 的软件，去完成一行命令就能做到的事？"

这是一个为 **macOS / Linux** 用户整理的命令行工具（CLI）精选集。这些工具免费、开源、极其强大，能够替代昂贵的付费软件，极大提升生产力。

**适用人群**：自媒体创作者、开发者、效率追求者。

---

## 🛠️ 前置准备

确保你的 Mac 已安装 **Homebrew**。如果没有，请先运行：

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

---

## 1. FFmpeg —— 媒体处理的“万物之神”

全球视频技术的基石。格式转换、压缩、提取音频，无所不能。

- **安装命令**：
  ```bash
  brew install ffmpeg
  ```

### 🔥 实战“一行流”：
- **秒转格式（无损，不重编码）**：
  `ffmpeg -i input.mkv -c copy output.mp4`
- **视频压缩（压缩到适合微信发送）**：
  `ffmpeg -i input.mp4 -vcodec libx264 -crf 28 output.mp4`
- **提取音频（视频变 MP3）**：
  `ffmpeg -i video.mp4 -vn audio.mp3`
- **提取视频中的第 00:00:10 到 00:00:20 片段**：
  `ffmpeg -i video.mp4 -ss 00:00:10 -t 00:00:10 -c copy cut.mp4`

---

## 2. ImageMagick —— 图片处理的“批处理之王”

如果你有 100 张图片要改尺寸或转格式，千万别用 Photoshop 一张张打开。

- **安装命令**：
  ```bash
  brew install imagemagick
  ```

### 🔥 实战“一行流”：
- **批量格式转换（当前目录下所有 PNG 转 JPG）**：
  `mogrify -format jpg *.png`
- **批量压缩尺寸（所有 JPG 缩放到 50%）**：
  `mogrify -resize 50% *.jpg`
- **降低图片质量（瘦身，质量降为 80%）**：
  `mogrify -quality 80 *.jpg`

---

## 3. Rclone —— 云存储的“瑞士军刀”

将 Google Drive, OneDrive, S3 等网盘挂载为本地硬盘，或在命令行高速同步。

- **安装命令**：
  ```bash
  brew install rclone
  ```

### 🔥 实战“一行流”：
- **配置向导（第一次使用必须运行）**：
  `rclone config`
- **将 VPS 文件夹备份到 Google Drive**：
  `rclone copy /my/local/folder remote:backup_folder`
- **列出网盘里的文件**：
  `rclone ls remote:backup_folder`

---

## 4. Pandoc —— 文档转换的“变形金刚”

格式转化神器。支持 Markdown, HTML, Word (docx), PDF, LaTeX 等互转。

- **安装命令**：
  ```bash
  brew install pandoc
  ```

### 🔥 实战“一行流”：
- **Markdown 转 Word（写简历神器）**：
  `pandoc resume.md -o resume.docx`
- **网页转 Markdown（保存资料神器）**：
  `pandoc https://example.com -o article.md`
- **Markdown 转 PDF**（需安装 latex 引擎）：
  `pandoc input.md -o output.pdf`

---

## 5. TLDR —— 拯救记性的“作弊条”

`man` 手册太长看不懂？TLDR (Too Long; Did not Read) 只给你看最常用的例子。

- **安装命令**：
  ```bash
  brew install tldr
  ```

### 🔥 实战“一行流”：
- **忘了 tar 命令怎么解压？**
  `tldr tar`
- **忘了 git 怎么提交？**
  `tldr git commit`

---

## 🌟 特别收录：yt-dlp (下载神器)

虽然你可能已经装了，但它值得作为核心工具记录在案。全网视频下载（YouTube, Bilibili, Twitter, TikTok）。

- **安装命令**：
  ```bash
  brew install yt-dlp
  ```

### 🔥 常用命令速查：
- **下载最佳画质 MP4**：
  `yt-dlp -f "bv+ba/b" --merge-output-format mp4 "URL"`
- **下载音频 (MP3)**：
  `yt-dlp -x --audio-format mp3 "URL"`
- **借用浏览器登录 (解决 B站/Twitter 限制)**：
  `yt-dlp --cookies-from-browser chrome "URL"`

---

## 📝 结语

掌握这些工具，你的终端就是一个强大的**自动化工厂**。
建议将常用的命令保存为 `alias`（别名），效率翻倍。
```

***

### 只要你把上面这一大段粘贴进去，点击 GitHub 的 "Preview"（预览）按钮，你就会发现：
*   **#** 变成了大黑标题。
*   **-** 变成了圆点列表。
*   **```bash ... ```** 变成了那个灰色的代码框，里面的命令是可以复制的。

快去试试吧！
