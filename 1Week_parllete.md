<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>1Week_parllete</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h1 id="parlette">Parlette</h1>
<p><code>Android Studio 4.1.1</code> version 기준 Parlette 구성 요소 중<br>
생소한 View 들을 위주로 그 <strong>기능</strong>을 조사한다.</p>
<h2 id="text">Text</h2>
<ul>
<li>
<p><strong>TextView</strong><br>
안드로이드 UI에서 텍스트를 표시하는 기능을 담당한다.</p>
</li>
<li>
<p><strong>EditText</strong><br>
사용자가 직접 텍스트를 입력, 수정 할 수 있는 TextView이다.<br>
<strong>inputType</strong> 속성에 따라서 입력할 수 있는 자료형이 지정된다.<br>
Plain Text, Password, E-mail, Phone, Number, Time, Date, Postal Address, Multiline Text 등이 EditText에 해당된다.</p>
</li>
<li>
<p><strong>AutoCompleteTextView / MultiAutoCompleteTextView</strong><br>
자동완성 검색 기능을 구현하기 위한 Textview이다.</p>
</li>
<li>
<p><strong>CheckedTextView</strong><br>
선택이 가능하도록 checkbox를 함께 제공하는 Textview이다.</p>
</li>
<li>
<p><strong>TextInputLayout</strong><br>
EditText에 입력된 텍스트를 기반으로 View가 유동적으로 반응하기 위해서 고안된 레이아웃이다.</p>
</li>
</ul>
<h2 id="button">Button</h2>
<ul>
<li>
<p><strong>Chip / ChipGroup</strong><br>
Android에서 어떤 키워드 혹은 카테고리, 요소, 타입 등을 표현할 때 종종 타원형의 background에 그 텍스트를 표현하는데,  Material Design에서는 이를 구현할 수 있도록 Chip이라는 것을 제공한다.</p>
</li>
<li>
<p><strong>ToggleButton</strong><br>
Toggle button은 두 가지 상태 중 하나로 Toggle 되도록 만든 버튼이다.<br>
두 가지 상태 중 하나를 선택할 수 있다는 점에서 RadioButton을 떠올릴 수 있지만 UI가 다르다. 불이 꺼지고 켜지는 상태를 표현하는 스위치 모양이다.</p>
</li>
<li>
<p><strong>FloatingActionButton(FAB)</strong><br>
FAB은 우측 하단에 있는 버튼처럼 화면 위에 나타나며 어플에서 여러 기능을 수행하는 버튼이다. 특히나 리스트뷰 구조에서 많이 사용되며 화면이 움직이더라도 FAB버튼은 고정되어 떠있다.</p>
</li>
</ul>
<h2 id="widgets">Widgets</h2>
<ul>
<li>
<p><strong>WebView</strong><br>
반응형 웹사이트를 안드로이드 디바이스에서 띄워줄 수 있는 위젯이다.<br>
WebView를 이용하여 홈페이지를 앱 내에서 호출이 가능하여 반응형 앱을 개발하는데 유용하다.<br>
Manifest 파일에 <code>INTERNET</code> 권한을 추가해야 한다.</p>
</li>
<li>
<p><strong>VideoView</strong><br>
다양한 자원에서 영상을 불러올 수 있는 동영상 재생  위젯이다. <code>MediaController</code>라는 UI를 제공하고 <code>scaling</code>과 <code>tinting</code> 등 다양한 디스플레이 기능을 제공하고 있어 간편하게 사용할 수 있습니다.<br>
<code>MediaController</code>는 VideoView의 컨트롤 UI를 담은 View다. 기본적으로 재생/정지, 되감기, 빨리감기와 Progress Slider를 내장하고 있다.<br>
외부 URL로부터 동영상을 스트리밍하기 위해서는 <code>INTERNET</code> 권한이 필요하다. 또한, 영상을 재생하는 도중에 화면이 어두워지거나 꺼지고 잠기는 것을 막으려면 <code>WAKE_LOCK</code> 권한이 필요하다.</p>
</li>
<li>
<p><strong>CalenderView</strong><br>
스크롤이 가능한 <strong>달력</strong>을 보여준다.<br>
탭, 클릭 이벤트로 날짜를 선택 할 수 있으며 원하는 날짜로 달력을 스크롤 하고 찾을 수 있다.<br>
<code>getDate()</code>, <code>setDate()</code>, <code>setFirstDayOfWeek()</code>, <code>getFirstDayOfWeek()</code>, <code>setMaxDate()</code> 등의 메서드가 있다.<br>
속성으로는 <code>id</code>, <code>firstDayOfWeek</code>, <code>maxDate</code>, <code>minDate</code> 등이 있다.</p>
</li>
<li>
<p><strong>RatingBar</strong><br>
<code>SeekBar</code>와 <code>ProgressBar</code>의 확장 버전으로 별 모양을 통해 평점이나 <strong>점수</strong> 또는 <strong>등급</strong>을 매길 때 사용하는 위젯이다.<br>
주요 속성으로는 <code>isIndicator</code>, <code>numStars</code>, <code>stepSize</code>, <code>rating</code> 등이 있다.<br>
RatingBar를 화면에 표시할 때 주의할점은 <code>layout_width</code> 속성입니다. 속성 값을 wrap_content가 아닌  match_parent 같은 속성으로 지정 될 경우 numStars 속성값과 관계없이 뷰 크기가 자동으로 조절되면서 표시되는 별의 개수도 의도하지 않게 늘어나게 됩니다.</p>
</li>
<li>
<p><strong>SearchView</strong><br>
안드로이드에서 <strong>검색 인터페이스</strong>를 만들 수 있는 두 가지 방식이 있다.<br>
<code>Search Dialog</code> 와 <code>Search Widget</code> 이다.<br>
<code>Search Widget</code> 은 <code>Search View</code> 의 인스턴스이다.<br>
<code>Search View</code> 는 액션바에 검색메뉴를 만들거나, submit 버튼 없이 사용자가 엔터를 눌렀을때 바로 검색이 되게 하고 싶은 경우에 사용할 수 있다.<br>
<code>iconifiedByDefault</code>, <code>queryHint</code> 등의 속성이 있다.</p>
</li>
<li>
<p><strong>SurfaceView</strong><br>
Android Application에서 View는 <code>GDI Thread</code>를  통해 <code>Surface</code>에 그려지게 된다. 만약 View에 동영상 또는 카메라 프리뷰와 같이 그려지는 양이 매우 많거나 빠른 화면 변화를 원한다면 <code>SurfaceView</code>를 사용해야 한다. <code>SurfaceView</code>의 내용은 <code>GDI Thread</code>를 통해서 <code>Surface</code>에 그려지지 않고 다른 Thread를 통해서 그려지기 때문이다. <code>SurfaceView</code>는 Window의 아래쪽에 위치하며, Window를 뚫어서(Punched) 자신이 보여지게끔 한다. 단, 해당 Window 위에 다른 View가 있는 경우 블렌딩(blended) 되어 보여지게 된다.<br>
<code>Surface</code>는 하나의 <strong>그래픽 버퍼</strong>로써 <code>SurfaceView</code>에 실제로 그림을 그리는 등의 작업을 하는 것은 <code>SurfaceHolder</code>라고 하는 <strong>콜백(Callback) 함수</strong> 다. 콜백 함수는 정의해 두기만 하면 사용자가 직접 호출하지 않더라도 운영체제가 알아서 호출해 주는 함수다.<br>
<code>SurfaceHolder</code> 를 이용해서 <code>Surface</code>라는 버퍼에 그림을 그리면 그것이 <code>SurfaceView</code>에 반영이 되고 그 결과가 사용자의 View에 표시되는 방식입니다.  <strong>더블 버퍼링</strong> 과정이라고 부른다.</p>
</li>
<li>
<p><strong>TextureView</strong></p>
</li>
</ul>
<h2 id="containers">Containers</h2>
<ul>
<li>
<p><strong>Spinner</strong><br>
목록 형태로 사용자에게 정보를 제공하는 View이다.<br>
<code>Spinner</code>를 배치할 레이아웃은 기본형 혹은 Custom으로 제작이 가능하다.<br>
<code>Spinner</code>의 외형은 기본적으로 <code>simple_spinner_item</code>과 <code>simple_spinner_dropdown_item</code>이 제공된다.</p>
</li>
<li>
<p><strong>RecyclerView</strong><br>
안드로이드 앱에서 종종 <code>ListView</code> 형식의 데이터를 스크린에 출력해야 하는 상황이 있는데, <code>RecyclerView</code>는 <strong>많은 수</strong>의 데이터를 처리할 때 생기는 리스크를 최소화 해준다.<br>
<code>RecyclerView</code>는 데이터를 <code>ViewHolder</code>의 리스트로 표현한다.<br>
<code>ViewHolder</code>는 실제 아이템의 레퍼런스를 가지며 추가할 뷰를 캐쉬하는 역할을 한다.<br>
<code>RecyclerView</code>는 처음 데이터를 표현할 때만 <code>ViewHolder</code>에 뷰를 생성한 한다. (Visbile Screen에 보여줄 갯수 + Smooth한 스크롤을 위한 추가갯수).<br>
<code>RecyclerView</code>는 미리 생성한 뷰들을 <code>Queue</code> 또는 <code>recycling bin</code>에 넣어둔다. 스크롤 시에는 큐에 저장된 뷰를 빼서 <code>RecyclerView</code>에 표현한다. 스크롤을 통해 지나간 뷰들은 다시 빼서 재사용을 위해 Queue에 넣는다.<br>
말 그대로 <strong>재사용</strong>의 효율을 극대화 한 라이브러리다.</p>
</li>
<li>
<p><strong>ScrollView</strong><br>
구현하려는 뷰의 높이가 실제 화면의 높이보다 클 때 화면을 스크롤할 수 있도록 하기 위해 사용한다.<br>
스크롤 한다는 부분에서 <code>RecyclerView</code>와 비슷하지만 <code>ScrollView</code>는 단 하나의 자식 뷰를 가질 수 있으며, 리스트 형식이 아니다. 가로 세로 스크롤 옵션 설정이 가능하다.<br>
<code>ScrollView</code>를 이용하여 내용을 감싸주면 화면의 높이보다 내용물이 커질 때 자동으로 스크롤이 가능하도록 된다.</p>
</li>
<li>
<p><strong>NestedScrollView</strong><br>
안드로이드 개발을 하다보면 <code>ScrollView</code> 안에 <code>RecyclerView</code>를 넣어야 하는 경우가 생긴다. 이럴 때,  <code>NestedScrollView</code>를 사용하면 이중스크롤 상황에서 발생할 수 있는 <strong>포커싱 문제</strong>를 해결할 수 있다. 이름처럼 중첩된 스크롤뷰라는 뜻이다. <code>RecyclerView</code> 안에서 <strong>다른 형태의 뷰</strong>가 보여지는 상황, 혹은 <strong>위에 타이틀이 있고 아래에 리스트 목록이 보이는</strong> 상황에서 사용할 수 있다.</p>
</li>
<li>
<p><strong>ViewPager</strong><br>
좌우 스크롤을 통해 화면을 넘겨볼 수 있는 기능을 제공해준다. 부분 화면 여러 개를 변환하여 보여주기 때문에 Fragment를 사용하여 구현하며, 여러 개 중 하나를 선택하는 형태의 위젯이므로 리스트뷰와 같이 어댑터를 사용하여 데이터를 분배해 주어야 한다.</p>
</li>
<li>
<p><strong>CardView</strong><br>
리스트뷰를 보여줄 때 카드 형태로 뷰를 구현하기도 한다.<br>
하지만, 직접 그림자도 그려야 하고, 틀을 만들어야 하는 어려움이 존재했다. 이를 해결하기 위해 SDK 21버전부터 <code>CardView</code>가 추가되었다.<br>
<code>CardView</code>는 <code>FrameLayout</code> 클래스를 확장한 형태다.<br>
둥근 모서리, 배경과 그림자가 추가된 <code>FrameLayout</code> 이다.<br>
일반적으로 <code>CardView</code>는 리스트 형태로 보여주기 때문에  재사용이 가능한  <code>RecyclerView</code>와 함께 사용된다.</p>
</li>
<li>
<p><strong>AppBarLayout / ToolBar</strong><br>
안드로이드에는 원래 <code>ActionBar</code>가 기본적으로 제공되고 있었지만, 액션바는 안드로이드 API 버전마다 다른 기능과 다른 동작을 제공해 개발자가 사용자에게 일관된 UX를 제공하는 데 불편함이 있었다.<br>
이에 대한 해결책으로 구글은 <code>Material Design</code> 패키지에 있는 <code>AppBarLayout</code>과 <code>ToolBar</code>를 제공한다.<br>
<code>AppbarLayout</code>은 <code>vertical LinearLayout</code>을 상속한 레이아웃으로, 특히나 스크롤 제스처에 대해 몇 가지 동작을 적용할 수 있다.<br>
단, 주의할 점은 <code>AppBarLayout</code>는 <code>CoordinatorLayout</code>의 바로 아래 자식이어야 한다. 다른 <code>ViewGroup</code> 안에서 <code>AppBarLayout</code>을 사용한다면 해당 기능은 동작하지 않는다.<br>
<code>AppBarLayout</code>이 스크롤을 인식하기 위해서는 <code>CoordinatorLayout</code> 안에 같은 수준으로 선언된 형제 뷰(sibling)가 <code>RecyclerView</code>나 <code>NestedScrollView</code>처럼 <strong>스크롤 가능</strong>한 뷰여야 한다.<br>
스크롤 가능한 sibling view는 <code>AppBarLayout.ScrollingViewBehavior</code>를 통해  <code>AppBarLayout</code>과 바인딩을 해야 한다.<br>
안드로이드 버전에 따라 다르게 동작하는 <code>Action bar</code>와 다르게, <code>Toolbar</code>는 하위 호환성을 제공함으로 많은 버전에서 일관되게 동작한다. 또한 액티비티에 기본 요소로 포함된 <code>Action bar</code> 와는 다르게 <code>Toolbar</code> 는 따로 추가해야 한다.<br>
액티비티의 레이아웃 XML에 <code>android.support.v7.widget.Toolbar</code>를 추가한 다음, 액티비티에 ".NoActionBar"가 포함된 테마를 지정하여 기본 액션바가 사용되지 않게 만들어야 한다. 그리고 액티비티의 <code>setSupportActionBar()</code> 메서드를 호출하면 툴바를 액티비티의 <code>Action bar</code> 로 사용할 수 있다.</p>
</li>
<li>
<p><strong>BottomAppBar</strong><br>
Toolbar를 확장한 클래스로, 앞서 언급한 <code>FAB</code>을 붙여서 하단의 action bar로 사용한다.</p>
</li>
<li>
<p><strong>NavigationView</strong><br>
<code>NavigationView</code> 를 사용하기 위해서는 <code>DrawerLayout</code>으로 <code>NavigationView</code>를 감싸야 한다. <code>DrawerLayout</code>은 자신의 영역 안에서 자식 뷰가 "Drawer(서랍)"와 같은 동작을 수행하도록 만들어주는 레이아웃입니다.</p>
</li>
<li>
<p><strong>BottomNavigationView</strong><br>
보통 <code>Coordinator Layout</code>, <code>Frame Layout</code>과 <code>Fragment</code>를 이용하여 구현한다.  메뉴 리소스를 구현하여 적용한다. 하단에 메뉴가 나타난다.</p>
</li>
<li>
<p><strong>TabLayout / TabItem</strong><br>
<code>TabLayout</code>은 안드로이드에서 <code>Tab</code> 기능을 구현하는데 사용된다.<br>
레이아웃 리소스에서 이를 추가할 때 <code>TabLayout</code> 과 <code>TabItem</code>을 지정하면 간단히 구현이 가능하다.<br>
소스 코드에서는 <code>TabLayout</code> 클래스의 <code>addTab()</code> 메서드를 통해 새로운 탭을 추가할 수 있다.</p>
</li>
<li>
<p><strong>ViewStub</strong><br>
차원이 없는 가벼운 뷰로, 무엇을 그리거나 레이아웃에 참여하지 않는다.  <code>android:layout</code> 속성을 포함하여 확장할 레이아웃을 지정해야 한다.<br>
레이아웃을 표시 및 확장하면 레이아웃으로 교체된다.</p>
</li>
<li>
<p><strong>&lt;Include&gt;</strong><br>
레이아웃을 작성할 때 Title 이나 Bottom에 똑같은 기능을 가지는 Layout을 여러 Activity에서 사용하는 경우가 생기는 경우가 많다. 그럴 경우 Activity 마다 같은 형식의 Layout을 만들어 주는 것보다 <code>include</code> 라는 속성을 이용하면 하나의 Title 혹은 Bottom 레이아웃을 작성한후 그것을 모든 Activity에 적용 시킬 수 있다. 이는 소스 코드 보다는 xml 파일에서 주로 작성된다.</p>
</li>
<li>
<p><strong>NavHostFragment</strong></p>
</li>
<li>
<p><strong>&lt;requestFocus&gt;</strong><br>
뷰에 Focus를 주기 위해서 사용된다. 보통 앱이 처음 시작됬을때 화면에 EditText가 있을 경우 자동으로 키보드가 올라오는 경우가 있는데 이를 방지하기 위해 다른 View에 focus를 줘서 키보드가 올라오지 않도록 많이들 쓰곤 한다. xml 파일과 소스 코드에서 모두 설정이 가능하다. <code>View.requestFocus()</code> 로 강제 포커싱이 가능하다.</p>
</li>
</ul>
<h2 id="helpers">Helpers</h2>
<ul>
<li>
<p><strong>Barrier</strong><br>
Barrier는 다국어 지원에 유용하게 사용 가능하다.<br>
예를 들어서, 세로 방향으로 2가지의 텍스트가 있을 때 더 긴쪽의 텍스트를 기준하여 특정 방향으로 뷰를 배치하고 싶을 때 사용할 수 있다. <code>barrierDirection</code> 속성을 설정하여 방향을 정할 수 있다.<br>
가로 세로 방향을 정한 후에는 <code>dp</code>, <code>px</code>, <code>percent</code> 등의 수치로 위치를 정한다.</p>
</li>
<li>
<p><strong>Guideline</strong><br>
Guideline은 뷰를 배치하기 위해 뷰그룹 내에 설정할 수 있는 일종의 기준선이다. 가로/세로로 적용할 수 있으며,  xml 상에서의 적용방법은 LinearLayout과 같이 <code>android:orientation="vertical/horizontal"</code> 로 적용할 수 있다.</p>
</li>
<li>
<p><strong>MockView</strong><br>
프로토 타이핑에 유용한 뷰다.</p>
</li>
<li>
<p><strong>ImageFilterView / ImageFilterButton</strong></p>
</li>
<li>
<p><strong>Flow</strong></p>
</li>
<li>
<p><strong>Layer</strong></p>
</li>
</ul>
<h2 id="google">Google</h2>
<h3 id="android-용-google-api">Android 용 Google API</h3>
<ul>
<li>
<p><strong>AdView</strong><br>
앱의 레이아웃에 배너 광고를 배치할 수 있는 뷰다.<br>
배너 광고를 게재하려면 먼저 광고를 게재할 <code>Activity</code> 또는 <code>Fragment</code> 레이아웃에 <code>AdView</code>를 넣으면 된다.  xml 레이아웃 파일에서 설정하는 것이 가장 쉬운 방법이다.<br>
<code>ads:adSize</code>, <code>ads:adUnitId</code> 등의 속성이 있다.</p>
</li>
<li>
<p><strong>MapView</strong><br>
기본적으로 FrameLayout을 확장한다.<br>
구글 맵 서비스에서 얻어온 지도 데이터를 보여준다.</p>
</li>
</ul>
</div>
</body>

</html>
