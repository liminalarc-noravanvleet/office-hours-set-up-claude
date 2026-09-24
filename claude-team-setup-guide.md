# Getting Started with Your Team Claude Account (Mac)

Welcome! This guide walks you through everything you need to get fully set up with Claude. No technical background is assumed, and the terminal section explains every single step.

By the end of this guide you will have:

1. **Claude in your web browser**, signed in to your team account and protected with multi-factor authentication (MFA).
2. **The Claude desktop app** installed on your Mac.
3. **Claude Code running in your Mac's Terminal.**

Plan on about 20 minutes total. Work through the sections in order, because each one builds on the last.

---

## Before You Begin

- Find the email inviting you to join Claude.
  - If you don't have the invitation, or it has expired, reach out to Donald Turner.
- **Your phone**, for setting up multi-factor authentication.
- **Your Mac login password** (you may be asked for it when installing things).

The invitation email will look like this:

![Example Claude invitation email from Donald Turner to join LiminalArc's workspace on the Team plan](claude-invite-email.png)

---

## Section 1: Set Up Claude in Your Browser (with MFA)

### Step 1.1 — Accept your team invitation

- Open your work email and look for an invitation from Anthropic / Claude. The subject line usually mentions being invited to join your organization on Claude. Check your spam or junk folder if you don't see it.
- Click the **Accept invitation** (or **Join**) button in the email. Your web browser will open to claude.ai.
- If you don't have an invitation, contact Donald Turner and ask him to send one to your work email address.

### Step 1.2 — Sign in with your work identity

On the sign-in page, use **single sign-on (SSO)**: enter your work email and you'll be sent to your company's normal login page (for example Okta, Microsoft, or Google). Sign in exactly as you do for other work tools.

> **Tip:** Always use your work email. If you sign in with a personal email, you'll end up in a separate personal account instead of your team's workspace.

### Step 1.3 — Turn on multi-factor authentication (MFA)

You'll be prompted to set up MFA as part of signing in with SSO.

### Step 1.4 — Confirm you're in the team workspace

1. Once you're signed in, click your name or initials in the bottom-left corner of the screen.
2. You should see your organization's name. If you see more than one account listed (for example, a personal one), select your team organization.

### ✅ Section 1 checkpoint

You're done with this section when:

- You can open **claude.ai**, see your organization's name under your profile, and send Claude a message (try typing "Hello!" and pressing Return).
- Signing in requires a second step through SSO.

---

## Section 2: Install the Claude Desktop App on Your Mac

The desktop app gives you Claude in its own window, so you don't need to keep a browser tab open.

### Step 2.1 — Download the app

1. In your browser, go to **claude.ai/download**.
2. Click the **Download for macOS** button. A file ending in `.dmg` will download (it usually lands in your **Downloads** folder).

### Step 2.2 — Install the app

1. Open **Finder**, then click **Downloads** in the left sidebar.
2. Double-click the Claude `.dmg` file you just downloaded. A small window will open showing the Claude icon and an **Applications** folder.
3. **Drag the Claude icon onto the Applications folder.** This copies the app onto your Mac.
4. Close that small window. In Finder's sidebar you'll see a Claude item with an eject symbol (⏏) next to it. Click the eject symbol to tidy up.

### Step 2.3 — Open the app and sign in

1. Press **Command (⌘) + Space** on your keyboard to open Spotlight search, type **Claude**, and press **Return**.
2. If your Mac asks *"Claude is an app downloaded from the internet. Are you sure you want to open it?"*, click **Open**.
3. Click **Sign in**. Use **SSO**, the same as in Section 1. Your browser may open briefly to finish signing in, then send you back to the app.
4. Confirm you're in your team workspace by clicking your name in the bottom-left corner.

> **Tip:** To keep Claude handy, right-click its icon in your Dock while it's open and choose **Options → Keep in Dock**.

### ✅ Section 2 checkpoint

You're done with this section when the Claude app opens from your Applications folder, shows your organization's name, and replies to a message.

---

## Section 3: Run Claude Code in the Mac Terminal

Claude Code is a version of Claude that runs inside the **Terminal**, a built-in Mac app where you type instructions instead of clicking buttons.

### A quick orientation to the Terminal

- The Terminal is a window where you type a command and press **Return** to run it.
- The line where you type is called the **prompt**. It usually ends with a `%` symbol and looks something like `yourname@Your-MacBook ~ %`.
- **You don't type the `%`.** Only type (or paste) the command itself.
- Select the command in this guide, press **⌘ + C** to copy, click inside the Terminal window, and press **⌘ + V** to paste. Then press **Return**.
- When you type your Mac password in the Terminal, **nothing will appear on screen**, not even dots. That's normal. Type it and press Return.
- When a command is finished, a fresh prompt (ending in `%`) appears, ready for the next command.

### Step 3.1 — Open the Terminal

1. Press **⌘ + Space** to open Spotlight search.
2. Type **Terminal**.
3. Press **Return**. A window with a white or black background and a blinking cursor will open.

> **Tip:** Right-click the Terminal icon in your Dock and choose **Options → Keep in Dock** so it's easy to find next time.

### Step 3.2 — Install Claude Code

1. Copy this entire command (it's all one line):

   ```
   curl -fsSL https://claude.ai/install.sh | bash
   ```

2. Click inside the Terminal window and paste it with **⌘ + V**.
3. Press **Return**.
4. Wait. You'll see text scroll by as it downloads and installs. This usually takes under a minute.
5. When it's done, you'll see a message saying the installation was successful, and a fresh prompt will appear.

**What that command does, in plain English:** `curl` downloads Anthropic's official installer from claude.ai, and `bash` runs it. It installs Claude Code only for your user account, and it keeps itself updated automatically from then on.

### Step 3.3 — Close and reopen the Terminal

This step lets the Terminal recognize the newly installed program.

1. Quit the Terminal completely by pressing **⌘ + Q**.
2. Open it again the same way as Step 3.1 (**⌘ + Space**, type **Terminal**, press **Return**).

### Step 3.4 — Check that the install worked

1. Copy and paste this command, then press **Return**:

   ```
   claude --version
   ```

2. You should see a version number, something like `2.1.211 (Claude Code)`. The exact number doesn't matter; seeing any number means it worked.

**If you instead see `command not found: claude`**, paste the following command and press Return. It tells your Terminal where Claude Code was installed:

```
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc && source ~/.zshrc
```

Then run `claude --version` again. If it still doesn't work, jump to **Troubleshooting** at the end of this guide.

### Step 3.5 — Create a practice folder (recommended)

Claude Code works on the files in whichever folder your Terminal is "in." It's a good habit to give it its own folder to start.

1. Paste this command and press **Return**. It creates a folder called `claude-practice` in your home folder:

   ```
   mkdir ~/claude-practice
   ```

2. Paste this command and press **Return**. It moves the Terminal "into" that folder (`cd` stands for "change directory"):

   ```
   cd ~/claude-practice
   ```

   Your prompt will now show `claude-practice` in it, which tells you where you are.

### Step 3.6 — Start Claude Code and sign in

1. Type the following and press **Return**:

   ```
   claude
   ```

2. The first time, Claude Code asks you a few setup questions. Use the **up and down arrow keys** to move between choices and press **Return** to select:
   - **Choose a color theme** — pick whichever looks easiest to read.
   - **Choose how to log in** — select the option for your **Claude account with a subscription** (this covers Team plans). Do **not** choose the API/Console option.
3. Your web browser will open to a Claude authorization page. Sign in with **SSO** if asked, make sure your **team organization** is selected, and click **Authorize**.
4. When the browser says you're done, switch back to the Terminal window (click it, or press **⌘ + Tab** until it's selected).
5. Claude Code may ask whether you **trust the files in this folder**. Since it's your own practice folder, choose **Yes**.

### Step 3.7 — Say hello

1. You'll now see a box with a `>` prompt inside it. That's Claude Code waiting for you.
2. Type a message in plain English and press **Return**. For example:

   ```
   Create a file called hello.txt that says welcome to the team
   ```

3. Before Claude Code changes anything on your computer, it asks for your permission. Read what it wants to do, then use the arrow keys to choose **Yes** and press **Return**.
4. To see the result, open Finder, press **⌘ + Shift + H** to go to your home folder, and open the **claude-practice** folder. Your new `hello.txt` file will be there.

### Step 3.8 — Exit Claude Code

When you're finished, type `/exit` and press **Return** (or press **Control + C** twice). You'll return to the normal Terminal prompt.

**Next time**, you only need three steps: open Terminal, `cd` into your folder, and type `claude`. You won't need to install or sign in again.

### ✅ Section 3 checkpoint

You're done with this section when typing `claude` in the Terminal opens Claude Code, you're signed in with your team account, and Claude responds to your message.

---

## Troubleshooting

**I never received an invitation email.**
Check spam and junk folders, then ask Donald Turner to resend it to your work email address.

**I signed in but don't see my organization's name.**
You probably signed in with a personal email. Sign out (click your name in the bottom-left, then **Log out**), then sign back in using your work email or company SSO.

**The Mac says the app "can't be opened."**
Open **System Settings → Privacy & Security**, scroll down, and click **Open Anyway** next to the message about Claude. Only do this for the app you downloaded from claude.ai.

**`command not found: claude` in the Terminal, even after the fix in Step 3.4.**
Quit Terminal fully with **⌘ + Q**, reopen it, and try `claude --version` again. If that still fails, run the install command from Step 3.2 once more and read the final lines it prints, since they sometimes include a specific instruction to copy and run.

**The install command shows an error like `403` or `curl: (6)`.**
Your network may be blocking the download. This is common on company VPNs or guest Wi-Fi. Try a different network, or ask IT to allow access to `claude.ai`.

**The browser didn't open when signing in to Claude Code.**
Look in the Terminal for a long web link. Hold **⌘** and click it, or copy and paste it into your browser's address bar.

**Claude Code says my account doesn't have access.**
Your team seat may not include Claude Code, or you may have authorized a personal account by mistake. Type `/login` inside Claude Code to sign in again and choose your team organization. If it still fails, ask Donald Turner to confirm your seat includes Claude Code.

**Want a full health check?**
Run this in the Terminal (outside of Claude Code) and share the output with IT if you need help:

```
claude doctor
```

---

## Helpful Links

- Claude Help Center: https://support.claude.com
- Claude Code installation docs: https://code.claude.com/docs/en/setup
- Anthropic's beginner terminal guide: https://code.claude.com/docs/en/terminal-guide
- Download the desktop app: https://claude.ai/download
