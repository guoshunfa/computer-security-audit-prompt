# 电脑安全检测指令词

中文（默认） · [English](#english)

## 背景

之前为了解决客户电脑上的 bug，我在自己的 Mac 上登录了客户的悠悠远程账号。后来正常使用电脑时，电脑突然被远程控制，我才意识到需要重新检查远程访问权限。

在我的使用经历中，登录后出现了默认允许远控、开机自启等设置，相关开关分散在主界面和独立设置页。程序运行时，我也曾在 Dock 和菜单栏都看不到它的图标。这让我担心：过去几个月里，自己的电脑是否一直存在未被注意到的访问风险？锁屏或睡眠后又是什么状态？

这是我的个人经历，不是对该软件所有版本默认行为的验证，也没有证实这几个月持续发生过未授权访问或睡眠期间被控制。我对 ToDesk 等同类工具的权限设置也产生了疑问，希望检查实际状态，而不是只看应用有没有窗口或图标。

因此，我整理了这份指令词，让 AI 读取电脑当前状态，找出不易察觉的后台活动和风险，返回详细信息，帮助使用者决定哪些软件或功能需要关闭、卸载或进一步核实。**指令词本身只做检测和报告，不执行这些处理。**

## 检查什么

- 后台进程及其来源、权限、启动关系与活动。
- 开机和登录启动项、服务、计划任务及异常重试。
- 远程控制、无人值守访问、远程登录，以及可读取的锁屏、睡眠和网络唤醒相关设置。
- 卸载后遗留的启动入口、服务、驱动、系统扩展、权限和文件。
- 屏幕录制、输入监听、完全磁盘访问等敏感权限，以及系统和浏览器扩展。
- 网络监听、连接、文件共享、访客写入权限、代理、VPN 和隧道。
- 系统安全设置、账户权限，以及已有日志中的异常操作线索。
- CPU、内存、交换、磁盘占用和异常增长的日志。
- 虚拟机、容器、本地数据库、开发服务器和 MCP 等后台组件。

## 使用

打开 **[独立指令词：PROMPT.md](PROMPT.md)**，复制完整正文到能够读取本机信息的 AI 客户端。

**我的使用场景是 macOS + Codex。** Windows、Linux、其他电脑和其他 AI 客户端未做验证，不保证检查完整、准确或不会出现问题。指令中保留其他系统的适配要求，不代表已经验证兼容。

提示词不是权限隔离机制。使用前应核对客户端实际权限，有只读或沙箱限制时优先启用；无法确认操作是否只读时，指令要求跳过并报告。使用云端模型时，发送给模型的信息可能离开电脑，需自行核对客户端的数据处理设置。

报告区分事实、推断和未知，并列出未覆盖范围。“未发现异常”不等于绝对安全；本项目不保证发现所有后台活动，也不能替代专业取证。

---

## English

# Computer Security Audit Prompt

### Background

While fixing bugs on a customer's computer, I signed in to the customer's 悠悠远程 remote-access account on my own Mac. Later, my Mac was unexpectedly controlled remotely during normal use, prompting me to review its remote-access permissions.

In my experience, settings such as allowing remote control and launching at startup were enabled after sign-in, with controls spread across the main interface and separate settings pages. I also observed the application running without a visible Dock or menu bar icon. This raised concerns about unnoticed access risks over the preceding months, and about what happens when the Mac is locked or asleep.

This is a personal account, not a verification of default behavior across all versions. It does not establish that unauthorized access continued throughout those months or occurred during sleep. It also prompted questions about permission settings in similar tools such as ToDesk.

I created this prompt to help an AI inspect the computer's current state, identify less-visible background activity and risks, and return a detailed report. Users can then decide what to disable, uninstall or investigate. **The prompt only inspects and reports; it does not perform those actions.**

### Coverage

- Background processes, ownership, privileges, launch relationships and activity.
- Startup and login entries, services, scheduled tasks and repeated failures.
- Remote control, unattended access, remote login, and readable lock, sleep and network-wake settings.
- Uninstall remnants: launch entries, services, drivers, extensions, permissions and files.
- Sensitive permissions, including screen recording, input monitoring and full disk access; system and browser extensions.
- Network listeners, connections, file sharing, guest write access, proxies, VPNs and tunnels.
- System security settings, account privileges and suspicious events in existing logs.
- CPU, memory, swap, disk usage and unusually growing logs.
- Virtual machines, containers, local databases, development servers and MCP components.

### Usage and limits

Open **[the standalone prompt: PROMPT.md](PROMPT.md)** and copy its full text into an AI client with access to the computer. The prompt is written in Chinese.

**My usage context is macOS + Codex.** Windows, Linux, other computers and other AI clients have not been validated. Completeness, accuracy and problem-free operation are not guaranteed. Instructions for adapting to other systems do not constitute compatibility testing.

A prompt is not a security boundary. Check the client's actual permissions and prefer read-only or sandbox restrictions where available. The prompt requires uncertain operations to be skipped and reported. Information sent to a cloud model may leave the computer; review the client's data-handling settings.

The report separates facts, inferences and unknowns, and lists coverage gaps. “No anomalies found” does not establish that a computer is safe. This project cannot guarantee detection of every background activity or replace professional forensic investigation.
