# imagezip

前端性能图像（jpg、png、gif）压缩工具。

**为什么要做图片压缩**
> Google官方的最佳实践中关于图片优化有下面这样一段描述：对于网页来说，在所下载的字节数中，图片往往会占很大比例。因此，优化图片通常可以卓有成效地减少字节数和改进性能：浏览器需要下载的字节数越少，对客户端带宽的争用就越少，浏览器下载内容并在屏幕上呈现内容的速度就越快。

## Install

```
# 使用npm安装
npm install imagezip -g 

# 使用yarn安装
yarn global add imagezip
```

## Usage

### 基本使用

```bash
➜  imagezip --help
Usage: index [options]

Options:
  -V, --version         output the version number
  -Q --quality [0~100]  JPG压缩质量 (default: "80")
  -I --input [folder]   原始图片目录 (default: "./")
  -O --output [folder]  压缩图片存放目录 (default: "./")
  -h, --help            output usage information
```

### 基本功能

```bash
# 进入图片存放目录
cd assets

# 压缩当前目录所有图片
imagezip

# 压缩当前目录单个图片
imagezip demo.jpg

# 压缩 /Users/furic/www/assets/ 目录中的 demo.jpg
imagezip /Users/furic/www/assets/demo.jpg

# 压缩多个图片
imagezip demo1.jpg demo2.png demo3.gif

# 压缩当前目录所有图片并将压缩后的图片保存到 当前目录下的 minify 目录
imagezip --output minify

# 压缩 /Users/furic/www/assets 目录下的所有图片 并保存到 /Users/furic/www/minify目录
imagezip --input /Users/furic/www/assets --output /Users/furic/www/minify
```
> 若不设置`--output`参数，压缩后的图片将覆盖原图片。

### 使用示例

```bash
➜  cd assets
.
├── hsy.child.jpg
├── hsy.loading.gif
└── hsy.png

➜  imagezip
✔ hsy.child.jpg (saved 611 kB to 330 kB - 281 kB/46%)
✔ hsy.loading.gif (saved 445 kB to 423 kB - 21.9 kB/4.9%)
✔ hsy.png (saved 1.4 MB to 629 kB - 768 kB/55%)
Minified 3 images (saved 2.45 MB to 1.38 MB - 1.07 MB/43.7%)
```
结果说明：
> (saved 原图大小(kB) to 压缩后图片大小(kB) - 压缩大小(kB) / 压缩率%)