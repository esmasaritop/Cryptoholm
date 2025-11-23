CAN-Bus Güvenlik Analizi: Kaynak Kimlik Doğrulama (Authentication) Zafiyeti Simülasyonu
Proje Özeti
Bu proje, CAN-Bus (Controller Area Network) protokolünün en temel mimari zafiyetlerinden biri olan mesaj kimlik doğrulama (authentication) eksikliğini ele almakta ve bu durumun yol açtığı güvenlik anomalilerini simüle etmektedir. CAN-Bus'taki mesajlar, hangi ECU'dan (Elektronik Kontrol Ünitesi) geldiğine dair güvenilir bir kimlik bilgisi taşımadığı için, kötü niyetli bir aktör, meşru bir ECU'yu taklit ederek kritik sistemlere sahte komutlar gönderebilir.

Proje, bu "Sahte Giriş (Impersonation) Anomalisi" üzerinde durarak, söz konusu zafiyetin pratik bir simülasyon ortamında nasıl istismar edilebileceğini ve bu tür yetkisiz mesajların savunma mekanizmalarıyla nasıl tespit edilip engellenebileceğini göstermeyi amaçlamaktadır.
Odaklanılan Güvenlik Senaryosu: Sahte Giriş (Impersonation) Anomalisi
CAN protokolü mesajları, sadece öncelik belirleyen bir ID taşır, bu ID mesajın kaynağını doğrulamaz. Bu, bir saldırganın ağa erişimi olduğunda, herhangi bir meşru ECU'nun kimliğine bürünerek komut gönderebileceği anlamına gelir.

Senaryo Adımlarının Savunma Perspektifinden İncelenmesi:
Meşru ECU Davranışının Tespiti:

Normal Akış: Legitimate_ECU.py (Örn: Motor Kontrol Ünitesi - ECU_A), belirli bir CAN ID'si (Örn: 0x100) ile düzenli bir frekansta (100ms'de bir) "Normal Çalışma Durumu" mesajı göndermektedir.

Savunma Odak Noktası: Savunma sistemi (Sniffer/IDS), 0x100 ID'sinin bu düzenli kalıbını ve veri içeriği aralığını öğrenir.

Sahte Giriş (Impersonation) Saldırısı:

Zafiyet: CAN ID'si 0x100 herkes tarafından kullanılabilir.

Simülasyon: Attacker.py devreye girer. Saldırgan, meşru ECU_A'nın ID'sini (0x100) kullanarak yüksek öncelikli ve kritik bir komut (Örn: Motoru Ani Durdurma veri paketi) içeren bir mesajı ağa enjekte eder.

Anomali Tespiti: Ağda aniden, meşru ECU_A'nın normal frekansı dışında ve meşru veri aralığının dışında bir veri içeriğine sahip 0x100 mesajları görülmeye başlar. Bu, bir kimlik doğrulama anomalisi ve frekans anormalliği kombinasyonudur.

Anomali Tespiti ve Engelleme (Savunma):

Tepki: Sniffer.py veya bir CAN tabanlı Saldırı Tespit Sistemi (IDS), aşağıdaki kriterlere uyan 0x100 mesajlarını tespit eder:

Frekans Anormalliği: Normalde 100ms'de bir gelen mesajın, araya 10ms'de bir gelen başka bir 0x100 paketi girmesi.

Veri İçeriği Anormalliği: Motorun çalışması için beklenen veri aralığının dışına çıkan bir veri (Motor Durdurma Komutu).

Sonuç: Sistem, bu anomaliyi tespit ederek aracı güvenli moda geçirir veya sahte mesajın diğer ECU'lara ulaşmasını engeller (Simülasyonda gözlemleme aşaması).

🛠️ Kurulum ve Simülasyon Bileşenleri
Simülasyonun Çalıştırılması
Simülasyonumuz üç ana bileşenden oluşur ve kimlik doğrulama anomalisi aşağıdaki gibi gözlemlenir:

Adım: Meşru ECU'yu Çalıştırın (Legitimate_ECU.py)

Normal "Kalp Atışı" mesajları (ID: 0x100) düzenli aralıklarla yayınlanır.

Adım: Ağı İzlemeye Başlayın (Sniffer.py)

IDS rolündeki dinleyici, 0x100 ID'sinin normal davranışını öğrenir (Frekans ve Veri içeriği).

Adım: Saldırıyı Başlatın ☠️ (Attacker.py)

Saldırgan, aynı ID (0x100) ile, ancak farklı bir veri içeriği ve daha sık bir frekansla (Daha yüksek öncelik alarak) sahte komutları enjekte eder.

Gözlem: Sniffer.py ekranında, meşru Kaynağın kimliğini taklit eden ve frekans/içerik kuralını bozan anormal mesajlar tespit edilmelidir.

Bu senaryo, CAN-Bus güvenliğini sağlamak için kimlik doğrulama mekanizmalarının ve frekans/veri bütünlüğü kontrollerinin şart olduğunu açıkça göstermektedir.
