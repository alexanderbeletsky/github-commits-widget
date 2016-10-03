github.commits.widget
=================

This is a very simple to use widget that perfect for open source projects sites. On open source project site you typically want to show how active is your development is. Namely, how many commits your project have and how often are they.

Installation
------------

Install bower component,

```bash
	$ bower install github.commits.widget
```

How to use
----------
Reference 'github.commits.widget.js' and containter div and place such script.

```html
<script>
	$(function() {
		$('#github-commits').githubInfoWidget(
			{ user: 'alexanderbeletsky', repo: 'github.commits.widget', branch: 'master' });
	});
</script>
```

This sample shows a short *last modification* message related to the site (e.g., `Last modification just now`):

```yaml
...
baseurl:             "/my-repo"
branch:              "gh-pages"
...
author:
  name:              itsme
...
```

```html
Last modification<span id="last-site-mod"> unknown</span>
```

```html
$(function() {
	$('#last-site-mod').githubInfoWidget(
		{ user: '{{ site.author.name }}', repo: '{{ site.baseurl }}', branch: '{{ site.branch }}', nouser: true, nomsg: true, abstime: false, simple: 2, last: 1, limitMessageTo: 500 });
});
</script>
```

This sample shows a short *last modification* message related to a specific page (e.g., `Last modification: 2016-10-03, about 2 hours ago`):

```html
Last modification: <span id="last-page-mod">unknown</span>
```

```html
<script>
$(function() {
	$('#last-page-mod').githubInfoWidget(
		{ user: '{{ site.author.name }}', repo: '{{ site.baseurl }}', branch: '{{ site.branch }}', path: '{{ page.path }}', nouser: true, nomsg: true, abstime: true, simple: 1, last: 1, limitMessageTo: 500 });
});
</script>
```

Configuration
-------------

* user is your github account
* repo is name of repository; can be with or without initial `/`
* branch is the name of branch you want to track
* nouser (true/false/unset): if set to true, does not show user
* noavatar (true/false/unset): if set to true, does not show avatar
* nomsg (true/false/unset): if set to true, does not show message
* abstime (true/false/unset): if set to true, shows absolute time
* noreltime (true/false/unset): if set to true, does not show relative time
* simple (unset, 1, 2): if set to 1, shows a simple message without list; if set to 2, also show the number of commits in the tooltip


You might limit number commits shown in widget by providing with 'last' parameter:

```html
<script>
	$(function() {
		$('#github-commits').githubInfoWidget(
			{ user: 'alexanderbeletsky', repo: 'github.commits.widget', branch: 'master', last: 15 });
	});
</script>
```

You might also limit the length of commit message, by 'limitMessageTo' parameter:

```html
<script>
	$(function() {
		$('#github-commits').githubInfoWidget(
			{ user: 'alexanderbeletsky', repo: 'trackyt.api.csharp', branch: 'master', last: 15, limitMessageTo: 30 });
	});
</script>
```

You can control the avatar size (in pixels) by providing avatarSize option. Default value is 20px.

```html
<script>
	$(function() {
		$('#github-commits').githubInfoWidget(
			{ user: 'alexanderbeletsky', repo: 'trackyt.api.csharp', branch: 'master', last: 15, limitMessageTo: 30, avatarSize: 33 });
	});
</script>
```

# Legal Info (MIT License)

Copyright (c) 2012 Alexander Beletsky

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
