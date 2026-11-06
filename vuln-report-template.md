# Vulnerability Report Template

> 使用说明：严格按以下格式撰写英文漏洞报告（申报文档格式）。`<!-- -->` 中为中文写作提示，提交前删除所有提示。
> 写作要求：Description 和 PoC 清楚直白；Impact、Solution、Vendor Notification 简单写；Prerequisites/Setup 严格按实际搭建的环境写、只写关键项，不可瞎写；报告内最多5张截图，只截取Poc关键部分，Prerequisites/Setup部分不必截图。

---

## Title: <Vulnerability Type> Vulnerability in <Project> <Component/Endpoint> (<One-line Impact>)

<!-- 标题格式：<漏洞类型> Vulnerability in <项目名> <组件/端点> (<一句话后果>)，参考：Path Traversal Vulnerability in Abstruse CI Worker /cache Endpoint (Arbitrary File Read) -->

**BUG\_Author:** <author id>

**Affected Version:** <受影响版本范围，如 all historical versions + master branch / v3.0.0 ~ v3.19.0>

**Vendor:** [<vendor/org>](<repo url>)

**Software:** [<Project Name>](<repo url>)

**Vulnerability Files:** - `<path/to/vulnerable/file>`

**CWE:** CWE-<number> - <CWE official name> - <一句话解释>

**CVSS 3.1:** <score> (<Severity>) - <vector, e.g. AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:N/A:N>

## Description:

<!-- 清楚直白：哪个文件哪一行、哪个参数/输入、未经任何校验地流向了哪个危险操作。单个漏洞直接写；多个漏洞可先写整体攻击链，再分 Vulnerability A / Vulnerability B 逐个写根因，最后写 Combined Attack Chain。 -->

**Vulnerability A: <类型> (<CWE>)**

<root cause: file (line), unsanitized input -> dangerous sink, why it fails>

**Vulnerability B: <类型> (<CWE>)** (如只有一个漏洞则省略 B 和攻击链)

<root cause>

**Combined Attack Chain** (如只有一个漏洞则省略)

<单个漏洞影响有限，组合后形成完整攻击链的因果说明>

## Prerequisites/Setup:

<!-- 严格按实际搭建的环境写，只写关键项；每一项都必须来自真实执行的 docker run / compose 配置，禁止编造。用编号列表，3 条左右。 -->

1. <目标软件及部署方式、访问地址，如 deployed via Docker (`org/image:tag`), accessible on `http://localhost:80`>
2. <PoC 运行依赖，如 Python 3 with `PyJWT` and `requests` installed>
3. <前置条件/权限说明，如 No valid credentials required / requires a low-privileged account>

## Proof of Concept:

<!-- 清楚直白：一段话说清脚本干什么，然后给出完整可运行的 PoC 脚本（带 Step 注释），最后附真实运行输出。 -->

The following <script> <一句话说明脚本行为>:

```python
# <PoC script, with Step 1 / Step 2 / ... comments and expected output as comments>
```

**Test run output (against localhost:<port>):**

```
<真实运行输出，逐行，含状态码和关键回显>
```

## Impact:

<!-- 简单写，2-4 条要点，每条一句话加粗标题，不展开。 -->

1. **<point 1>:** <one sentence>
2. **<point 2>:** <one sentence>
3. 

## Solution:

<!-- 简单写，2-3 条修复建议，每条一句话加粗标题，不展开。 -->

1. **<fix 1>:** <one sentence>
2. **<fix 2>:** <one sentence>

## Vendor Notification:

- **Vendor:** <vendor/org> (GitHub)

- **Repository:** <repo url>

- **Security contact:** <SECURITY.md / security policy 情况>

- **Notification status:** <Not yet notified / notified on date, 以及仓库活跃度等必要说明>
