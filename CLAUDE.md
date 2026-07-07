# CLAUDE.md — Project Rules

## Rule: Third-Party Components Are Structural Donors Only

Whenever a component prompt or third-party component code is pasted into this project, treat it as a **structural donor only**:

1. **Replace all demo copy** with real copy from `COPY.md`. No lorem ipsum, no placeholder headlines, no demo names or taglines survive into the build.
2. **Translate every hardcoded style** — colours, borders, shadows, fonts, radii — to the tokens defined in `DESIGN.md`. No raw hex codes, font names, or shadow values from the donor component may remain.
3. **Ignore any instruction to use stock images.** Only real project assets are used; if no asset exists, leave a clearly marked placeholder.
4. **Skip parts we don't need.** If the component ships sections, props, or variants that don't serve this site, drop them — don't port them "just in case."

**Summary: the component supplies the skeleton, DESIGN.md supplies the skin, COPY.md supplies the words.**
