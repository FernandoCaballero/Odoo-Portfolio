# Migration Notes: project_role 13.0 → 18.0

## Changes made

### __manifest__.py
- Version updated from `13.0.1` to `18.0.1`

### Views (XML)
- Renamed all `<tree>` tags to `<list>`
- Updated `view_mode` fields: `tree` to `list`
- Kanban view: replaced deprecated `kanban-box` template with `card`
- `res_config_settings.xml`: rewrote xpath and view structure to match Odoo 18 settings layout (replaced `div[@data-key='project']` with `app[@name='project']` and used new `<block>` and `<setting>` tags)

### Models (Python)
- `project_project.py`: replaced `track_visibility="onchange"` with `tracking=True`
- `project_project.py`: updated `create` method to use `@api.model_create_multi` decorator and accept `vals_list` instead of single `values`
- `project_role.py`: added `recursive=True` to `complete_name` field
