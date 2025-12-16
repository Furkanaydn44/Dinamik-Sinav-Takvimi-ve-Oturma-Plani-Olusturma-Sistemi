# 📅 Dinamik Sınav Takvimi ve Oturma Planı Oluşturma Sistemi

Bu proje, üniversite bölümleri için sınav takvimi oluşturma ve öğrenci oturma planı hazırlama süreçlerini otomatize eden kapsamlı bir masaüstü uygulamasıdır.

**Python** ve **PyQt5** kullanılarak geliştirilen sistem; öğrenci ve ders verilerini Excel'den okur, çakışmasız sınav programları oluşturur ve sınav salonları için görsel oturma planları hazırlar.

## 🚀 Özellikler

### 🔐 Yetkilendirme ve Yönetim
* **Rol Tabanlı Giriş:** Admin ve Bölüm Koordinatörü olmak üzere iki farklı yetki seviyesi.
* **Kullanıcı Yönetimi:** Admin paneli üzerinden yeni koordinatör ekleme ve silme.
* **İstatistikler:** Sistemdeki toplam ders, öğrenci ve derslik sayılarının anlık takibi.

### 🏫 Derslik ve Envanter Yönetimi
* **Derslik Tanımlama:** Kapasite, satır, sütun ve sıra yapısı (2'li, 3'lü, 4'lü) tanımlama.
* **Görselleştirme:** Derslik oturma düzeninin ızgara (grid) yapısında görsel önizlemesi.

### 📂 Veri Entegrasyonu (Excel)
* **Ders Listesi Yükleme:** Bölüm derslerinin Excel formatında toplu aktarımı.
* **Öğrenci Listesi Yükleme:** Öğrenci numarası, sınıfı ve aldığı derslerin sisteme işlenmesi.
* **Hata Yakalama:** Mükerrer kayıtlar veya eksik veriler için detaylı hata raporlaması.

### 🗓️ Akıllı Sınav Programı Algoritması
* **Çakışma Kontrolü:** Aynı öğrencinin aynı saatte iki sınavı olmamasını garantiler.
* **Kısıtlar:**
    * Günlük sınav limiti (Her sınıf seviyesi için günde max 2 sınav).
    * Sınav türü (Vize, Final, Bütünleme) seçimi.
    * Tarih aralığı ve saat kısıtlamaları.
    * İstisna ders süreleri belirleme.
* **Excel Çıktısı:** Oluşturulan takvimi Excel formatında dışa aktarma.

### 🪑 Oturma Planı ve Raporlama
* **Rastgele Dağıtım:** Öğrencileri kapasiteye göre dersliklere rastgele dağıtır.
* **Görsel Plan:** Hangi öğrencinin hangi sırada oturacağını gösteren interaktif şema.
* **PDF Export:** Sınav salonu kapısına asılmak üzere detaylı oturma planı çıktısı (ReportLab ile).

## 🛠️ Teknik Altyapı ve Gereksinimler

Proje **Python 3.x** ile geliştirilmiştir. Çalıştırmak için aşağıdaki kütüphanelerin yüklü olması gerekir:

```bash
pip install pyqt5 pandas openpyxl fpdf pulp reportlab
```

 * GUI: PyQt5

* Veritabanı: SQLite3 (Yerel veritabanı)

* Veri İşleme: Pandas

* Raporlama: ReportLab (PDF), OpenPyxl (Excel)

* Optimizasyon: PuLP / Heuristic Algorithms

### 💻 Kurulum ve Kullanım
## 1. Projeyi İndirin: Bu depoyu (repository) yerel makinenize klonlayın.

## 2. Uygulamayı Başlatın: Terminal veya IDE üzerinden main.py dosyasını çalıştırın:

```bash

python main.py
```
##  3. Giriş Yapın: İlk kurulumda varsayılan Admin hesabı ile giriş yapın:

* E-posta: admin@example.com

* Şifre: admin

##  4.İş Akışı:

* Adım 1: "Derslik Girişi" sekmesinden sınav yapılacak salonları tanımlayın.

* Adım 2: "Ders Listesi Yükle" sekmesinden ders Excel dosyasını yükleyin.

* Adım 3: "Öğrenci Listesi Yükle" sekmesinden öğrenci verilerini yükleyin.

* Adım 4: "Sınav Programı Oluştur" sekmesinden tarihleri seçip programı oluşturun.

* Adım 5: "Oturma Planı" sekmesinden sınavları seçip PDF çıktılarını alın.

### 📂 Veritabanı Yapısı
Sistem exam_scheduler.db adında bir SQLite veritabanı oluşturur ve şu tabloları kullanır:

* users: Kullanıcı yetkileri.

* classrooms: Salon kapasite ve düzen bilgileri.

* courses & students: Akademik veriler.

* exams: Oluşturulan sınav takvimi.

* seating: Öğrenci-koltuk eşleşmeleri.

### ⚠️ Önemli Notlar
PDF çıktıları için ReportLab kütüphanesi zorunludur. Türkçe karakter desteği için sistemde DejaVuSans.ttf fontunu arar, bulamazsa varsayılan fontu kullanır.

Excel dosyalarının formatı, sistemin beklediği sütun başlıklarına (Öğrenci No, Ad Soyad, Ders vb.) uygun olmalıdır.

### 📄 Lisans
Bu proje açık kaynaklıdır ve eğitim/geliştirme amaçlı kullanıma uygundur.
