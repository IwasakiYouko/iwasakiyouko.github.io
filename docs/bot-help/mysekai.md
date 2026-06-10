---
title: MySekai 查询
outline: false
---

<script setup>
import ChatBox from '/bot-help/components/ChatBox.vue'

const msam = [
  { text: '/msam', from: 'user' },
  { text: '[包含烤森的资源信息以及具体四张地图资源点的图片]', from: 'bot' }
]

const fixture = [
  { text: '/mysekai家具列表', from: 'user' },
  { text: '[包含所有当前服务器mysekai家具的列表]', from: 'bot' }
]

const msf = [
  { text: '/msf', from: 'user' },
  { text: '[在家具列表的基础上标黑未制作家具的列表]', from: 'bot' }
]

const msr = [
  { text: '/msr', from: 'user' },
  { text: '可以查看唱片持有情况的列表图片', from: 'bot' }
]

const msb = [
  { text: '/msb', from: 'user' },
  { text: '[可以查看已获取的mysekai蓝图的列表]', from: 'bot' }
]

const msp = [
  { text: '/msp 2', from: 'user' },
  { text: '[返回mysekai相册中正数第二张图片]', from: 'bot' }
]

const msg = [
  { text: '/msg mmj' , from: 'user'},
  { text: '[升级more more jump的大门所需的每级材料的列表]' , from: 'bot' }
]

const bjsk = [
  { text: '/bjsk 1-5', from: 'user' },
  { text: '[当前烤森百景 1 到 5 名的投稿、评价数和前后差距]', from: 'bot' }
]
</script>

# MySekai 相关查询

::: info
除烤森百景 SK 外，部分功能需要在Haruki工具箱绑定并上传数据之后才能正常使用
:::

> ⚠️ **除烤森百景 SK 外，MySekai 查询需用户绑定 Haruki工具箱账号并上传 MySekai 数据**
>
> ⚠️ **普通 MySekai 查询暂不支持国服；烤森百景 SK 可使用 `/cn` 前缀查询国服**

## 查询烤森百景

- `/百景sk` `/烤森百景sk` `/mysekai-housing-sk` `/mshsk` `/bjsk`
  - 查询当前进行中烤森百景的投稿排名线，返回指定名次的投稿缩略图、评价数以及与前后一名的差距。
  - 不填参数时默认查询 `1-5` 名；可以写单个名次、逗号分隔或范围，如 `/bjsk 1`、`/bjsk 1,3,5`、`/bjsk 10-14`。一次最多查询 5 个名次。
  - 可用 `id=<housing_id>` 查询指定百景，如 `/bjsk id=25 1-5`；也支持 `/bjsk 25 1-5` 的简写。
  - 可用区服前缀指定服务器，如 `/jpbjsk 1-5`、`/cnbjsk 1-5`。
  - 高级参数一般无需填写：`sample=2` 可指定采样次数，`interval=1000` 可指定多次采样间隔（毫秒）。
  - 结果基于采样统计，仅供参考。

## 查询烤森资源

- `/msa` `/pjsk mysekai res` `/mysekai-resource` `/mysekai资源` `/烤森资源`
  - 查询烤森信息（资源、天气、来访角色等）。
- `/msm` `/pjsk mysekai map` `/mysekai-map` `/mysekai地图` `/烤森地图` `/msmap`
  - 查询烤森地图。
  - `/msm <id>`可以单独输出某张地图
- `/msam`
  - 同时输出 `msa` 和 `msm` 对应的统计信息以及四张烤森地图。

## 查询烤森收集


- `/烤森家具列表` `/mysekai-fixture-list` `/mysekai家具列表`
  - 查询所有家具列表。
- `/家具列表` `/pjsk mysekai furniture` `/pjsk mysekai fixture` `/msf` `/mysekai 家具`
  - 查询账号已获得家具列表,。
- `/msr` `/pjsk mysekai musicrecord` `/mysekai-music-record` `/mysekai唱片` `/烤森唱片` `/mss` `/mssong`
  - 查询烤森音乐唱片收集。
- `/msb` `/pjsk mysekai blueprint` `/mysekai blueprint` `/mysekai 蓝图`
  - 查询烤森蓝图列表。
- `/msp` `/pjsk mysekai photo` `/pjsk mysekai picture` `/mysekai 照片`
  - 展示烤森内拍摄的照片，需要指定图片编号（从1开始）。



## 查询烤森养成

- `/烤森对话列表` `/mysekai-talk-list` `/mysekai对话列表`
  - 查询烤森角色对话列表。
- `/msg` `/pjsk mysekai gate` `/mysekai-door-upgrade` `/mysekai大门升级` `/烤森大门升级` `/msgate`
  - 查询烤森大门升级所需材料，如果没有指定团队，会显示距离满级最近的团队的大门。

## 指令示例 
<div class="chatbox-grid">
<ChatBox :messages="msam" />

<ChatBox :messages="fixture" />

<ChatBox :messages="msf" />

<ChatBox :messages="msr" />

<ChatBox :messages="msb" />

<ChatBox :messages="msp" />

<ChatBox :messages="msg" />

<ChatBox :messages="bjsk" />
</div>
