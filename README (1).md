# Stok Yönetimi ve Envanter Optimizasyonu

Endüstri mühendisliğinde sık kullanılan **stok / envanter kontrol modellerini** Python ile uygulayan,
**doğrusal programlama** ve **Monte Carlo simülasyonu** ile politikaları karşılaştıran bir proje.

## Notebook'lar

| Dosya | İçerik |
|---|---|
| [`stok_optimizasyonu.ipynb`](stok_optimizasyonu.ipynb) | EOQ, backorder'lı EOQ, newsvendor, emniyet stoğu, (Q, r) politikası, simülasyon, ABC analizi |
| [`02_lp_optimizasyon.ipynb`](02_lp_optimizasyon.ipynb) | Depo kapasitesi kısıtlı çok kalemli EOQ (Lagrange) ve çok dönemli parti büyüklüğü problemi (MILP, PuLP) |
| [`03_talep_tahmini.ipynb`](03_talep_tahmini.ipynb) | Talep tahmini (MA, SES, mevsimsel naive, Holt-Winters) ve tahmin kalitesinin stok politikasına etkisi |

GitHub'da notebook'lar açılınca formüller ve grafikler doğrudan görünür.

## Temel formüller

- **EOQ:** Q* = √(2DS / H)
- **Backorder'lı EOQ:** Q* = √(2DS / H) · √((H + B) / B)
- **Newsvendor:** Q* = μ + z · σ, kritik oran CR = (p − c) / (p − s)
- **Emniyet stoğu:** SS = z · σ_gün · √L
- **Kısıtlı EOQ (Lagrange):** Q_i = √(2 D_i S_i / (H_i + 2 λ w_i))
- **(R, S) politikası:** S = Σ tahmin(R+L gün) + z · σ_e · √(R+L)

## Nasıl çalıştırılır

```bash
git clone https://github.com/cerengunduz/stok-optimizasyonu.git
cd stok-optimizasyonu
pip install -r requirements.txt
jupyter notebook
```

Gerekli kütüphaneler: `numpy`, `pandas`, `matplotlib`, `jupyter`, `pulp`.

## Veri hakkında

- `stok_optimizasyonu.ipynb` içindeki ABC analizi ve `03_talep_tahmini.ipynb` içindeki talep verisi **üretilmiş örnek veridir**.
- `03_talep_tahmini.ipynb`, `tarih` ve `talep` sütunlu bir `talep.csv` dosyası bulursa gerçek veriyle çalışır (notebook içinde adımlar anlatılmıştır).

## Ekip

| Ad Soyad | Katkı / görev | GitHub |
|---|---|---|
| Ceren Gündüz | Depo kurulumu, notebook ve README dosyalarının yüklenmesi, ekibin depoya eklenmesi, koordinasyon | [@cerengunduz](https://github.com/cerengunduz) |
| Burak Efe Arslan | Planlanan görev: gerçek veri bulma ve talep tahmini notebook'unu gerçek veriyle çalıştırma | [@burakefearslanturk](https://github.com/burakefearslanturk) |
| Şevval Bengü | Planlanan görev: bütçe kısıtlı model ve (s, S) – (Q, r) karşılaştırması | [@sevvallbengu](https://github.com/sevvallbengu) |

> Planlanan görevler tamamlandıkça bu sütun, yapılan işi anlatacak şekilde güncellenir.

## Yol haritası ve görev dağılımı (planlanan)

| Görev | Sorumlu |
|---|---|
| Gerçek talep verisi bulma ve `03_talep_tahmini.ipynb`'yi gerçek veriyle çalıştırıp yorumlama | Burak Efe Arslan |
| `02_lp_optimizasyon.ipynb` modeline bütçe (nakit) kısıtı ekleme, (s, S) ve (Q, r) politikalarını karşılaştıran yeni notebook | Şevval Bengü |
| Sonuçların birleştirilmesi, README ve sunum | Ceren Gündüz |

> Bu dağılım öneridir; ekip olarak anlaştığınız gibi değiştirin. Bir görev tamamlanınca kutu işaretlenir ve katkı yukarıdaki Ekip tablosuna yazılır.

## Notlar

- Simülasyonlarda talep normal dağılımlı, tedarik süresi sabit ve karşılanamayan talep kayıp satış olarak varsayılmıştır.
- Bu projenin kodları hazırlanırken yapay zekâ (Claude) desteği alınmıştır.
