# CUHKSZ-CVGL 数据集（DenseUAV 对齐 v3）

- 卫星底图：`cuhksz_satellite_z19_125pct.png`，尺寸 7328×4411，0.2755 m/px。
- 标注来源：`annotations.json`，2 个范围（套索），中心间距 20 m。
- 地点类 = 被帧 GT 引用的中心点：93 类，每类三档物理裁剪 [384, 512, 640] px → 统一 512×512；
  `test/PosInfo.txt` 记录每张卫星图的中心经纬度。
- query：一帧一 GT，共 106 帧；ground truth 为帧 ↔ 所属中心点三档卫星图。
