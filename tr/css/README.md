# CSS - güzelleştirin!

Blogumuz çirkin görünüyor, değil mi? Kendini iyi vakti geldi? Bunun için CSS kullanacağız.

## CSS nedir?

Basamaklı Stil sayfası (CSS), bir biçimlendirme dili (HTML gibi) kulanarak yazılan bir web sitesinin görünümünü ve biçimlendirmesini açıklamak için kullanılan dildir. Web sayfamız için makyaj olarak davranın. ;)

Ancak sıfırdan başlamak istemiyoruz, değil mi? Bir kez daha, programcıların internette ücretsiz olarak piyasaya sürdüğü şeyleri kullanacağız. Tekerleği yeniden icat etmek eğlenceli değil, biliyorsun.

## Bootstrap'ı kullanalım!

Önyükleme, güzel web sitelerini geliştirmek için en popüler HTML ve CSS çerçevesinden biridir:

Twitter'da çalışan programcılar tarafından yazılmıştır. Şimdi dünyanın her yerinden gönüllüler tarafından geliştirildi!

## Önyükleme Kayışını Yükle

To install Bootstrap, you need to add this to your `<head>` in your `.html` file:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css">
```

Bu, projeniz herhangi bir dosya eklemez. Sadece internette bulunan dosyalara işaret ediyor. Sadece devam edin, web sitenizi açın ve sayfayı yenileyin. İşte burada!

![Şekil 14.1](images/bootstrap1.png)

Zaten daha güzel görünüyorsun!

## Django'daki statik dosyalar

Finally we will take a closer look at these things we've been calling **static files**. Statik dosyalar, tüm CSS ve resimlerdir. Onların içeriği istek içeriğine bağlı değildir ve her kullanıcı için aynı olacaktır.

### Django için statik dosyaları nerede koymalı

Django already knows where to find the static files for the built-in "admin" app. Now we just need to add some static files for our own app, `blog`.

We do that by creating a folder called `static` inside the blog app:

    djangogirls
    ├── blog
    │   ├── migrations
    │   ├── static
    │   └── templates
    └── mysite
    

Django uygulamalarınızın klasörlerinizin herhangi birinde "statik" olarak adlandırılan klasörleri otomatik olarak bulacaktır. Sonra içeriğini statik statik dosyalar olarak kulanılabilir.

## İlk CSS dosyanız!

Web sayfanıza kendi stilinizi eklemek için şimdi bir CSS dosyası oluşturalım. Create a new directory called `css` inside your `static` directory. Then create a new file called `blog.css` inside this `css` directory. Ready?

    djangogirls
    └─── blog
         └─── static
              └─── css
                   └─── blog.css
    

Time to write some CSS! Open up the `blog/static/css/blog.css` file in your code editor.

Burada CSS'yi özelleştirme ve öğrenmeyle ilgili çok derinlemesine gidemeyeceğiz. Daha fazla bilgi edinmek isterseniz, bu sayfanın sonunda ücretsiz bir CSS jursu için bir öneri var.

Ama en azından biraz yapalım. Belki başlığımızın rengini değiştirebiliriz? Renkleri anlamak için bilgisayarlar özel kodlar kullanır. These codes start with `#` followed by 6 letters (A–F) and numbers (0–9). For example, the code for blue is `#0000FF`. You can find the color codes for many colors here: http://www.colorpicker.com/. You may also use [predefined colors](http://www.w3schools.com/colors/colors_names.asp), such as `red` and `green`.

In your `blog/static/css/blog.css` file you should add the following code:

{% filename %}blog/static/css/blog.css{% endfilename %}

```css
h1 a {
    color: #FCA205;
}
```

`h1 a` is a CSS Selector. This means we're applying our styles to any `a` element inside of an `h1` element. So when we have something like `<h1><a href="">link</a></h1>`, the `h1 a` style will apply. In this case, we're telling it to change its color to `#FCA205`, which is orange. Elbette, kendi rengini buraya koyabilirsin!

Bir CSS dosyasında, HTML dosyasındaki öğelerin stillerini belirleriz. Öğeleri tanımlamanın ilk yolu öğe adıdır. Bunları HTML bölümündeki etiketler olarak hatırlayabilirsin. Things like `a`, `h1`, and `body` are all examples of element names. We also identify elements by the attribute `class` or the attribute `id`. Class and id are names you give the element by yourself. Classes define groups of elements, and ids point to specific elements. For example, you could identify the following tag by using the tag name `a`, the class `external_link`, or the id `link_to_wiki_page`:

```html
<a href="https://en.wikipedia.org/wiki/Django" class="external_link" id="link_to_wiki_page">
```

You can read more about [CSS Selectors at w3schools](http://www.w3schools.com/cssref/css_selectors.asp).

We also need to tell our HTML template that we added some CSS. Open the `blog/templates/blog/post_list.html` file and add this line at the very beginning of it:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{% load staticfiles %}
```

We're just loading static files here. :) Between the `<head>` and `</head>` tags, after the links to the Bootstrap CSS files, add this line:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<link rel="stylesheet" href="{% static 'css/blog.css' %}">
```

The browser reads the files in the order they're given, so we need to make sure this is in the right place. Otherwise the code in our file may be overriden by code in Bootstrap files. We just told our template where our CSS file is located.

Your file should now look like this:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{% load staticfiles %}
<html>
    <head>
        <title>Django Girls blog</title>
        <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
        <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css">
        <link rel="stylesheet" href="{% static 'css/blog.css' %}">
    </head>
    <body>
        <div>
            <h1><a href="/">Django Girls Blog</a></h1>
        </div>

        {% for post in posts %}
            <div>
                <p>published: {{ post.published_date }}</p>
                <h1><a href="">{{ post.title }}</a></h1>
                <p>{{ post.text|linebreaksbr }}</p>
            </div>
        {% endfor %}
    </body>
</html>
```

OK, save the file and refresh the site!

![Figure 14.2](images/color2.png)

Nice work! Maybe we would also like to give our website a little air and increase the margin on the left side? Let's try this!

{% filename %}blog/static/css/blog.css{% endfilename %}

```css
body {
    padding-left: 15px;
}
```

Add that to your CSS, save the file and see how it works!

![Figure 14.3](images/margin2.png)

Maybe we can customize the font in our header? Paste this into your `<head>` in `blog/templates/blog/post_list.html` file:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<link href="//fonts.googleapis.com/css?family=Lobster&subset=latin,latin-ext" rel="stylesheet" type="text/css">
```

As before, check the order and place before the link to `blog/static/css/blog.css`. This line will import a font called *Lobster* from Google Fonts (https://www.google.com/fonts).

Find the `h1 a` declaration block (the code between braces `{` and `}`) in the CSS file `blog/static/css/blog.css`. Now add the line `font-family: 'Lobster';` between the braces, and refresh the page:

{% filename %}blog/static/css/blog.css{% endfilename %}

```css
h1 a {
    color: #FCA205;
    font-family: 'Lobster';
}
```

![Şekil 14.3](images/font.png)

Harika!

Yukarıda belirtildiği gibi, CSS'nin bir sınıf kavramı var. Bunlar, HTML kodunun bir parçasını adlandırmanıza ve stilleri yalnızca diğer parçalara dokunmadan bu parçaya uygulamanızı sağlar. Bu süper yararlı olur! Belki de div'ınız vardır(üstbilgi ve yayınınız gibi) farklı şeyler yapıyorsunuz. Bir sınıf onları farklı görünmelerine yardımcı olur.

Go ahead and name some parts of the HTML code. Add a class called `page-header` to your `div` that contains your header, like this:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<div class="page-header">
    <h1><a href="/">Django Girls Blog</a></h1>
</div>
```

And now add a class `post` to your `div` containing a blog post.

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<div class="post">
    <p>published: {{ post.published_date }}</p>
    <h1><a href="">{{ post.title }}</a></h1>
    <p>{{ post.text|linebreaksbr }}</p>
</div>
```

Şimdi, farklı seçicilere bildirim blokları ekleyeceğiz. Selectors starting with `.` relate to classes. Aşağıdaki kodları anlamanıza yardımcı olabilecek birçok harika öğretici ve Web'de CSS hakkında açıklamalar bulunur. For now, just copy and paste it into your `blog/static/css/blog.css` file:

{% filename %}blog/static/css/blog.css{% endfilename %}

```css
.page-header {
    background-color: #ff9400;
    margin-top: 0;
    padding: 20px 20px 20px 40px;
}

.page-header h1, .page-header h1 a, .page-header h1 a:visited, .page-header h1 a:active {
    color: #ffffff;
    font-size: 36pt;
    text-decoration: none;
}

.content {
    margin-left: 40px;
}

h1, h2, h3, h4 {
    font-family: 'Lobster', cursive;
}

.date {
    color: #828282;
}

.save {
    float: right;
}

.post-form textarea, .post-form input {
    width: 100%;
}

.top-menu, .top-menu:hover, .top-menu:visited {
    color: #ffffff;
    float: right;
    font-size: 26pt;
    margin-right: 20px;
}

.post {
    margin-bottom: 70px;
}

.post h1 a, .post h1 a:visited {
    color: #000000;
}
```

Ardından, bildirileri sınıf bildirimleri ile görüntüleyen HTML kodunu çevreleyin. Değiştirin:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{% for post in posts %}
    <div class="post">
        <p>published: {{ post.published_date }}</p>
        <h1><a href="">{{ post.title }}</a></h1>
        <p>{{ post.text|linebreaksbr }}</p>
    </div>
{% endfor %}
```

in the `blog/templates/blog/post_list.html` with this:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<div class="content container">
    <div class="row">
        <div class="col-md-8">
            {% for post in posts %}
                <div class="post">
                    <div class="date">
                        <p>published: {{ post.published_date }}</p>
                    </div>
                    <h1><a href="">{{ post.title }}</a></h1>
                    <p>{{ post.text|linebreaksbr }}</p>
                </div>
            {% endfor %}
        </div>
    </div>
</div>
```

Bu dosyaları kaydedin ve web sitenizi yenileyin.

![Şekil 14.4](images/final.png)

Bravo! Harika görünüyor, değil mi? HTML'ye sınıf eklediğimiz yerleri bulmak için yapıştırdığımız kodu inceleyin ve bunları CSS'de kullandık. Turkuaz olmasını istersen, nerden değiştirebilirsin?

Don't be afraid to tinker with this CSS a little bit and try to change some things. Playing with the CSS can help you understand what the different things are doing. If you break something, don't worry – you can always undo it!

We really recommend taking this free online [Codeacademy HTML & CSS course](https://www.codecademy.com/tracks/web). It can help you learn all about making your websites prettier with CSS.

Ready for the next chapter?! :)