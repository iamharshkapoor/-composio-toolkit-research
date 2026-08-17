# Populate the GitHub Source Repository

The repository root files are already present. To add the editable source tree through GitHub’s browser upload page, unzip the supplied source bundle, open the extracted `github-source-upload/` folder, and **drag these five folders together** onto GitHub’s **Add file → Upload files** page:

```text
client/
data/
scripts/
server/
shared/
```

GitHub preserves the folders when they are dragged into the page. Enter this commit message and click **Commit changes**:

```text
Add Composio case-study source and research pipeline
```

After the commit, the root `README.md` becomes runnable because its referenced `client/`, `data/`, and `scripts/` paths will exist in the repository.
