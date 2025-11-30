# 📈 Bitcoin Fiyat Tahminlemesi: Makroekonomik Yaklaşım

![Project Banner](images/project_banner.png) 
*(Not: Bu görseli images/project_banner.png olarak yükleyiniz veya bir URL kullanınız)*

| **Bölüm** | **Detaylar** |
| :--- | :--- |
| **Proje Künyesi** | **Ders:** Veri Madenciliği (FET445)<br>**Dönem:** Güz 2024-2025<br>**Grup:** MacroMinds |
| **Proje Amacı** | Bitcoin'in yüksek volatilitesini sadece teknik analizle değil, makroekonomik göstergelerle (Enflasyon, Faiz, S&P 500 vb.) modelleyerek; **kısa** (1-7 gün), **orta** (30 gün) ve **uzun** (365 gün) vadeli fiyat hareketlerini tahmin etmektir. |
| **Veri Seti** | **Kaynaklar:** Yahoo Finance (BTC-USD), FRED (Makro Veriler).<br>**Boyut:** 4067 Satır, 73 Sütun (Birleştirilmiş & İşlenmiş).<br>**İçerik:** `BTC-USD`, `CPI` (TÜFE), `DXY` (Dolar Endeksi), `FEDFUNDS` (Faiz), `GSPC` (S&P500), `VIX` (Volatilite).<br><br>![Korelasyon](images/correlation_matrix.png)<br>*(Görsel: Veriler arasındaki ilişki matrisi)* |
| **Metodoloji** | **1. Ön İşleme:** Eksik veri tamamlama, Lag Features (Gecikmeli veri), Scaling.<br>**2. Özellik Seçimi:** PCA, SelectKBest, RFE, Lasso-based.<br>**3. Modeller:** Linear Reg., Ridge, Lasso, SVR, Decision Tree, KNN, Logistic Reg. |
| **Sonuçlar & Performans** | Aşağıdaki tablo 5 kişilik ekibin en iyi model sonuçlarını özetlemektedir:<br><br>| Model | Hedef (Target) | Özellik Seti | RMSE | R² Score | Yön Doğruluğu |<br>| :--- | :--- | :--- | :--- | :--- | :--- |<br>| **Linear Regression** | Target_1d | Full | 1091.90 | 0.9974 | 0.52 |<br>| **Ridge Regression** | Target_30d | PCA (20) | 4876.50 | 0.9472 | 0.55 |<br>| **SVR** | Target_7d | Full | 3150.20 | 0.9780 | 0.56 |<br>| **KNeighbors** | Target_365d | Full | 18342.11 | 0.2534 | 0.49 |<br><br>![Sonuç Tablosu](images/results_table.png)<br>*(Görsel: Detaylı performans karşılaştırması)* |
| **Temel Bulgular** | • **Kısa Vade:** Linear modeller %99 başarı sağladı (Random Walk etkisi).<br>• **Orta Vade:** PCA kullanımı, Ridge modelinde gürültüyü azaltarak başarıyı artırdı.<br>• **Yön Tahmini:** SVR modeli %56 ile en iyi sinyali üretti.<br>• **Uzun Vade:** Temel modeller 1 yıllık tahminlerde yetersiz kaldı ($R^2 < 0.25$). |
| **Kurulum & Kullanım** | Projeyi yerel ortamda çalıştırmak için:<br>`git clone https://github.com/KULLANICI_ADINIZ/REPO_ADI.git`<br>`pip install pandas numpy scikit-learn matplotlib seaborn ta-lib`<br>Notebook dosyasını çalıştırın. |
| **Takım Üyeleri** | 1. **Khaiitmurod Khabibullayev** (Linear, DT, SelectKBest)<br>2. **Abdumajid Abdulkhaev** (Ridge, KNN, RFE)<br>3. **Yesset Yelebayev** (Lasso, SVR, Lasso-based)<br>4. **Diyorjon Ochilov** (Linear, DT, Mutual Info)<br>5. **İbrahim Halil Yanaç** (Logistic, KNN, PCA) |
| **Lisans** | Bu proje **MIT Lisansı** altında açık kaynaklıdır. |
