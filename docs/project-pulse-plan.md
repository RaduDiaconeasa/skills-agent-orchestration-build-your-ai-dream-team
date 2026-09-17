# Project Pulse implementation plan

## Goal

Build a lightweight Project Pulse dashboard for Mona's team that gives contributors a clear, readable snapshot of active projects, owners, status, recent activity, priority, and short summary notes. The final result should be a static dashboard that opens from a VS Code launch configuration and presents a polished, contributor-friendly interface.

## Team and responsibilities

### Orchestrator
- Coordinates the workflow between Planner, Designer, and Coder.
- Confirms file ownership, sequencing, and validation steps.
- Keeps the work aligned with the Project Pulse brief and the final handoff requirements.

### Planner
- Defines the implementation phases, dependencies, and validation expectations.
- Identifies the required files and the work needed to turn the brief into a working dashboard.
- Keeps the project delivery path explicit for design, coding, and review.

### Designer
- Owns the dashboard information hierarchy and visual structure.
- Defines the card layout, status badge treatment, spacing, color system, and readability standards.
- Ensures the interface feels polished and easy to scan for contributors.
- Primary responsibility: `app/index.html` and `app/styles.css` design decisions.

### Coder
- Implements the static app experience and data model.
- Builds the HTML, CSS, and JSON structure needed for real dashboard content.
- Creates the launch configuration needed to open the app in the browser from VS Code.
- Primary responsibility: `app/index.html`, `app/styles.css`, `app/project-data.json`, and `.vscode/launch.json`.

## File assignments

- `app/index.html`: Dashboard shell, title, project cards, summary sections, and layout structure.
- `app/styles.css`: Visual styling, status colors, spacing, card layout, and responsive presentation.
- `app/project-data.json`: Top-level `projects` array with each entry including `name`, `owner`, `status`, `recentActivity`, and `priority`.
- `.vscode/launch.json`: VS Code launch config named `Run Project Pulse Dashboard` that serves `app/` and opens `index.html`.

## Implementation phases

### Phase 1: Data and structure setup
- Confirm the required data schema and dashboard content fields.
- Create the project data model in `app/project-data.json`.
- Create the launch configuration in `.vscode/launch.json` so the app can run locally.

### Phase 2: User experience and layout
- Build the dashboard skeleton in `app/index.html`.
- Apply the design system and spacing in `app/styles.css`.
- Include a clear Project Pulse title, project cards, and visual status treatments.

### Phase 3: Integration and polish
- Connect the HTML to the stylesheet and JSON data source.
- Check that the app renders without a directory listing, and the browser opens the dashboard directly.
- Finalize accessibility, readability, and card consistency.

## Dependencies

- The app data structure in `app/project-data.json` should be defined before the HTML renders project values.
- `app/index.html` depends on `app/styles.css` for layout and visual styling.
- The dashboard page depends on the launch configuration to open in the intended browser context.
- The launch config depends on the static app files living under `app/` and serving `index.html` from that directory.

## Parallel work decisions

- Designer and Coder can begin in parallel once the core data schema and brief are clear.
- The Designer can draft the visual hierarchy and card system while the Coder prepares the project structure and data schema.
- The launch configuration can be prepared in parallel with the static page implementation, as long as the final app path and target file match the expected `index.html` behavior.
- The Planner and Orchestrator should review the work together before final validation to ensure the output matches the brief.

## Validation expectations

The dashboard is considered complete when:

- `app/index.html` includes the title `Project Pulse`.
- The app references `styles.css` and the project data file.
- `app/project-data.json` contains a top-level `projects` array.
- `.vscode/launch.json` exists and includes the launch configuration `Run Project Pulse Dashboard`.
- The dashboard loads from `app/index.html` instead of a directory listing.
- All project cards display useful summary fields: project name, owner, status, recent activity, and priority.
- The final presentation is clean, scannable, and contributor-friendly.

## Summary

This plan keeps the work focused on a small, static dashboard while still using the orchestration pattern deliberately. The Planner defines the work, the Designer shapes the user experience, and the Coder implements the final static app and local launch path. Validation ensures the dashboard meets the brief before the handoff is complete.
