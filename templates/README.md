# Templates

This folder contains reusable configuration templates for the custom Jira Agile workflow and dashboard showcased in this project.

These are **descriptive JSON templates** that document the exact setup used to achieve a 20% reduction in test cycle time through improved QA visibility and process flow. Since Jira does not allow direct import of full workflows or dashboards via JSON for Software projects, these files serve as clear, step-by-step blueprints that you (or any Jira administrator) can manually recreate in your own Jira instance.

## Files

- **`qa-optimization-dashboard.json`**  
  Configuration for the "QA Optimization Dashboard".  
  Includes a curated set of gadgets:
  - Created vs Resolved Chart
  - Sprint Burndown Chart
  - Pie Chart: Issues by Status
  - Issue Statistics: Defects by Priority
  - Average Age Chart for open issues

  **How to recreate**:
  1. Go to Dashboards → Create dashboard.
  2. Name it "QA Optimization Dashboard".
  3. Add each gadget listed in the JSON, using the specified title, type, and JQL filter (replace `PROJ` with your actual project key).

- **`qa-optimized-workflow.json`**  
  Full definition of the "QA Optimized Workflow" with dedicated testing statuses and logical transitions.

  **How to recreate**:
  1. Navigate to Project Settings → Workflows (requires Jira admin permissions).
  2. Create a new workflow or edit an existing one.
  3. Add the statuses listed under `steps`.
  4. Create the transitions exactly as defined in the `transitions` and `globalTransitions` sections.
  5. Associate the workflow with your project's issue types (typically Task, Story, Bug).

## Tips for Implementation

- Replace the placeholder project key `PROJ` with your actual Jira project key in all filters.
- For the dashboard to be most effective, ensure your team consistently uses the custom statuses (especially "In Testing", "Blocked", "Code Review", and "Ready for Deployment").
- The workflow works best in Scrum or Kanban boards with columns mapped directly to the statuses.

Feel free to adapt these templates to your team's specific needs while keeping the core QA-focused improvements intact.

If you implement this in your project and see similar gains, I'd love to hear about it!