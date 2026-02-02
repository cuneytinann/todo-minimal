
# todo-minimal

Tarayıcıda çalışan, iç içe (nested) görevler destekleyen minimal bir to-do uygulaması. Kurulum gerektirmez; tek bir `index.html` dosyasıyla çalışır.

Canlı sürüm:
- https://cuneytinann.github.io/todo-minimal/

## Özellikler

- Tek dosya (`index.html`): harici kütüphane yok, build yok.
- Çoklu liste: birden fazla bağımsız to-do listesi oluşturma/silme.
- İç içe görevler: her göreve alt görev eklenebilir (nested yapı).
- Tri-state tamamlanma mantığı:
  - Alt görevi olmayan (leaf) görevler checkbox ile doğrudan tamamlanır.
  - Üst görevler, alt görevlerin tamamı bitince “tamamlandı” görünümüne geçer.
  - Üst görevin checkbox’ını değiştirmek, tüm alt görevleri de aynı duruma getirir.
- Sıralama:
  - Listeler ve görevler için sıra numarası (#) ile yeniden sıralama.
  - 1..N aralığında girince “swap”, aralık dışı girince başa/sona “move” davranışı.
- Liste rengi:
  - Her liste için renk seçici.
  - Derinliğe göre daha yumuşak (alpha azaltılmış) arka plan tonları.
- Tema: açık/koyu tema geçişi.
- Otomatik kaydetme: tüm değişiklikler Local Storage’a kaydedilir; üstte son kayıt zamanı görünür.
- Yedekleme:
  - “İndir (JSON)” ile tam yedek alınır.
  - “Yükle (JSON)” ile içe aktarılır (append-only; var olan veriyi silmez).
  - Eşdeğer listeler otomatik atlanır (aynı başlık + aynı görev ağacı + aynı renk/alpha).

## Hızlı Başlangıç

1) Proje kökünde `index.html` dosyasını tarayıcıda açın.
2) Kullanım:
   - “+ Yeni Liste” ile liste ekleyin.
   - “Yeni madde yaz ve Enter…” alanına yazıp Enter’a basın (veya “Ekle”).
   - Her görevde “Alt görev +” ile alt görev oluşturun.
   - # alanlarıyla liste/görev sıralamasını değiştirin.
   - “İndir (JSON)” / “Yükle (JSON)” ile yedek alıp geri yükleyin.

Not: Gizli mod veya sıkı gizlilik ayarlarında Local Storage kısıtlıysa otomatik kaydetme çalışmayabilir.

## Veri Saklama ve Yedek Formatı

- Uygulama durumu tarayıcının Local Storage’ında saklanır.
- JSON yedeği uygulamanın tamamını içerir: tema, listeler, görev ağacı, renkler vb.
- İçe aktarma append-only çalışır; mevcut kayıt silinmez.
- Eşdeğer listeler otomatik atlanır (done/order/id eşdeğerlikte dikkate alınmayabilir).

## Gizlilik

Veri yalnızca yerel tarayıcıda tutulur. Sunucuya gönderim yoktur (tek statik sayfa).

