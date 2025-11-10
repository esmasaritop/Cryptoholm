# Cryptoholm
# 🚗 Blokzincir Tabanlı Araç İçi Ağ Güvenliği

## 📖 Proje Özeti
Bu proje, akıllı araçlarda kullanılan **Controller Area Network (CAN-Bus)** protokolünün güvenlik açıklarını azaltmak amacıyla geliştirilmiştir.  
CAN-Bus, araç içi iletişimde en yaygın kullanılan protokol olmasına rağmen, **kimlik doğrulama, mesaj bütünlüğü ve şifreleme** gibi temel güvenlik mekanizmalarından yoksundur.  
Bu durum, mesaj enjeksiyonu, sahte mesaj ve tekrar saldırıları gibi tehditlere karşı araçları savunmasız bırakmaktadır.

Projenin temel amacı, **blokzincir teknolojisinin merkeziyetsiz, değiştirilemez ve izlenebilir yapısından** yararlanarak, araç içi iletişim güvenliğini artırmaktır.  
Bu kapsamda, **CAN-Bus mesaj trafiği üzerinde gerçek zamanlı çalışabilen hafif bir blokzincir tabanlı güvenlik katmanı** tasarlanacaktır.

---

## 🎯 Amaçlar
- Araç içi ağlarda **kimlik doğrulama** ve **mesaj bütünlüğü** sağlamak  
- **Sahte mesaj** ve **tekrar saldırılarını** tespit etmek  
- Blokzincir altyapısı ile **izlenebilir, güvenilir ve merkeziyetsiz** bir güvenlik sistemi kurmak  
- Akıllı araçlarda siber güvenlik farkındalığını artırmak  

---

## 🧠 Temel Kavramlar
- **Blokzincir (Blockchain)**  
- **Dağıtık Defter Teknolojisi (Distributed Ledger Technology / DLT)**  
- **Zero Trust Architecture (Sıfır Güven Mimarisi)**  
- **Defense in Depth (Derinlemesine Savunma)**  
- **Tamper-Evident Logging (Değiştirildiği Tespit Edilebilir Kayıt)**  
- **CAN-Bus Protokolü**  
- **Zaman Damgalama ve Kimlik Doğrulama**  

---

## ⚙️ Kullanılacak Teknolojiler
- **Python / C++** → Ağ trafiği analizi ve mesaj simülasyonu  
- **Blockchain Framework (ör. Hyperledger / Ethereum TestNet)**  
- **Kriptografik hash fonksiyonları** (SHA-256 vb.)  
- **Dijital imzalar ve anahtar yönetimi**  
- **Veri kaydı ve bütünlük kontrolü** için blokzincir entegrasyonu  

---

## 🔬 Problem Tanımı
Araç içi ağlar performans ve maliyet öncelikli tasarlandığından, güvenlik unsurları ikinci planda kalmıştır.  
CAN-Bus protokolü kimlik doğrulama ve şifreleme desteğine sahip değildir. Bu nedenle:
- Mesajların kaynağı doğrulanamaz,  
- Mesaj enjeksiyonu ve sahte mesaj saldırıları mümkündür,  
- Tekrar (replay) saldırılarına karşı koruma zayıftır.

Blokzincir teknolojisiyle bu güvenlik açıkları azaltılarak, **araç içi iletişimde güvenilirlik ve izlenebilirlik** sağlanacaktır.

---

## 📊 Beklenen Çıktılar
- CAN-Bus üzerinde çalışan **blokzincir tabanlı güvenlik katmanı prototipi**  
- Mesaj doğrulama ve kayıt modülü  
- Performans, gecikme ve güvenlik analiz raporları  
- Akıllı araç güvenliği için model önerisi  

---

## 🌐 Kapsam
Proje, yalnızca araç içi ağ güvenliğiyle sınırlı değildir.  
Ayrıca **IoE (Internet of Everything)** kapsamında araç, altyapı sistemleri, sensörler ve kullanıcı cihazları arasındaki iletişim güvenliği de ele alınacaktır.  

---

## 👥 Katkıda Bulunanlar
- **Esma Sarıtop**  
- **Ebuzer Yitiz**
- **Elif Sakar**
- **Salih Atiç**
- **Yağız Enes Doğan**
- **Yusuf Erdem Aykaç**
- **Kumru Çelik**
- **Mervan Oktan**
- **Ahmet Taha Çetintaş**
- **Batuhan Özkan**
- **Gülendam Oral**
- **Tayfun Kaydı**
- **Yusuf Kaymaz**
---

## 📚 Kaynaklar
Proje, güncel akademik yayınlar ve IEEE/ACM kaynaklarına dayanmaktadır.  
Detaylı kaynakça ve literatür özeti için *Bilgi Notu.pdf* dosyasına bakabilirsiniz.

---

## 🧩 Anahtar Kelimeler
`Blockchain` `CAN-Bus` `Siber Güvenlik` `Akıllı Araçlar` `IoE` `Otonom Sistemler` `Zero Trust` `Defense in Depth`
