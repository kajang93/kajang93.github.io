---
layout: post
title:  "JS 쿠키, 원하는 값을 배열에서 제거"
date:   2022-11-10 11:00:00
categories: Javascript
---

{% highlight javascript %}
var sList = getCookie("cookie 컬럼명");
var aList = [];
if (null !== sList) aList = sList.split(',');
var index2 = aList.indexOf('' + idx + '');

for (var i = 0; i < aList.length; i++) {
    var index = aList[i].indexOf(idx);
    if (index > -1) {
        aList.splice(index2, 1);
    }
}
setCookie("cookie 컬럼명", aList, 365);

{% endhighlight %}

