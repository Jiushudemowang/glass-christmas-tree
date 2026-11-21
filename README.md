# 玻璃雪球 · 粒子圣诞树

一棵封存在玻璃穹顶里的粒子圣诞树。体积雪在球内真实下落并响应光照，玻璃折射随视角弯曲；树、星河、五角星、烟花在粒子间平滑变形。配乐由 Web Audio 现场合成，零外部音频依赖。

单文件、零构建、无需安装任何东西。

## 在线体验

**https://jiushudemowang.github.io/glass-christmas-tree/**

## 本地运行

直接双击 `index.html` 也能看，但摄像头手势会失效。建议起一个本地服务：

```bash
python -m http.server 8000
```

然后打开 <http://localhost:8000/>，点击「开启魔法」。

摄像头只用于本地手势识别，画面不会上传；拒绝授权也完全可以体验。

## 操作

| 操作 | 效果 |
|---|---|
| ✊ 握拳 / 键盘 `1` | 圣诞树 |
| 🖐 张手 / 键盘 `2` | 星河 |
| ✌️ 比耶 / 键盘 `3` | 五角星 |
| 👌 捏合 / 键盘 `4` | 烟花 |
| 挥手 / 鼠标拖拽 | 旋转视角 |
| 键盘 `M` 或底部胶囊按钮 | 音乐开关 |

启动时自动播放音乐盒配乐，**Jingle Bells → Silent Night → We Wish You a Merry Christmas** 三首公有领域名曲轮播。

## 技术

- Three.js 0.169（WebGL，兼容性优先，非 WebGPU）
- 9000 粒子树 + 4200 体积雪粒子，GPU 顶点着色器形态插值
- 玻璃穹顶：`transmission` + `ior 1.5` + `clearcoat` 真实折射
- UnrealBloom 后处理 + 程序化十字星芒、螺旋彩灯、许愿光点、散景
- MediaPipe Tasks Vision 手势识别（失败时自动回退到鼠标/键盘）
- Web Audio 合成音乐盒音色 + 卷积混响

灵感来自 Forged.build 为保时捷做的 Holiday Snow Globe（WebGPU 体积雪），本站按其思路用 WebGL 重写。

## 许可

MIT
