---
title: "The summary of three years of missing data"
author: "ChenYW"
date: "2020-07-29"
output:
  html_document: 
    css: style.css
    df_print: kable
    fig_caption: yes
    highlight: textmate
    keep_md: yes
    number_sections: yes
    theme: readable
    toc: yes
  pdf_document: 
    extra_dependencies: xcolor
    fig_caption: yes
    highlight: tango
    includes: null
    keep_tex: yes
    number_sections: yes
    toc: yes
    toc_depth: 4
  word_document:
    toc: yes
geometry: margin = 0.8in
header-includes:
- \usepackage{color,xcolor,chngcntr,setspace,placeins,fancyhdr, url}
- \usepackage[ruled,vlined,linesnumbered]{algorithm2e}
- \onehalfspacing
- \counterwithin{equation}{section}
- \counterwithin{table}{section}
- \pagestyle{fancy}
linkcolor: black
editor_options: null
chunk_output_type: inline
urlcolor: black
---
<style>
pre.BK {background-color: #DCDCDC;}
</style>
\Large
\newpage 
\small
<details>
<summary>Setup</summary>

```r
knitr::opts_chunk$set(echo = TRUE, message = FALSE, warning = FALSE,
                      attr.source='.numberLines', attr.output = ".numberLines")
# , class.source = "BK"
rm(list=ls())
suppressMessages(Sys.setlocale("LC_TIME", "English"))
```

```
## [1] "English_United States.1252"
```
</details>


```{.numberLines}
## Number of platforms: 2
## - platform: Advanced Micro Devices, Inc.: OpenCL 2.1 AMD-APP (2580.6)
##   - context device index: 0
##     - gfx804
##   - context device index: 1
##     - Intel(R) Core(TM) i7-8705G CPU @ 3.10GHz
## - platform: Intel(R) Corporation: OpenCL 2.1 
##   - context device index: 0
##     - Intel(R) HD Graphics 630
##   - context device index: 1
##     - Intel(R) Core(TM) i7-8705G CPU @ 3.10GHz
## checked all devices
## completed initialization
```

\large

<!-- # Validation based on the noise from t distribution -->
<!-- ###################################################################### -->

<!--html_preserve--><div id="htmlwidget-f514a692a8945672b494" style="width:100%;height:auto;" class="datatables html-widget"></div>
<script type="application/json" data-for="htmlwidget-f514a692a8945672b494">{"x":{"filter":"none","data":[["1","2","3","4","5","6","7","8","9","10","11","12","13","14","15","16","17","18","19","20","21","22","23","24","25","26","27","28","29","30","31","32","33","34","35","36","37","38","39","40","41","42","43","44","45","46","47","48","49","50","51","52","53","54","55","56","57","58","59","60","61","62","63","64","65","66","67","68","69","70","71","72","73","74","75","76","77","78","79","80","81","82","83","84","85","86","87","88","89","90","91","92","93","94","95","96","97","98","99","100","101","102","103","104","105","106","107","108","109","110","111","112","113","114","115","116","117","118","119","120","121","122","123","124","125","126","127","128","129","130","131","132","133","134","135","136","137","138","139","140","141","142","143","144","145","146","147","148","149","150","151","152","153","154","155","156","157","158","159","160","161","162","163","164","165","166","167","168","169","170","171","172","173","174","175","176","177","178","179","180","181","182","183","184","185","186","187","188","189","190","191","192","193","194","195","196","197","198","199","200","201","202","203","204","205","206","207","208","209","210","211","212","213","214","215","216","217","218","219","220","221","222","223","224","225","226","227","228","229","230","231","232","233","234","235","236"],["Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Shijiazhuang","Zhangjiakou","Zhangjiakou","Zhangjiakou","Zhangjiakou","Zhangjiakou","Zhangjiakou","Zhangjiakou","Zhangjiakou","Zhangjiakou","Qinhuangdao","Qinhuangdao","Qinhuangdao","Qinhuangdao","Tangshan","Langfang","Langfang","Langfang","Langfang","Langfang","Langfang","Langfang","Langfang","Langfang","Langfang","Langfang","Langfang","Langfang","Langfang","Langfang","Langfang","Langfang","Langfang","Baoding","Baoding","Baoding","Baoding","Baoding","Baoding","Cangzhou","Hengshui","Hengshui","Hengshui","Hengshui","Hengshui","Hengshui","Xingtai","Xingtai","Xingtai","Xingtai","Xingtai","Handan","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Tianjin","Beijing","Beijing","Beijing","Beijing","Beijing","Beijing","Beijing","Beijing"],[1,1,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,15,15,15,17,17,17,17,17,17,22,22,22,23,28,30,30,30,30,30,30,30,30,30,30,30,30,30,30,30,32,32,32,34,35,35,35,36,36,42,43,43,43,43,44,45,46,46,46,47,47,52,54,54,56,56,56,56,56,56,56,56,56,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,57,58,58,58,58,58,58,58,58,58,58,58,58,58,58,58,58,58,58,58,58,58,58,59,59,59,59,59,59,59,59,59,59,59,59,59,59,60,60,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,62,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,63,64,64,64,64,65,66,66,67,67,71,74,76],["Shijigongyuan","Shijigongyuan","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Zhongnanxiaoqu","Renmingongyuan","Renmingongyuan","Renmingongyuan","Tanjichang","Tanjichang","Tanjichang","Tanjichang","Tanjichang","Tanjichang","Jianshedasha","Jianshedasha","Jianshedasha","Shizhengfu","Wuziju","Jiancezhongxin","Jiancezhongxin","Jiancezhongxin","Jiancezhongxin","Jiancezhongxin","Jiancezhongxin","Jiancezhongxin","Jiancezhongxin","Jiancezhongxin","Jiancezhongxin","Jiancezhongxin","Jiancezhongxin","Jiancezhongxin","Jiancezhongxin","Jiancezhongxin","Kaifaqu","Kaifaqu","Kaifaqu","Jiancezhan","Dibiaoshuichang","Dibiaoshuichang","Dibiaoshuichang","Huadianerqu","Huadianerqu","Dianshizhuanbozhan","Shihuanbaoju","Shihuanbaoju","Shihuanbaoju","Shihuanbaoju","Shijiancezhan","Dianjibeichang","Luqiaogongsi","Luqiaogongsi","Luqiaogongsi","Dahuoquan","Dahuoquan","Dongwushui","Beichenkejiyuanqu","Beichenkejiyuanqu","Hangtianlu","Hangtianlu","Hangtianlu","Hangtianlu","Hangtianlu","Hangtianlu","Hangtianlu","Hangtianlu","Hangtianlu","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Meijiang","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nanjinglu","Nankoulu","Nankoulu","Nankoulu","Nankoulu","Nankoulu","Nankoulu","Nankoulu","Nankoulu","Nankoulu","Nankoulu","Nankoulu","Nankoulu","Nankoulu","Nankoulu","Qianjindao","Qianjindao","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Shijiancezhongxin","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Tianshanlu","Yuejinlu","Yuejinlu","Yuejinlu","Yuejinlu","Wanshouxigong","Dongsi","Dongsi","Nongzhanguan","Nongzhanguan","Guanyuan","Changping","Shunyi"],[201609,201702,201501,201502,201503,201504,201505,201506,201507,201508,201509,201510,201511,201512,201601,201602,201603,201604,201605,201606,201607,201608,201609,201610,201611,201612,201701,201702,201703,201704,201705,201706,201707,201708,201709,201710,201712,201505,201507,201509,201606,201607,201703,201709,201710,201712,201501,201509,201606,201607,201608,201609,201610,201611,201612,201701,201702,201703,201704,201705,201706,201707,201708,201509,201702,201703,201508,201609,201706,201707,201610,201701,201511,201709,201710,201711,201712,201711,201502,201512,201611,201711,201507,201510,201508,201507,201712,201704,201705,201706,201707,201708,201709,201710,201711,201712,201507,201508,201509,201510,201511,201512,201601,201602,201603,201604,201605,201606,201607,201608,201609,201610,201611,201612,201701,201702,201703,201704,201705,201706,201707,201708,201709,201710,201711,201712,201501,201506,201511,201606,201607,201608,201609,201610,201611,201612,201701,201702,201703,201704,201705,201706,201707,201708,201709,201710,201711,201712,201611,201612,201701,201702,201703,201704,201705,201706,201707,201708,201709,201710,201711,201712,201505,201703,201507,201508,201509,201510,201511,201512,201601,201602,201603,201604,201605,201606,201607,201608,201609,201610,201611,201612,201701,201702,201703,201704,201705,201706,201707,201708,201709,201710,201711,201712,201507,201508,201509,201510,201511,201512,201601,201602,201603,201604,201605,201606,201607,201608,201609,201610,201611,201612,201701,201702,201703,201704,201705,201706,201707,201708,201709,201710,201711,201712,201506,201508,201511,201607,201606,201606,201607,201510,201712,201607,201510,201605],[2,3,31,28,31,30,31,30,31,31,30,31,30,31,31,29,31,30,31,30,31,31,30,31,30,31,31,28,31,30,31,30,31,31,3,3,31,1,1,3,1,1,9,3,3,31,2,11,29,31,31,30,31,30,31,31,28,31,30,31,30,31,31,29,2,30,6,1,10,3,1,1,1,30,31,30,31,2,2,1,1,2,1,1,1,1,31,4,31,30,31,31,30,31,30,31,30,31,30,31,30,31,31,29,31,30,31,30,31,31,30,31,30,31,31,28,31,30,31,30,31,31,30,31,30,31,1,1,1,29,31,31,30,31,30,31,31,28,31,30,31,30,31,31,30,31,30,31,8,31,31,28,31,30,31,30,31,31,30,31,30,31,1,1,31,31,30,31,30,31,31,29,31,30,31,30,31,31,30,31,30,31,31,28,31,30,31,30,31,31,30,31,30,31,31,31,30,31,30,31,31,29,31,30,31,30,31,31,30,31,30,31,31,28,31,30,31,30,31,31,30,31,30,31,1,2,3,1,1,1,2,1,1,1,6,1],[0.07,0.11,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,0.1,0.1,1,0.03,0.03,0.1,0.03,0.03,0.29,0.1,0.1,1,0.06,0.37,0.97,1,1,1,1,1,1,1,1,1,1,1,1,1,1,0.97,0.07,0.97,0.19,0.03,0.33,0.1,0.03,0.03,0.03,1,1,1,1,0.07,0.07,0.03,0.03,0.07,0.03,0.03,0.03,0.03,1,0.13,1,1,1,1,1,1,1,1,0.97,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,0.03,0.03,0.03,0.97,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,0.27,1,1,1,1,1,1,1,1,1,1,1,1,1,0.03,0.03,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,0.03,0.06,0.1,0.03,0.03,0.03,0.06,0.03,0.03,0.03,0.19,0.03]],"container":"<table class=\"display\">\n  <thead>\n    <tr>\n      <th> <\/th>\n      <th>City<\/th>\n      <th>SiteId<\/th>\n      <th>StatioName<\/th>\n      <th>YearMonth<\/th>\n      <th>MissCount<\/th>\n      <th>MissRatio<\/th>\n    <\/tr>\n  <\/thead>\n<\/table>","options":{"columnDefs":[{"targets":5,"render":"function(data, type, row, meta) {\nreturn type === 'display' && data.length > 6 ?\n'<span title=\"' + data + '\">' + data.substr(0, 6) + '...<\/span>' : data;\n}"},{"className":"dt-right","targets":[2,4,5,6]},{"orderable":false,"targets":0}],"order":[],"autoWidth":false,"orderClasses":false},"callback":"function(table) {\ntable.page(3).draw(false);\n}"},"evals":["options.columnDefs.0.render","callback"],"jsHooks":[]}</script><!--/html_preserve-->