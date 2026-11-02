---
name: geoskill-spatial-autocorrelation
description: 'Global Moran I+LISA+Gi*+蒙特卡洛检验，评估空间聚集模式'
---

# 空间自相关分析 | Spatial Autocorrelation

Assesses spatial clustering patterns: computes Global Moran's I (with normal-approximation z/p values), Local Moran's I (LISA), and Getis-Ord Gi*, and derives pseudo p-values via Monte Carlo random permutation tests. Supports rook adjacency and KNN weight matrices.

## Core Algorithm / 核心算法

- Global Moran's I and its variance
- LISA local autocorrelation
- Getis-Ord Gi* with Monte Carlo test

## Dependencies / 依赖

```bash
pip install numpy rasterio scipy geopandas shapely
```

## Usage / 使用方法

### Example 1 (Synthetic Data, Offline)

```bash
python geoskill-spatial-autocorrelation.py --bbox 116.0 39.0 117.0 40.0 --synthetic --output-dir ./out
```

### Example 2 (Specified Region + Silent Mode)

```bash
python geoskill-spatial-autocorrelation.py --bbox 121.0 31.0 122.0 32.0 --synthetic --output-dir ./out2 --quiet
```

### Example 3 (Real Input)

```bash
python geoskill-spatial-autocorrelation.py --input <your data file> --output-dir ./out3
```

### Example 4 (Minimal-Region Boundary Test)

```bash
python geoskill-spatial-autocorrelation.py --bbox 116.39 39.90 116.40 39.91 --synthetic --output-dir ./out4 --quiet
```

## Output / 输出

| File | Format | Description |
|---|---|---|
| `lisa.tif` | GeoTIFF/GeoJSON/JSON | Primary output |
| `gi_star.tif` | GeoTIFF/GeoJSON/JSON | Primary output |
| `autocorrelation_stats.json` | GeoTIFF/GeoJSON/JSON | Primary output |
| `output-manifest.json` | JSON | Run manifest |

## Data Source / 数据源 / Source

- Synthetic mode: locally generates physically consistent simulated data, with no external data source.
- Real mode: reads local input files, with no network requests.

## Privacy / 隐私声明 / Privacy

- Runs fully offline by default and makes no network requests.
- `--synthetic` mode reads no external data.
- All computation is done locally; no user data is uploaded.

## License / License

MIT

---

> 中文完整版：需要时再读 [references/SKILL.zh-CN.md](references/SKILL.zh-CN.md)，不要默认全量加载。
