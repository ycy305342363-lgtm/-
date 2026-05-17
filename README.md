# 记账本 - PWA 记账应用

一个支持 iPhone 快捷指令的个人记账网页应用。

## 功能特性

- 📝 快速记账：选择分类、输入金额，一键记录
- 📊 统计分析：按日/周/月查看收支统计、分类排行、趋势图表
- 🔍 搜索筛选：按分类、关键词搜索账单
- 📱 添加到主屏幕：体验接近原生 App
- 📅 快捷指令：通过 URL Scheme 支持 iPhone 快捷指令
- 💾 数据导出：支持导出 CSV 文件备份

## 使用方式

### 方式一：直接使用

1. 将整个文件夹上传到任意 Web 服务器（GitHub Pages、Vercel 等）
2. 用 iPhone Safari 打开网址
3. 点击分享按钮 → 添加到主屏幕

### 方式二：本地使用

1. 在电脑上安装任意 HTTP 服务器（如 Python）
2. 在 `D:/记账` 目录下运行：`python -m http.server 8000`
3. 确保手机和电脑在同一 WiFi 下
4. 用 iPhone Safari 打开 `http://电脑IP:8000`
5. 点击分享按钮 → 添加到主屏幕

## 快捷指令配置

### 快速记账快捷指令

1. 打开 iPhone「快捷指令」App
2. 点击右上角 **+** 创建新快捷指令
3. 添加以下操作：

**操作 1：文本**
```
记账本://add?amount=35&category=food&note=午饭
```

**操作 2：打开 URL**

4. 保存并命名（如"记账"）
5. 可以对 Siri 说"记账"来触发

### 语音记账快捷指令

1. 创建新快捷指令
2. 添加操作：

**操作 1：听写文本**
（让 Siri 听你说的话）

**操作 2：获取文本中的数字**
（提取金额）

**操作 3：文本**
```
记账本://add?amount=[数字]&category=food&note=[听写的文本]
```

**操作 4：打开 URL**

### 支持的分类参数

**支出分类：**
- `food` - 🍜 餐饮
- `transport` - 🚗 交通
- `shopping` - 🛒 购物
- `entertainment` - 🎮 娱乐
- `housing` - 🏠 住房
- `medical` - 💊 医疗
- `education` - 📚 教育
- `other` - 📌 其他

**收入分类：**
- `salary` - 💰 工资
- `bonus` - 🎁 奖金
- `investment` - 📈 投资
- `freelance` - 💼 兼职
- `other` - 📌 其他

## 数据存储

- 数据存储在浏览器 LocalStorage 中
- 卸载 App 或清除浏览器数据会丢失记录
- 建议定期使用"导出 CSV"功能备份

## 技术栈

- HTML5 + CSS3 + JavaScript
- PWA (Progressive Web App)
- LocalStorage 数据持久化
- URL Scheme 快捷指令集成
