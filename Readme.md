# İstanbul Medeniyet Üniversitesi Anket Otomasyon Aracı

İstanbul Medeniyet Üniversitesi'nin vize ve final sınavlarından sonra öğrencilere sunduğu anketleri otomatik doldurmak için bu rehberi takip edebilirsiniz.

## Gerekli Adımlar

### 1. Geliştirici Konsolunu Açın
- **Windows / Linux:** `Ctrl + Shift + J`
- **Mac:** `Cmd + Opt + J`

UBYS sisteminde geliştirici panelini açtıktan sonra aşağıdaki komutları konsola yapıştırarak çalıştırabilirsiniz.

![Geliştirici Konsolu Açma](images\1.PNG)

### 2. Komutun Çalıştırılması
Aşağıdaki komut, anket sayfasındaki tüm radio butonlarını otomatik olarak seçer. 

```javascript
$('[type="radio"]').each((index, element) => {
    if ((index + 1) % 5 === 0 || index === 70) { // 5'in katı veya indeks 71 ise
        $(element).prop('checked', true); // Radio butonunu seçili yap
        $(element).parent('div').addClass('checked'); 
    }
});
```

![Komut Çalıştırma](images\4.PNG)


**Not:** Farklı notlandırmalar için koddaki `5` sayısını değiştirerek, seçimlerinizi uyarlayabilirsiniz.

### Warning Hatası Alırsanız
Konsolda bir *Warning* hatası görüyorsanız, aşağıdaki komutu çalıştırarak bu hatayı çözebilirsiniz:

```javascript
allow pasting
```

![Warning](images\2.PNG)

### 3. Puanlandırma Değerleri

Koddaki `5` değerini aşağıdaki puanlamalara göre değiştirebilirsiniz:

1. **Kesinlikle Katılmıyorum**
2. **Katılmıyorum**
3. **Ne Katılıyorum Ne de Katılmıyorum**
4. **Katılıyorum**
5. **Kesinlikle Katılıyorum**

---
![Sonuç Görseli](images\3.PNG)

**Dikkat:** Bu araç yalnızca eğitim ve rehberlik amacıyla paylaşılmıştır. Lütfen üniversitenizin kurallarını göz önünde bulundurarak kullanın.