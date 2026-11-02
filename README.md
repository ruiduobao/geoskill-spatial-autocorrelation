# Spatial Autocorrelation Analysis (geoskill-spatial-autocorrelation)

> Global Moran's I + LISA + Gi* + Monte Carlo test to assess spatial clustering patterns

---

## 1. Overview

Assesses spatial clustering patterns: computes Global Moran's I (with z/p values from the normal approximation), Local Moran's I (LISA) and Getis-Ord Gi*, and derives pseudo p-values via Monte Carlo random permutation tests. Supports rook adjacency and KNN weight matrices.

## 3. Quick Start

```bash
pip install -r requirements.txt
python geoskill-spatial-autocorrelation.py --bbox 116 39 117 40 --synthetic --output-dir ./out
```

## 4. CLI Parameters

Run `python <skill>.py --help` for the full list. Common parameters:

| Parameter | Type | Description |
|---|---|---|
| `--bbox` | `float[4]` | WGS84 bounding box `min_lon min_lat max_lon max_lat` |
| `--input` | `path` | Local input file (GeoJSON/GeoTIFF/etc.) |
| `--output-dir` | `path` | Output directory (default `./output`) |
| `--synthetic` | `flag` | Use synthetic data instead of real input |
| `--quiet` | `flag` | Suppress non-essential stdout |

## 5. Input / Output

| File | Format | Description |
|---|---|---|
| `lisa.tif` | GeoTIFF/GeoJSON/JSON | Primary output |
| `gi_star.tif` | GeoTIFF/GeoJSON/JSON | Primary output |
| `autocorrelation_stats.json` | GeoTIFF/GeoJSON/JSON | Primary output |
| `output-manifest.json` | JSON | Run manifest |

## 6. Technical Principle

- Global Moran's I and its variance
- LISA local autocorrelation
- Getis-Ord Gi* and Monte Carlo test

## 8. License

MIT License. See [`LICENSE`](./LICENSE) for full text.

---

> 中文完整版：[references/SKILL.zh-CN.md](references/SKILL.zh-CN.md)
