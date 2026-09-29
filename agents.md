# agents.md

Instructions for any AI coding agent working on this project. Read this file fully before making changes.

## Project overview

A simple, fast todo list web app. Users can add tasks, mark them done, edit them, delete them, filter by status, and clear finished tasks. Tasks are saved in the browser so they survive a page refresh.

## Tech stack

- Plain HTML, CSS and vanilla JavaScript in a single file: `index.html`
- No frameworks, no build step, no backend
- Fonts from Google Fonts (Bricolage Grotesque for headings, Atkinson Hyperlegible for body text), with system font fallbacks
- Data is stored in `localStorage` under the key `todo-list-v1`

## File structure

```
/
├── index.html   # The entire app: markup, styles and script
└── agents.md    # This file
```

Keep everything in `index.html` unless the project grows large enough to justify splitting it. If you split it, update this file.

## How to work on this project

1. **Understand before changing.** Read `index.html` and this file before editing anything.
2. **Plan first.** Before writing code, state in a few sentences what you will change and why.
3. **Make small, focused changes.** One feature or fix at a time. Do not rewrite working code without a reason.
4. **Test after every change.** Open `index.html` in a browser and check the test checklist below.
5. **Explain what you did.** Summarise the change and anything the user should know.

## Coding rules

- Use `const` and `let`, never `var`.
- Never insert user-typed text with `innerHTML`. Use `textContent` to prevent script injection.
- Wrap every `localStorage` read and write in `try/catch`, and make the app work even if storage is empty or unavailable.
- Keep the data shape consistent: each task is `{ id: string, text: string, done: boolean }`.
- Call `save()` then `render()` after any change to the task list.
- Keep functions short and named clearly for what they do.
- Comment only where the reason for the code is not obvious.

## Design rules

- Colours are defined as CSS variables on `:root`. Use the variables, never hard-coded colours.
- Support both light and dark mode through the existing variable overrides.
- The layout must work on phones (down to 320px wide) and on desktop.
- Every button must be reachable by keyboard and have a visible focus outline.
- Icon-only buttons need an `aria-label`.
- Respect `prefers-reduced-motion`.
- Write interface text in plain, sentence-case language. Buttons say exactly what they do ("Add", "Clear finished tasks").

## Test checklist

Before finishing any change, confirm:

- [ ] A new task can be added with the button and with the Enter key
- [ ] Empty or whitespace-only tasks are ignored
- [ ] Tasks can be marked done and un-done
- [ ] Double-clicking a task lets you edit it; Enter saves, Escape cancels
- [ ] Tasks can be deleted
- [ ] The All / To do / Done filters show the right tasks
- [ ] "Clear finished tasks" removes only completed tasks
- [ ] The task counter is correct
- [ ] Tasks are still there after refreshing the page
- [ ] The app looks right in light mode, dark mode and on a phone screen

## Deployment

The app is a single static file, so it can be hosted anywhere that serves HTML: a Claude artifact link, GitHub Pages, Netlify or Vercel. After deploying, open the live link and run the test checklist again.

## Ideas for future work

- Due dates and reminders
- Drag-and-drop reordering
- Task categories or colour tags
- Sync across devices with a backend or database
