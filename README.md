# iptrust_data

Public-source company disclosures, broker research and industry reports, organized with source URLs and file integrity records. / 按上市公司和行业分类的公开披露与研究资料库。

## Browse / 浏览

| Collection | Contents | PDFs |
|---|---|---:|
| [Haidilao / 海底捞 — HKEX:06862](listed-companies/haidilao/) | FY2023–FY2025 annual and interim reports, results announcements, 2026 interim disclosures, ESG and broker research | 27 |
| [Food & beverage / 餐饮行业](industry/food-and-beverage/) | CCFA × Meituan industry whitepapers (2024, 2025) | 2 |

[Browse all 29 documents](CATALOG.md) · [CSV catalog](catalog.csv) · [JSON catalog](catalog.json)

PDFs are committed directly to this public repository. No Git LFS, login or subscription is required to download them. The catalog provides both PDF preview links and direct download links.

## Organization / 目录结构

```text
listed-companies/haidilao/
  reports/annual/<year>/
  reports/interim/<year>/
  reports/results-announcements/<year>/
  reports/esg/<year>/
  research/<year>/
industry/food-and-beverage/whitepapers/<year>/
catalog.json · catalog.csv · CATALOG.md
```

Each PDF has an adjacent `.source.json` recording its publisher, report date, source URLs, retrieval timestamp, page count, original and published SHA-256 hashes, and compression method. Metadata distinguishes the original publisher from the download host; some publicly accessible PDFs are hosted by Eastmoney or other mirrors. Original issuer links are included where available.

## Compression and verification / 压缩与校验

- 29 PDFs; 133.7 MiB before → 119.8 MiB published (10.38% smaller).
- Lossless structural optimization with qpdf 12.4.2: compressed object streams and recompressed Flate streams at level 9. Images are not downsampled or recompressed with lossy encoding. If optimization increased a file's size, its original bytes were retained.
- Every PDF passed page-count and complete extracted-text equality checks against its downloaded original. First, middle and last pages were rendered with Poppler at a maximum dimension of 900 pixels; corresponding before/after renders were byte-identical. Qpdf structural warnings from source documents are retained in [validation.json](validation.json).
- Original downloaded PDFs remain in the local source archive; only the smaller optimized or original variant is stored here. Original source URLs and SHA-256 hashes allow provenance checks.

## Coverage and document rights / 范围与版权

Collected on 2026-10-17. This is a curated collection, not a complete historical research archive. FY2026 is not yet complete; the collection includes 2026 interim disclosures rather than a 2026 annual report. The 2026 CCFA whitepaper is not included because a complete publicly downloadable PDF was not obtained.

Documents retain their original publisher copyright notices and disclaimers. Public availability does not create an open-content license: this repository grants no additional rights in third-party PDFs. Consult each report and its original publisher for usage terms. Contact the repository maintainers through [GitHub Issues](https://github.com/ksamint/iptrust_data/issues) for a source correction or removal request.

Research opinions, forecasts and ratings are dated views of their authors. No financial figures or investment conclusions have been independently audited for this archive.
