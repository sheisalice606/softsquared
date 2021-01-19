<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>1Week_layout</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h1 id="layouts">Layouts</h1>
<ul>
<li>
<p><strong>LinearLayout</strong><br>
<code>View</code>를 수직 또는 수평 방향으로 정렬할 수 있는 레이아웃이다.<br>
방향은 <code>orientation</code> 속성을 <code>vertical</code>, <code>horizonta</code>l 로 지정 가능하며 <code>layout_weight</code> 속성을 이용하여 영역 분할이 가능하다.  <code>weight_Sum</code> 속성을 지정하고 가중치 분배 여부에 따라 공백을 남기는 것도 가능하다.</p>
</li>
<li>
<p><strong>FrameLayout</strong><br>
<code>FrameLayout</code>은 여러 View) 위젯들 중 하나를 Layout의 전면에 표시할 때 사용하는 클래스다. 꼭 하나의 View만 표시가 가능한 것은 아니지만 꼭 필요한 상황이 아니라면 하나의 View만 표시하도록 권고한다.<br>
기본적으로 <code>FrameLayout</code>에 배치된 View 들은 <strong>Left &amp; Top</strong> 의 위치에 놓여지는데 이는 <code>layout_gravity</code> 속성의 설정으로 변경이 가능하다.<br>
<code>Fragment</code>의 컨테이너로 가장 많이 사용되는 레이아웃이기도 하다.</p>
</li>
<li>
<p><strong>RelativeLayout</strong><br>
View들의 상대적인 위치를 고려하여 배치할 수 있는 레이아웃이다.<br>
<code>View</code>들의 상대적인 위치 뿐 아니라 부모 레이아웃인 <code>RelativeLayout</code> 자체도 상대적인 요소로 사용된다. 배치 관련 속성을 따로 추가하지 않으면 <code>View</code>는 자동으로 <strong>Left &amp; Top</strong> 위치에 생성된다. 그 상태로 또 한번 <code>View</code>를 추가하면 같은 위치에 <strong>overlap</strong> 되기 때문에 하나 이상의 배치 기준을 정해야 한다.</p>
</li>
<li>
<p><strong>GridLayout</strong><br>
2차원의 격자무늬 형태를 띈, 행과 열로 구성된 레이아웃이다.<br>
GridLayout을 사용할 경우 다른 레이아웃을 중첩으로 사용할 필요가 없기 때문에 메모리 사용량을 줄일 수 있다는 장점이 있다.<br>
<code>orientation</code>, <code>rowCount</code>, <code>columnCount</code> 등을 속성으로 가진다.<br>
<code>alignmentMode</code> 속성을 지정하면 View들을 정렬할 때 기준이 되는 View의 여백을 포함하여 나머지 View들을 정렬 여부를 결정할 수 있다.<br>
<code>layout_gravity</code> 속성을 지정하면 View를 셀을 특정 위치에 지정할 수 있다.<br>
<code>layout_row</code>, <code>layout_column</code> 속성으로도 위치 지정이 가능하다.<br>
<code>layout_columnspam</code>, <code>layout_rowspan</code> 속성을 이용하면 그 값만큼 셀의 행과 열을 합칠 수 있다.</p>
</li>
<li>
<p><strong>TableLayout</strong><br>
<code>GridLayout</code>과 마찬가지로 행과 열로 이루어진 레이아웃이다.<br>
<code>TableLayout</code> 아래에 <code>TableRow</code>를 선언하여 <strong>row</strong>를 추가하고, <code>TableRow</code>아래에 View를 선언하여 <strong>column</strong>을 추가하여 사용한다.<br>
<code>TableLayout</code>의 전체 column 수는 가장 많은 셀을 가진 <code>TableRow</code>의 셀 갯수로 결정된다.<br>
기본적으로 column 의 너비는 <strong>다른 row 같은 column</strong>을 충족하는 셀 중에서 가장 넓은 셀의 너비로 결정된다.<br>
<code>TableLayout</code>, <code>TableRow</code>, <code>View</code> 의 <code>background</code> 속성을 각각 지정 가능하다.<br>
<code>background</code> 속성과 <code>padding</code>, <code>layout_margin</code> 속성을 이용하여 셀 테두리를 효과를 구현할 수 있다.<br>
<code>TableRow</code> 에서 <code>layout_column</code> 속성을 이용하여 View를 원하는 column에 위치시킬 수 있다.<br>
<code>TableRow</code> 에서 <code>layout_span</code> 속성을 이용하여 셀 합치기도 가능하다.<br>
<code>TableRow</code> 에서 <code>layout_weight</code> 속성을 이용하여 셀 영역 분할이 가능하다.<br>
<code>TableLayout</code> 에서 <code>collapseColumns</code> 속성을 이용하여 특정 column 숨기기가 가능하다.<br>
<code>TableLayout</code> 에서 <code>shrinkColumns</code> 속성을 이용하여 특정 column 너비를 줄이는 것이 가능하다.<br>
<code>TableLayout</code> 에서 <code>stretchColumns</code> 속성을 이용하여 특정 column의 너비를 넓힐 수 있다.</p>
</li>
<li>
<p><strong>ConstraintLayout</strong><br>
<code>ConstraintLayout</code>은 레이아웃 구성 시, View의 위치와 크기를 유연하게 조절할 수 있게 만들어주는 레이아웃이다.<br>
<code>ConstraintLayout</code> 은 레이아웃에 배치되는 View들에 여러 제약(Constraint)을 적용하여 각 뷰의 위치와 크기를 결정한다.<br>
<code>ConstraintLayout</code>이 제공하는 제약 속성의 이름은 기본적으로 <code>layout_constraint</code>로 시작하며, 바로 뒤에 구체적인 제약 조건이 명시된다. <strong>ex) app:layout_constraintLeft_toRightOf</strong></p>
</li>
</ul>
</div>
</body>

</html>
