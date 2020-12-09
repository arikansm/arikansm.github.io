---
layout: postpage
title: Koronavirüs Tweetleri Gün Bazlı Duygu Tahmini
description: blog yazısı
author: Süleyman Muhammed ARIKAN
side_panel: true
side_panel_title: İlgili Github Deposu
side_panel_fa: fa-code-fork
side_panel_strong: arikansm/covid-tweets-sentiment-forecast
side_panel_url: https://github.com/arikansm/covid-tweets-sentiment-forecast
side_panel_link_text: Git
excerpt_separator: <!--devam-->
date: 2020-06-01T00:00:00Z
---

Koronavirüs ile ilişkili olarak paylaşılacak ingilizce tweetler arasındaki duygu dağılımını tahmin edecek bir uygulama üzerine çalışma gerçekleştirilerek yaklaşık olarak 190 satırdan oluşan kaynak kodları geliştirilmiştir. Çalışma ile; prophet algoritması ve nltk kütüphanesi ile gerekli önişlem adımları hakkında bilgi sahibi olunabilir.
<!--devam-->

Çalışma kapsamında 1 haftalık (13-19 Mart 2020) gerçek tweetler toplanmıştır. Yaklaşık 2,5 milyon tweet üzerinde gün bazlı duygu analizi gerçekleştirilerek 8. gün (20 Mart 2020) için paylaşılacak tweetler arasındaki duygu dağılımı tahmin edilmiştir. Duygu tahminleri için doğal dil işleme kütüphanlerinden nltk tercih edilirken, gelecek tahmini için zaman serisi analizi algoritmaları arasından prophet kullanılmıştır.  

Öncelikle 1 hatalık tweetler ilgili dosyalardan okunur. Elde edilmiş veriler arasından yalnızca ingilizce olanlar seçilir. Tweetlerden duygu analizi için önemsiz olan kayıtların çıkarılması amacıyla önişlem adımları uygulanır. Bu adımlar; url adreslerinin temizlenmesi, tüm karakterlerin küçük harfe çevrilmesi, noktalama işaretlerinin silinmesi ve gereksiz kelimelerin (ve-and, veya-or, vb.) çıkarılması faaliyetlerinden oluşmaktadır. Önişlem adımlarının tamamlanması ile nltk kütüphanesi üzerinden duygu analizi için puanlama yapılır. Her tweet için hesaplanan bu puanlama 0 ise nötr, 0 dan büyün ise olumlu, 0 dan küçük ise olumsuz olarak duygu yönelimi kabul edilir. Böylece her tweet için duygu analizi yapılmış olur. Yapılan analiz için aşağıda görüldüğü üzere grafik çizdirilmiştir.

![Covid-19 İlişkili Tweetler için Günlük Duygu Analizi Sonuçları](/media/covid_tweets/7gun_analiz_sonuclari.png){:style="max-width: 100%; height: auto; display:block; margin-left: auto; margin-right: auto;"}

Bu bilgiler ışığında 8. Gün için paylaşılacak tweetlerin duygu dağılımı tahmin edilmeye çalışılmıştır. Bu kapsamda zaman serisi algoritması kullanılması uygun görülmüş ve prophet tercih edilmiştir. 

![8. Gün Duygu Tahmini](/media/covid_tweets/gun8_tahminler.png){:style="max-width: 50%; height: auto; display:block; margin-left: auto; margin-right: auto;"}

Prophet ile duygu dağılımı tahmin edilen 8. gün için karşılaştırma yapmak adına ilgili günün tweet verisi analiz edilerek gerçek duygu dağılımı da hesaplanmıştır. Her iki sonuç aşağıda görülebildiği üzere kullanıcı için çizdirilmiştir. Sonuç olarak duygular arası orantı benzer olarak tahmin edilirken toplam tweet sayısı 8. günün gerçek tweet sayısına nazaran daha az hesaplanmıştır.

![8. Gün Geçek Duygu Değerleri](/media/covid_tweets/gun8_gercek_degerler.png){:style="max-width: 50%; height: auto; display:block; margin-left: auto; margin-right: auto;"}

## Video

Program çalışması sırasında ekran kaydı alınmış ve video üzerine çeşitli açıklamalar eklenmiştir. Ekran kaydına ulaşmak için [tıklayınız](/media/covid_tweets/video.mp4).
