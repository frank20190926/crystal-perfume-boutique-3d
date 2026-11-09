# Crystal / Perfume Boutique — Contest 2801401

本目录保存用户给定坐标的 CAD、三维模型和建筑图。已读取设计去 AI 化规范 V2.0，并直接检查 `brief/IMG_4951.PNG`。外墙、服务核、四根柱及明确指定的主要家具坐标保持原值；图纸没有内部 QA 字样。当前属于坐标复现稿，存在下述面积与空间冲突，不能当作已完成碰撞消解的施工布局。

## 文件

| 文件 | 内容 |
|---|---|
| `exports/Crystal_Perfume_Boutique_Coordinate_Review_Pack.zip` | 本轮六项文件、同源 Blender 模型、重建脚本、字体与验证报告；供坐标复核，包含以下未解决事项 |
| `layout_geometry.json` | 毫米坐标、五区多边形、逐项面积、门窗、柱、家具表、涂料色号、假设与冲突 |
| `exports/Crystal_Perfume_Boutique_99sqm.dxf` | AutoCAD R2010 / AC1024，毫米，52 个原生尺寸，含平面和三组立面 |
| `exports/Crystal_Perfume_Boutique_99sqm.dwg` | LibreDWG 生成的 AutoCAD 2000 二进制兼容版 |
| `exports/Crystal_Perfume_Boutique_99sqm_Axonometric.blend` | Blender 5.1.1 原生模型，直接读取相同 JSON，不使用图像生成器 |
| `assets/cad_floorplan_99sqm.png` | 2200 × 2800，暖白分区、门扇开启弧、家具与原图四个主尺寸 |
| `assets/cad_3d_axonometric.png` | 2200 × 1600，正投影剖切轴测，35° 西南平行光，真实玻璃/陈列物体 |
| `assets/cad_elevations_vitrines.png` | 2400 × 1500，东、西、南立面、柜体照明剖面、油漆与展柜表 |
| `exports/cad_validation.json` | DXF 版本、图层、实体数量、原生尺寸与重开审计 |
| `exports/dwg_validation.json` | DWG 全部已放置实体的回读比较、转换警告及局限 |
| `exports/blender_validation.json` | Blender 版本、几何文件哈希、物体数、相机和光源参数 |
| `exports/verification.json` | 文件完整性检查与单独列出的空间碰撞，二者不混为“通过” |

本次轴测源模型独立命名为 `_Axonometric.blend`，避免覆盖目录中另一路透视渲染的 `.blend` 与脚本。DXF 字体在 `assets/fonts/`，需要语义文字编辑时加载对应字体。

这些是无图框的建筑图素材，不是已批准或已提交的竞赛展板。本轮没有对外发送、推送或部署。

## 面积核算与待协调事项

给定 L 形边界的真实计算面积为 **113.21235 m²**；给定西侧服务核为 **14.78130 m²**；相减为 **98.43105 m²**。这与原图写出的 **99.27 m²** 不一致。JSON 保留原图标签，另外保存几何实算，不缩放坐标或制造平衡面积。五区以互不重叠的多边形覆盖服务核以外区域，总和 98.43105 m²；面积包含家具和新隔墙，不标为净可用面积。01 区含其余连接通道，避免留下漏算地块。

| 项目 | 核对结果与当前处理 |
|---|---|
| VIP 面积 | 给定 `[250,2100]–[3800,5400]` 只有 11.715 m²，不能写成 16.8 m²。 |
| 沙发 / 柱 | 沙发与 COL-1 相交 451 × 550 mm；按原坐标保留，未自行移动结构或家具。 |
| VIP 单椅 | 两把单椅的外包范围与茶几相交；西侧单椅还与 reserve credenza 相交。 |
| O-03 | 与 COL-4 的平面投影重叠；本稿未把柱切掉或用柜体掩盖。 |
| O-04 / 北备餐间 | 柜体范围与依据原图重建的北备餐间门洞重合；门位并非原图标尺寸，需协调。 |
| 办公访客椅 | 指定后柜与暂定访客椅外包范围相交；桌、后柜原始坐标保持不变。 |
| 储藏间 | 1400 × 600 桌与南/北货架的间距仅 250 / 100 mm，不是经过验证的工作通道。 |
| 东北展柜 | 11750–13950 只有 2200 mm；图示 V-05、V-06 各 1100 mm。前四柜仍为 1150 mm。若东北柜也必须 1150 mm，需要改长度或位置。 |

家具调整询问尚未得到答复；没有把任何修改方案当作已批准。后续先协调上述冲突，再从几何源脚本重建，避免只修一张图片。

## 尺寸解释与来源边界

- 西南角 `(0,0)`；X 向东、Y 向北；DXF 平面保持原点，模型空间 1:1 mm。立面为独立正投影，原点偏移记录在 `cad_validation.json`。
- 窗口、结构柱、主要墙与家具范围来自本轮坐标。P-01..03 的 X / Y、两把 VIP 单椅的位置按中心点解释。
- 墙厚、层高 2800、隔墙与展柜高度 2400、窗台高度、服务门位置、非指定座椅尺寸和家具高度属于建模假设；没有冒充原图标注。
- 东柜用 500 mm 深柜体，置于给定的 550 mm 带内。货架端部避开储藏间暗门。外墙厚度向外偏移，不改变指定室内轮廓。
- Blender 1 单位 = 1 m，所有毫米坐标除以 1000，平面没有重新拉伸。西、南、服务核墙及相应门在展示剖切中保留 600 mm；完整墙、门和西窗在 `07_Full_Height_Walls` 集合中隐藏保留。打开该集合并隐藏 `06_Cutaway` 可恢复完整围护。
- 白底、玻璃折射、柜内 3000 K 灯带和产品均在 Blender 中建模/渲染。没有使用生成式效果图替代真实几何。
- 色号按用户指定保存：OC-17 `#F3EFE6`、OC-85 `#E6DEC8`、OC-23 `#E4E0D8`、Champagne Bronze `#C5B08B`。这些是本任务的数字表现值，油漆实体样板另行核定。

## CAD 兼容性

DXF 保留原生 TEXT、DIMENSION 与可独立控制的全部 12 个指定图层，重开审计 0 错误、0 修复。DWG 采用本机 LibreDWG 支持的 R2000 格式；为避免该转换器丢失文字定位和尺寸角度，DWG 的文字与尺寸分解为矢量图形。文字、尺寸语义编辑以 R2010 DXF 为准。

DWG 已转换回 DXF，逐实体比较几何、图层与毫米单位。LibreDWG 有元数据、句柄等警告；详细记录见验证 JSON 和 `review/dxf2dwg.log`、`review/dwg2dxf.log`。本机回读通过不等于 Autodesk AutoCAD 实机认证。

## 重建

使用现有依赖 `ezdxf / shapely / numpy / matplotlib / Pillow`、LibreDWG 和 Blender 5.1；本轮未安装依赖。命令均在本目录执行：

```sh
PYTHONDONTWRITEBYTECODE=1 python3 scripts/geometry.py
PYTHONDONTWRITEBYTECODE=1 python3 scripts/build_cad.py
PYTHONDONTWRITEBYTECODE=1 python3 scripts/convert_dwg.py
/Applications/Blender.app/Contents/MacOS/Blender --factory-startup -b --threads 8 --python scripts/render_blender.py
PYTHONDONTWRITEBYTECODE=1 python3 scripts/verify.py
```

`geometry.py` 是几何源；调整它后重新生成 JSON、CAD、PNG 和 Blender，验证器会核对 JSON 与 Blender 的哈希。保留的 1200px 预览在 `review/previews/`，用于本地评审。正式 PNG 为用户要求的原始像素尺寸。
