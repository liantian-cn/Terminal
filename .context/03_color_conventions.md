# 颜色约定

颜色在 Terminal 里是协议字段，不是“看起来差不多就行”的视觉效果。

当前代码里的真实映射源是 `terminal/pixelcalc/color_map.py`，它镜像 `DejaVu` 的颜色定义。

## 基础原则

- 先认颜色类别，再认业务意义。
- 不要把未知颜色硬猜成已知类别。
- 对 `STATUS_BOOLEAN`，代码只关心黑 / 非黑，不关心具体是哪一种非黑色。
- 对 `MARK_FRAME`，代码应忽略其语义，它只是分区装饰，不是解码锚点。

## 重要颜色组

### `SPELL_TYPE`

用于区分：

- 友方 Buff
- 友方 Debuff
- 敌方 Debuff
- 玩家技能
- 可打断敌方法术
- 不可打断敌方法术
- 魔法 / 诅咒 / 疾病 / 中毒 / 激怒 / 流血

`BadgeCell` 的脚标颜色就是通过这组颜色映射出 `cell_type`。

### `ROLE`

用于区分：

- `TANK`
- `HEALER`
- `DAMAGER`
- `NONE`

### `CLASS`

用于区分职业。

### `STATUS_BOOLEAN`

这组颜色没有独立颜色语义，当前代码只做：

- 黑色 = `false`
- 非黑色 = `true`

不要把这组颜色的具体 RGB 当成更细的业务分类。

### `MARK_POINT`

当前有两个近黑色锚点颜色：

- `15,25,20`
- `25,15,20`

`capture/find_template_bounds.py` 会用它们拼成一个 8x8 模板，在整屏截图里定位矩阵区域。

### `MARK_FRAME`

- 只表示视觉分区
- 不参与锚点定位
- 不参与数据真假判断
- 不参与解码结果含义定义

## Agent 规则

- 改颜色常量、颜色分类、脚标语义时，先改这里，再改代码。
- 看到 `MARK_FRAME` 颜色不要把它误当稳定协议锚点。
- 看到 `MARK_POINT` 颜色要想到 capture 定位阶段，而不只是 pixelcalc 解码阶段。
