# 1. Headers

# text // h1수준의 제목
##### text // h6수준의 제목
text // h1수준의 제목
==
text // h6수준의 제목
--



# 2. Links
[Hexo](https://hexo.io/) // [텍스트]에 (링크)걸림
http://github.com // Automatic!



# 3. 코드 블럭 ( <figure class=”highlight language“> )
```뒤에 언어를 명시하면 해당 언어의 문법에 맞게 하이라이트해준다.

```language // python, bash
$ hexo new "My new post" // backtick 3개 이상부터
```


# 4. 코드 블럭 옵션(언어 설정, 제목, URL)

``` [language] [title] [url] [link text]
code snippet
```
// 예시
``` C Array.map www.naver.com naver
array.map(callback[, thisArg]) 
```


# 5. 깜장색배경 ( <pre> )
까만색으로 표기하고싶은 부분을 들여쓰기 (Tab 1번)
<pre></pre>태그 자체가 수식 없이 그대로 보여주는거


# 6. Emphasis (<code>)
``강조`` 또는 `강조`


# 7. Escaping characters
&lt; <
&gt; >


# 8. 글자 효과
**bold** __bold__
*italic* _italic_
~~취소~~
<u> 밑줄 </u>


# 9. 수평선
*******************************************************


# 10. Blockquotes
> text // >를 많이 붙일수록 커진다. >>> 3개까지.


# 11. Images
이미지는 어쩔 수 없이 <table>로 감싸거나 해서 맞춰야 할 것 같다.
Inline script로 배치를 조절해야하는데
table태그를 쓰면 해당 줄이 차지하는 위치만큼 <br>태그가 먹음.
테이블 작성해놓고 줄바꿈 모두 삭제해야함ㅠ
{% img /images/foldername/filename width height text %}


# 12. Lists
1. asdf
2. qwer
3. tyui
+ asdf
- asdf


# 13. Tables
테이블 마크다운. 헥소에서도 그려짐.
테이블이 안만들어지면 윗 문장과 한 줄 간격을 두고.
두번째 열의 :로 여백을 어느 정도 조절할 수 있다.
|컬럼명1|컬럼명2|컬럼명3|
|:-:|:-:|:-:|
|값1|값2|값3|


# 14. Youtube
{% youtube video_id %}
