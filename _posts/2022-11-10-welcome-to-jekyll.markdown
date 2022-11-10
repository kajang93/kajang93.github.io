---
layout: post
title:  "JS 쿠키에서 원하는 값을 배열에서 제거"
date:   2022-11-09 11:10:00
categories: JAVASCRIP
---

You'll find this post in your `_posts` directory - edit this post and re-build (or run with the `-w` switch) to see your changes!
To add new posts, simply add a file in the `_posts` directory that follows the convention: YYYY-MM-DD-name-of-post.ext.

Jekyll also offers powerful support for code snippets:

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
{% endhighlight %}
Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll's GitHub repo][jekyll-gh].

[jekyll-gh]: https://github.com/mojombo/jekyll
[jekyll]:    http://jekyllrb.com
