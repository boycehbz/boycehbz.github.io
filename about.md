---
title: About
layout: page
---
![Profile Image]({% if site.external-image %}{{ site.picture }}{% else %}{{ site.url }}/{{ site.picture }}{% endif %})

<p>Hi there! I am Buzhen Huang (黄步真), a Tenure-Track Associate Professor at <a href="https://cic.tju.edu.cn/">College of Intelligence and Computing</a>, Tianjin University (TJU), where I work closely with Prof. <a href="https://cic.tju.edu.cn/faculty/likun/index.html">Kun Li</a>. I received my Ph.D. from Southeast University (SEU) in 2025. I was a visiting student at <a href="https://www.comp.nus.edu.sg/~leegh/">CVRP Lab</a>, National University of Singapore (NUS), from 2023 to 2024.
My research interests lie in human reconstruction, motion capture, and character animation.</p>
<!-- I obtained my B.E. degree in Automation at Hangzhou Dianzi University (HDU) under the supervision of Prof. <a href="https://cgyan-iipl.github.io/">Chenggang Yan</a> and Prof. <a href="https://www.gaoyue.org/">Yue Gao</a>.  -->


<span style="color:red">长期招收硕士研究生，本科生和实习生，欢迎对三维视觉和具身智能感兴趣的同学与我联系！(hbz@tju.edu.cn)</span>

<h2>News</h2>

<ul>  
	<table style="width:100%;border:0px;border-spacing:0px;border-collapse:separate;margin-right:auto;margin-left:auto;"><tbody>
    		  <tr>
            <td class="news_date1">
            <li>[2025-10-17]  We organized <a href="https://www.prcv.cn/CN/BBS-KongJian/" target="_blank">Spatial Perception and Generation</a> workshop at PRCV 2025 .</li>
            </td>
          </tr>
    		  <tr>
            <td class="news_date1">
            <li>[2025-06-16]  One paper accepted to IROS 2025.</li>
            </td>
          </tr>
    		  <tr>
            <td class="news_date1">
            <li>[2025-02-26]  Two papers accepted to CVPR 2025.</li>
            </td>
          </tr>
    		  <tr>
            <td class="news_date1">
            <li>[2025-01-22]  One paper accepted to ICLR 2025.</li>
            </td>
          </tr>
        	<!-- <tr>
            <td class="news_date1">
            <li>[2024-11-12]  Invited talk at <a href="https://cic.tju.edu.cn/faculty/likun/people.html" target="_blank">TJU-3DV</a>.</li>
            </td>
          </tr> -->
        	<tr>
            <td class="news_date1">
            <li>[2024-11-05]  I was selected as a <a href="https://neurips.cc/Conferences/2024/ProgramCommittee#top-reviewers" target="_blank">top reviewer</a> of NeurIPS 2024.</li>
            </td>
          </tr>
      		<tr>
            <td class="news_date1">
            <li>[2024-08-17]  Invited talk on Human Interaction Modeling at <a href="https://www.prai.net/prai2024.html" target="_blank">PRAI 2024</a>.</li>
            </td>
          </tr>
    		  <tr>
            <td class="table_toggle" style="display: none;">
            <li>[2024-02-27]  One paper accepted to CVPR 2024.</li>
            </td>
          </tr>
    		  <tr>
            <td class="table_toggle" style="display: none;">
            <li>[2023-07-14]  One paper accepted to ICCV 2023.</li>
            </td>
          </tr>
  		    <tr>
            <td class="table_toggle" style="display: none;">
            <li>[2023-04-19]  One paper accepted to IJCAI 2023.</li>
            </td>
          </tr>
  		    <tr>
            <td class="table_toggle" style="display: none;">
            <li>[2023-02-10]  We released <a href="https://github.com/boycehbz/CHOMP#ocmotion-dataset" target="_blank">OcMotion</a> dataset.</li>
            </td>
          </tr>
  		    <tr>
            <td class="table_toggle" style="display: none;">
            <li>[2023-02-07]  CrowdRec won the 1st place in <a href="https://www.gigavision.cn/track/track?nav=GigaCrowd&type=nav" target="_blank">GigaCrowd Challenge</a>.</li>
            </td>
          </tr>
		      <tr>
            <td class="table_toggle" style="display: none;">
            <li>[2022-08-24]  Honored to receive <a href="http://tc.ccf.org.cn/tccad/jlry/txkysjjj/hjrxx/2022-10-14/775286.shtml" target="_blank">Style3D Graduate Fellowship</a>!</li>
            </td>
          </tr>
		      <tr>
            <td class="table_toggle" style="display: none;">
            <li>[2022-08-09]  One paper accepted to TPAMI 2022.</li>
            </td>
          </tr>
          <tr class="table_toggle" style="display: none;">
            <td class="news_date1">
            <li>[2022-06-12]  One paper accepted to TIP 2022.</li>
            </td>
          </tr>
          <tr class="table_toggle" style="display: none;">
            <td class="news_date1">
            <li>[2022-03-02]  One paper accepted to CVPR 2022.</li>
            </td>
          </tr>
          <tr class="table_toggle" style="display: none;">
            <td class="news_date1">
            <li>[2022-01-05]  Invited talk at <a href="https://www.noahlab.com.hk/#/home" target="_blank">Huawei Noah's Ark Lab</a>.</li>
            </td>
          </tr>
          <tr class="table_toggle" style="display: none;">
            <td class="news_date1">
            <li>[2021-10-04]  One paper accepted to 3DV 2021.</li>
            </td>
          </tr>
          <tr class="table_toggle" style="display: none;">
            <td class="news_date1">
            <li> [2020-02-24]  One paper accepted to CVPR 2020.</li>
            </td>
          </tr>
        </tbody></table>
	<div style="margin-bottom:25px;padding: 0px 0px 0px 0px;">
			<a id="toggle_button" href="javascript:toggle()">Show more</a><script>
				function toggle() {
				var rows = document.getElementsByClassName("table_toggle");
				var y = document.getElementById("toggle_button");
				if (rows[0].style.display == "none") {
					for (var i = 0; i < rows.length; i++) {
					rows[i].style.display = "";
					}
					y.innerHTML = "Show less";
				} else {
					for (var i = 0; i < rows.length; i++) {
					rows[i].style.display = "none";
					}
					y.innerHTML = "Show more";
				}
				}
			</script>
	</div>
	<!-- <li>[2022-08-09]  One paper accepted to TPAMI2022.</li>
	<li>[2022-06-12]  One paper accepted to TIP2022.</li>
	<li>[2022-03-02]  One paper accepted to CVPR2022.</li>
	<li>[2022-01-05]  I gave a talk at <a href="https://www.noahlab.com.hk/#/home">Huawei Noah's Ark Lab</a>.</li>
    <li>[2021-10-04]  One paper accepted to 3DV2021.</li>
    <li> [2020-02-24]  One paper accepted to CVPR2020.</li> -->
</ul>



<h2>Academic Service</h2>

<ul>
  <li>Session Chair: IJCAI.</li><br>
	<li>Conference Reviewer: NeurIPS, CVPR, ICCV, ECCV, ICLR, ICML, etc.</li><br>
	<li>Journal Reviewer: TPAMI, TMM, CVMJ, Computers & Graphics, etc.</li><br>
</ul>

<h2>Teaching Assistant</h2>

<ul>
    <li>
	<span style="display:inline-block;font-size:1.7rem;font-family:Arial;font-weight:bold;">Digital Image Processing System</span><br>
	<span style="display:inline-block;font-size:1.4rem;font-family:Arial;padding-bottom:0.6rem">Instructor: Yangang Wang, Fall 2020</span>
	</li>
    <li>
	<span style="display:inline-block;font-size:1.7rem;font-family:Arial;font-weight:bold;">Introduction to Artificial Intelligence</span><br>
	<span style="display:inline-block;font-size:1.4rem;font-family:Arial;padding-bottom:0.6rem">Instructor: Yangang Wang, Fall 2019</span>
	</li>
</ul>


<!-- <h2>Projects</h2>

<ul>
	<li><a href="http://yangangwang.com/papers/ZHANG-OOH-2020-03.html">Occluded Human Reconstruction</a></li><br>
	<li><a href="https://github.com/boycehbz/MvSMPLfitting">MvSMPLfitting</a></li>
</ul> -->

<br>
<br>
<br>
<br>
<br>
<br>

<script type='text/javascript' id='clustrmaps' src='//cdn.clustrmaps.com/map_v2.js?cl=ffffff&w=220&t=m&d=xcwYgsgvqVyiWGs5jS1qzD1OrC8Kb39Z7cJaCSxaUF0&cmo=ff5353&cmn=ff5353'></script>
