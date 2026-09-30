# DialScript

An IVR testing tool for Amazon Connect and beyond.

**Requires Windows.** Built and tested on Windows 10/11. This will not run on
macOS or Chromebook — there's no version of this app for those platforms.

## Getting Started

1. Extract the zip file to any folder.
2. Double-click `DialScript.exe` to launch.
   - Windows may show a "Windows protected your PC" warning the first time,
     since this is a small independent tool rather than a widely-distributed
     signed app. Click **More info** → **Run anyway**.
3. The app comes pre-loaded with a couple of sample scripts and a sample
   batch, so there's something to try immediately.

That's it — no installation and nothing else to set up.

## What's Inside

- **Environment** — switch between Production, Development, and Integration
  (or add your own) — each keeps its own separate Phone Book, scripts, and
  batches, so testing in one never mixes with another.
- **Phone Book** — save phone numbers you test against regularly, with
  autocomplete when dialing.
- **Script Selector** — save, search, and reload test scripts by name, or
  import one someone shared with you.
- **Call Target & Step Builder** — build a sequence of steps (touch-tone
  input, spoken text, or hang up) to run once a call connects.
- **Batch** — group a few scripts together and run them back-to-back in one go.
- **How to share scripts with others** — a help link at the bottom of the
  app explains how to send a script to someone else, or import one they've
  sent you.

For a full walkthrough of every feature, see **TESTING.md**.

## Notes

- This build allows a limited number of test calls; you'll see a message
  with contact info once you reach the limit.
- **Logging is on by default**, writing to
  `%AppData%\DialScript\Production\Logs\DialScript-log.txt` for both
  individual scripts and batches. Use **Change...** to pick a different file,
  or **Stop** to turn logging off (the app remembers either choice).
- Phone numbers are assumed to be US/Canada (+1).
- Each call runs a fixed script — it doesn't listen to or react to what
  comes back from the other end during the call.
- Recordings are kept only on your PC (or your chosen Recording Location).
  After each one is saved and verified locally, it's removed from Twilio.
- **Transcribe Recording** (checkbox, on by default): after each call, the
  recording is converted to text and written into the log, plus a `.txt`
  next to the `.mp3`. It adds roughly 10-30 seconds per call. Untick it to skip that
  time; to transcribe a call later instead, use **Transcribe a Saved Recording...** and pick the
  `.mp3`. Transcription runs offline on your PC; the first time, it
  downloads a ~140 MB speech model to `%AppData%\DialScript\Models\`.
  Automatic transcripts can contain mistakes — the recording is always the
  source of truth.
