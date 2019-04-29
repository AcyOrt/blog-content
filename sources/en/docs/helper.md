---
category: Customization
title: Helper
order: 6
---

AcyOrt has built-in helper functions for rendering templates, and you can customize helper functions

### Built-in functions

There are 4 built-in functions that cannot be overridden by custom function

**URL**

Return the URL path with the root directory

```html
{{ _url(path) }}

<!-- example, current root path is `root` -->
<p>{{ _url('path') }}</p> <!-- <p>/root/path/to</p> -->
<a href="{{ _url() }}">link</a> <!-- <a href="/root">link</a> -->
```

**time**

Time formatting, depending on the time zone, language settings, check [Moment.js](http://momentjs.com/) for more details

```html
{{ _time(date, format) }}

<!-- example -->
<p>{{ _time(Date.now(), 'YYYY') }}</p> <!-- <p>2018</p> -->
```

**language**

Use `__` or `_n` in the template to translate multilingual text, check [i18n ](https://github.com/acyortjs/i18n)

```html
{{ __(page.title) }}
{{ _n(page.posts) }}

<!-- example -->

<!--
The yaml language file

# i18n config yml
index:
  title: Home
posts:
  zero: No posts
  one: One post
  other: %d posts

-->

<p>{{ __('index.title') }}</p> <!-- <p>Home</p> -->
<p>{{ _n('posts', 3) }}</p> <!-- 3 posts -->
```

### Custom functions

Custom helper functions, check [helper](/api/helper/)