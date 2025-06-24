# -Ger-ek-Hayat-Verileriyle-Kira-Fiyat-Tahmini-oklu-Do-rusal-Regresyon-Analizi
Bu projede, İzmir’in Buca ilçesindeki kiralık evlere ait veriler kullanılarak kira fiyatlarını etkileyen faktörler çoklu doğrusal regresyon analizi ile incelenmiştir. Amaç, kira fiyatlarını etkileyen önemli değişkenleri belirlemek ve bu değişkenlerin etkisini istatistiksel olarak test ederek bir tahmin modeli geliştirmektir.

Analiz Süreci:
 • Veri seti Kaggle’dan alınmış, 138 gözlem ve 7 değişken içerir
 • Bağımlı değişken: price (kira fiyatı)
 • Bağımsız değişkenler: gross (brüt alan), num_rooms, building_age, furnishing_status, floor_type
 • Veriler grafiksel olarak incelenmiş, normallik ve varyans homojenliği testleri uygulanmıştır
 • Çoklu doğrusal regresyon modelleri kurularak model performansları karşılaştırılmış, en uygun model seçilmiştir
 • Modelde etkileşim terimleri (örneğin: gross:building_age) ve polinom terimler kullanılmış
 • Modelin açıklayıcılığı: Adjusted R² = %44.3, F-istatistiği anlamlı
 • En etkili faktörler: brüt alan, bina yaşı ve mobilya durumu

Sonuçlar ve Öneriler:
Model, kira fiyatı tahmininde başarılı sonuçlar vermiştir. Fiyatlar üzerinde brüt alanın ve mobilya durumunun pozitif etkisi, bina yaşının ise negatif etkisi gözlemlenmiştir. Modelin açıklayıcılığı orta düzeydedir; daha yüksek doğruluk için daha büyük ve çeşitli veri setleriyle çalışılması önerilir.

Kullanılan Teknolojiler:
R, ggplot2, car, stats, base R fonksiyonları
