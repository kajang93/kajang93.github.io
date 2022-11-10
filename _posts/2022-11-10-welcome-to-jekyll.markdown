---
layout: post
title:  "JS 쿠키, 원하는 값을 배열에서 제거"
date:   2022-11-10 14:41:00
categories: Comment
---

You'll find this post in your `_posts` directory - edit this post and re-build (or run with the `-w` switch) to see your changes!
To add new posts, simply add a file in the `_posts` directory that follows the convention: YYYY-MM-DD-name-of-post.ext.

Jekyll also offers powerful support for code snippets:

{% highlight JavaScript %}
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
Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll's GitHub repo][jekyll-gh].

[jekyll-gh]: https://github.com/mojombo/jekyll
[jekyll]:    http://jekyllrb.com
