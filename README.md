#  SQL Sorğu Layihəsi - Məhsul, Alış və Satış Analizi


Bu layihə, məhsul, alış, satış, təchizatçı və kateqoriya məlumatları ilə əlaqəli verilənlər bazasında bir sıra analitik sorğuların hazırlanmasına yönəlib. Layihənin məqsədi, məhsul mövcudluğu, təchizatçı performansı, satış statistikaları və məhsul qiymətləndirmə mövzularında əsas iş suallarına cavab tapmaqdır.

Layihə SQL dilindən istifadə edərək müxtəlif biznes suallarını cavablandıran və qərar qəbul etmə prosesində kömək edən məlumatlar təqdim edir. Bu README faylı, layihənin məqsədini, cavablandırılan iş suallarını və sorğuları dəstəkləyən verilənlər bazası strukturu dəyişikliklərini izah edir.

## Məqsəd
Bu layihənin məqsədi:
- Məhsul mövcudluğu və satışları ilə bağlı məlumatları təqdim etmək.
- Təchizatçıların fəaliyyətini izləmək və tendensiyaları müəyyənləşdirmək.
- Məhsul kateqoriyalarını izləmək və ən vacib kateqoriyaları müəyyənləşdirmək.
- Qiymətləndirmə və satış məlumatlarını təhlil edərək daha yaxşı qərar qəbul etməyi təmin etmək.

Sorğular əsasən aşağıdakı sahələri əhatə edir:
- Verilənlər bazasında olan ümumi məhsul sayı.
- Son bir ayda konkret təchizatçıdan alınan məhsulların ümumi alış qiyməti.
- Son rübdə ən çox məhsul təqdim edən təchizatçını müəyyənləşdirmək.
- Ötən həftədə həyata keçirilən ümumi satış məbləği.
- Ən yüksək qiymətə sahib olan məhsulu müəyyənləşdirmək.
- Alınan, lakin hələ də satılmayan məhsulları tapmaq.
- Ən çox məhsul olan kateqoriyanı tapmaq.
- Hər bir məhsulun orta satış qiymətini hesablamaq.
- Son bir ayda neçə təchizatçının məhsul tədarük etdiyini müəyyənləşdirmək.
- Son bir ayda hansı məhsulların satılmadığını tapmaq.

## Layihənin Əsas Xüsusiyyətləri

### 1. Məhsul Analizi:
- Verilənlər bazasında olan ümumi məhsul sayını tapmağa yönəlmiş sorğu.
- Alınan, lakin satılmayan məhsulları müəyyənləşdirmək.
- Qiyməti ən yüksək olan məhsulu tapmaq.

### 2. Satış Analizi:
- Ötən həftədəki ümumi satış məbləğini hesablamaq.
- Hər bir məhsulun orta satış qiymətini hesablamaq.

### 3. Təchizatçı Performansı:
- Son rübdə ən çox məhsul təqdim edən təchizatçını müəyyənləşdirmək.
- Son bir ayda neçə təchizatçının məhsul tədarük etdiyini hesablamaq.

### 4. Kateqoriya Analizi:
- Ən çox məhsul olan kateqoriyanı tapmaq.

### 5. Alış Məlumatları:
- Son bir ayda konkret təchizatçıdan alınan məhsulların ümumi alış qiymətini tapmaq.
- Son bir ayda satılmayan məhsulları müəyyənləşdirmək.

## Verilənlər Bazası Dəyişiklikləri
Bu layihədə lazım olan sorğuların işləməsi üçün verilənlər bazası strukturu üzərində bir neçə dəyişiklik edilib:

### 1. Məhsul Cədvəlinə Yeni Sütunlar Əlavə Edildi:
- `categoryid` adlı yeni bir sütun `product` cədvəlinə əlavə olunaraq hər bir məhsulun bir kateqoriya ilə əlaqələndirilməsi təmin edildi.
- `product` cədvəlindəki `categoryid` sütunu ilə `category` cədvəli arasında xarici açar əlaqəsi quruldu.

### 2. Kateqoriya Cədvəlinə Yeni Sütunlar Əlavə Edildi:
- `category` cədvəlinə `productid` adlı yeni bir sütun əlavə edilib, hər bir kateqoriyanın müəyyən məhsullarla əlaqələndirilməsi təmin olundu.

### 3. Xarici Açar Əlaqələri:
- `product`, `category`, `purchase` və `supplier` cədvəlləri arasında xarici açar əlaqələri yaradıldı ki, bu da verilənlər bazasında məlumatların düzgün inteqrasiyasını təmin edir və daha mürəkkəb sorğulara imkan verir.

### 4. Verilənlər Yeniləndi:
- `product` və `category` cədvəllərində məhsul və kateqoriya arasında mənalı əlaqələrin qurulması üçün verilənlər yeniləndi.

## Cavablandırılan Əsas İş Sualları:

### 1. Verilənlər bazasında neçə məhsul var?
Bu sorğu, bazada olan ümumi məhsul sayını müəyyən edir və müəssisənin inventar səviyyəsini qiymətləndirməyə kömək edir.

### 2. Son bir ayda konkret təchizatçıdan alınan məhsulların ümumi alış qiyməti nə qədərdir?
Bu sorğu, təchizatçıların maliyyətlərini qiymətləndirməyə və zamanla müqayisə etməyə imkan verir.

### 3. Son rübdə hansı təchizatçı ən çox məhsul təqdim edib?
Bu sorğu, ən fəal təchizatçıları müəyyənləşdirir və onların performansını izləməyə imkan verir.

### 4. Ötən həftə nə qədər satış həyata keçirildi?
Bu sorğu, ötən həftəki satış performansını qiymətləndirməyə kömək edir.

### 5. Ən yüksək qiymətə sahib məhsul hansıdır?
Bu sorğu, qiyməti ən yüksək olan məhsulu müəyyənləşdirir və müəssisənin premium məhsullarını təyin etməyə kömək edir.

### 6. Hansı məhsullar alınmış, lakin hələ də satılmayıb?
Bu sorğu, alınan və hələ də satılmayan məhsulları müəyyənləşdirir və ehtiyac varsa, əlavə satış təşviqatları təklif edir.

### 7. Ən çox məhsul olan kateqoriya hansıdır?
Bu sorğu, müəssisənin ən əhəmiyyətli məhsul kateqoriyasını müəyyənləşdirir.

### 8. Hər bir məhsulun orta satış qiyməti nə qədərdir?
Bu sorğu, məhsulun satış qiymətinin orta səviyyəsini müəyyənləşdirir və qiymət strategiyalarını qiymətləndirməyə kömək edir.

### 9. Son bir ayda neçə təchizatçı məhsul tədarük edib?
Bu sorğu, təchizatçı şəbəkəsini izləməyə kömək edir və təchizatçı fəaliyyətinin trendlərini təhlil edir.

### 10. Son bir ayda hansı məhsullar satılmayıb?
Bu sorğu, son bir ayda satılmayan məhsulları müəyyənləşdirir və ehtiyac varsa, endirim və ya promosyonlar təklif edir.


Bu layihə, müəssisənin məhsul, satış və təchizatçı məlumatlarını təhlil edən bir sıra SQL sorğuları təqdim edir. Verilənlər bazası dəyişiklikləri məlumatların düzgün inteqrasiyasını təmin edir və daha mürəkkəb analizlərə imkan verir. Bu layihə, biznes analitikləri, əməliyyat menecerləri və qərar qəbul edənlər üçün faydalı bir vasitədir, çünki müəssisənin məhsul inventarını, təchizatçı performansını və satışları effektiv şəkildə izləməyə imkan verir.
