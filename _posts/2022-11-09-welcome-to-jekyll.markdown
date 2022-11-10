---
layout: post
title:  "JS 쿠키에서 원하는 값을 배열에서 제거"
date:   2022-11-09 11:10:00
categories: JAVASCRIP
---

구글링해도 안나오길래..

기존 `red, yellow, green`을 쿠키에 넣고

필요할때마다 쿠키를 가져와서 단어가 있으면 원하는 행동 호출하고

이런 식이였어요. 참고부탁드려요~!


{% highlight javascript %}
//기존에 있는 쿠키를 가져옴
var sList = getCookie("cookie 컬럼명");
var aList = [];

//쿠키가 있으면 기존 string 형태를 ,따옴표 기준으로 단어를 배열로 형성 (없으면 제외)
  if (null !== sList) aList = sList.split(',');
    //제거하고 싶은 단어를 배열에 index 번호를 index2에 추출
    var index2 = aList.indexOf('' + '제거하고 싶은 단어' + '');
    
    //배열을 for문 돌린다
    for (var i = 0; i < aList.length; i++) {
        var index = aList[i].indexOf('제거하고 싶은 단어');
        
        if (index > -1) {
            //제거하고 싶은 단어가 있을때
            aList.splice(index2, 1);
            //aList에서 index2를 추출한 번호를 제거
        }
    }
//제거 후 남은 배열 setCookie 인자 전달
setCookie("cookie 컬럼명", aList, 365);


//setCookie 함수
function setCookie(name, value, exp) {
    var date = new Date();
    //오늘 날짜부터 365일 추가한 날짜까지 cookie 저장
    date.setTime(date.getTime() + exp * 24 * 60 * 60 * 1000);
    document.cookie = name + '=' + value + ';expires=' + date.toUTCString() + ';path=/';
}


{% endhighlight %}
