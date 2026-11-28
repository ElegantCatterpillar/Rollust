# Changelog

All notable changes to Rollust are listed here.
The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and versions follow [Semantic Versioning](https://semver.org/).

Write each entry as something the user notices, in one short sentence.

## [Unreleased]

## [1.0.0] - 2026-11-27

### Changed

- Rollust is now freeware under the Rollust Freeware License: still free for personal and commercial use, but its source code is no longer published. Settings → License lists the bundled third-party licenses.

### Added

- Back up several iPhones at once, for example on two USB ports. Each iPhone gets its own folder inside the destination and its own card above the copy, where you pause, cancel, retry or see the result of that iPhone. The tray lists every iPhone and can pause or resume them all, and the next copy of an iPhone goes back to the folder it used before.
- Explore shows how many backed-up files were deleted from the iPhone since, and "View history" lists them with whether the PC copy is still there, plus each iPhone's recent activity. Clean only forgets them in Rollust; it never touches the iPhone or the PC.
- Rollust remembers each iPhone and what was backed up from it and where, in a file encrypted with Windows so only Rollust on your account can read it. Explore marks files backed up and still on the PC in green, and files backed up but no longer at that path in yellow ("No longer there"), with the date and folder; it never searches other folders. Settings → Data can forget it.
- Uninstalling now honors the two boxes in Settings → Uninstall: it deletes your settings, or the scan cache, the iPhone history and the logs, only if you checked them. Your copied photos and their reports are never touched.

## [0.2.0] - 2026-11-24

### Added

- Rollust looks for new versions when it opens and once a day (you can turn it off in Settings → Updates). It only tells you; it downloads and installs a signed update when you click "Download and install", and never during a copy.
- The Source screen keeps looking while iPhones are listed, so you can plug in another one. While waiting it speaks about your iPhone and only mentions that you can connect more than one.
- Closing the window sends Rollust to the tray, and the scan and the copy keep going. The tray icon and the taskbar button show how the copy is going, and choosing Exit during a copy asks first.
- "Delete from iPhone…" on the Result screen shows what it would delete (only files copied and verified), asks you to tick a box and type a word, and checks each file on the PC again before deleting it. It worked on a real iPhone; it stays turned off in builds until you decide to turn it on.
- "Report a problem" on the Result screen opens a GitHub issue already filled in with what happened, the copy and the log, without your Windows user, folders, iPhone name or serial numbers.
- If the iPhone stops answering mid-copy (unplugged or locked), the copy waits for it, reconnects by itself and goes on from the same file.
- Copies photos and videos from an iPhone connected by USB to a folder on the PC.
- The Source screen shows the iPhone model (e.g. "iPhone 15 Pro Max") and the name you gave it.
- Rollust starts Apple's device service by itself when it is off; if it can't, Source and Prepare explain why the model is missing, open Apple Devices, or report the problem on GitHub.
- The steps in the title bar go back to any step you already reached and use the guide colors: green done, blue current, amber with a skipped item, gray not reached.
- The Explore screen lists the iPhone's folders and files so you can pick exactly what to copy, with search and a running total of files and size.
- The Explore screen has a date range: presets (Everything, Over a year old, Last 12 months, This year) with tooltips that explain each one and preview its dates, files and size, From/To dates and a draggable slider over a per-month histogram (hover a month to see its files and size) mark the files to copy, showing what stays out and files with no date.
- The date range moves by whole months by default (month pickers, arrows: 1 month, Shift+arrows: 1 year); the "Pick days" switch turns on day precision, and the choice is remembered.
- The Destination screen picks the folder (with an optional root folder, "Rollust" by default), checks the free space, and remembers the copy options: mode, integrity check on/off, skip existing, deep check, verifier threads, sounds and auto reconnect.
- The Destination screen fits the window without scrolling; skip existing, deep check and verifier threads live in an "Advanced options" window that warns before you change them and only applies them when you confirm.
- Language and theme are picked with compact ES/EN and System/Light/Dark toggles in the title bar.
- The Copy screen shows real progress (files and size copied, speed, time left, files verified, the current file and the last ones checked), pauses and resumes between files, cancels, and alerts with sound and a notification when the iPhone disconnects or locks, the drive fills up, or the copy ends.
- Verifies every copied file (size, hash and decoding) in parallel while the copy continues.
- Report per folder that says which iPhone folders are safe to delete.
- Source screen: pick the connected iPhone (shows iOS version and space used, warns when it is locked); other connected drives show only as a small line, not as rows. While no iPhone is found it waits, detects it by itself and lists the steps, including installing Apple Devices for the USB driver.
- Skips files that were already copied, so an interrupted copy resumes where it stopped.
- Logs in `%LOCALAPPDATA%\Rollust\logs` (last 7 days) to help report problems.
- Desktop app with light and dark themes, in English and Spanish.
- Step-by-step "Prepare iPhone" guide: one setting per view with an illustration of the iPhone screen, skip or go back at any step, a summary at the end and a new photo check. It remembers where you left it.
- The "Prepare iPhone" guide starts with a step done on the PC: it checks the Apple Devices app and Apple's USB driver separately, opens the app if it is installed (or Microsoft Store if not) and keeps checking until the driver appears. While the driver is missing the step cannot be skipped.
- The guide summary fits the window without scrolling: the photo check and the settings reminder sit beside the list.
- The guide's progress bar is clickable: jump straight to any step you already passed or answered, also from the final summary.
- The guide's progress bar grows when you hover it and shows the name of the step it takes you to. It only opens steps you already reached, and its colors say how each one went: gray not reached yet, blue current, green done, amber skipped.
- The guide summary no longer cuts off its list in small windows; the page scrolls instead.
- Checks a sample photo and tells you whether the iPhone sends original HEIC files or slower converted ones.
- Optional auto reconnect: after one Windows administrator prompt, the app can restart a hung iPhone USB connection on its own.
- The installer installs for all users, and uninstalling also removes the auto reconnect permission.
- The Explore screen opens with the iPhone's last scan at once and checks for changes in the background, folder by folder, marking new files; you can pick files and continue before it ends. If the iPhone can't be opened when the copy starts, "The iPhone was disconnected" offers Retry and keeps your selection.
- The Result screen lists each copied folder with its files, size and OK / warning / failed counts, and only marks it "Safe to delete" when every file of that folder was copied and verified. Filter the folders with failures, retry only the failed files, open the report or the destination folder, and get a reminder to set the iPhone settings back.
- The Result screen puts "Open report" and "Open destination folder" next to the title, and the reminder comes before the folder list. "Auto-Lock" and "USB Accessories" in the reminder open a popup that shows how to set each one back. A long folder list now scrolls inside its table, so the buttons stay in view.
- Rollust now has a license: free for personal and commercial use, changes go only to the original repository, copies can't be shared, and anything that shows Rollust must name its repository.
- RustSave is now called Rollust. Your settings, saved scans, logs, theme and language move to the new name on first start (close RustSave first). Auto reconnect has to be turned on again once, and uninstalling also removes the old permission.
- A "Test" button next to "Sounds and notifications" plays the alert sound, shows a Windows notification and flashes the taskbar, and says what did not work.

### Fixed

- While a big video copies, the copy screen keeps counting its bytes, speed and time left instead of looking stuck until the file ends.
- "Open on GitHub" copies a long report before opening the browser, so it is really on the clipboard to paste; if a copy fails, the dialog says so.
- When checking the iPhone for changes takes long (often right after reconnecting it), the Explore screen says the iPhone is answering slowly.
- Counts of one read correctly ("1 archivo", "Se borró 1 archivo", "1 file") instead of the plural form, and the Result summary reads "0 fallos" / "1 aviso" instead of "0 fallo" / "1 avisos".
- A copy stopped by a lost iPhone now offers "Ver resultado" next to "Reintentar", so its partial result and the report are reachable.
- The reconnect notice now also asks to unlock the iPhone, since Windows does not see it while it is locked.
- A reloaded window no longer loses a running copy: the copy screen comes back with its progress (and its result once it ends), and an alert that already played does not play again.
- The Copy screen shows the total size and the time left instead of "NaN".
- Unplugging the iPhone during a copy now stops it with a lost-connection alert, instead of marking every remaining file as failed.
- The guide summary shows your connected iPhone with the same details as the Source screen, instead of a sample-photo check that often could not finish.
- In the light theme, text on blue, green and amber buttons and badges is white, so it reads clearly.
- Canon RAW photos (.CR3) copied from the iPhone no longer show a warning saying their extension does not match their content.
