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

Sonunda ** statık dosyalar </ 0> olarak adlandırdığımız şeyleri yakından inceleyeceğiz . Statik dosyalar, tüm CSS ve resimlerdir. Onların içeriği istek içeriğine bağlı değildir ve her kullanıcı için aynı olacaktır.</p> 

### Django için statik dosyaları nerede koymalı

Django, dahili "admin" uygulaması için statik dosyaları nerede bulacağını zaten biliyor. Şimdi kendi uygulamanız için ` blog </ 0> için bazı statik dosyalar eklememiz yeterlidir .</p>

<p>Bunu, blog uygulaması içinde <code> statik </ 0> olarak adlandırılanbir klasör oluşturarak yaparız :</p>

<pre><code>djangogirls
├── blog
│   ├── migrations
│   ├── static
│   └── templates
└── mysite
`</pre> 

Django uygulamalarınızın klasörlerinizin herhangi birinde "statik" olarak adlandırılan klasörleri otomatik olarak bulacaktır. Sonra içeriğini statik statik dosyalar olarak kulanılabilir.

## İlk CSS dosyanız!

Web sayfanıza kendi stilinizi eklemek için şimdi bir CSS dosyası oluşturalım. ` statik </ 0> dizininizin içine <code> css </ 0> adında yeni bir dizin oluşturun . Daha sonra bu <code> css </ 0> dizisinin içine <code> blog.css </ 0> adında yeni bir dosya oluşturun . Hazır?</p>

<pre><code>djangogirls
└─── blog
     └─── static
          └─── css
               └─── blog.css
`</pre> 

Bazı CSS yazma zamanı! Aç ` blog / statik / css / blog.css </ 0> kodunuzu düzenleyicisinde dosyayı.</p>

<p>Burada CSS'yi özelleştirme ve öğrenmeyle ilgili çok derinlemesine gidemeyeceğiz. Daha fazla bilgi edinmek isterseniz, bu sayfanın sonunda ücretsiz bir CSS jursu için bir öneri var.</p>

<p>Ama en azından biraz yapalım. Belki başlığımızın rengini değiştirebiliriz?
Renkleri anlamak için bilgisayarlar özel kodlar kullanır. Bu kodlar <code> # </ 0> ile başlar ve ardından 6 harf (A-F) ve sayılar (0-9) gelir. Örneğin, mavi kod <code> # 0000FF </ 0> ' dır . Birçok renk renk kodunu http://www.colorpicker.com/ adresinde bulabilirsiniz. <code> Kırmızı </ 1> ve <code> Yeşil </ 1> gibi <a href="http://www.w3schools.com/colors/colors_names.asp"> önceden tanımlı renkler </ 0> 'i de kullanabilirsiniz .</p>

<p>Reklamlara <code> Blog / statık / css 7 blog.css </ 0> aşağıdaki kodu eklemek gerekir file:</p>

<p>{% filename%} blog / statık / css / blog.css {% endfilename%}</p>

<pre><code class="css">h1 a {
    color: #FCA205;
}
`</pre> 

` h1 a </ 0> bir CSS Seçici'dir. Bu, stilleri bir <code> h1 </ 0> öğesinin içindeki herhangi bir <code> a </ 0> öğesini uyguladığımızı gösterir . Böylece, <code>&lt;h1&gt;&lt;a href=""&gt; bağlantı </ 0> gibi bir şey olduğunda , <code> h1 a </ 1> tarzı geçerli olur . Bu durumda, portakal rengini <code> # FCA205 </ 0> olarak değiştirmesini söylüyoruz . Elbette, kendi rengini buraya koyabilirsin!</p>

<p>Bir CSS dosyasında, HTML dosyasındaki öğelerin stillerini belirleriz. Öğeleri tanımlamanın ilk yolu öğe adıdır. Bunları HTML bölümündeki etiketler olarak hatırlayabilirsin. Gibi şeyler <code> bir </ 0> , <code> h1 </ 0> ve <code> vücut </ 0> eleman isimleri örnekleridir .
Öğeleri, <code> sınıfı </ 0> özniteliği veya <code> kimliği </ 0> özniteliği ile tanımlıyoruz . Sınıf ve kimlik, öğeyi kendiniz verdiğiniz isimlerdir. Sınıfların öğelerin gruplarını tanımlar ve kimlikler belirli öğelere işaret eder. For example, you could identify the following tag by using the tag name <code>a`, the class `external_link`, or the id `link_to_wiki_page`:

```html
<a href="https://en.wikipedia.org/wiki/Django" class="external_link" id="link_to_wiki_page">
```

You can read more about [CSS Selectors at w3schools](http://www.w3schools.com/cssref/css_selectors.asp).

HTML şablonumuza bazı CSS eklediğimizi de söylemeliyiz. Aç ` blog / templates 7 blog / post_list.html </ 0>vdosya ve bunun en başında bu satırı ekleyin:</p>

<p>{% filename%} blog 7 şablonlar / blog / posta_list.html</p>

<pre><code class="html">{% load staticfiles %}
`</pre> 

Sadece statik dosyaları burada yüklüyoruz. :) `<head>` ve ` </ 2> </ 1> etiketleri arasında, önyüklenirler CSS dosyalarına yapılan bağlantılar sonrasında şu satırı ekleyin:</p>

<p>{% filename%} blog / şablonlar / posta_list.html {% endfilename%}</p>

<pre><code class="html"><link rel="stylesheet" href="{% static 'css/blog.css' %}">
`</pre> 

Tarayıcı dosyaları verilen sırayla okuyor, bu yüzden doğru yerde olduğundan emin olmalıyız. Aksi kodları dosyamızdaki kodları önyüklenirler dosyalarındaki kodlarla geçersiz kılınabilir. Sadece CSS dosyamızın bulunduğu şablonumuzu söyledik.

Dosyanız şimdi şöyle görünmelidir:

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

Tamam, dosyayı kaydedin ve siteyi yenileyin!

![Şekil 14.2](images/color2.png)

İyi iş! Belki de web sitemize biraz hava vermek ve sol taraftaki marjı artırmak istiyoruz? Hadi bunu deneyelim!

{% filename %}blog/static/css/blog.css{% endfilename %}

```css
body {
    padding-left: 15px;
}
```

Bunu CSS'nize ekleyin, dosyayı kaydedin ve nasıl çalıştığını görün!

![Şekil 14.3](images/margin2.png)

Belki yazı tipini başlığımızda özelleştirebiliriz? Senin yapıştırın `<head>` içinde ` blog / templates / blog /post_list.html </ 1> dosyasında:</p>

<p>{% filename %}blog/templates/blog/post_list.html{% endfilename %}</p>

<pre><code class="html"><link href="//fonts.googleapis.com/css?family=Lobster&subset=latin,latin-ext" rel="stylesheet" type="text/css">
`</pre> 

As before, check the order and place before the link to `blog/static/css/blog.css`. This line will import a font called *Lobster* from Google Fonts (https://www.google.com/fonts).

Find the `h1 a` declaration block (the code between braces `{` and `}`) in the CSS file `blog/static/css/blog.css`. Şimdi ` font- aile satırını ekleyin : 'ıstakoz'; </ 0> ' yı işaretleyin ve sayfayı yenileyin:</p>

<p>{% filename %}blog/static/css/blog.css{% endfilename %}</p>

<pre><code class="css">h1 a {
    color: #FCA205;
    font-family: 'Lobster';
}
`</pre> 

![Şekil 14.3](images/font.png)

Harika!

Yukarıda belirtildiği gibi, CSS'nin bir sınıf kavramı var. Bunlar, HTML kodunun bir parçasını adlandırmanıza ve stilleri yalnızca diğer parçalara dokunmadan bu parçaya uygulamanızı sağlar. Bu süper yararlı olur! Belki de div'ınız vardır(üstbilgi ve yayınınız gibi) farklı şeyler yapıyorsunuz. Bir sınıf onları farklı görünmelerine yardımcı olur.

Devam edin ve HTML kodunun bazı bölümlerini adlandırın. Adlı bir sınıf ekleme ` sayfa başlığı </ 0> için sizin <code> div </ 0> böyle, Üstbilginizi içerdiğini:</p>

<p>{% filename%} blog / şablonlar / blog / posta_list.html {% endfilename%}</p>

<pre><code class="html">&lt;div class="page-header"&gt; 
&lt;h1&gt;&lt;a href="/"&gt; Django kız blog </ 1> </ 0>
`</pre> 

Ve şimdi bir blog yazısı içeren ` div </ 0> 'na sınıf <code> sonrası </ 0> ekleyin .</p>

<p>{% filename %}blog/templates/blog/post_list.html{% endfilename %}</p>

<pre><code class="html"><div class="post">
    <p>published: {{ post.published_date }}</p>
    <h1><a href="">{{ post.title }}</a></h1>
    <p>{{ post.text|linebreaksbr }}</p>
</div>
`</pre> 

Şimdi, farklı seçicilere bildirim blokları ekleyeceğiz. Selectors starting with `.` relate to classes. Aşağıdaki kodları anlamanıza yardımcı olabilecek birçok harika öğretici ve Web'de CSS hakkında açıklamalar bulunur. Şimdilik, kopyalayıp ` blog / statık / css / blog.css </ 0> dosyanıza yapıştırın :</p>

<p>{% filename %}blog/static/css/blog.css{% endfilename %}</p>

<pre><code class="css">.page-header {
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
`</pre> 

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

Bu CSS ile biraz uğraşmaktan korkmayın ve bazı şeyleri değiştirmeye çalışın. CSS ile oynamak, farklı şeylerin ne yaptığını anlamanıza yardımcı olur. Bir şeyi kırarsan endişelenmeyin - her zaman geri alabilirsiniz!

Bu ücretsiz çevrimiçi  Codeacademy HTML & amp; CSS kursu </ 0> . Web sitelerinizi CSS ile daha güzel yapmak hakkında her şeyi öğrenmenize yardımcı olur.</p> 

Bir sonraki bölüm için hazır mısınız ?! :)