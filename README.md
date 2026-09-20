# Stok Yönetimi ve Envanter Optimizasyonu

Endüstri mühendisliğinde sık kullanılan **stok / envanter kontrol modellerini** Python ile uygulayan
ve **Monte Carlo simülasyonu** ile politikaların rastgele talep altında nasıl davrandığını gösteren bir proje.

Ana çalışma: [`stok_optimizasyonu.ipynb`](stok_optimizasyonu.ipynb)
(GitHub'da açınca formüller ve grafikler doğrudan görünür.)

## İçindekiler

| Bölüm | Konu |
|---|---|
| 1 | EOQ (Ekonomik Sipariş Miktarı) ve toplam maliyet eğrisi |
| 2 | Eksik stoklu (backorder) EOQ |
| 3 | Newsvendor (gazete satıcısı) modeli |
| 4 | Emniyet stoğu ve (Q, r) politikası |
| 5 | Simülasyon: envanter seviyesinin zaman içindeki değişimi |
| 6 | Maliyet – hizmet düzeyi dengesi |
| 7 | ABC / Pareto analizi |

## Temel formüller

- **EOQ:** Q* = √(2DS / H)
  (D: yıllık talep, S: sipariş maliyeti, H: birim başına yıllık elde tutma maliyeti)
- **Backorder'lı EOQ:** Q* = √(2DS / H) · √((H + B) / B)
- **Newsvendor:** Q* = μ + z · σ, kritik oran CR = (p − c) / (p − s)
- **Emniyet stoğu:** SS = z · σ_gün · √L
- **Yeniden sipariş noktası:** r = μ_gün · L + SS

## Nasıl çalıştırılır

```bash
git clone https://github.com/cerengunduz/stok-optimizasyonu.git
cd stok-optimizasyonu
pip install -r requirements.txt
jupyter notebook stok_optimizasyonu.ipynb
```

Gerekli kütüphaneler: `numpy`, `pandas`, `matplotlib`, `jupyter`.

## Ekip

| Ad Soyad | Katkı alanı | GitHub |
|---|---|---|
| Ceren Gündüz | _(kendi katkını yaz)_ | [@cerengunduz](https://github.com/cerengunduz) |
| _(Arkadaş 1)_ | _(katkı alanı)_ | _(@kullanici-adi)_ |
| _(Arkadaş 2)_ | _(katkı alanı)_ | _(@kullanici-adi)_ |

> Katkı alanları, herkesin gerçekte yaptığı işe göre doldurulmalıdır.

## Yol haritası

- [ ] Çok kalemli / kapasite kısıtlı sipariş problemi (doğrusal programlama, PuLP)
- [ ] Gerçek talep verisiyle tahmin (hareketli ortalama, üstel düzeltme) ve politika karşılaştırması
- [ ] (s, S) ve (Q, r) politikalarının karşılaştırılması
- [ ] ABC analizinin gerçek veri setiyle yapılması

## Notlar

- Simülasyonda talep normal dağılımlı, tedarik süresi sabit ve karşılanamayan talep kayıp satış olarak varsayılmıştır.
- ABC bölümündeki veri örnek olarak üretilmiştir.
