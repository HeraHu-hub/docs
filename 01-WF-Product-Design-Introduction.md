# 产品简介

## 产品概述
- 工作流平台（WorkFlow）是基于ansible之上，提供基础操作的原子平台；具备上百台并发处理能力，除了支持脚本执行、文件拉取 / 分发、定时任务等一系列基础运维场景以外，还支持根据实际运维场景，通过流程调度能力将零碎的单个任务组装成一个自动化作业流程；而每个任务都可做为一个原子节点，将其封装成插件，提供给上层或周边系统/平台使用，如CMDB、监控平台、数据库审计平台、日志平台等，利用工作流串联整个运维体系平台，实现跨系统调度自动化，和资源及应用全生命周期管理。

## 功能特性

<table><tbody>
<tr style="font-weight:bold;"><td width="15%" >	菜单	</td><td width="15%">	功能名称	</td><td width="70%">	功能说明	</td></tr>
<tr><td>	首页	</td><td>	快捷入口	</td><td>	通过对业务配置异常分析给出提醒和明细列表，提供便捷的收藏任务、以及常用执行的操作入口。	</td></tr>
<tr><td rowspan="2" style="vertical-align:middle;">	快速执行	</td><td>	执行脚本	</td><td>	可通过手动编写、本地上传，或引用业务/公共脚本的方式进行批量脚本执行。	</td></tr>
<tr><td style="vertical-align:middle;">	文件传输	</td><td>	支持本地上传或从服务器上选择源文件两种方式，满足"一对多"、"多对多"、"多对一"等多种分发文件场景。	</td></tr>
<tr><td rowspan="7" style="vertical-align:middle;">	业务管理	</td><td style="vertical-align:middle;">	作业	</td><td>	提供作业编排功能，支持用户将多个脚本执行、文件分发或人工确认步骤组装成作业模板，并按使用场景衍生多个对应的执行方案；提供调试功能来满足作业调试场景，支持使用标签对作业进行分类管理。	</td></tr>
<tr><td style="vertical-align:middle;">执行方案</td><td> 汇总展示所有作业的工作流列表 </td></tr>
<tr><td style="vertical-align:middle;">脚本</td><td> 提供脚本的版本管理功能，包括版本增删改查、版本日志、版本对比、版本状态变更（上线/下线/禁用）等。 </td></tr>
<tr><td style="vertical-align:middle;">定时</td><td> 支持将作业执行方案设置成单次或周期执行的定时任务。 </td></tr>
<tr><td style="vertical-align:middle;">执行历史</td><td> 记录所有通过作业平台页面或 API 调用的方式发起的脚本执行、文件分发、作业和定时任务操作信息，提供任务重做和日志回溯的能力。 </td></tr>
<tr><td>	账号	</td><td>	提供在执行脚本或分发文件时所需的服务器账户的管理和维护功能。	</td></tr>
<tr><td style="vertical-align:middle;">	消息通知	</td><td>	支持用户根据执行任务的状态发送消息通知，包括脚本执行/文件分发/作业执行的成功或失败状态，帮助用户及时得知任务的执行情况。	</td></tr>
<tr><td rowspan="3" style="vertical-align:middle;">	平台管理	</td><td>	公共脚本	</td><td>	功能与业务的脚本管理相同，但公共脚本面向的是整个作业平台所有业务，满足提供公共需求的脚本使用场景。	</td></tr>
<tr><td style="vertical-align:middle;">	用户角色	</td><td>	区分用户角色，用于管理用户的脚本和作业的权限。 </td></tr>
<tr><td style="vertical-align:middle;">	全局设置	</td><td>	作业平台管理员功能，支持配置消息通知渠道、历史数据存储策略、账号命名规则和高危语句规则设置。	</td></tr>
</tbody></table>

## 产品架构

- 产品架构是Vue + Flask + Ansible + Mysql
![系统架构图](https://github.com/user-attachments/assets/1f2e52c4-6222-401b-b647-5b854ca2d08f)

*讨论点：ansible是用jumpserver内置ansible，主机列表从jumpserver拉取，还是WF搭建一个ansible，主机列表从cmdb获取。*

- 部署图（待补充）

## 迭代计划

- 一期（8月）：实现基本功能的原子操作，如文件传输，执行命令和脚本（Task）。
- 二期（9月）：实现将每个原子操作的任务封装成插件，作为作业编排的组件（Job）。
- 三期（10月）：实现插件组合成工作流作业模板（WorkFlow）。
