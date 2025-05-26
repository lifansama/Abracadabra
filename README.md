# Abracadabra 魔曰

<div align=center>
<img src="https://github.com/user-attachments/assets/4c6544fe-166b-4572-acd6-cd1d6d3b4ca0" width="20%" height="20%">
</div>

<div align=center>
<h3>Abracadabra 魔曰</h3>

<h3>下一代文本加密工具</h3>
</div>

<div align=center>

[<img src="https://img.shields.io/badge/license-AIPL%201.1-yellow"/>](LICENSE.md)
![JavaScript](https://img.shields.io/badge/lang-JavaScript-orange)
![WASM](https://img.shields.io/badge/binary-WASM-b33bb3)

[<img src="https://img.shields.io/github/v/release/SheepChef/Abracadabra?color=00aaff"/>](https://github.com/SheepChef/Abracadabra/releases/latest)
[<img src="https://img.shields.io/github/actions/workflow/status/SheepChef/Abracadabra/node.js.yml?branch=main&label=%E6%9E%84%E5%BB%BA"/>](https://github.com/SheepChef/Abracadabra/actions/workflows/node.js.yml)
![GitHub Repo stars](https://img.shields.io/github/stars/SheepChef/Abracadabra)

</div>

<div align=center>

[<img src="https://img.shields.io/badge/立刻使用-ffd91c?logo=cloudflarepages&style=for-the-badge&logoColor=000000" width="170"/>](https://abra.halu.ca/)
[<img src="https://img.shields.io/badge/下载插件-8a54ff?logo=googlechrome&style=for-the-badge&logoColor=ffffff" width="170" />](#浏览器插件)

[<img src="https://img.shields.io/badge/前端源码仓库-9a10b5?style=for-the-badge" width="120" />](https://github.com/SheepChef/Abracadabra_demo)
[<img src="https://img.shields.io/badge/贡献压缩字典-54ffac?style=for-the-badge" width="120" />](https://forms.gle/BBD5McqU6Bws6hiw6)
[<img src="https://img.shields.io/badge/更新频道-0970ba?logo=telegram&style=for-the-badge&logoColor=ffffff" width="118" />](https://t.me/abracadabra_cn)

</div>

**Abracadabra(魔曰)** 是一个安全高效的文本加密工具，对任意给定数据进行加密处理。完全开源，易于部署，易于使用。

---

✨ 查阅 [**快速使用**](#快速使用) 一节，以快速开始使用/部署本项目。  
✨ 查阅 [**细节和使用指南**](https://github.com/SheepChef/Abracadabra/blob/main/USAGE.md) 以深入了解本项目的细节。  

👉 查阅 [**开放源代码许可**](#开放源代码许可) 一节，了解本项目的依赖项和许可证。

## 特性

- **仿真，使用文言语法句式**。
- 开源，所有源代码公开可查。
- 随机，加密结果具有随机性。
- 安全，AES256 + 三重转轮混淆。
- 双模式，同时支持仿真加密和传统加密。

###  **古文仿真：崭新的加密方案**

> 鹏彰于物，不必奏也。捷天谨走，城光益添，和人弥任，铃夜皆写，呈雨以登铃。
>
> 尝见寒裳，恭飞静星之光，可风者悦。此曲有快林雅木，近局怡鲤。骏冰之庭，写之林而筑之心也。夏非成而返之者，孰请无楼。南天之梦，游之物而度之月也。铃曰，何惠之需？写请与其心，而笑可振以镜者，林也。今之报者，亦将有听于此鹤，不请定也。

构造高仿真文言文，**参考《古文观止》《经史百家杂钞》《古文辞类纂》等古代典籍。**  
加密强度不变，但引入更复杂的组句/语法选择机制，将密码学与中国古典语言学相融合。

密文高度随机，支持用户自定义随机性和文本风格偏好，打造前所未有的跨文化数字加密方案。

## 快速使用

请查阅 [**部署指南**](DEPLOY.md) 来了解详细使用方法。

旧的 C++ 版本已被废弃，不再受后向兼容维护。

### JavaScript

使用 npm 下载 Abracadabra 库。

你也可以前往 Release 页面直接下载Js文件。

```shell
npm install abracadabra-cn
```

然后，在项目中引入库文件

```javascript
import { Abracadabra } from "abracadabra-cn";
```

### WebAssembly

前往 Release 下载编译好的 WebAssembly 文件。

然后，使用 [**wasmtime**](https://github.com/bytecodealliance/wasmtime) 来调用它。

```shell

echo '{"method":"NEXT","mode":"ENCRYPT","inputType":"TEXT","outputType":"TEXT","input":"愿青空的祝福，与我的羽翼同在","key":"ABRACADABRA","q":true,"r":50,"p":false,"l":false}' | wasmtime abracadabra-cn.wasm

```

本项目的 WebAssembly 模块使用 [**Javy**](https://github.com/bytecodealliance/javy) 编译而来，方便在 C++、Rust、Go 等语言中调用，**不推荐**在类似 Python、 Java、Node.js 的解释器中调用。

要调用本 WebAssembly 模块，需要使用尚在预览状态的 [**WASI**](https://github.com/WebAssembly/WASI)，目前仅有 wasmtime 提供了最完整的 WASI 支持，但它在各个语言的实现并不一致，具体请见 [**部署指南**](DEPLOY.md)。

### 静态页面 / 前端源码

本项目有自动托管在Cloudflare Pages的静态页面可供直接使用。

如果你想自行快速部署这个静态页，可以在Release中下载快速部署文件包。若要自行编译或修改，请前往前端源代码仓库。

浏览器插件和油猴脚本的源码同样在前端源代码仓库，分别位于 crx 和 userscript 分支。

[<img src="https://img.shields.io/badge/静态页面-ffd91c?logo=cloudflarepages&style=for-the-badge&logoColor=000000" width="130"/>](https://abra.halu.ca/)
[<img src="https://img.shields.io/badge/前端源码-9a10b5?style=for-the-badge" width="103" />](https://github.com/SheepChef/Abracadabra_demo)

### 浏览器插件

浏览器插件基于本项目的 JavaScript 实现。

已上架 **Chrome WebStore**, **Edge 加载项** 和 **Firefox 扩展**。

如果不方便访问Chrome插件商店，也可以访问Edge插件商店，和Firefox扩展商店。

[<img src="https://img.shields.io/badge/Chrome 商店-8a54ff?logo=chromewebstore&style=for-the-badge&logoColor=ffffff" width="171" />](https://chrome.google.com/webstore/detail/jgmlgdoefnmlealmfmhjhnoiejaifpko)
[<img src="https://img.shields.io/badge/MSEdge 商店-8a54ff?logo=data:image/svg%2bxml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyMyAyMyI+CiAgICA8cGF0aCBmaWxsPSIjZjNmM2YzIiBkPSJNMCAwaDIzdjIzSDB6Ii8+CiAgICA8cGF0aCBmaWxsPSIjZjM1MzI1IiBkPSJNMSAxaDEwdjEwSDF6Ii8+CiAgICA8cGF0aCBmaWxsPSIjODFiYzA2IiBkPSJNMTIgMWgxMHYxMEgxMnoiLz4KICAgIDxwYXRoIGZpbGw9IiMwNWE2ZjAiIGQ9Ik0xIDEyaDEwdjEwSDF6Ii8+CiAgICA8cGF0aCBmaWxsPSIjZmZiYTA4IiBkPSJNMTIgMTJoMTB2MTBIMTJ6Ii8+Cjwvc3ZnPg==&style=for-the-badge&logoColor=ffffff" width="170" />](https://microsoftedge.microsoft.com/addons/detail/abracadabra-%E9%AD%94%E6%9B%B0/kfkmhdcahjblddpkkmnjeppmfmfoihkb)
[<img src="https://img.shields.io/badge/Firefox 商店-8a54ff?logo=firefoxbrowser&style=for-the-badge&logoColor=ffffff" width="174" />](https://addons.mozilla.org/zh-CN/firefox/addon/abracadabra-%E9%AD%94%E6%9B%B0/)

> **提示：Edge 插件商店的上架审核速度十分缓慢，因此更新速度也更慢。不推荐从Edge商店下载本插件。**

### Android 客户端

本项目的 Android 客户端完全在 WebView 中静态运行。  

![image](https://github.com/user-attachments/assets/0f3b1c92-8853-4c70-8ef2-58630769beda)

APK使用HBuilderX自动打包，**完全离线运行，没有自动更新等配套功能**。

功能和界面均和前端静态网页没有差异。  

APK文件可以 [**在 Release 中下载**](https://github.com/SheepChef/Abracadabra/releases/latest)

## 细节概要

请查阅 [**细节和使用指南**](https://github.com/SheepChef/Abracadabra/blob/main/USAGE.md) 了解更多。

[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/SheepChef/Abracadabra)

### 加解密过程

```
明文 -> 压缩 -> AES-256-CTR -> Base64 -> 三重转轮 -> 映射汉字 -> 组句(仅仿真加密时) -> 密文

密文 -> 解仿真(仅仿真加密) -> 转轮逆映射 -> Base64 -> AES-256-CTR 解密 -> 解压缩 -> 明文
```

### 映射表

Abracadabra 以最常用的 3000 个汉字为密本，对大小写拉丁字母，阿拉伯数字和部分符号进行映射。

密表为纯人工编纂，没有让人眼花缭乱的生僻字。

映射表公开可查，查阅 [**映射表(传统)**](https://github.com/SheepChef/Abracadabra/blob/main/src/javascript/mapping.json) 或者 [**映射表(仿真)**](https://github.com/SheepChef/Abracadabra/blob/main/src/javascript/mapping_next.json) 以了解密本的全貌。

### AES-256-CTR

核心安全性由久经考验的 AES 加密算法提供，采用无填充的AES-256-CTR，节省密文长度。

AES 加密密钥和转轮密钥是同一个，均采用哈希值。

### 三重转轮混淆

模拟古老的转轮，每次加密均会对密本映射进行偏移。

简言之，程序会将给定的密钥进行 SHA256，得到一个长度为 32 的 Uint8_t 数组。

这个数组中的每个数字，都会决定三重转轮中每个转轮每次迭代的转动方向和转动距离。

数字/符号，字母分别拥有一套转轮，即总共六个转轮，改变密钥相当于更换一套完全不同的转轮。

转轮显著增加了 Base64 密文的安全性，查阅 [**Issue#30**](https://github.com/SheepChef/Abracadabra/issues/30) 来了解转轮的详细运行机制。

### 随机性

在映射为汉字的时候，每个字母/数字/符号均有多种可能性，完全随机选择。

这显著增强了密文的安全性，使得各种攻击难以奏效。

## 比较

```
明文：Abracadabra

魔曰(仿真)：铃有将报，局有竟然。故探盈声者，当度青莺之静云。非木也，琴与树换，振棋以至雁。
魔曰(传统)：困句夏之全玚凪斋或骏琅咨兆咩谜理金说宙银歌舒

熊曰：呋食性類啽家現出爾常肉嘿達嗷很
佛曰：諸南隸僧南降南吽諸陀南摩隸南僧南缽南薩咤南心彌嚴迦聞婆吽願南眾南色南兜南眾南如婆如南
社会主义：自由民主公正文明法治文明公正民主公正和谐公正民主公正自由公正民主公正文明法治文明公正民主
兽音：~呜嗷嗷嗷嗷呜呜啊呜嗷呜嗷呜呜~嗷啊呜啊嗷啊呜嗷呜~呜~嗷~呜呜嗷嗷嗷嗷嗷嗷呜啊嗷呜啊呜嗷呜呜~嗷啊嗷啊嗷啊呜嗷嗷~~~嗷~呜呜嗷嗷嗷嗷嗷嗷呜啊嗷呜呜呜嗷呜呜~呜啊呜啊嗷啊呜嗷嗷~嗷啊
火星文：（不支持英文）

```

## 鸣谢

感谢 [**Unishox2**](https://github.com/siara-cc/Unishox2) 提供高效的短文本压缩方案。

感谢贡献 PR 和参与测试的所有人。

## 开放源代码许可

**⚠️本项目受私有许可证保护**，使用本项目则默认视为同意并遵守相关条款。禁止将本项目用于非法用途。  
👉 查阅 [**AIPL-1.1 许可**](LICENSE.md) 来了解详细信息，也可以前往 [**#87**](https://github.com/SheepChef/Abracadabra/issues/87) 查阅简单介绍。  

---

以下是本项目的依赖项：

- [**Unishox2**](https://github.com/siara-cc/Unishox2) 短字符串压缩实现 _©Siara-cc_, **Apache-2.0** License.
- [**crypto-js**](https://github.com/brix/crypto-js) AES加密实现 _©Jeff Mott/Evan Vosberg_, **MIT** License.
- [**pako**](https://github.com/nodeca/pako) GZIP压缩实现 _©Vitaly Puzrin/Andrei Tuputcyn_, **MIT** License.
- [**js-base64**](https://github.com/dankogai/js-base64) Base64编码工具实现 _©Dan Kogai_, **BSD-3-Clause** License.
- [**mersenne-twister**](https://github.com/boo1ean/mersenne-twister) 梅森旋转算法实现 _©Makoto Matsumoto/Takuji Nishimura_, **BSD-3-Clause** License.

本项目许可证与所有依赖项的许可证兼容。

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=SheepChef/Abracadabra&type=Date)](https://star-history.com/#SheepChef/Abracadabra&Date)
