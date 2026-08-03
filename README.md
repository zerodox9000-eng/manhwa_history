# Aeon History Archive

This public repository stores Aeon's daily AniList statistic snapshots outside the active backend repository.

Snapshots are independently compressed by year:

```text
anilist/YYYY/YYYY-MM-DD.json.gz
```

`manifest.json` records each snapshot's date, record count, raw and compressed size, and SHA-256 checksums. The backend verifies every manifest entry can be restored before it publishes a new archive commit or removes an old active snapshot.

The live app does not download this repository. It continues to use the compact weekly history and Updates exports from [manhwa_db](https://github.com/zerodox9000-eng/manhwa_db).

To restore one snapshot:

```bash
gzip -dc anilist/YYYY/YYYY-MM-DD.json.gz > YYYY-MM-DD.json
```
