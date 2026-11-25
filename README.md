SUNUM AKICILIĞI ANALİZÖRÜ

Öğrenci sunumlarında konuşma hızı ve dolgu sözcüklerinin Python tabanlı otomatik analizi

TÜBİTAK 2209-A Üniversite Öğrencileri Araştırma Projeleri kapsamında geliştirilmektedir.

PROJE HAKKINDA

Öğrenci sunumları sözlü akıcılık açısından genellikle gözleme ve öznel yargıya dayanarak değerlendirilir. Öğrenciler de konuşma hızları ve dolgu sözcük kullanımları ("ııı", "eee", "şey", "yani" vb.) hakkında ölçülebilir geri bildirim alamaz.

Bu proje, Türkçe sunum ses kayıtlarını otomatik olarak analiz eden ve öğrenciye kişiselleştirilmiş geri bildirim raporu üreten açık kaynaklı bir Python aracı geliştirir. Proje ayrıca bu geri bildirimin sunum akıcılığına etkisini deneysel olarak inceler.

HESAPLANAN GÖSTERGELER

Konuşma hızı: Toplam kelime sayısının toplam konuşma süresine oranı (kelime/dk)
Artikülasyon hızı: Kelime sayısının, duraksamalar çıkarıldıktan sonra kalan süreye oranı (kelime/dk)
Dolgu sözcük sıklığı: 100 kelimedeki dolgu sözcük sayısı
Duraksama oranı: Kelimeler arasındaki 0,5 saniye ve üzeri boşlukların süreye oranı (%)

NASIL ÇALIŞIR?

Kayıt: Sunum yaka mikrofonu veya bilgisayar mikrofonu ile tek kanallı, 16 kHz ses dosyası olarak kaydedilir.
Transkripsiyon: Kayıt, faster-whisper ile Türkçe metne dönüştürülür ve her kelimenin başlangıç-bitiş zamanı elde edilir. Dolgu seslerinin yakalanması için modele "ııı, eee, şey, yani" gibi örnekler içeren bir başlangıç istemi verilir.
Gösterge hesaplama: Kelime zaman damgalarından konuşma hızı, artikülasyon hızı ve duraksamalar hesaplanır.
Dolgu sözcük tespiti: Sözcükler bir dolgu sözlüğüyle eşleştirilir (ııı, eee, şey, yani, işte, hani, falan, filan). "Yani", "işte" gibi bağlama göre anlamlı da olabilen sözcükler için ek kurallar uygulanır.
Rapor: Her kayıt için dört gösterge, kısa bir düzey değerlendirmesi ve öğrenciye yönelik geri bildirim metni üretilir. Sonuçlar bir tabloya kaydedilir.

GİZLİLİK

Yazılım tamamen yerel bilgisayarda çalışır. Ses kayıtları internet üzerinden hiçbir hizmete gönderilmez.
Araştırmada kayıtlar gerçek ad yerine katılımcı koduyla saklanır. Proje sonunda ses kayıtları silinir, yalnızca anonim sayısal göstergeler tutulur.

DOĞRULAMA

Yazılımın çıktıları, iki araştırmacının birbirinden bağımsız olarak elle etiketlediği referans kayıtlarla karşılaştırılır.

KAPSAM VE SINIRLILIKLAR

Araç yalnızca ses boyutuna odaklanır. İçerik, ses tonu, vurgu, göz teması ve beden dili kapsam dışıdır.
Bağlama göre dolgu olup olmadığı değişen sözcüklerin (ör. "yani", "işte") ayrıştırılması bilinen bir zorluktur.
Whisper tabanlı model "ııı", "eee" gibi sesleri her zaman metne yansıtmayabilir. Bu durumda akustik boşluk tabanlı tespit veya transkriptlerin elle düzeltildiği yarı otomatik kullanım devreye alınır.
Donanım yetersizse daha küçük model (medium/small) veya işlemci (CPU) modu kullanılabilir. Uzun kayıtlar bölümlere ayrılarak işlenir.

BEKLENEN ÇIKTILAR

Türkçe sunum konuşmaları için doğrulanmış, açık kaynaklı analiz yazılımı
Türkçe öğrenci sunumlarına ilişkin betimleyici referans değerler (konuşma hızı, artikülasyon hızı, dolgu sözcük sıklığı, duraksama oranı)
Bir kongre bildirisi ve hakemli dergiye gönderilecek bir makale
