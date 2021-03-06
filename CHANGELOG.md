Changelog
=========

2.1
---

New sketch features:
  * Lathe groups create circle and face entities.
  * New toolbar button for creating lathe groups.
  * Chord tolerance is separated into two: display chord tolerance (specified
    in percents, relative to model bounding box), and export chord tolerance
    (specified in millimeters as absolute value).
  * Bezier spline points can be added and removed after the spline is created.
  * When an unconstrained extrusion is switched between "union" and
    "difference", its normal is flipped.
  * Groups can be added in the middle of the stack. Note that this results
    in files incompatible with version 2.0.
  * Active group can be removed.
  * Removing an imported group does not cause all subsequent groups to also
    be removed.
  * When a new group with a solid is created, the color is taken from
    a previous group with a solid, if any.
  * Entities in a newly active group do not become visible.
  * When entities are selected, "Zoom to fit" zooms to fit only these
    entities and not the entire sketch.
  * Zero-length edges are reported with a "zero-length error", not
    "points not all coplanar".

New constraint features:
  * Height of the font used for drawing constraint labels can be changed.
  * New constraint, length difference, placed with J.
    (Patch by Peter Ruevski)
  * Horizontal/vertical constraints are automatically added if a line segment
    is close enough to being horizontal/vertical. This can be disabled by
    holding Ctrl.
  * Reference dimensions and angles can be placed with Shift+D and Shift+N.
  * Copying and pasting entities duplicates any constraints that only involve
    entities in the clipboard, as well as selected comments.
  * Diameter constraints can be shown as radius.
  * The "pi" identifier can be used in expressions.
  * Constraint labels can be snapped to grid.
  * Integer angles are displayed without trailing zeroes.
  * Angle constraints have proper reference lines and arrowheads.
  * Extension lines are drawn for point-line distance constraints.

New solver features:
  * Sketches with redundant and unsolvable constraints are distinguished.
  * New group setting, "allow redundant constraints". Note that it makes
    the solver less stable.

New rendering and styling features:
  * New line style parameter: stippling, based on ISO 128.
  * Outlines of solids can be drawn in a particular style (by default, thick
    lines) controlled by the "Show outline of solid model" button.
  * Occluded edges can be drawn in a particular style (by default, stippled
    with short dashes) controlled by the "Show hidden lines" button.
  * Solids can be made transparent.

New export/import features:
  * The old "import" command (for .slvs files) is renamed to "link".
  * If a linked .slvs file is not found, first the relative path recorded
    in the .slvs file is checked and then the absolute path; this is
    an inversion of the previously used order. If it is still not found,
    a dialog appears offering to locate it.
  * DXF and DWG files can be imported, with point-coincident, horizontal and
    vertical constraints automatically inferred from geometry, and distance
    and angle constraints created when a dimension placed against geometry
    exists.
  * Triangle mesh can be exported for viewing in the browser through WebGL.
  * Export dialogs remember the last file format used, and preselect it.
  * Exported DXF files have exact circles, arcs and splines instead of
    a piecewise linear approximation (unless hidden line removal was needed).
  * Exported DXF files preserve color and line thickness.
  * In exported DXF files, constraints are represented as DXF dimensions,
    instead of piecewise linear geometry.
  * When exporting 2d views, overlapping lines are removed.

Other new features:
  * Native Linux (GTK 2 and GTK 3) and Mac OS X ports.
  * Automatically save and then restore sketches if SolveSpace crashes.
    (Patch by Marc Britten)
  * Unicode is supported everywhere (filenames, group names, TTF text,
    comments), although RTL scripts and scripts making heavy use of ligatures
    are not rendered correctly.
  * The vector font is grid-fitted when rendered on screen to make it easier
    to read regardless of its size.

2.0
---

Initial public release.
