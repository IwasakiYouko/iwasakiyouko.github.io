---
title: 活动查询
outline: false
---

<script setup>
import ChatBox from '/bot-help/components/ChatBox.vue'

const eventdetail = [
  { text: '/活动 17', from: 'user' },
  { text: '[id为17的活动详情]', from: 'bot' }
]

const eventlist = [
  { text: '/活动列表', from: 'user' },
  { text: '[包含当前服务器所有活动的长串列表]', from: 'bot' }
]

const eventlistmmj = [
  { text: '/活动列表 mmj 橙', from: 'user'},
  { text: '[包含所有mmj成员参与了的活动属性为橙的活动的列表]', from: 'bot' }
]

const eventlistonlymmj = [
  { text: '/活动列表 仅mmj 蓝', from: 'user'},
  { text: '[包含仅有mmj成员参与了的活动属性为蓝的活动的列表]', from: 'bot' }
]

const eventplanner = [
  { text: '/活动规划 pt1000w 当前pt120w 歌 虾ex 龙hd 5火 10火', from: 'user' },
  { text: '[按目标 PT、歌曲、火数与组卡结果生成活动规划]', from: 'bot' }
]

</script>

# 活动

## 活动指令

- `/活动列表` `/pjsk events` `/events` `/活动一览` `/event-list`
  - 活动列表。
- `/查活动` `/pjsk event` `/活动` `/event`
  - 查询当前/指定活动信息。
- `/冲榜记录` `/pjsk event record` `/活动记录`
  - 查询指定账号的冲榜记录（⚠️需要上传 suite 数据）。
- `/活动规划` `/pjsk event planner` `/event-planner`
  - 根据目标 PT 或目标排名、当前 PT、歌曲、火数与组卡条件生成活动规划图（⚠️需要上传 suite 数据）。

## 可选参数说明

- 查询单个活动格式：
  - 直接使用活动 id：`123`
  - 负数索引，表示倒数第几个活动：`-1`
  - 箱活缩写，例如 `mnr1`
- 查询多个活动筛选方式：
  - 团名英文缩写：`mmj` `vs`
  - 仅团名缩写: `仅mmj` `仅25h`
  - 查询某个角色有出场的活动：`miku` `miku ick`
  - 查询角色箱活：`ick箱` `ickban`
  - 查询混活：`混活`
  - bonus 属性：`cool` `蓝` `蓝星`
  - 年份：`2025年` `今年` `去年`
  - 活动类型：`普活` `5v5` `wl` `wl`
- 以上参数可以混合使用，用空格分隔。

注意，仅+团名和团名是两个不同参数，前者只会检索出团队的箱活，后者会检索全局有该团队成员参与的活动

## 活动规划参数

- 目标：必须提供目标 PT 或目标排名。PT 支持 `pt1000w` `目标1200万` `打到1500w`，排名支持 `t100` `100名`。
- 当前进度：可写 `当前pt120w` `已有pt300万`；不写时会优先读取 suite 中该活动的当前 PT，读取不到则按 0 计算。
- 歌曲：在 `歌` / `歌曲` 后填写歌曲名或别名，可在歌曲后直接接难度，如 `虾ex` `龙hd`。不写歌曲时默认计算 `虾 expert` 与 `龙 hard`；`野车` / `omakase` / `随机` 会按随机曲计算。
- 火数：支持 `1火` 到 `10火`，不写时默认同时计算 `5火` 与 `10火`。
- 活动：可写 `event154` 指定活动；不写时使用当前活动。没有当前活动时需要指定活动 ID。
- 卡组：活动规划会复用活动组卡参数，例如 `当前` `顶配` `画布` `已读` `wl3 mzk` `#123 456 789 101 112` `队友综合25w` `队友实效200`。更多组卡参数可参考[组卡文档](/bot-help/recommend)。
- 区服：不写区服时使用默认绑定账号的区服，也可以使用 `/jp活动规划` `/cn活动规划` 等前缀指定。

查看内置帮助可发送 `/活动规划 help`。

## 指令示例
<div class="chatbox-grid">
<ChatBox :messages="eventdetail" />

<ChatBox :messages="eventlist" />

<ChatBox :messages="eventlistmmj" />

<ChatBox :messages="eventlistonlymmj" />

<ChatBox :messages="eventplanner" />
</div>
