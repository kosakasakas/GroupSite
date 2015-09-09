+++
date = "2015-07-05T17:48:26+09:00"
title = "Physically-based Character Animation"
description = ""
image = "iwamoto.jpg"
+++

## Physically-based Character Animation
<div class="embedded-image-wrapper">
    <div class="embedded-image-container">
        <img src="../../img/projects/iwamoto.jpg" alt="" />
    </div>
</div>

### Abstract
---
Due to the recent advancement of computer graphics hardware and software algorithms, deformable characters have become more and more popular in real-time applications such as computer games. While there are mature techniques to generate primary deformation from skeletal movement, simulating realistic and stable secondary deformation such as jiggling of fats remains challenging. On one hand, traditional volumetric approaches such as the finite element method require higher computational cost and are infeasible for limited hardware such as game consoles. On the other hand, while shape matching based simulations can produce plausible deformation in real-time, they suffer from a stiffness problem in which particles either show unrealistic deformation due to high gains, or cannot catch up with the body movement. In this paper, we propose a unified multi-layer lattice model to simulate the primary and secondary deformation of skeleton-driven characters. The core idea is to voxelize the input character mesh into multiple anatomical layers including the bone, muscle, fat and skin. Primary deformation is applied on the bone voxels with lattice-based skinning. The movement of these voxels is propagated to other voxel layers using lattice shape matching simulation, creating a natural secondary deformation. Our multi-layer lattice framework can produce simulation quality comparable to those from other volumetric approaches with a significantly smaller computational cost. It is best to be applied in real-time applications such as console games or interactive animation creation. 

### Demo
---
<div class="embedded-image-wrapper">
    <div class="embedded-image-container">
        <iframe width="650" height="350" src="https://www.youtube.com/embed/xgx6M9o_RUs" frameborder="0" allowfullscreen></iframe>
    </div>
</div>

### Publication
---
<div class="publication">
<p>
<b><i>Multi-layer Lattice Model for Real-Time Dynamic Character Deformation</i></b><br>
Naoya Iwamoto，Hubert P.H. Shum, Longzhi Yang, and Shigeo Morishima<br>
The 2015 Computer Graphics Forum (CGF)<br>
Proceedings of the 2015 Pacific Conference on Computer Graphics and Applications (PG 2015), Beijing, 2015.10.07-09<br>
[ <a href="https://dl.dropboxusercontent.com/u/10792480/paper/iwamoto/2015_PG/PG2015_iwamoto.pdf"><i class="fa fa-file-pdf-o text-primary"></i> Paper</a> ]
<br>
<br>

<p>
<b><i>キャラクターの身体構造を考慮した実時間肉揺れ生成手法</i></b><br>
岩本 尚也，森島 繁生<br>
画像電子学会誌 第44巻, 第3号. 2015年7月<br>
<br>

<p>
<b><i>Material Parameter Editing System for Volumetric Simulation Models.</i></b><br>
Naoya Iwamoto and Shigeo Morishima.<br>
In Proceedings of the ACM SIGGRAPH (SIGGRAPH 14), Anaheim, 2014.08.10-14<br>
[ <a href="https://dl.dropboxusercontent.com/u/10792480/paper/iwamoto/2014_SIGGRAPH/Siggraph_iwamoto.pdf"><i class="fa fa-file-pdf-o text-primary"></i> Abstract</a> ]
[ <a href="https://dl.dropboxusercontent.com/u/10792480/paper/iwamoto/2014_SIGGRAPH/Siggraph_iwamoto_poster.pdf"><i class="fa fa-file-pdf-o text-primary"></i> Poster</a> ]
<br>
<br>

<p>
<b><i>多重レイヤーボリューム構造を考慮した キャラクターのリアルタイム肉揺れアニメーション生成手法.</i></b><br>
岩本 尚也，森島 繁生<br>
Visual Computing/GCAD合同シンポジウム2015, 姫路, 2015.06.28-30.<br>
[ <a href="https://dl.dropboxusercontent.com/u/10792480/paper/iwamoto/2015_VCGCAD/VCGCAD_iwamoto.pdf"><i class="fa fa-file-pdf-o text-primary"></i> Paper</a> ]
[ <a href="https://dl.dropboxusercontent.com/u/10792480/paper/iwamoto/2015_VCGCAD/VCGCAD2015_iwamoto_poster.pdf"><i class="fa fa-file-pdf-o text-primary"></i> Poster</a> ]<br>
<br>

<p>
<b><i>"肉揺れ"を実現するキャラクターアニメーションシステム</i></b><br>
岩本 尚也，森島 繁生<br>
CEDEC, 横浜, 2014.09.02-04<br>
[ <a href="https://dl.dropboxusercontent.com/u/10792480/paper/iwamoto/2014_CEDEC/nikyure_slides.pdf"><i class="fa fa-file-pdf-o text-primary"></i> Slide</a> ]<br>
<br>

<p>
<b><i>ボーンベースの弾性体キャラクターアニメーションシステムの研究</i></b><br>
岩本 尚也，森島 繁生<br>
卓越シンポジウム2013. 2013.12<br>
<br>

<p>
<b><i>スケルトンベースの高速な弾性体キャラクターアニメーション手法</i></b><br>
岩本 尚也，森島 繁生<br>
ビジュアルコンピューティングワークショップ2013. 画像電子学会誌,第42巻,第1号,「VCWS2013報告」p115-123(2013), 2013.11.<br>
<br>







</div>
