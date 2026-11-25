---
title: "Signal vs OS AI agents: what changed, what to check, what builders should learn"
---

# Signal vs OS AI agents: what changed, what to check, what builders should learn

On **20 Nov 2026** Signal published "Signal is Serious About Protecting Your Privacy" (https://signal.org/blog/protecting-your-privacy/). AI agents built into phone operating systems "scan" what's on your screen to answer questions. Signal says that captures your messages and puts them in whatever database or server the agent uses, outside Signal's control. So it now blocks that capture.

## What it does, platform by platform
| Platform | What Signal does |
|---|---|
| **iOS 27** | Blocks screenshots inside the app, so Siri AI's Onscreen Awareness can't capture chats. A new **"Block Siri AI"** toggle appears in Signal Settings. |
| **Android** | Automatically turns on **"Screen security"** when it detects an AI assistant (e.g. Gemini Intelligence) trying to read the screen. Not every vendor's Android build can be detected. |
| **Windows 11** | Already done last year: screenshot blocking by default against Microsoft Recall. |
| **macOS** | Not covered. Signal says it can't reliably block screenshots on macOS. |

## Settings to check today
1. **Signal on iOS:** Signal Settings: keep **Block Siri AI** on.
2. **Signal on Android:** Signal Settings: check **Screen security** is on (it also hides chats in the app switcher).
3. **Mac on macOS 27:** System Settings > Siri > **Excluded Apps**: add Signal. This is Signal's own recommendation.
4. Want screenshots back? You can turn the protection off in Signal's settings, but Signal warns this may expose your and your contacts' messages to AI agents.

**Limits Signal admits:** blocking screenshots doesn't stop every route. An agent could still read files already on the device. Third-party agents that use accessibility permissions are another route (Signal names Meta's Muse).

## If you build an AI agent that reads screens or notifications
- **Expect to be blocked.** Privacy apps will hide from screenshots. Handle a blank or secure window as "no access", not as an error to work around.
- **Accessibility is not a skeleton key.** Signal calls out agents that use accessibility permissions to reach app data. Ask for the narrowest access and say why.
- **Screens aren't the only leak.** Signal wants an opt-out that also covers the filesystem, notifications and APIs. Don't index notification text from messaging apps by default.
- **Keep captured data local and short-lived**, and let users exclude apps.

## If you build an app with sensitive screens
- Android: set `WindowManager.LayoutParams.FLAG_SECURE` on screens with OTPs, chats or payment details. Android's docs: it keeps the window "from appearing in screenshots or from being viewed on non-secure displays". https://developer.android.com/reference/android/view/WindowManager.LayoutParams#FLAG_SECURE
- Signal's two asks to Apple, Google and Microsoft: an easy, documented way for apps to **opt out of AI data access**, and clear docs on how OS agents access and process data.

## Sources (checked 25 Nov 2026)
- https://signal.org/blog/protecting-your-privacy/
- https://developer.android.com/reference/android/view/WindowManager.LayoutParams#FLAG_SECURE

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
