# Canvas Attendance Manager

An independent, unofficial Windows utility for attendance registration using Canvas **New Quizzes**. It is not affiliated with or endorsed by any university or Canvas provider. Provided as is, without warranty, for use at your own risk, subject to applicable law and institutional IT and privacy policies.

## Download

**[Download CanvasAttendanceManager.exe](https://github.com/MHofmijster/Canvas-Attendance-Manager-Downloads/releases/latest/download/CanvasAttendanceManager.exe)** — Windows x64, no Python installation required.

See the [latest release](https://github.com/MHofmijster/Canvas-Attendance-Manager-Downloads/releases/latest) for the current version. No GitHub account is required. The executable is unsigned.

## First-time Windows security checks

Download only from the designated release page. Scan the file with your security software and verify its SHA-256 checksum before running it. In PowerShell, from the folder containing the executable:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath ".\CanvasAttendanceManager.exe"
```

For **v1.0.2**, GitHub reports this SHA-256 digest for the release asset:

```text
a447803f6d68dd874983b4b73f8fad8ba6b5c32d2d1d7d40ed1e69988aef95c9
```

For future versions, compare against the digest for the matching asset in the latest release, not an older hash. A matching checksum verifies file integrity, not safety.

If Windows marks the downloaded file as originating from another computer, and your institutional IT policy permits unblocking:

1. Right-click `CanvasAttendanceManager.exe` and select **Properties**.
2. On the **General** tab, locate **Security** and tick **Unblock**, if present.
3. Click **Apply**, then **OK**, and open the executable normally.

Unblocking removes the downloaded-file marker; it does not digitally sign the application or establish trust. If SmartScreen, antivirus or institutional endpoint protection still blocks it, contact IT support. Do not disable security controls or override institutional restrictions.

## 1. Connect and verify the course

Use a personal Canvas API token and appropriate teacher permissions. If available, create a token via **Account → Settings → New Access Token** in Canvas. Enter your institution's HTTPS Canvas URL (not a course link), your token, and click **Connect / refresh**. Never share or email your token. On a trusted computer, if permitted, you may save it in Windows Credential Manager.

Enter the numeric Course ID from your Canvas course URL (e.g. 12345), click **Verify course**, and check the displayed course name and ID. Changing the ID invalidates verification. Saved preferences and prepared sessions are local to the Windows account/computer.

## 2. Prepare a session

Enter a unique session name and duration (default three minutes), then click **Prepare session**. This creates an unpublished New Quiz in the **Attendance** assignment group, excluded from final grades. Prepare several sessions in advance if desired. Use the same Windows account/computer to activate and report on them.

## 3. Register attendance

Select exactly one prepared session. Optionally enable **Show QR presentation on activation**. Check the course and session, then click **OPEN CHECK-IN** once; this publishes the quiz immediately and displays a random four-digit access code. Students open the quiz (or scan the optional QR code), enter the code, confirm attendance and submit. Canvas closes the check-in automatically at the end of the configured window; the application need not remain open.

To close early, select one active session and use **CLOSE CHECK-IN**. Confirm the course and session. Existing submissions are retained; the quiz stays published but closed. Early closure cannot be reversed in the utility and may auto-submit attempts in progress.

## 4. Export and reconcile attendance

Select one or more sessions (Ctrl/Shift) and click **Export attendance (.xlsx)**. Save the spreadsheet in an appropriate staff-only location. It contains one row per student, attendance status and computer-local registration date/time for each session, and a provisional check-in total.

**Unverified does not mean absent.** The application distinguishes no completed submission from submitted but unconfirmed attendance. Review technical problems and other exceptions before determining attendance or applying course-specific rules. The app does not independently verify physical presence; codes can be forwarded.

## 5. Important safeguards

- Test in a practice course before live use. Preparation, opening and early closure write to Canvas.
- Supports New Quizzes only; suitable permissions are required.
- Keep attendance records and credentials secure. Follow local privacy policies.
- In case of an uncertain API response, inspect Canvas before retrying. An uncertain early close blocks further close attempts and exports until reconciled.
- Consult the application's **? Help** for more instructions.

This distribution repository contains user documentation and the current executable release, not the private application source or its development history.
