# Personal theme adjusted

*Ghost*의 **Kasper** 테마 사용, 테마 제작자가 요구한 부분 추가 및 수정:

* `gem install jekyll-paginate`
* **baseurl -> " "**
* `gem build`


# Remove Dummy texts 

기본으로 첨부되어 있는 더미 텍스트 및 게시물 등 삭제 및 개인정보로 대체:

* **name: YK's New Blog**
* **description: study & others**
* **meta_description: "Codes and life stuffs"**
* **domain_name:** `"http://Poiurity.github.io"`
* **author: "LEE YEONGUK"**
* **about me ->** `about.md` **: Blog discription**
* 이 외에도 `https://Poiurity.github.io`에 나타나는 모든 개인정보 포함

# Add Images
`favicon.ico` 추가 및 profile 이미지 추가

* **profile:**
    ![profile](https://raw.githubusercontent.com/Poiurity/Poiurity.github.io/main/assets/images/profile.png)
* **favicon:**
    ![favicon](https://raw.githubusercontent.com/Poiurity/Poiurity.github.io/main/assets/favicon.ico)

# Add plug-ins
*disqus*, *jekyll-admin* plug-in 추가

* **disqus** 
**default(kasper) :** disqus plugin 추가 포맷 존재 및 `disqus.html` 파일을 통해 유동적으로 실행
**modified:** `post.html`에 아래의 코드 추가
```html
<h2>Comments</h2>
            <div id="disqus_thread"></div>
            <script>
				let PAGE_URL = "{{site.url}}{{page.url}}"
				let PAGE_IDENTIFIER = "{{page.url}}"
				var disqus_config = function () {
				this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
				this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
				};
				(function() { // DON'T EDIT BELOW THIS LINE
				var d = document, s = d.createElement('script');
				s.src = 'https://poiurity.disqus.com/embed.js';
				s.setAttribute('data-timestamp', +new Date());
				(d.head || d.body).appendChild(s);
				})();
			</script>
			<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
```
* **jekyll-admin**
`GemFile` 에 코드 `gem "jekyll-admin"` , `group: :jekyll_plugins` 추가 및 `bundle install` 진행