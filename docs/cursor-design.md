# Cursor Design

The monitor uses monotonic cursors.

Rules:

- Never move backwards because of late indexed content.
- A lower ID with newer indexing time does not replace the scan cursor.
- Runtime state stays outside the repository.
- Repository files define policy, not current observations.
