# Deployment — GitHub Pages

This guide covers the existing **`divyasomaiya/stdtc`** repository and custom domain **`dtcst.clickworthybydtc.in`**.

## 1. Repository files

Keep `index.html` and `CNAME` in the repository root on the `main` branch.

```text
/index.html
/CNAME
```

The custom-domain file should contain exactly:

```text
dtcst.clickworthybydtc.in
```

Do not name the homepage `index.html.html`.

## 2. GitHub Pages settings

Go to **Repository → Settings → Pages**.

- **Source:** Deploy from a branch
- **Branch:** `main`
- **Folder:** `/ (root)`
- **Custom domain:** `dtcst.clickworthybydtc.in`

The site automatically rebuilds after commits to the publishing branch.

## 3. Cloudflare DNS

If Cloudflare is the authoritative DNS provider for `clickworthybydtc.in`, create this record:

| Field | Value |
| --- | --- |
| Type | `CNAME` |
| Name | `dtcst` |
| Target | `divyasomaiya.github.io` |
| Proxy status | DNS only (grey cloud) |
| TTL | Auto |

Keep other unrelated domain, email, Workers, and subdomain records unchanged.

GitHub Pages should show **DNS check successful** once the record resolves correctly.

## 4. Enforce HTTPS

In **Settings → Pages**, activate **Enforce HTTPS** once GitHub has issued and attached the TLS certificate. The checkbox can remain unavailable while the certificate is still being provisioned, even after the DNS check succeeds. Keep the DNS record unchanged during ordinary provisioning.

Do not enter real financial transactions over an HTTP-only public website. Check for the browser's secure connection indicator first.

Official GitHub help: [Securing GitHub Pages with HTTPS](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https).

## 5. First use on the hosted website

1. Open the hosted HTTPS address.
2. Download a backup from the old local HTML copy before changing devices or domains.
3. Use **Backup & Restore → Restore Backup File** on the hosted site.
4. Review the preview carefully: restoring **replaces** local data on the destination, it does not merge datasets.
5. Confirm the amounts, statuses, reserved advance buckets, transaction counts and screenshots.
6. Save a fresh backup after verifying the hosted copy.

**Important:** `file://`, `https://dtcst.clickworthybydtc.in`, and other origins have separate browser storage. The site being hosted does not move the old database automatically.

## 6. Updating the application

Commit the updated `index.html` to `main` and wait for the GitHub Pages deployment to complete. A normal source-file update at the same domain should not reset the origin's IndexedDB, but **download a JSON backup first** and test new versions before relying on them for real records.

Do not commit actual exported backups, reports, or screenshots to GitHub.
