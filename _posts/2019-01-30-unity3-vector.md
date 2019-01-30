---
layout: post
date: 2018-1-30
tags: unity
title: retr0의 유니티-벡터연산기초
category: Game
comment: true

---

<p><a href="https://www.udemy.com/retr0-unity/">retr0의 유니티 게임프로그래밍 에센스</a> 를 듣고 복습하는 내용<br>
중간에 sokovan 프로젝트를 하긴 했으나 나중에 포스팅…<br>
강의를 들으면서 필기 한것이라 틀린 내용이 있을수도 있음!</p>
<h2 id="벡터-연산-기초">벡터 연산 기초</h2>
<p><strong>Vector2 (x,y)</strong></p>
<ul>
<li><strong>벡터는 길이(거리,속도)와 방향을 가진다.</strong></li>
<li>절대좌표: 원점(0,0)에서 얼마나 떨어져 있는가 , 특정한 점</li>
<li>상대좌표: 원래위치에서 얼마나 더 갈 것인가, 화살표 혹은 상대적인 위치</li>
<li>벡터의 크기(Magnitude): 선의 실제 길이</li>
</ul>
<p>ex) Vector (2,3)</p>
<ul>
<li>원래 위치에서 “상대적으로” (2,3) 만큼 가고 있다.</li>
<li>방향 -  (2,3)</li>
<li>거리 : <span class="katex--display"><span class="katex-display"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><msqrt><mn>13</mn></msqrt></mrow><annotation encoding="application/x-tex">\sqrt{13}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 1.04em; vertical-align: -0.083905em;"></span><span class="mord sqrt"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.956095em;"><span class="svg-align" style="top: -3em;"><span class="pstrut" style="height: 3em;"></span><span class="mord" style="padding-left: 0.833em;"><span class="mord">1</span><span class="mord">3</span></span></span><span class="" style="top: -2.91609em;"><span class="pstrut" style="height: 3em;"></span><span class="hide-tail" style="min-width: 0.853em; height: 1.08em;"><svg width="400em" height="1.08em" viewBox="0 0 400000 1080" preserveAspectRatio="xMinYMin slice"><path d="M95,702c-2.7,0,-7.17,-2.7,-13.5,-8c-5.8,-5.3,-9.5,
-10,-9.5,-14c0,-2,0.3,-3.3,1,-4c1.3,-2.7,23.83,-20.7,67.5,-54c44.2,-33.3,65.8,
-50.3,66.5,-51c1.3,-1.3,3,-2,5,-2c4.7,0,8.7,3.3,12,10s173,378,173,378c0.7,0,
35.3,-71,104,-213c68.7,-142,137.5,-285,206.5,-429c69,-144,104.5,-217.7,106.5,
-221c5.3,-9.3,12,-14,20,-14H400000v40H845.2724s-225.272,467,-225.272,467
s-235,486,-235,486c-2.7,4.7,-9,7,-19,7c-6,0,-10,-1,-12,-3s-194,-422,-194,-422
s-65,47,-65,47z M834 80H400000v40H845z"></path></svg></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.083905em;"><span class=""></span></span></span></span></span></span></span></span></span></span><br>
<strong>목적지(y) - 현재위치(x) = 간격(z)</strong><br>
: 현재위치에서 목적지 까지의 거리<br>
ex) (-4, 1) - (2, 4) = (-6, -3)<br>
거리:<br>
<span class="katex--display"><span class="katex-display"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><msqrt><mn>45</mn></msqrt></mrow><annotation encoding="application/x-tex"> 
\sqrt{45}
</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 1.04em; vertical-align: -0.083905em;"></span><span class="mord sqrt"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.956095em;"><span class="svg-align" style="top: -3em;"><span class="pstrut" style="height: 3em;"></span><span class="mord" style="padding-left: 0.833em;"><span class="mord">4</span><span class="mord">5</span></span></span><span class="" style="top: -2.91609em;"><span class="pstrut" style="height: 3em;"></span><span class="hide-tail" style="min-width: 0.853em; height: 1.08em;"><svg width="400em" height="1.08em" viewBox="0 0 400000 1080" preserveAspectRatio="xMinYMin slice"><path d="M95,702c-2.7,0,-7.17,-2.7,-13.5,-8c-5.8,-5.3,-9.5,
-10,-9.5,-14c0,-2,0.3,-3.3,1,-4c1.3,-2.7,23.83,-20.7,67.5,-54c44.2,-33.3,65.8,
-50.3,66.5,-51c1.3,-1.3,3,-2,5,-2c4.7,0,8.7,3.3,12,10s173,378,173,378c0.7,0,
35.3,-71,104,-213c68.7,-142,137.5,-285,206.5,-429c69,-144,104.5,-217.7,106.5,
-221c5.3,-9.3,12,-14,20,-14H400000v40H845.2724s-225.272,467,-225.272,467
s-235,486,-235,486c-2.7,4.7,-9,7,-19,7c-6,0,-10,-1,-12,-3s-194,-422,-194,-422
s-65,47,-65,47z M834 80H400000v40H845z"></path></svg></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.083905em;"><span class=""></span></span></span></span></span></span></span></span></span></span></li>
</ul>
<p><strong>벡터를 방향 x 속도(거리)로 표기하는 법 ( normalized vector )</strong><br>
좌항에 항등원(길이가 1이고 방향이 같은 벡터)을 넣으면됨!<br>
'<strong>기준점에서 반지름이 1인 원</strong>’과 ‘<strong>기준점과 해당 벡터의 좌표를 이은 직선</strong>’ 사이의 접점이 생긴다. 그 점을 기준으로 하는 벡터가 항등원이 된다.</p>
<p>ex) Vector(-4,3)의 예시<br>
<img src="https://user-images.githubusercontent.com/31947480/51933120-f39be600-2443-11e9-8b5d-31c435061c59.png" alt="default"></p>
<p>이러한 표기의 장점은 <strong>같은 방향의 더 먼거리</strong>를 표기하기가 쉽다는 것</p>

