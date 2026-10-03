# 薄荷苏打

清凉薄荷色系的亮色主题合集——4 套色板，Claymorphism 软萌风。

## 这是什么

一只**纯数据插件**：没有一行界面代码，`contributes.themes` 指过去，色板就进了主题列表。装上是给 LinkDesk 多加几套配色，卸掉它们就消失，其他插件毫无感觉。

- 插件 ID：`theme-mint-soda`
- 系统类型：亮色（light）
- 色板：薄荷苏打 Mint Soda · 薄荷冰露 Mint Dew · 海盐薄荷 Sea Salt Mint · 青柠薄荷 Lime Mint
- 怎么换：设置 → 外观 → 主题

## 结构

```
plugin.json               声明（contributes.themes）
themes/mint-soda.json     色板——一套文件里装 4 个 colorway
```

## 作者备忘：图标颜色与两个「玻璃旋钮」

- **图标颜色主题驱动不了**：colorway 里写 `icon-active` **无效**（壳从不读它，本版已删）——图标墨色由壳按当前主题的**文字色**自动派生，作者无需也无法为图标指定颜色。`icon-inactive` 仍然有效，但它只服务**欢迎页「非激活图标」**的用色。
- **colorway 键是逐键直通的**：键名写错**不报错、也不生效**（没有白名单替你挡），新增键前先查壳的外观变量契约。
- **「玻璃感」有两个旋钮**：主题配方里的 `glass.opacity` = tint 盖片（这只主题自带的玻璃底色有多厚）；用户设置里的 `app.glassOpacity` = 玻璃表面 color-mix 比例（用户想让所有玻璃表面透多少）。两者相乘，不是同一个东西。
- **`bg-*` 这组背景键建议写全**：缺的键会从锚点派生，观感未必是你要的。
