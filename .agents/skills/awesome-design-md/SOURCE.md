# Source and provenance

- **Upstream:** https://github.com/VoltAgent/awesome-design-md
- **Pinned revision:** `3b605329240ce735b510037cca322f1831fdd7f8`
- **Revision date:** 2026-10-14
- **Installed:** 2026-10-27
- **Upstream license:** MIT; see `LICENSE`.

The upstream repository is a Markdown reference library and did not contain an Agent Skill at this revision. This project adds only the local `SKILL.md` wrapper, this provenance file, and the generated `CATALOG.md` index.

The complete upstream `design-md/` directory is vendored unchanged: 84 design-system folders, each with a `DESIGN.md`. Most folders also include the upstream `README.md` pointer. At this pinned revision, the preview files mentioned by older upstream documentation are no longer present in the repository, so the generated catalog links only to files that actually exist. Keeping the collection local avoids network access during normal skill use.

To update this skill deliberately, replace `design-md/` and `LICENSE` from a reviewed upstream revision, regenerate `CATALOG.md`, and update the revision fields above. `npx skills update` does not manage this wrapper because no corresponding upstream `SKILL.md` exists.
