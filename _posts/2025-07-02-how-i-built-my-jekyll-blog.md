---
layout: post
title: "Nasıl Kendi Jekyll Blogumu Kurdum"
date: 2025-07-03 12:00:00 +0300
categories: jekyll deneyim blog
---

Merhaba! Bu yazıda, kişisel olarak nasıl kendi Jekyll blogumu kurduğumu, karşılaştığım sorunları ve çözümleriyle birlikte detaylı şekilde anlatacağım. Amacım, benzer bir yola çıkacak arkadaşlara yol göstermek ve onların süreci kolayca aşmasına yardımcı olmak.

---

### Neden Jekyll?

Hazır blog platformları yerine kendi kontrolümde, hızlı ve güvenli bir blog kurmak istedim. Jekyll'in basit yapısı ve GitHub Pages ile ücretsiz yayın imkanı sağlaması beni cezbetti.

---

### 1. Gerekli Araçları Kurmak

Öncelikle, Ruby ve Jekyll kuracağız.Mac kullanıyorum, terminalden:

brew install ruby

Sonra,

export PATH="/usr/local/opt/ruby/bin:$PATH"

ruby -v ile sürümü kontrol ettim.Sistemimde Ruby 3.4 yüklüydü, günceldi.

Sonra terminali kapatıp açtım ve

Sonrasında Jekyll ve Bundler'ı yükledim:

gem install bundler jekyll

çalıştırdım.

Kurulumun başarılı mı diye kontrol ettim:

jekyll -v

Bazen izin sorunları çıkabilir; bu durumda RubyGems ve sistem izinlerini kontrol etmek gerekiyor.

2. Yeni Blog Projesi Oluşturmak

Terminalde:

jekyll new my-blog
cd my-blog
bundle install

komutlarını kullandım. Bu, blogun temel klasör yapısını ve gerekli dosyaları oluşturdu.

3. Tema Seçimi ve Ayarlamalar

Varsayılan tema yerine daha sade bir tema olan Hyde'ı tercih ettim. Gemfile dosyasına:

gem "hyde"

satırını ekledim. _config.yml dosyasında da:

theme: hyde

şeklinde ayarladım.

GitHub’a sadece dosyaları yükleyince Jekyll otomatik çalışıyor ama theme ayarı varsa kendi temasını kullanıyor.
Bu yüzden theme: hyde yazısını kaldırdım.
 index.html dosyasına layout: default ekledim.
Eğer layout belirtilmezse, Jekyll sayfayı render edemez.
Ve GitHub’a _layouts klasörünü doğru commit ettim.
Temanın tüm dosyalarının GitHub'a yüklendiğinden emin oldum.

4. Yazıları Hazırlamak

Yazılarımı _posts klasörüne koydum. Dosya isimleri şu formattaydı:

YYYY-MM-DD-yazi-basligi.md

Yazılarımı Markdown ile yazdım, çünkü hem basit hem de Jekyll bunu direkt işliyor.
Her yazının başında front matter kısmı vardı:

---
layout: post
title: "Blogumu Kurarken Yaşadıklarım"
date: 2025-07-02
---

5. Blogu Yerelde Çalıştırmak

Değişiklikleri görmek için terminalde:

bundle exec jekyll serve

komutunu kullandım. Sonra tarayıcıdan http://localhost:4000 adresine giderek sonucu kontrol ettim.

Eğer sayfa boş görünüyorsa, genellikle:

Tema dosyalarının eksikliği,
Yazıların yanlış formatta olması,
_config.yml ayarlarının hatalı olması
gibi nedenler olabilir. Ben bu noktada sabırlı olup tek tek dosyalarımı ve ayarları kontrol ettim.


6. GitHub'da Yayınlama

Projeyi GitHub'da barındırarak, hem versiyon kontrolü yaptım hem de GitHub Pages sayesinde ücretsiz yayın sağladım.

git init
git add .
git commit -m "İlk blog yayını"
git branch -M main
git remote add origin https://github.com/kullaniciadi/repoadi.git
git push -u origin main

Bundan sonra, her değişiklik sonrası:

git add .
git commit -m "Yeni yazı eklendi"
git push


7. Karşılaştığım Zorluklar ve Çözümler
Teoriye çok fazla takılmadan, öğrendiğim şeyleri hemen uygulamaya çalıştım. Kodları ve ayarları deneyerek, hatalarla karşılaşıp onları çözerek ilerledim.
Bu “deneme-yanılma” süreci bana çok şey kattı.

Tema dosyalarının eksikliği:
Başlangıçta sadece _config.yml'de tema belirttim ama temaya ait _layouts, _includes klasörlerini yüklemediğim için sayfa boş kaldı. Tema klasörünü ve dosyalarını doğru şekilde koymak şart.
Gelecekteki tarihli yazılar:
Yazılarımın tarihi gelecekteyse (bugünden sonraki tarih) Jekyll onları göstermiyor. _config.yml'e future: true ekleyerek bunu düzelttim.
Port çakışması:
bundle exec jekyll serve komutunu tekrar çalıştırdığımda Address already in use hatası aldım. Mevcut çalışan Jekyll sürecini kapatıp tekrar açtım.


Sonuç

> Kendi blogumu kurmak zorlu ama çok öğreticiydi. Sabır ve araştırma ile blogumu oluşturabildim. Hatalarla karşılaştım, pes etmedim ve her defasında biraz daha öğrendim. 
Notlar aldım, sabrettim ve sonunda bu blogu oluşturabildim. Eğer sen de yapmak istersen, umarım bu yazı yardımcı olur.


İyi bloglamalar!


