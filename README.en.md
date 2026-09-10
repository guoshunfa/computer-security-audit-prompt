# Computer Security Audit Prompt

[中文](README.md) · English

## Background

While fixing bugs on a customer's computer, I signed in to the customer's UU远程 remote-access account on my own Mac. Later, my Mac was unexpectedly controlled remotely during normal use, prompting me to review its remote-access permissions.

In my experience, settings such as allowing remote control and launching at startup were enabled after sign-in, with controls spread across the main interface and separate settings pages. I also observed the application running without a visible Dock or menu bar icon. This raised concerns about unnoticed access risks over the preceding months, and about what happens when the Mac is locked or asleep.

This is a personal account, not a verification of default behavior across all versions. It does not establish that unauthorized access continued throughout those months or occurred during sleep. It also prompted questions about permission settings in similar tools such as ToDesk. I wanted to check actual behavior rather than rely on visible windows or icons.

I created this prompt to help an AI inspect the computer's current state, identify less-visible background activity and risks, and return a detailed report. Users can then decide what to disable, uninstall or investigate. **The prompt only inspects and reports; it does not perform those actions.**

## Coverage

- Background processes, ownership, privileges, launch relationships and activity.
- Startup and login entries, services, scheduled tasks and repeated failures.
- Remote control, unattended access, remote login, and readable lock, sleep and network-wake settings.
- Uninstall remnants: launch entries, services, drivers, extensions, permissions and files.
- Sensitive permissions, including screen recording, input monitoring and full disk access; system and browser extensions.
- Network listeners, connections, file sharing, guest write access, proxies, VPNs and tunnels.
- System security settings, account privileges and suspicious events in existing logs.
- CPU, memory, swap, disk usage and unusually growing logs.
- Virtual machines, containers, local databases, development servers and MCP components.

## Usage and limits

Open **[the standalone prompt: PROMPT.md](PROMPT.md)** and copy its full text into an AI client with access to the computer. The prompt is written in Chinese.

**My usage context is macOS + Codex.** Windows, Linux, other computers and other AI clients have not been validated. Completeness, accuracy and problem-free operation are not guaranteed. Instructions for adapting to other systems do not constitute compatibility testing.

A prompt is not a security boundary. Check the client's actual permissions and prefer read-only or sandbox restrictions where available. The prompt requires uncertain operations to be skipped and reported. Information sent to a cloud model may leave the computer; review the client's data-handling settings.

The report separates facts, inferences and unknowns, and lists coverage gaps. “No anomalies found” does not establish that a computer is safe. This project cannot guarantee detection of every background activity or replace professional forensic investigation.
