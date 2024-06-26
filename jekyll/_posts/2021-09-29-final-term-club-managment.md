---
title: "OSPP 2021-结项报告-开发基于Wechaty实现微俱乐部会员&活动管理的微信小程序"
author: mangguo188
categories:
  - project
  - ospp
image: /assets/2021/09-final-term-club-managment/wechaty.webp
tags:
  - summer-of-wechaty
  - summer-2021
  - ecosystem
  - ospp
  - ospp-2021
  - final-term
---

## 暑期2021

“开源软件供应链点亮计划-暑期2021”（以下简称 暑期2021）是由中科院软件所与 openEuler 社区共同举办的一项面向高校学生的暑期活动。
旨在鼓励在校学生积极参与开源软件的开发维护，促进国内优秀开源软件社区的蓬勃发展。
根据项目的难易程度和完成情况，参与者还可获取“开源软件供应链点亮计划-暑期2021”活动奖金和奖杯。
官网：[https://summer.iscas.ac.cn/](https://summer.iscas.ac.cn/)

本项目 [开发基于Wechaty实现微俱乐部会员&活动管理的微信小程序] 系 暑期2021 支持的开源项目。

## 项目信息

- 导师：鲁玉超

- 学生：陈婧

- 项目介绍：<https://github.com/wechaty/summer/issues/78>

- 项目名称：开发基于微信实现微俱乐部会员&活动管理的微信小程序  

- 方案描述：本项目需要基于wechaty开发一个能进行会员和活动管理的小程序。小程序的核心内容为报名服务，WeChat机器人作为服务之一完成接收信息，并响应入库的工作。本程序意在为使用者提供更方便快捷的管理成员及管理活动的功能。

- 时间规划：
  - 阶段一
    - 完成时间：7月20日
    - 计划描述：引入聊天机器人，整理基础适用/开发生产环境/用户协议，绑定用户数据到俱乐部，使用微信开放平台实现“关键词回复”功能。
  - 阶段二
    - 完成时间：8月15日
    - 计划描述：实践“群主发布活动”功能，实践“群主管理活动”功能，实践“成员标签活动”功能，完善以上功能块进行调试。
  - 阶段三
    - 完成时间：9月5日
    - 计划描述：实践“活动相册”功能、“帮助”功能（将关键词与操作关联，要求提高容错性），如果有空余时间，设计自定功能。
  - 阶段四
    - 完成时间：9月30日
    - 描述计划：实践自设定功能，收集中出现的问题，针对程序运行程序功能，小整体优化升级（用户数据处理）。

## 项目总结

- 项目成果

项目仓库: <https://github.com/mangguo188/wechaty-club-management>  

- 遇到的问题及解决方案：
  - 启动小程序后仅出现授权页面，授权后无应有显示。
    - 方案：本项目需要小程序与机器人一同登录，只有机器人持有者登入小程序，界面才会正确显示。找到云开发日志中机器人持有者发布的消息，将其wxid赋值给小程序使用者（小程序使用者原先的wxid是系统自动生成的数字，仅保证wxid唯一，但无意义）。
  - 云函数编写过程中常出现错误，但是错误查找需要提交运行，时间周期长且提交次数有限，需要发掘更好检验错误的方法。
    - 方案：在老师的建议下，我先在机器人中模拟后端返回，将函数编写在机器人服务中，检验函数的正确性，当所有函数运行完毕无错后再在后端更改相应函数，此举大大减少了云函数的上传次数，降低电脑负荷。
  - 本项目仅对文本信息可做出响应反馈，对于超链接、图片、视频等消息无法提取有效信息。
    - 方案：暂时搭建响应超链接、图片、视频的框架，后续功能待有时间可持续开发。
  - 编写完成后，小程序的云开发部分与前端部分与机器人位于同一文件夹下，两者分别不明晰，加上每个文件夹下都有index.js文件，极易出现修改错误。
    - 方案：将小程序封装到mp文件夹下，机器人封装到wechatbot文件夹下，使两者功能可以分开使用，也易连接（需要注意的是，由于小程序云函数封装到mp文件夹下，从微信开发者工具上查看时只需要打开mp文件夹，不然会出现无法部署的问题）。

- 项目展望：
  - 本项目仅完成基础功能开发，目前使用者进入小程序可以随时查看群活动与该群内成员id，包括报名记录等便利统计数据的内容。但将基本框架已搭建完毕，后续有时间可加更多功能模块，包括如何将群机器人与小程序1对1的关系解开，方便更多小程序使用者简便获取活动管理功能等。

## 项目展示

### live coding视频：

{% include iframe.html src="https://youtu.be/5LZ08re5YR8" %}

> 国内链接：<https://www.bilibili.com/video/BV1hR4y1n7AH/>

### PPT展示视频：

{% include iframe.html src="https://youtu.be/eSgaD32njVw" %}

> 国内链接：<https://www.bilibili.com/video/BV1uP4y187T9/>

### 项目PPT：

{% include iframe.html src="/assets/2021/09-final-term-club-managment/final-term.pdf" %}

## 联系我们

- 项目链接：<https://github.com/mangguo188/wechaty-club-management>  
- 联系方式：1017137803@qq.com
