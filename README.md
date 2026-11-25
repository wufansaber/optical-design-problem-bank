# 光学设计题库

用 Optiwork v1.2 做历届光学设计竞赛题。每题保存题源、原始约束、可打开的处方和复验数据。复现公开处方时注明出处，重新设计时注明起点。

## 已复验

题目完成 Optiwork 和 Zemax 同处方复验后在此登记。额外练习目标和赛题硬性要求以单题说明为准。

- [ILDC 1990 单色四片式](problems/ildc-1990-monochromatic-quartet/README.md) · Optiwork / Zemax 三场平均 2.2492 / 2.2492 µm，制造几何初审通过。
- [IODC 2017 百年镜头](problems/iodc-2017-centennial/README.md) · 合题基础解，Optiwork / Zemax 最大 RMS 波前均约 0.069982 波。

- [Optiland 消色差双片](problems/optiland-achromatic-doublet/README.md) · 双软件评分 0.12970 / 0.12970，各场与波长全通光。

- [Optiland 50 mm F/4 多色点斑](problems/optiland-50mm-rms/README.md) · 双软件评分 0.23598 / 0.23598，全场通光。

- [Optiland 24 mm F/4 广角](problems/optiland-24mm-wide-angle/README.md) · 双软件多色 FFT MTF 评分 0.58708 / 0.58847，全场通光。

- [IODC 1998 实心胶合镜头](problems/iodc-1998-solid-glass/README.md) · 七片基础解，清口径玻璃质量 957.93 g，满场相对照度 90.41%，完成双软件复验。

- [IODC 2010 Green Lens](problems/iodc-2010-green-lens/README.md) · 共用球面半径，双软件已复验得分 48.536 mm·°。

- [IODC 2014 Cinderella Lens](problems/iodc-2014-cinderella-lens/README.md) · 十片排入十块毛坯，双软件已复验得分 120.000 mm·°。

- [IODC 2021 Down Under Lens](problems/iodc-2021-down-under-lens/README.md) · 同半径符号反转，正反向双软件复验，公共得分 57.000 mm·°。

- [IODC 2023 Yin-Yang Lens](problems/iodc-2023-yin-yang-lens/README.md) · 两波长共焦，Zemax 50 × 50 网格复算得分 1.90064 mm·°·波。

## 题目索引

| 题目 | 设计要点 | 题源 |
| --- | --- | --- |
| ILDC 1990 单色四片式 | 四片 BK7 球面镜，固定焦距、F 数和视场，压低三场几何点斑 | [竞赛结果论文](https://doi.org/10.1117/12.47896) · [题面与公开处方](https://www.genetic-programming.org/hc2007/06-Gagne/Gagne-RT-LVSN-2007-01.pdf) |
| IODC 1994 Rochester Lens Design Problem | 继续核对完整题面和评分规则 | [会议论文目录](https://opg.optica.org/aop/conference.cfm?meetingid=22&yr=1994) |
| IODC 1998 Solid Glass Lens | 实心胶合系统，首末面之间没有空气隙 | [赛事题面与结果](https://iodc.info/1998/06/1998-lens-design-problem/) |
| IODC 2002 色散模拟 | 用 100 mm、F/8 的折射球面系统逼近衍射元件的色散行为 | [赛事档案](https://iodc.info/iodc-2002/) |
| IODC 2006 交替分片 | 一块 100 mm 厚玻璃沿内部曲面分片，交替抽出组成两套镜头 | [赛事档案](https://iodc.info/iodc-2006/) |
| IODC 2010 Green Lens | 所有曲面共享一个半径绝对值，并可用平面 | [赛事档案](https://iodc.info/iodc-2010/) |
| IODC 2014 Cinderella Lens | 所有元件须能装入规定尺寸的十块毛坯 | [赛事档案](https://iodc.info/iodc-2014/) |
| IODC 2017 Centennial Lens | 保留固定平板和双球模块，最大化评分光线高度的乘积 | [赛事题面](https://iodc.info/2016/09/2017-lens-design-problem/) |
| IODC 2021 Down Under Lens | 验证原向与按指定规则翻转后的系统 | [赛事题面](https://iodc.info/2020/09/the-2021-iodc-shafer-cup-competition/) |
| IODC 2023 Yin Yang Lens | 在两组波长约束下设计同一套光学系统 | [赛事题面](https://iodc.info/2022/08/the-2023-iodc-shafer-cup-competition/) |
| IODC 2027 Schoenberg Lens | 每片镜的四项尺寸各用 0–9 一次，再最大化入瞳直径与半视场的乘积 | [赛事题面](https://iodc.info/2026/09/the-2027-iodc-shafer-cup-competition/) |
| 2013 中国镜头设计题 | 共轭变焦，待核对完整规格 | [Optica 会议论文](https://opg.optica.org/abstract.cfm?uri=IODC-2014-ITu1A.5) |
| Optiland 多色点斑优化 | 50 mm、F/4、3–6 片，五场共质心多色 RMS | [赛事题面](https://www.optiland.org/competitions) · [共同规则](https://www.optiland.org/competitions/rules) |
| Optiland 中等广角 | 24 mm、F/4、全视场 60°，以 20 lp/mm 多色 MTF 评分 | [裁判规则](https://github.com/optiland/challenges-eval/blob/main/RULES.md) |
| Optiland 消色差双片 | 100 mm、F/8、EPD 12.5 mm，两片与三场多色 RMS | [裁判规则](https://github.com/optiland/challenges-eval/blob/main/RULES.md) |
| Nonimaging 2026 Square Peg | 将立方光源发出的光反射到圆形开口 | [赛事题面和名次](https://nonimaging-conference.org/competition-2026/) |

历届照明题另见 [IODC 照明题目录](https://iodc.info/category/illumination-problem/) 和 [2027 非成像联合竞赛](https://nonimaging-conference.org/competition-2027/)。
