# Bitcoin-Price-Prediction-Mining
# 📈 Bitcoin Fiyat Tahminlemesi: Makroekonomik Yaklaşım

![Project Banner](https://via.placeholder.com/1000x300?text=Bitcoin+Price+Prediction+Project+Banner)

| **Bölüm** | **Detaylar** |
| :--- | :--- |
| **Ders / Grup** | Veri Madenciliği (FET445) / **MacroMinds** |
| **Proje Amacı** | Bu proje, Bitcoin (BTC) fiyat hareketlerini sadece teknik analizle değil, küresel makroekonomik göstergelerle (enflasyon, faiz, para arzı vb.) birleştirerek **kısa (1-7 gün)**, **orta (30 gün)** ve **uzun (365 gün)** vadede tahmin etmeyi amaçlar. |
| **Veri Seti** | **Kaynak:** Yahoo Finance & FRED (Federal Reserve Economic Data)<br>**Boyut:** 4067 Satır, 73 Sütun<br>**Finansal:** BTC-USD (Açılış, Kapanış, Hacim)<br>**Makro:** `FEDFUNDS` (Faiz), `CPI` (Enflasyon), `DXY` (Dolar Endeksi), `GSPC` (S&P 500), `VIX` (Korku Endeksi)<br>**Türetilmiş:** RSI, MACD, SMA, Logaritmik Getiriler |
| **Görselleştirme** | **Korelasyon Matrisi:**<br>![Korelasyon Matrisi](images/correlation_matrix.png)<br>*(BTC fiyatı ile DXY ve VIX arasındaki negatif ilişkiyi gösterir)* |
| **Metodoloji** | **1. Ön İşleme:** Eksik veri doldurma, Lag (Gecikme) özellikleri (t-1, t-7), Ölçeklendirme (StandardScaler).<br>**2. Özellik Seçimi:** PCA (%95 Varyans), SelectKBest, RFE, Lasso-based.<br>**3. Modeller:** Linear Regression, Ridge, Lasso, Decision Tree, KNN, SVR, Logistic Regression. |
| **Performans** | **En İyi Sonuçlar:**<br>• **Kısa Vade (1 Gün):** Linear Regression (R²: 0.99, RMSE: 1091)<br>• **Orta Vade (30 Gün):** Ridge Regression + PCA (R²: 0.94)<br>• **Yön Tahmini:** SVR (%56 Doğruluk)<br><br>![Sonuç Tablosu](images/results_table.png) |
| **Bulgular** | • Kısa vadeli tahminlerde yüksek başarı (%99 R²) sağlandı.<br>• PCA kullanımı, orta vadeli tahminlerde hata oranını (RMSE) düşürdü.<br>• Uzun vadeli (1 yıl) tahminlerde temel modellerin yetersiz kaldığı görüldü. |
| **Kurulum** | ```bashgit clone [https://github.com/KULLANICI_ADINIZ/Bitcoin-Price-Prediction-Mining.gitcd](https://github.com/KULLANICI_ADINIZ/Bitcoin-Price-Prediction-Mining.gitcd) Bitcoin-Price-Prediction-Miningpip install pandas numpy scikit-learn matplotlib seaborn ta-lib``` |
| **Takım Üyeleri** | **Khaiitmurod Khabibullayev:** Linear Reg, Decision Tree, SelectKBest<br>**Abdumajid Abdulkhaev:** Ridge, KNN, RFE<br>**Yesset Yelebayev:** Lasso, SVR, Lasso-based Selection<br>**Diyorjon Ochilov:** Linear Reg, Decision Tree, Mutual Info<br>**İbrahim Halil Yanaç:** Logistic Reg, KNN, PCA |
| **Lisans** | Bu proje [MIT](https://choosealicense.com/licenses/mit/) lisansı altındadır. |
