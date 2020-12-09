<div align="center"> 
<h1 align="center">Bilibili助手</h1>
<img src="https://img.shields.io/github/issues/srcrs/BilibiliTask?color=green">
<img src="https://img.shields.io/github/stars/srcrs/BilibiliTask?color=yellow">
<img src="https://img.shields.io/github/forks/srcrs/BilibiliTask?color=orange">
<img src="https://img.shields.io/github/license/srcrs/BilibiliTask?color=ff69b4">
<img src="https://img.shields.io/github/search/srcrs/BilibiliTask/main?color=blue">
<img src="https://img.shields.io/github/v/release/srcrs/BilibiliTask?color=blueviolet">
<img src="https://img.shields.io/github/languages/code-size/srcrs/BilibiliTask?color=critical">
</div>

# 简介

👯✨📫

哔哩哔哩(`B`站)自动完成每日任务，
投币，点赞，直播签到，自动兑换银瓜子为硬币，自动送出即将过期礼物，漫画`App`签到，大会员领取`B`币卷等。每天获得`65`点经验，助你快速升级到`Lv6`。

开源不易，如果本项目对你有帮助，那么就请给个`star`吧。😄

重要提示，如果收到了`b`站的账号安全通知，可以考虑将`Actions`禁用一段时间，观望一段时间再进行使用，具体禁用步骤，请参考此[Issues](https://github.com/srcrs/BilibiliTask/issues/78)。

# 功能

* [x] 自动获取经验(投币、点赞、分享视频) 
* [x] 直播辅助(直播签到，自动送出即将过期的礼物) 
* [x] 自动兑换银瓜子为硬币 
* [x] 自动领取年度大会员每月权益(每月`1`号领取`B`币劵、权益礼包) 
* [x] 月底自动用B币卷给自己充电(每月`28`号)
* [x] 月底自动用B币卷兑换金瓜子(每月`28`号)
* [x] 漫画辅助脚本(漫画`APP`签到) 
* [x] 支持功能自定义(自定义投币数量，银瓜子兑换硬币开关等)
* [x] 账户失效提醒(发送到你的微信或者钉钉提醒、邮箱提醒)
* [x] 支持多种方式推送运行结果(钉钉、微信)

# 目录

- [简介](#简介)
- [功能](#功能)
- [目录](#目录)
- [使用方法](#使用方法)
  - [1.fork本项目](#1fork本项目)
  - [2.准备需要的参数](#2准备需要的参数)
  - [3.将获取到参数填到Secrets](#3将获取到参数填到secrets)
  - [4.开启actions](#4开启actions)
  - [5.进行一次push操作](#5进行一次push操作)
- [进阶使用](#进阶使用)
  - [1.配置文件说明](#1配置文件说明)
  - [2.推送运行结果到微信](#2推送运行结果到微信)
  - [3.推送运行结果到钉钉](#3推送运行结果到钉钉)
  - [4.自定义程序运行时间](#4自定义程序运行时间)
- [如何拉取最新代码](#如何拉取最新代码)
  - [方法一](#方法一)
  - [方法二](#方法二)
- [更新日志](#更新日志)
- [参考项目](#参考项目)

关于日志中的 ✔ 和 ❌ 说明

符号 | 说明
-|-
✔ | 本次程序运行，成功的执行了代码，并完成了任务(例如，分享视频，今日未分享过，那么程序就应该请求分享视频的接口，协助完成分享视频的任务)。
❌ | 可能两种操作会出现这个符号。1.程序成功的执行了，尝试去完成任务，但是中途遇到了未知的失败。2.程序成功的执行了，检测到此类任务已经完成(例如，分享视频，今日已经分享过，那么程序不应该请求分享视频的接口，无需协助完成分享视频的任务)，就无需再去完成。可以理解为跳过或遇到错误。

# 使用方法

## 1.fork本项目

项目地址：[srcrs/BilibiliTask](https://github.com/srcrs/BilibiliTask)

## 2.准备需要的参数

本项目成功运行需要三个参数，分别是`SESSDATA`，`bili_jct`，`DedeUserID`

- 打开`b`站首页（任意一个页面都行）--> 按下`F12` --> `Application` --> `Cookies` --> `https://www.bilibili.com`

- 找到所需要参数对应的数据，找不到可能是你的账号没有登录。

![](img/获取Cookie.png)

## 3.将获取到参数填到Secrets

在`Secrets`中的`Name`和`Value`格式如下：

Name | Value
-|-
BILI_JCT | xxxxx
DEDEUSERID | xxxxx
SESSDATA | xxxxx

将上一步获取的参数，填入到Secrets中，一共需要添加三个键值对。

![](img/添加Secrets.png)

## 4.开启actions

默认`actions`处于禁止状态，在`Actions`选项中开启`Actions`功能，把那个绿色的长按钮点一下。如果看到左侧工作流上有黄色`!`号，还需继续开启。

![](img/开启actions.gif)

## 5.进行一次push操作

默认`push`操作会触发工作流运行。

+ 打开`README.md`，将里面的 😄 删除一个即
