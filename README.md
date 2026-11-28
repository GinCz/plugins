# ⚡ WordPress Ultra-Light Plugins Suite (VladiMIR+AI)

> **Repository:** [GinCz/plugins ↗](https://github.com/GinCz/plugins)  
> **Author:** `VladiMIR (GinCz) + AI`  
> **Brand Tag:** `(VladiMIR+AI✅)`  
> **Version Format:** `YYYY-MM__G.BB` (e.g. `2026-09__1.31`)  

A collection of ultra-lightweight, secure, and high-performance micro-plugins for **WordPress** and **WooCommerce**, engineered by **VladiMIR (GinCz) + AI** and **Antigravity AI**.

These plugins serve as clean, 100% ad-free replacements for bloated third-party plugins from WordPress.org. They eliminate aggressive upgrade banners, tracking scripts, slow database queries, and vulnerable dashboards.

---

## 🔄 How the Native WordPress Auto-Update System Works

All plugins in this repository automatically update directly from WordPress without requiring external updater plugins, WP-CLI daemons, or paid licenses.

### 1. Architecture & Mechanism
```
┌───────────────────────────────┐
│     WordPress Admin / Core    │
│  (wp_version_check / WP-Cron) │
└───────────────┬───────────────┘
                │
                ▼ (Intercepted via 'Update URI: https://vladimir-ai.updates/<slug>')
┌───────────────────────────────┐
│   vladimir-ai-updater.php     │
│   (Shared Client in Plugins)  │
└───────────────┬───────────────┘
                │
                ▼ (HTTPS GET with 6-hour Transient Cache)
┌────────────────────────────────────────────────────────────────────────┐
│  https://raw.githubusercontent.com/GinCz/plugins/main/updates.json    │
└───────────────┬────────────────────────────────────────────────────────┘
                │
                ▼ (If new version available > installed version)
┌───────────────────────────────┐
│ WordPress Core Plugin Upgrader│ ──▶ Downloads ZIP: https://raw.githubusercontent.com/.../zips/<slug>.zip
│                               │ ──▶ Overwrites wp-content/plugins/<slug>/ seamlessly
└───────────────────────────────┘
```

1. **Header Declaration:** Each plugin specifies `Update URI: https://vladimir-ai.updates/<slug>` in its main PHP header. This tells WordPress core to bypass `wordpress.org` checks for this slug and route requests to our filter hook `update_plugins_vladimir-ai.updates`.
2. **Shared Updater Client (`vladimir-ai-updater.php`):** A byte-identical copy is included in each plugin. The first loaded plugin activates the updater, while others short-circuit, ensuring exactly one cacheable HTTP request.
3. **Manifest (`updates.json`):** Hosted in this public repository at `https://raw.githubusercontent.com/GinCz/plugins/main/updates.json`. WordPress caches the manifest in `_vladimir_ai_manifest` site transient for 6 hours.
4. **Security & Validation:** `vladimir_ai_update_package_allowed()` strictly enforces an allow-list: packages must originate from `https://github.com/GinCz/plugins/` or `https://raw.githubusercontent.com/GinCz/plugins/`.
5. **Admin Details Modal:** The updater hooks into `plugins_api` to render full plugin information, changelogs, and author details inside the native WordPress update dialog.

---

## 📦 Plugins Catalog (13 Modules)

| # | Plugin Slug | Name | Replaces | Action Links |
| :-: | :--- | :--- | :--- | :--- |
| **1** | [`404-410-301`](./404-410-301/) | `404-410-301 (SEO 404/410 + Auto-Redirect) (VladiMIR+AI✅)` | *404 to 301, Redirection* | Settings • Docs |
| **2** | [`classic-editor-tinymce`](./classic-editor-tinymce/) | `Classic Editor - TinyMCE (VladiMIR+AI✅)` | *Classic Editor + TinyMCE Advanced* | Settings • Docs |
| **3** | [`clean-head-meta`](./clean-head-meta/) | `Clean Head Meta & Anti-Fingerprint (VladiMIR+AI✅)` | *Head Meta Data, WP Hide* | Settings • Docs |
| **4** | [`disable-update-emails`](./disable-update-emails/) | `Disable Update Notification Emails (VladiMIR+AI✅)` | *Manage Notification E-mails* | Settings • Docs |
| **5** | [`image-resizer`](./image-resizer/) | `Image Resizer on Upload (VladiMIR+AI✅)` | *Imsanity, Resize Images* | Settings • Docs |
| **6** | [`translit-cyr-lat`](./translit-cyr-lat/) | `Cyrillic & European to Latin SEO Transliteration (VladiMIR+AI✅)` | *Cyr-To-Lat, RusToLat* | Settings • Docs |
| **7** | [`wp-allow-html-cats`](./wp-allow-html-cats/) | `Allow HTML in Category & Taxonomy Descriptions (VladiMIR+AI✅)` | *Allow HTML in Category Descriptions* | Settings • Docs |
| **8** | [`wp-auto-sku`](./wp-auto-sku/) | `WooCommerce Auto SKU Generator & SKU Search (VladiMIR+AI✅)` | *Easy Auto SKU Generator* | Settings • Docs |
| **9** | [`wp-bulk-delete-clean`](./wp-bulk-delete-clean/) | `WP Bulk Delete Clean (VladiMIR+AI✅)` | *WP Bulk Delete, Bulk Delete* | Tools • Docs |
| **10** | [`wp-online-counter`](./wp-online-counter/) | `Live Active Users & Visitors Counter (VladiMIR+AI✅)` | *Online Active Users, WP Online Counter* | Settings • Docs |
| **11** | [`wp-seo-micro`](./wp-seo-micro/) | `WP SEO Micro (VladiMIR+AI✅)` | *Yoast SEO, Rank Math, SEOPress* | Settings • Docs |
| **12** | [`wp-simple-post-order`](./wp-simple-post-order/) | `WP Simple Post & Category Order (VladiMIR+AI✅)` | *Simple Custom Post Order, Post Types Order* | Settings • Docs |
| **13** | [`wp-test-email-micro`](./wp-test-email-micro/) | `WP Test Email Micro (VladiMIR+AI✅)` | *WP Test Email* | Tools • Docs |

---

## 📥 Direct Download Center (Ready-to-Install ZIP Packages)

All plugins can be downloaded as standalone `.zip` archives ready for immediate installation via **WordPress Admin ➔ Plugins ➔ Add New ➔ Upload Plugin**:

| # | Plugin Name | Slug | Version | 1-Click Download | Documentation |
| :-: | :--- | :--- | :-: | :--- | :--- |
| **1** | 404-410-301 SEO & Redirect | `404-410-301` | `1.33` | [📥 Download ZIP](https://raw.githubusercontent.com/GinCz/plugins/main/zips/404-410-301.zip) | [Readme](https://github.com/GinCz/plugins/tree/main/404-410-301) |
| **2** | Classic Editor - TinyMCE | `classic-editor-tinymce` | `1.31` | [📥 Download ZIP](https://raw.githubusercontent.com/GinCz/plugins/main/zips/classic-editor-tinymce.zip) | [Readme](https://github.com/GinCz/plugins/tree/main/classic-editor-tinymce) |
| **3** | Clean Head Meta & Anti-Fingerprint | `clean-head-meta` | `1.31` | [📥 Download ZIP](https://raw.githubusercontent.com/GinCz/plugins/main/zips/clean-head-meta.zip) | [Readme](https://github.com/GinCz/plugins/tree/main/clean-head-meta) |
| **4** | Disable Update Notification Emails | `disable-update-emails` | `1.31` | [📥 Download ZIP](https://raw.githubusercontent.com/GinCz/plugins/main/zips/disable-update-emails.zip) | [Readme](https://github.com/GinCz/plugins/tree/main/disable-update-emails) |
| **5** | Image Resizer on Upload | `image-resizer` | `1.41` | [📥 Download ZIP](https://raw.githubusercontent.com/GinCz/plugins/main/zips/image-resizer.zip) | [Readme](https://github.com/GinCz/plugins/tree/main/image-resizer) |
| **6** | Cyrillic & European to Latin SEO Transliteration | `translit-cyr-lat` | `1.31` | [📥 Download ZIP](https://raw.githubusercontent.com/GinCz/plugins/main/zips/translit-cyr-lat.zip) | [Readme](https://github.com/GinCz/plugins/tree/main/translit-cyr-lat) |
| **7** | Allow HTML in Categories & Taxonomies | `wp-allow-html-cats` | `1.31` | [📥 Download ZIP](https://raw.githubusercontent.com/GinCz/plugins/main/zips/wp-allow-html-cats.zip) | [Readme](https://github.com/GinCz/plugins/tree/main/wp-allow-html-cats) |
| **8** | WooCommerce Auto SKU Generator | `wp-auto-sku` | `1.31` | [📥 Download ZIP](https://raw.githubusercontent.com/GinCz/plugins/main/zips/wp-auto-sku.zip) | [Readme](https://github.com/GinCz/plugins/tree/main/wp-auto-sku) |
| **9** | WP Bulk Delete Clean | `wp-bulk-delete-clean` | `1.31` | [📥 Download ZIP](https://raw.githubusercontent.com/GinCz/plugins/main/zips/wp-bulk-delete-clean.zip) | [Readme](https://github.com/GinCz/plugins/tree/main/wp-bulk-delete-clean) |
| **10** | Live Active Users & Visitors Counter | `wp-online-counter` | `1.31` | [📥 Download ZIP](https://raw.githubusercontent.com/GinCz/plugins/main/zips/wp-online-counter.zip) | [Readme](https://github.com/GinCz/plugins/tree/main/wp-online-counter) |
| **11** | WP SEO Micro | `wp-seo-micro` | `1.31` | [📥 Download ZIP](https://raw.githubusercontent.com/GinCz/plugins/main/zips/wp-seo-micro.zip) | [Readme](https://github.com/GinCz/plugins/tree/main/wp-seo-micro) |
| **12** | WP Simple Post & Category Order | `wp-simple-post-order` | `1.31` | [📥 Download ZIP](https://raw.githubusercontent.com/GinCz/plugins/main/zips/wp-simple-post-order.zip) | [Readme](https://github.com/GinCz/plugins/tree/main/wp-simple-post-order) |
| **13** | WP Test Email Micro | `wp-test-email-micro` | `1.31` | [📥 Download ZIP](https://raw.githubusercontent.com/GinCz/plugins/main/zips/wp-test-email-micro.zip) | [Readme](https://github.com/GinCz/plugins/tree/main/wp-test-email-micro) |

---

## 🌐 Internationalization & Language Support

All plugins include native gettext internationalization (`.pot`, `.po`, `.mo`) and bundled multilingual translations:
* **Default Interface:** English (`en_US`)
* **Included Localizations:** German (`de_DE`), French (`fr_FR`), Spanish (`es_ES`), Italian (`it_IT`), Czech (`cs_CZ`), Slovak (`sk_SK`), Polish (`pl_PL`).
* **Zero Overhead:** Translations load on-demand based on site locale settings via native WordPress core gettext hooks.

---

## 📋 Version History & Changelog

<details>
<summary><b>Click to expand full suite version history</b></summary>

### 2026-11
* **Packaging & Documentation:** Standardized Download Center with direct `.zip` release links and 100% English documentation across all repositories.
* **Auto-Updater Hardening:** Sanitized manifest structures in `updates.json` and ensured SHA-256 package validation.
* **Compatibility:** Fully tested against WordPress 6.8 and PHP 8.1 - 8.3.

### 2026-10
* Added maintenance mode and custom redirect codes to `404-410-301`.
* Updated `image-resizer` with intelligent WebP compression heuristics.
* Improved AJAX pagination in `wp-bulk-delete-clean`.

### 2026-09
* Initial public release of the VladiMIR+AI WordPress Ultra-Light Plugins Suite.
* Introduced zero-dependency native auto-update mechanism (`vladimir-ai-updater.php`).

</details>

---

## 🏷️ Keywords, Topics & Search Metadata

           

<br/>

## 📜 License

All plugins are released under the [GPL-2.0-or-later](https://www.gnu.org/licenses/gpl-2.0.html) license.

<br/>

---

<br/>

<div align="center">

<h3>= Rooted by VladiMIR + AI =</h3>

<br/>

<a href="https://github.com/GinCz" target="_blank" rel="noopener noreferrer"><img src="https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white" alt="GitHub" /></a>
&nbsp;&nbsp;<b>|||</b>&nbsp;&nbsp;
<a href="https://www.linkedin.com/in/gincz/" target="_blank" rel="noopener noreferrer"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>

<br/><br/>

<sub>plugins &copy; 2026. VladiMIR + AI</sub>

</div>
