# Contributing back to the original repository

This fork (`jacsif52-5/clure-site`) is based on [`krov-0s9d9x/clure-site`](https://github.com/krov-0s9d9x/clure-site).

## Changes in this fork

### Fix: use Next.js Link for internal navigation (Footer & ArticlesList)

**Problem:** Footer links ("Статьи", "Плейлисты", "О нас") and the "Все статьи" button used plain `<a href>` tags, which caused full page reloads and redirected to the home page instead of navigating to the correct page.

**Solution:** Replaced `<a href>` with Next.js `<Link>` components for all internal navigation links.

**Files changed:**

- `components/Footer.js` — Internal footer links now use `<Link>` instead of `<a>`
- `components/ArticlesList.js` — "Все статьи" button now uses `<Link>` instead of `<a>`, added `import Link from 'next/link'`

### Cleanup

- Removed tracked `.DS_Store` file and added `.DS_Store` to `.gitignore`

## How to push these changes to the original repository

1. Go to the original repository: https://github.com/krov-0s9d9x/clure-site
2. Click **"New pull request"**
3. Click **"compare across forks"**
4. Set base repository to `krov-0s9d9x/clure-site` (base: `master`)
5. Set head repository to `jacsif52-5/clure-site` (compare: `master`)
6. Review the changes and click **"Create pull request"**
7. Add a descriptive title and body, then submit

Alternatively, use the GitHub CLI:

```bash
gh pr create \
  --repo krov-0s9d9x/clure-site \
  --head jacsif52-5:master \
  --base master \
  --title "fix: use Next.js Link for footer and internal navigation" \
  --body "Replace plain <a href> tags with Next.js <Link> components in Footer.js and ArticlesList.js to enable proper client-side routing instead of full page reloads."
```
