# 📚 LibraryOS — Semantik Kütüphane Yönetim Sistemi

Web Teknolojileri dersi dönem projesi. Kütüphane domain'i üzerinde XML, HTML/JS ve RDF/Semantik Web katmanlarını entegre eden tam kapsamlı bir proje.

## 🗂 Proje Yapısı

```
library-project/
├── index.html              # Ana web arayüzü (HTML + CSS + JS)
├── rapor.html              # Proje raporu (PDF'e dönüştürmek için)
├── README.md               # Bu dosya
├── xml/
│   ├── library.xsd         # XML Schema tanımı
│   ├── books.xml           # 15 kitap kaydı
│   ├── authors.xml         # 14 yazar kaydı
│   └── categories.xml      # 10 kategori kaydı
└── rdf/
    └── library.ttl         # RDF Turtle (~315 triple)
```

## 🚀 Kurulum ve Çalıştırma

### 1. GitHub Pages (Önerilen)
Repoyu fork ettikten sonra GitHub Pages'i etkinleştirin:
- Settings → Pages → Branch: main → / (root)
- Siteniz `https://kullanici.github.io/library-project/` adresinde canlı olacak

### 2. Yerel Sunucu ile Çalıştırma

**Python (en kolay):**
```bash
cd library-project
python3 -m http.server 8000
# Tarayıcıda: http://localhost:8000
```

**Node.js ile:**
```bash
npx serve .
```

**VS Code:**
- Live Server eklentisini kurun → index.html üzerinde "Open with Live Server"

> ⚠️ **Not:** `file://` protokolüyle doğrudan açarsanız XML fetch() çalışmaz. Lütfen bir HTTP sunucusu kullanın. Uygulama yine de çalışır (fallback verisi mevcuttur), ancak XML dosyaları gerçek zamanlı okunmaz.

## ✅ Doğrulama

### XML Doğrulama
1. [validator.w3.org](https://validator.w3.org/) → Validate by File Upload
2. `books.xml`, `authors.xml`, `categories.xml` dosyalarını XSD'ye karşı doğrulayın

### RDF Doğrulama
1. [validate.fhwa.dot.gov](http://validate.fhwa.dot.gov/sld/api/validat) veya
2. [RDF Playground](https://rdfplayground.dcc.uchile.cl/) → Turtle formatında `library.ttl` yükleyin

## 🌐 Namespace'ler

| Prefix | URI |
|--------|-----|
| `lib:` | `http://example.org/library#` |
| `libr:` | `http://example.org/library/resource/` |
| `dc:` | `http://purl.org/dc/elements/1.1/` |
| `schema:` | `https://schema.org/` |
| `rdf:` | `http://www.w3.org/1999/02/22-rdf-syntax-ns#` |
| `rdfs:` | `http://www.w3.org/2000/01/rdf-schema#` |
| `owl:` | `http://www.w3.org/2002/07/owl#` |

## 📊 İstatistikler

- **15** kitap kaydı (books.xml)
- **14** yazar kaydı (authors.xml)
- **10** kategori (categories.xml)
- **~315** RDF triple (library.ttl)
- **7** XSD özel tip tanımı
- **4** RDF sınıfı (Book, Author, Category, Publisher)
- **9** RDF özellik tanımı

## 🔑 Özellikler

- ✅ XML + XSD ile yapılandırılmış veri modeli
- ✅ Gerçek zamanlı XML parsing (`DOMParser` + `fetch()`)
- ✅ Arama (başlık/yazar/açıklama) ve filtreleme (kategori/dil/müsaitlik)
- ✅ Detay modal (her kitap için)
- ✅ "XML Olarak İndir" (tekil kitap)
- ✅ "RDF Kaydı İndir" (Turtle snippet)
- ✅ Tüm XML ve RDF dosyaları indirilebilir
- ✅ RDF `<link rel="alternate">` semantik anotasyon
- ✅ RDFa anotasyonları (schema:Book, schema:name)
- ✅ Responsive dark-theme tasarım

## 📋 Teslim Listesi

- [x] `library.xsd` — XSD şema (en az 5-6 element + attribute + kısıtlamalar)
- [x] `books.xml` — 15 kitap kaydı
- [x] `authors.xml` — 14 yazar kaydı
- [x] `categories.xml` — 10 kategori kaydı
- [x] `index.html` — Tam işlevli web arayüzü
- [x] `library.ttl` — ~315 RDF triple, Turtle formatı
- [x] `rapor.html` → PDF raporu (tarayıcıda Ctrl+P ile PDF)
- [x] `README.md` — Bu dosya

## 📄 Raporu PDF'e Dönüştürme

```bash
# Tarayıcıda rapor.html dosyasını açın
# Ctrl+P → "PDF olarak kaydet" seçin
```

## 🔮 Gelecek Geliştirmeler

- [ ] Apache Jena Fuseki ile SPARQL endpoint
- [ ] OWL reasoner entegrasyonu
- [ ] DBpedia/Wikidata sameAs linkleri
- [ ] JSON-LD + Google Rich Results
- [ ] SHACL doğrulama
