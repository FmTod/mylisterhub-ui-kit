---
name: mylisterhub-ui
description: >-
  Prototype MyListerHub screens as static HTML that look like the real app.
  Use when asked to mock up, prototype or design a MyListerHub page, modal,
  table, form or component, or to restyle a mock so it matches MyListerHub.
---

# MyListerHub UI prototypes

MyListerHub is a multi-marketplace listing tool for eBay sellers. Its screens are dense,
utilitarian and built from a few repeated parts. A prototype that looks right is one assembled from
those parts, not designed fresh. This kit gives you the parts as plain CSS classes (`mlh-*`) and three
page templates measured from the running app.

- `DESIGN.md`: the visual language (palette, type, shape, layout). Read it once before your first prototype.
- `assets/tokens.css`: every colour and radius, in light and dark. It is generated from the app, so never edit it.
- `assets/components.css`: the `mlh-*` classes.
- `templates/`: `list.html`, `record.html` and `settings.html`. Each is a working page with the app frame.
- `screens/`: screenshots of the real app to compare against.

## Steps

1. **Pick the archetype.** Every MyListerHub screen is one of these:

   | The screen… | Archetype | Start from |
   | --- | --- | --- |
   | shows many records in a table with filters | list page | `templates/list.html` |
   | creates, edits or shows one record | record page | `templates/record.html` |
   | configures the account | settings page | `templates/settings.html` |
   | asks for a few fields or a confirmation over a page | modal | the `#create-modal` block in `templates/list.html` |

   Done when you can name the archetype and its template.
2. **Copy the template** to a new `.html` file in the user's working directory. Replace each
   `<link href="../assets/….css">` with a `<style>` block holding that file's full contents, so the
   prototype is a single file that opens anywhere. Done when the copied file renders on its own, with
   no broken styles.
3. **Fill it with the user's content**, using only the parts in [Parts](#parts). Keep the
   `FRAME` block (top bar and side nav) untouched apart from moving `is-active`. Done when every
   element on the screen uses an `mlh-*` class or a plain semantic tag the kit styles.
4. **Run the checklist** below. Done when every box holds.
5. **Render and compare.** Open the file at 1280×800 in light mode and in dark mode (the moon button
   toggles `html.dark`). Put it next to the matching screenshot in `screens/` and fix any mismatch in
   spacing, weight or colour. Done when a reader couldn't tell from the frame which one is the mock.

## Parts

Each part maps to a real app component, which is the name developers will use when they build it.
Put that name in an HTML comment above each block (`<!-- FormSection: Pricing -->`) so the handoff
maps one to one.

| Need | Classes | App component |
| --- | --- | --- |
| Title row of a page | `mlh-page-header` with `__title` (`h1`, back button, badges), `__center`, `__actions` | `PageHeader` |
| Tabs between sibling pages | `mlh-tabs` inside `mlh-page-header__title`, active link `is-active` | `SectionLayout` tabs |
| Status filter chips under the header | `mlh-chips` holding `mlh-btn mlh-btn--sm`; selected chip `mlh-btn--selected`, others `--secondary` | `TabulatorViewChips` |
| Data table | `mlh-table-wrap` > `table.mlh-table`, filters in `th`, checkbox column `mlh-col-check`, actions column `mlh-col-actions`, then `mlh-table-footer` | Tabulator table |
| Record page body | `mlh-record` (add `--wide` with a nav), `__nav` for jump links, `__body`, optional `__aside`; the page's `main` gets `mlh-main--grey` | `RecordPage` |
| Group of fields or details | `section.mlh-section` > `__header` (`h2`, `__description`, `__actions`) + `__body` | `FormSection` |
| Save row | `mlh-action-bar` with optional `__start`, then Cancel `mlh-btn--cancel`, Save `--primary`, Save & Close `--secondary` | `SaveBtn` + `CancelBtn` |
| Settings page | `mlh-subnav` beside `main`, content in `mlh-container` | `SettingLayout` |
| Field | `label.mlh-field` > `span.mlh-label` + `mlh-input` / `mlh-select` / `mlh-textarea`, then `mlh-help` or `mlh-error`; invalid control `is-invalid` | `MdbInput`, `MdbSelect` |
| Field layout | `mlh-grid mlh-grid--2/3/4`, `mlh-span-2` | Bootstrap row/col |
| Checkbox / switch | `label.mlh-check` / `label.mlh-switch` around an `input[type=checkbox]` | `MdbInput type=checkbox`, `MdbToggle` |
| Button | `mlh-btn` + `--primary`, `--secondary`, `--danger`, `--outline-danger`, `--warning`, `--ghost`, `--link`; sizes `--sm`, `--lg`, `--icon`, `--icon-sm` | `Button` |
| Status chip | `mlh-badge` + `--success`, `--info`, `--warning`, `--danger`, `--secondary`, `--alternate`, `--light`, `--dark`, `--outline`; `--pill` for counts | `Badge` |
| Inline message | `mlh-alert` + `--primary`, `--success`, `--info`, `--warning`, `--danger`, with an icon, `strong` title and text | `Alert` |
| Modal | `mlh-backdrop` > `mlh-modal` (`--sm`, `--lg`, `--xl`) > `__header` (`h5`, close button), `__body`, `__footer` | `ModalDialog` |
| Toast | `mlh-toast` + `--success`, `--warning`, `--danger` | `toast.success()` |
| Read-only details | `dl.mlh-details` with `dt` / `dd` pairs | detail block in a `FormSection` |
| Empty / loading | `p.mlh-empty`, `div.mlh-skeleton`, `div.mlh-spinner` | — |
| Thumbnail | `mlh-thumb` | — |
| Text helpers | `mlh-muted`, `mlh-small`, `mlh-xs`, `mlh-eyebrow`, `mlh-row`, `mlh-stack`, `mlh-spacer` | — |

Icons are Font Awesome 6 Free (`fa-solid` / `fa-regular`). The app uses the Pro light weight, so
pick the closest free icon and keep it.

## Checklist

- [ ] The page has exactly one `mlh-btn--primary`, for its main action. Toolbar buttons, Cancel in a
      modal, row actions and add-buttons are `--secondary`; destructive ones are `--danger` or
      `--outline-danger`. A primary inside a repeated row or card counts as more than one.
- [ ] The title row is `mlh-page-header`. There's no heading row you built yourself.
- [ ] Every colour comes from a token class or `var(--token)`. No hex, rgb or named colour in the prototype.
- [ ] Status chips use the badge colour for their meaning: success/active `--success`, attention
      `--warning`, failure `--danger`, informational `--info`, neutral `--secondary` or `--light`, high
      priority `--alternate`.
- [ ] A chip row's selected item is `mlh-btn--selected` (indigo), never primary.
- [ ] Text is sentence case, except headings, which the CSS uppercases.
- [ ] Record pages use `mlh-main--grey` with every field group in an `mlh-section`; list pages run
      the table edge to edge with no padding.
- [ ] Both light and dark mode read correctly.
- [ ] Table rows open from a "View / Edit" action button, not from clicking the row.
