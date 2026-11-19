# CUHKSZ-CVGL Dataset

A compact drone-to-satellite cross-view geo-localization (CVGL) retrieval dataset built on the CUHK-Shenzhen campus, aligned with the [DenseUAV](https://github.com/Dmmm1997/DenseUAV) conventions.

## Layout (all-test split)

```
test/
├── query_drone/<class_id>/<video>_f<frame>.jpg   # 1440x1080 drone frames (height scaled to 1080, center-cropped to 1440 wide)
├── gallery_satellite/<class_id>/H80.tif H90.tif H100.tif  # 512x512 satellite crops
└── PosInfo.txt                                   # "class_id/file N{lat} E{lon}" per gallery image
```

- 106 query frames over 93 place classes; each query matches the three-scale satellite crops (384/512/640 px physical footprint, ~106/141/176 m) of the exact center point it flies over.
- Center lattice spacing: 20 m (15 m for part of the area), auto-generated inside hand-drawn building ROIs.
- Satellite base: Google Maps zoom-19, 0.27547 m/px.
- `manifest.json` / `ground_truth.json` / `dataset_report.md` hold class metadata, query→positives mapping and build details.
