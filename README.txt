Claude Accessibility

One file that sets up Claude Code on Windows for blind and low vision people who use a screen reader such as NVDA or JAWS. Run it once and restart Claude Code.

What it does

It turns on Claude Code's screen reader mode and reduced motion, and turns off spinner tips and window title changes from Claude Code itself.

It installs a small Claude Code mod called quiet-tools, which:
Hides the lines for each command Claude runs, so you hear Claude's replies and not the commands in between. Press Control+O in Claude Code to see everything.
Hides the hint line under the prompt.
Replaces the "Churned for 3 seconds" line with "Done.", or "Done. Still working in the background." when something is still running.
Plays a soft chord when Claude finishes a reply.
Plays a different chord when Claude asks you a question or needs your permission, and repeats it every 6 seconds until you answer.
Sets the window title to what Claude is doing, such as Claude is working, Claude is done, or Claude needs your permission. With NVDA, press NVDA+T to hear it.
Tells Claude to write for a screen reader: answer first, and no tables, diagrams or emoji.
Adds a few extra words to the working line, like Faering and Paering.

It turns off the bell that Windows Terminal plays at the end of every reply.

You need

Windows 10 or 11, on an ARM, Intel or AMD PC.
Claude Code, already installed and signed in.

How to install

The easiest way: press Windows+R, paste this line, and press Enter.

powershell -NoProfile -ExecutionPolicy Bypass -Command "[Net.ServicePointManager]::SecurityProtocol=3072; $f=Join-Path $env:TEMP claude-accessibility.cmd; irm https://raw.githubusercontent.com/ce2004/claude-accessibility/main/claude-accessibility.cmd -OutFile $f; & $f"

Or download claude-accessibility.cmd from this page and double-click it. Windows may say "Windows protected your PC". Choose More info, then Run anyway.

When it finishes, it reads out what it did. Close Claude Code and start it again.

It is safe to run again at any time, for example to get a newer version. If one step fails, it says why and still does the rest.

Good to know

Type /copy in Claude Code to copy Claude's last reply to the clipboard, so you can paste it into Notepad and read it at your own pace.

The "auto mode on" and "/rc" labels near the prompt cannot be hidden by a mod.

How to undo it

The mod: in a terminal, run: claude plugin uninstall quiet-tools@claude-accessibility
Then delete the claude-accessibility folder inside the .claude folder in your user folder.

The settings: before the first change, the script saves a copy of each settings file next to it, ending in .before-claude-accessibility. To go back, delete the changed file and remove that ending from the copy's name. The Claude Code settings are in the .claude folder in your user folder. The Windows Terminal settings can also be changed in Windows Terminal under Settings, then Defaults, then Advanced, then Bell notification style.
