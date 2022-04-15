# **javascript 작성 방식** 
자바스크립트는 문서 내에 작성할 수도 있고 외부 파일로 분리해 작성할 수도 있다. 

- ## **인라인 자바스크립트(Inline javascript)**
    - 태그 내에 직접 자바스크립트 명령을 작성할 수 있다. 
    - 이벤트 핸들러 속성을 지정해 자바스크립트를 실행하도록 하는 고전적인 방식이지만 종종 사용한다. 
    - CSS 에서도 이러한 인라인 문법을 볼 수 있지만 HTML 문서와 분리하는 것이 원칙이므로 권장하지는 않는다. 
    ```html
    <ul>
        <li onclick="alert('멍멍!');">강아지</li>
        <li>소</li>
        <li>닭</li>
        <li onclick="alert('냐옹~');">고양이</li>
    </ul>
    ```
    첫 번째와 마지막 <li> 태그에 onclick 속성을 추가해 클릭하면 경고창을 띄우게 했다. 
    다시 한 번 말하지만, 현대적인 웹에선 CSS와 HTML, javascript 는 분리해서 작성하는게 원칙이다. 

- ## **내부 자바스크립트(Internal javascript)**
    - HTML 문서 내 별도의 영역에 자바스크립트를 작성하는 방식이다.
    ```html
    <body>
        <ul>
            <li id="dog">강아지</li>
            <li>소</li>
            <li>닭</li>
            <li>고양이</li>
        </ul>

        <script>
            var dog = document.getElelemtById('dog');

            // 강아지를 클릭 시 함수를 실행 
            dog.onclick = function () {
                alert('멍멍!');
            }
        </script>
    </body>
    ```

- ## **외부 자바스크립트(External javascript)**
    - HTML과 자바스크립트를 분리해 외부 자바스크립트 파일(확장자 *.js)로 작성한다. 
    - 문서에서 불러올 때는 script 태그 안의 src 속성에 자바스크립트 파일명을 지정한다. 
    - script 태그를 사용하는 방식에는 두 가지가 있는데, 하나는 그 안에 자바스크립트 코드를 작성하기 위한 일반적인 방식이고, 다른 하나는 script src="app.js" 와 같은 형식으로 내부에 src 속성을 추가하여 외부 자바스크립트 파일을 불러오는 목적으로 사용하는 방식이다.   
    후자의 경우 안에 자바스크립트를 쓰면 무시된다. 
    ```html
        <body>
            <h1>외부 자바스크립트</h1>
            <script src="app.js"></script>
        </body>
    ```
    - 자바스크립트는 HTML을 먼저 불러온 후에 실행되어야 하기 때문에 문서 하단(<body>) 태그가 끝나기 전에 작성한다. 이벤트 핸들러(onload)를 이용해 문서를 불러올 때까지 기다렸다가 자바스크립트를 실행하도록 할 수 있는데, 이러한 경우에는 상단에 작성할 수 있다. 

    