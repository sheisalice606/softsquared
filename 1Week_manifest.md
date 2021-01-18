<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>1Week_manifest</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h1 id="standard-mission">Standard Mission</h1>
<h2 id="manifest">Manifest</h2>
<ol>
<li>
<p>안드로이드의 Activity, Service, Broadcast Receiver, Content provider 는 통칭 <strong><code>4대 구성요소</code></strong> 로  <strong><code>컴포넌트</code></strong> 이다.</p>
</li>
<li>
<p>안드로이드의 <strong><code>Intent</code></strong> 는 컴포넌트간의 동작 수행을 위한 메세지 역할을 수행하는 매개체 역할을 하며, <code>Extra Data</code>를 <code>bundle</code> 객체에 담아 전달할 수 있다.<br>
밑에 나열된 속성은 Intent를 정의하는 특성이다. 안드로이드 시스템은 이와 같은 속성을 읽어 어느 앱 구성 요소를 시작해야 하는지 알 수 있다.</p>
</li>
</ol>
<ul>
<li>
<p><strong>구성 요소 이름(ComponentName)</strong><br>
선택 항목이다.<br>
인텐트를 명시적으로 만들어주는 정보다.<br>
구성 요소 이름이 없으면 해당 인텐트는 암시적 인텐트이다.<br>
다만, Service를 시작하는 경우는 항상 구성 요소 이름을 지정해야 한다.<br>
Intent 의 <code>ComponentName</code> 를 지정해야 한다.<br>
<code>setComponent()</code> 또는 Intent 생성자를 사용하여 설정한다.</p>
</li>
<li>
<p><strong>수행 작업(Action)</strong><br>
수행 작업을 나타내는 문자열이다.<br>
본인이 지정할 수도 있지만, 보통은 Intent 클래스나 다른 프레임워크 클래스가 정의한 작업 상수를 지정해야 한다.<br>
<code>ACTION_VIEW</code>, <code>ACTION_SEND</code>, <code>ACTION_MAIN</code> 등이 있다.<br>
<code>setAction()</code> 또는 Intent 생성자를 사용하여 설정한다.</p>
</li>
<li>
<p><strong>데이터(Data)</strong><br>
작업을 수행할 데이터의 MIME 유형을 참조하는 Uri 객체다.<br>
인텐트의 작업에 맞는 Uri 객체가 들어있어야 한다.<br>
인텐트 생성시 URI 와 MIME 유형을 알맞게 지정하는 것이 중요하다.<br>
URI 만 설정 -&gt; <code>setData()</code><br>
MIME 유형만 설정 -&gt; <code>setType()</code><br>
두가지 다 설정 -&gt;  <code>setDataType()</code></p>
</li>
<li>
<p><strong>카테고리(Category)</strong><br>
인텐트를 처리해야 하는 구성 요소 종류에 관한 추가 정보를 담은 문자열이다.<br>
대부분의 인텐트 안에는 카테고리가 없어도 된다.<br>
<em><code>CATEGORY_BROWSABLE</code></em> 은 대상 액티비티가 웹브라우저를 통해 시작되도록 허용하고 이미지, 이메일 메시지 등의 링크로 참조된 데이터를 표시하게 한다.<br>
<em><code>CATEGORY_LAUNCHER</code></em> 는 최초 액티비티 설정이다.<br>
카테고리는 addCategory로 설정 가능하다.</p>
</li>
</ul>
<ol start="3">
<li></li>
</ol>
<ul>
<li>
<p><strong>명시적 인텐트</strong><br>
인텐트를 충족하는 애플리케이션을 지정한다.<br>
일반적으로 앱 안에서 컴포넌트를 시작할 때 사용한다.<br>
해당 컴포넌트가 어떤 인텐트 필터를 선언하든 무관하게 항상 대상에 전달된다.</p>
</li>
<li>
<p><strong>암시적 인텐트</strong><br>
특정 컴포넌트의 이름을 대지는 않지만 이미 약속된 일반적인 작업을 선언한다.<br>
안드로이드 시스템이 해당 인텐트와 일치하는 인텐트 필터를 검색하고, 일치하는 항목을 찾으면 시스템이 해당 액티비티의 onCreate() 를 호출하여 이를 전달한다. 호환되는 인텐트 필터가 여러 개인 경우, 시스템에서 대화상자를 표시하여 사용자가 어느 앱을 사용할지 직접 선택이 가능하다.<br>
암시적 인텐트를 수신하기 위해서는 <code>CATEGORY_DEFAULT</code> 카테고리를 인텐트 필터에 포함해야 한다.</p>
</li>
</ul>
<ol start="4">
<li>
<p><strong>인텐트 필터</strong><br>
Manifest 파일에 들어있는 표현으로, 해당 구성 요소가 수신하고자 하는 인텐트의 유형을 나타낸다. 인텐트 필터를 선언하지 않는 경우 암시적 인텐트는 수신할 수 없다. <code>&lt;intent-filter&gt;</code> 로 정의하고 &lt;action&gt;, &lt;data&gt;, &lt;category&gt; 중 하나 이상을 사용하여 허용 인텐트 유형을 지정한다.</p>
</li>
<li>
<p>Manifest 파일의 <strong>package 정보</strong>는 컴포넌트와 소스코드가 들어있는 프로젝트의 기본 패키지 이름과 항상 일치해야 한다.<br>
앱이 APK 형태로 컴파일 된 후에는 고유의 어플리케이션 ID가  build.gradle 파일의 <code>applicationId</code> 속성에 지정된 값으로 전환된다. 따라서 <code>package</code> 이름과 <code>applicationId</code> 속성을 동일하게 유지하면 된다.</p>
</li>
<li>
<p>Android 앱은 특정 데이터나 시스템 기능에 엑세스하기 위한 <strong>권한</strong>을 요청해야 한다. 각 권한은 고유한 label로 식별이 가능하며, Android 6.0부터 사용자는 런타임에서 앱 권한을 승인하거나 거절할 수 있게 되었다.<br>
Manifest에서 <strong><code>&lt;uses-permission&gt;</code></strong> 요소로 권한을 요청할 수 있다.</p>
</li>
<li>
<p>Manifest 파일에서는 앱에 필요한 하드웨어, 소프트웨어 기능을 선언할 수 있다. 따라서 앱과 호환되는 기기 유형을 선언할 수 있다. 여러 태그가 있지만 일반적으로는 <strong><code>&lt;uses-feature&gt;</code></strong> 요소를 사용하여 선언할 수 있다.</p>
</li>
<li>
<p>해당 앱이 호환되는 최소 버전의 API를 나타려면 Manifest 파일에 <code>&lt;uses-sdk&gt;</code> 태그와 해당 태그의 <code>minSdkVersion</code>특성을 포함해야 한다. 하지만 이는 build.gradle 파일의 해당 속성으로 재 정의되기 때문에 이곳에서 값을 설정한다.</p>
</li>
<li>
<p><strong><code>&lt;manifest&gt;</code></strong> 및 <strong><code>&lt;application&gt;</code></strong> 요소만 필수 태그다.<br>
두 요소는 각각 한번만 실행되어야 한다. 다른 요소들은 규제가 없다.<br>
컴포넌트 요소들은 어느 순서로든 배치가 가능하다.<br>
이 규칙에는 두 가지 예외 사항이 있다.</p>
</li>
</ol>
<ul>
<li><strong><code>&lt;activity-alias&gt;</code></strong> 요소는 이 요소를 별명으로 사용하는 <strong><code>&lt;activity&gt;</code></strong> 다음에 와야한다.</li>
<li><strong><code>&lt;application&gt;</code></strong> 요소는 <strong><code>&lt;manifest&gt;</code></strong> 요소 내부의 마지막 요소여야 한다.</li>
</ul>
<ol start="10">
<li>어떤 Manifest 요소는 앱 컴포넌트에 대해 각각 작은 아이콘과 텍스트 레이블을 표시하기 위한 <code>icon</code> 과 <code>label</code>특성이 있다. 각각의 경우 상위에 설정된 아이콘과 레이블은 모든 하위 컴포넌트에 대한 아이콘과 레이블 값이 된다. 예를 들어 application 태그에 설정된 아이콘과 레이블이 앱의 각 컴포넌트에 대한 기본값이 된다. 또 유저의 앱 선택 상황에서 특별한 동작을 취하고 싶다면 intent filter 태그에 선언하기도 한다.</li>
</ol>
</div>
</body>

</html>
