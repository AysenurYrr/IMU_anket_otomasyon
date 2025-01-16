# İstanbul Medeniyet Üniversitesi Anket Otomasyon Aracı

İstanbul Medeniyet Üniversitesi'nin vize ve final sınavlarından sonra öğrencilere sunduğu anketleri otomatik doldurmak için bu rehberi takip edebilirsiniz.

## Gerekli Adımlar

### 1. Geliştirici Konsolunu Açın
- **Windows / Linux:** `Ctrl + Shift + J`
- **Mac:** `Cmd + Opt + J`

UBYS sisteminde geliştirici panelini açtıktan sonra aşağıdaki komutları konsola yapıştırarak çalıştırabilirsiniz.

![Geliştirici Konsolu Açma](https://github.com/AysenurYrr/IMU_anket_otomasyon/blob/b416eeb1711c81009688df84b35c6adc21963495/images/5.PNG)

### 2. Komutun Çalıştırılması
Aşağıdaki komut, anket sayfasındaki tüm radio butonlarını otomatik olarak seçer. 

```javascript
// Seçim yap
$('[type="radio"]').each((index, element) => {
    if ((index + 1) % 5 === 0 || index === 70) { // 5'in katı veya indeks 71 ise
        $(element).prop('checked', true); // Radio butonunu seçili yap
        $(element).parent('div').addClass('checked');
    }
});

// Anketi bitir butonuna tıkla
setTimeout(() => { 
    document.querySelector("#surveyParent > div:nth-child(5) > div > a")?.click();
}, 500); // 500 ms bekleme süresi, DOM'un güncellenmesini beklemek için
```

![Komut Çalıştırma](https://github.com/AysenurYrr/IMU_anket_otomasyon/blob/4c0356c132b2ed0da1c1945b447bf1fdc68e1d50/images/6.PNG)


### Warning Hatası Alırsanız
Konsolda bir *Warning* hatası görüyorsanız, aşağıdaki komutu çalıştırarak bu hatayı çözebilirsiniz:

```javascript
allow pasting
```

![Warning](https://github.com/AysenurYrr/IMU_anket_otomasyon/blob/b416eeb1711c81009688df84b35c6adc21963495/images/2.PNG)

### 3. Puanlandırma Değerleri

Koddaki `5` değerini aşağıdaki puanlamalara göre değiştirebilirsiniz:

1. **Kesinlikle Katılmıyorum**
2. **Katılmıyorum**
3. **Ne Katılıyorum Ne de Katılmıyorum**
4. **Katılıyorum**
5. **Kesinlikle Katılıyorum**

---
![Sonuç Görseli]([images\3.PNG](https://github.com/AysenurYrr/IMU_anket_otomasyon/blob/b416eeb1711c81009688df84b35c6adc21963495/images/3.PNG))

**Dikkat:** Bu araç yalnızca eğitim ve rehberlik amacıyla paylaşılmıştır. Lütfen üniversitenizin kurallarını göz önünde bulundurarak kullanın.
