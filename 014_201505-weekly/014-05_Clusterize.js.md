# Clusterize.js

- 페이지링크: [NeXTs](https://github.com/NeXTs/Clusterize.js)


Clusterize.js 대량의 데이터를 화면에 쉽게 보여주는  JS plugin 입니다.
![image](https://camo.githubusercontent.com/3fdf92a4434b15d2b82001608e7808e8980de6c7/687474703a2f2f6e657874732e6769746875622e696f2f436c7573746572697a652e6a732f696d672f7461626c655f6578616d706c652e676966)

 Tiny vanilla JS plugin  라고 소개했는데 vanilla  단어는 영어사전을 보니  "평범함"이란 뜻이네요.
  readme 페이지에는 데모 말고 별다른 설명은 없고 아래 사이트에 자세한 설명이 있습니다.
   http://nexts.github.io/Clusterize.js/

 우선 어떻게 작동하는지 설명드릴께요. 주요점은 모든 tags을 한번에 표현하지 않는다는 것입니다.
 clusters 가 리스트를 잘라서 현재 스크롤 위치에 해당되는 요소들만 보여줍니다.  그리고 추가로 리스트의 top  과  bottom 의 위치를 계산해서 테이블의 height  와 scrollbar  를 보여줍니다.


  그럼 제가 한번 위 사이트를 따라서 만들어보겠습니다.
우선 Clusterize.js 를 clone 받아서 아래와 같은 페이지를 만들어 보겠습니다.

			<!DOCTYPE html>
			<html>
			<head>
			<link rel="stylesheet" href="bower/clusterize/clusterize.css">
			<script src="bower/clusterize/clusterize.min.js"></script>
			
			<meta charset="EUC-KR">
			<title>clusterize</title>
			</head>
			<body>
			<div id="scrollArea" class="clusterize-scroll">
			  <div id="contentArea" class="clusterize-content">
			    <div class="clusterize-no-data">Loading data…</div>
			  </div>
			</div>
			</body>
			
			<script>
			
			var data = [];
			
			for (var int = 0; int < 10000; int++) {
				data[int]="<div>"+int + "  aaa</div>";
			
			}
			
			
			var clusterize = new Clusterize({
				 rows: data,
				  scrollId: 'scrollArea',
				  contentId: 'contentArea'
				});
			
			</script>
			</html>


위의 for 문을 통해  contentArea 에  10000 개의 데이터를  넣었습니다.
한번 브라우저로 열어보도록하겠습니다.
![image](https://raw.githubusercontent.com/TeamSEGO/github-trend-kr/master/img/014-05_NeXTs-Clusterize-1.png)

for 문으로 만들 데이터가 잘 표현되네요.

그럼 요소 검사로 div 영역을 확인해보겠습니다.
 한번 브라우저로 열어보도록하겠습니다.
![image](https://raw.githubusercontent.com/TeamSEGO/github-trend-kr/master/img/014-05_NeXTs-Clusterize-2.png)

헐.. 전 분명 10000 개의 데이터를 넣었는데 200 개까지 안보여지네요.

스크롤을 한번 내려보도록하겠습니다.

다시 div 영역이 바뀌는 것을 볼 수 있습니다.
![image](https://raw.githubusercontent.com/TeamSEGO/github-trend-kr/master/img/014-05_NeXTs-Clusterize-3.png)

이상 Clusterize 소개였습니다.

