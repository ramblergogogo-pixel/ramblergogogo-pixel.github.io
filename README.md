# 三分化训练计划 · GitHub Pages 版

这是已经整理好的静态网页/PWA版本，**不用 Node.js、不用 npm、不用构建**，直接丢到 GitHub Pages 就能跑。

## 最简单部署方法

1. 在 GitHub 新建一个仓库，例如：`fitness-plan`
2. 把这个压缩包里的**所有文件**上传到仓库根目录
3. 打开仓库：
   `Settings → Pages`
4. 在 `Build and deployment` 里选择：
   - Source：`Deploy from a branch`
   - Branch：`main`
   - Folder：`/(root)`
5. 点击 `Save`

等待几十秒到几分钟后，GitHub 会给你一个地址，通常类似：

`https://你的用户名.github.io/fitness-plan/`

## iPhone 添加到桌面

用 Safari 打开上面的 GitHub Pages 地址：

`分享 → 添加到主屏幕`

之后就可以像普通 App 一样从桌面启动。

## 数据保存

训练重量、完成打勾、体重、训练备注等，默认保存在手机浏览器的 `localStorage`。

建议定期使用：

`设置 → 导出备份`

保存 JSON 备份。

## 更新版本

以后如果修改 `index.html`，重新上传覆盖即可。

本版本的 Service Worker 会优先获取新内容，并自动清理旧缓存，比普通离线缓存更适合 GitHub Pages 更新。

## 文件说明

- `index.html`：应用主体
- `manifest.webmanifest`：PWA 配置
- `sw.js`：离线缓存 / 更新
- `icon-192.png`、`icon-512.png`：桌面图标
- `.nojekyll`：让 GitHub Pages 原样发布静态文件

## 新增：每餐食物克数

饮食页现在会根据当天 39 天碳循环目标和当前体重，自动给出：

- 早餐 / 午餐 / 加餐 / 晚餐的实际食物克数
- 鸡蛋 + 蛋清、鸡胸、牛肉、虾、三文鱼、希腊酸奶的蛋白质替换量
- 米饭、面、土豆、燕麦、全麦面包、香蕉、苹果的主食/碳水替换量
- 每餐蔬菜量、全天水果量以及食用油的粗略安排
- 肉类/米饭等按熟重，燕麦按干重，页面中已标注

食物营养值是便于执行的近似换算，不同品牌和烹饪方式会有误差。
