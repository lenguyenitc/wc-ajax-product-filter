# WCAPF custom code handoff

Date: 2026-09-04

This repo contains local custom changes on top of the upstream WCAPF plugin. The current git diff shows these are the files to review before any plugin update or rebase.

## Quick summary

- The plugin header was customized in [wc-ajax-product-filter.php](wc-ajax-product-filter.php), including a custom plugin name and version override (`999999.99`).
- The filter accordion trigger received accessibility updates in [templates/filter-title.php](templates/filter-title.php), including `aria-label` and SVG accessibility attributes.
- The frontend JavaScript in [public/js/wc-ajax-product-filter-scripts.js](public/js/wc-ajax-product-filter-scripts.js) includes custom handling for accordion toggles, hierarchy toggles, soft-limit behavior, filter input search, range/date pickers, and a popstate reload hook.
- Several core plugin files were modified and should be treated as custom/local overrides until they are compared with the upstream version:
  - [includes/class-wcapf-form.php](includes/class-wcapf-form.php)
  - [includes/class-wcapf-frontend-scripts.php](includes/class-wcapf-frontend-scripts.php)
  - [includes/class-wcapf-helper.php](includes/class-wcapf-helper.php)
  - [includes/class-wcapf-walker.php](includes/class-wcapf-walker.php)

## What to check before updating

1. Compare the forked files with upstream and re-apply any wanted custom logic.
2. Review the `die;` in [includes/class-wcapf-product-filter.php](includes/class-wcapf-product-filter.php) before shipping or upgrading.
3. Confirm the JS behavior in [public/js/wc-ajax-product-filter-scripts.js](public/js/wc-ajax-product-filter-scripts.js) still matches the site’s expected AJAX/filter flow.
4. Re-test the filter UI on a staging site after any upstream update.

## Notes

This is intentionally a lightweight handoff document. If the plugin is updated later, use the git diff from this repo as the source of truth for what was customized here.
