# 更新日志

## v1.0.7（2026-10-01）

- **去掉双语音译名（「我不要双语了」）**：字面量只留中文原文（中文界面显示中文），英文界面由壳过 `t()` 显示本仓字典里的英文。作者把译名写进字面量（`"薄荷苏打 Mint Soda"`）时，中文界面会中英混排——这条病只能靠「字面量纯中文 ＋ 译名住字典」治。
- 四个配色名全部纯中文化；英文译名沿用本仓详情说明里既有的那套（Mint Frost / Sea-Salt Mint / Lime Mint / Mint Soda），口径与旧双语字面量一致。
- **判据随 SDK 下发**：`@linkdesk/plugin-sdk` → **^0.1.64**——`npm run verify` 第 ⑧ 段的判域**扩到主题数据文件里的名字**（`contributes.themes[].label` ＋ 数据文件 `name`/`colorways[].name`，`@linkdesk/plugin-sdk/own-dict-coverage`）：名字同样「谁的仓谁译文」，双语字面量在旧判据里溜得过去、在新判据里当场红。
## v1.0.6（2026-09-30）

- **自有翻译归位（E6#161「谁的仓谁译文」）**：本仓 2 条可渲染文案的英文译名住进**本仓字典** `i18n/en.json`（新增 2 条） ＋ `contributes.i18n` 声明——不再依赖 `lang-defaults` 代管：文案在本仓声明、译名却在别的仓的字典里，本仓加一条声明那只仓无从跟上（跨仓追不上）。译名取值：池里现成的照抄（同键同值 ⇒ 按 E6#161「同值覆盖不出声」规则运行时零变化），池里没有的 2 条新写。
- **判据随 SDK 下发**：`@linkdesk/plugin-sdk` ^0.1.19 → **^0.1.61**——`npm run verify` 第 ⑧ 段「自有字典覆盖度」（manifest 渲染串缺口 🔴 / 源码 `t()` 缺口 ⚠️）由 `@linkdesk/plugin-sdk/own-dict-coverage` 判定（判据本体在 SDK，⛔ 不在本仓复制）。

## v1.0.5（2026-09-17）

- **E6#111n-6 外观族 id 带归属**（本轴「非样式命名空间归一化」清账 · 主题族）——本仓名额全在下面；**词干一字未动**，只加了「<插件 id>.」归属前缀：
- 配方 id `mint-soda` → `theme-mint-soda.mint-soda`
- 配色 id `mint-soda` → `theme-mint-soda.mint-soda`
- 配色 id `mint-dew` → `theme-mint-soda.mint-dew`
- 配色 id `sea-salt-mint` → `theme-mint-soda.sea-salt-mint`
- 配色 id `lime-mint` → `theme-mint-soda.lime-mint`
- 🔴 **显示名（`label` / `name`）一字未动** —— 设置页看到的主题名与配色名**没有变化**；主题的颜色 / 玻璃 / 字体等一切外观内容也**一字未动**（这是「改名 ≠ 改样子」的机械保证）。
- **旧 id 不会被丢**：壳侧读时归一（`normalizeRecipeId` / `normalizeColorwayId` / `normalizeIconThemeId`，**解析器门控**＝新名在册且旧名不在册才映）＋ 配置迁移**版本 12** 把盘上的旧值改写掉；用户已选的主题 / 配色 / 图标主题在升级后**照旧生效**（含「插件比壳晚到」的顺序，两问门控保证任一时刻都只有一种解释成立）。

## v1.0.4（2026-09-15）

- 配方 `$schema` 改**文档唯一认可的写法**（`./node_modules/@linkdesk/plugin-sdk/schemas/theme.schema.json`，相对工程根）——原来用的是已作废的越界相对路径（`../..` 一路指到壳仓 `public/schemas/`，脱离壳仓后编辑器的补全与校验全失效）
- 分发件随包带 **MIT 许可证**（`LICENSE`）——MIT 要求副本里带版权声明，而 zip 才是用户真正拿到的那份
- 新增 `AGENTS.md`：在这个仓里单开 AI 干活时的进场说明（这只插件是什么 / 规矩在哪 / 命令怎么敲）
- 补 `plugin.json` 的 `$schema`（本仓原先缺这一行，编辑器无字段补全/校验）

## v1.0.3（2026-09-14）

- 源码迁入独立仓（E6#99，L7 第 7.2 轮）——从壳仓 `Encaron/linkdesk` 抽出本插件子树，历史全保（hash 变）
- 随包 `plugin.json` 显式声明 `pluginId`（E6#98g）：插件身份不再靠目录名兜底，独立仓构建出的包名与身份稳定
- `$schema` 补上并指向本仓 `node_modules/@linkdesk/plugin-sdk`（本插件原先**没有**这个字段，是 18 只里唯一一只；补上后编辑器补全/校验与本仓其余插件一致）


## v1.0.2（2026-09-11）

- 声明身份图（E6#93c 资源与目录归位）：`resources/icon.svg` 早已随包，却一直没有 `icon` 字段，导致市场里显示的是默认「插头」块而不是自己的薄荷图

## v1.0.1（2026-09-11）

- 补充 README 与更新记录：详情页「详情」页签显示说明，「更改日志」页签不再是空

## v1.0.0（初始版本）

- 清凉薄荷色系亮色主题合集——薄荷苏打 / 薄荷冰露 / 海盐薄荷 / 青柠薄荷
