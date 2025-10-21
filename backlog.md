\## 🚀 Feature Backlog



This backlog is organised into \*\*Epics\*\* (high-level goals), \*\*Features\*\* (deliverable capabilities), and \*\*User Stories\*\* (descriptions of functionality from a user's perspective).



\### ### Epic 1: Core Reminder Functionality (MVP)



\*As a user, I want a reliable, hourly pop-up for Trello so that I am consistently reminded to review my tasks.\*



---



\#### \*\*Feature 1.1: Scheduled Task Execution\*\*

\*The system must be able to run a script automatically at a set interval.\*



\* \*\*User Story:\*\* As a user, I want a task to run automatically every hour, so I am reminded consistently without needing to start the tool manually.

&nbsp;   \* \*\*Acceptance Criteria:\*\*

&nbsp;       1.  A task must be configured in the OS task scheduler.

&nbsp;       2.  The task must be set to trigger every 1 hour.

&nbsp;       3.  The task trigger must run indefinitely.

&nbsp;       4.  The task can run whether the user is on AC power or battery.



---



\#### \*\*Feature 1.2: Intelligent Browser Launch\*\*

\*The script must open Trello.com in Firefox in a user-friendly way.\*



\* \*\*User Story:\*\* As a user, I want the scheduled task to open `trello.com` in Firefox, so I can review my board.

&nbsp;   \* \*\*Acceptance Criteria:\*\*

&nbsp;       1.  When the task runs, if Firefox is closed, it must be launched.

&nbsp;       2.  If Firefox is already open, the URL `https://trello.com` must be opened in a new tab.

&nbsp;       3.  The task must not open a \*new window\* if Firefox is already running.



---



\#### \*\*Feature 1.3: Window Focus Management\*\*

\*The script must bring the Trello window to the user's immediate attention.\*



\* \*\*User Story:\*\* As a user, I want the Trello window to pop up over my current work, so it immediately grabs my attention.

&nbsp;   \* \*\*Acceptance Criteria:\*\*

&nbsp;       1.  After the Trello tab is opened, the main Firefox window containing it must be brought to the foreground.

&nbsp;       2.  The window must "steal focus" from the currently active application.

&nbsp;       3.  If the Firefox window was minimised, it must be restored to its previous state (e.g., normal or maximised).

&nbsp;       4.  The script must correctly identify the window even if the title includes a specific Trello board name (e.g., "My Board | Trello - Mozilla Firefox").



---



\#### \*\*Feature 1.4: Silent Operation\*\*

\*The script's execution wrapper (the terminal) must be invisible.\*



\* \*\*User Story:\*\* As a user, I want the reminder to run without a terminal or console window flashing, so the experience is not jarring or unprofessional.

&nbsp;   \* \*\*Acceptance Criteria:\*\*

&nbsp;       1.  When the task runs, no PowerShell or Command Prompt terminal window is visible to the user.

&nbsp;       2.  The operation must be "headless" or hidden, with the only visible effect being the Firefox window coming into focus.



---



\### ### Epic 2: V2 Enhancements \& Usability



\*As a user, I want more control over the reminder, so it better fits my workflow and doesn't interrupt me at inconvenient times.\*



---



\#### \*\*Feature 2.1: Specific Board Navigation\*\*

\*Allow the user to be taken to a specific Trello board, not just the homepage.\*



\* \*\*User Story:\*\* As a user, I want the pop-up to open my \*specific\* "To-Do" board, not just the Trello homepage, so I am taken directly to the context I need to review.

&nbsp;   \* \*\*Acceptance Criteria:\*\*

&nbsp;       1.  The URL in the script (PowerShell or Python) must be easily changeable to a specific board URL.

&nbsp;       2.  The window-finding logic must still work when the window title reflects the specific board's name.



---



\#### \*\*Feature 2.2: "Snooze" / Intelligent Interruption\*\*

\*Prevent the pop-up if the user is already actively working in Trello.\*



\* \*\*User Story:\*\* As a user, if I am \*already\* using Trello when the hourly reminder is due, I do not want the script to run, so my window isn't jarringly re-focused.

&nbsp;   \* \*\*Acceptance Criteria:\*\*

&nbsp;       1.  The script must first check what the user's active foreground window is.

&nbsp;       2.  If the active window title already contains "Trello" and "Mozilla Firefox", the script must exit silently.

&nbsp;       3.  If the active window is anything else, the script proceeds with the normal pop-up logic.



---



\#### \*\*Feature 2.3: On-Demand Pause/Resume\*\*

\*Allow the user to temporarily disable the hourly reminder.\*



\* \*\*User Story:\*\* As a user, I want to be able to \*pause\* the reminders, so I am not interrupted during an important meeting or a deep-work session.

&nbsp;   \* \*\*Acceptance Criteria:\*\*

&nbsp;       1.  The user can temporarily disable the `Hourly Trello Popup` task in Windows Task Scheduler.

&nbsp;       2.  The user can re-enable the same task to resume the hourly reminders.



---





