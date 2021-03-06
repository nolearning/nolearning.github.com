---
layout: post
title: Operations Specification
---
#运维规范

##术语
* 可用性：即线上服务正常运行时间的百分比，采用N个9进行量化
	<table>
		<tr><td>描述</td><td>可用性级别</td><td>年度停机时间</td></tr>
		<tr><td>基本可用性</td><td>99%</td><td>87.6小时</td></tr>
		<tr><td>较高可用性</td><td>99.9%</td><td>8.8小时</td></tr>
		<tr><td>具有故障自动恢复能力的可用性</td><td>99.99%</td><td>53分钟</td></tr>
		<tr><td>极高可用性</td><td>99.999%</td><td>5分钟</td></tr>
	</table>

##概要
本文档主要包括产品上线前的运维规划，实施流程、监控机制、自动化、事故响应等方面进行了描述，用以保证线上高可用性与高性能。

##运维流程

* 运维规划
	* 业务整体方案审核
	* 形成运维规划文档
	* 运维规划变更依据业务变更
	* 更新运维规划文档
	* 依据运维数据进行容量规划——如应用服务器容量规划方面、数据库容量规划，主机容量规划、存储容量规划等
* 业务上线
	* 业务上线申请
	* 分析并审核申请
	* 确定上线部署方案
	* 发布上线方案、及时间
	* 上线实施
	* 上线后校验
* 日常维护
	* 查阅日常运行日志
	* 形成日常运行报告（无问题按周，有问题当天）
	* 业务服务错误通知开发人员处理
	* 基础软件升级，修补漏洞
* 定期测试维护
	* 制定测试方案(包括压力测试、安全测试等）
	* 实施测试维护
	* 定期测试记录
	* 业务服务问题通知开发人员处理
	* 基础软件维护
	* 形成定期测试维护报告
* 事故处理
	* 事故处理预案
	* 保存事故现场日志
	* 通知开发人员到场
	* 启动备用服务器或备用方案
	* 缺陷修复及上线
	* 形成事故报告
* 紧急上线
	* 发布紧急上线通知
	* 相关人员确认后上线部署
	* 部署后，QA线上测试确认
	* 形成紧急上线报告

##通知与文档
* 文档应提交到相应的版本管理服务器
* 文档应明了、信息完备
* 通知应以邮件形式发给相关人员（产品、测试、开发的相关人员）
	* 格式：
		* title：时间-流程类型-简述
		* body：问题描述、解决方案、回滚方案、验证方案、结果
	* 应做到团队内相关人员明白，明确范围、给出方案概要，给出相关文档链接

##规划内容
依据业务需求与远期目标、开发设计文档，形成运维规划文档，需包括

* 业务数据量（数据库容量、文件容量）
* 服务器要求（物理机器配置与数量、虚拟平台)
* 网络部署（网络划分、多子网、集群部署）
* 数据安全（RAID、备份）
* 软件选型（数据库、web服务器、代理服务器）
* 避免单点
* 备用方案
* 部署方案

##监控
* 确认采用监控工具（如：Nagios、Cacti、monit、Ganglia）
* 利用监控工具插件功能编写脚本监控特定事件
* 报警机制，采用邮件+短信的形式
* 报警服务的监控，定期测试报警服务是否正常

##自动化管理
* 安装自动化
* 部署自动化
* 软件升级自动化
* 监控自动化
* 注意自动化风险

##事故响应
* 建立团队内事故处理小组
* 制定事故处理预案
* 事故现场保存及事后分析
* 及时启动备用方案
