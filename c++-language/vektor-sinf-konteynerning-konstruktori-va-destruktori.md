# vektor sinf-konteynerning konstruktori va destruktori

Algoritmlar (algorithms) konteyner ichidagilar ustidan operatsiyalar bajaradi. Konteyner ichidagilarni initsializatsiyalash, qidirish, saralash va almashtirish uchun algoritmlar mavjud. Ko‘p algoritmlar konteyner ichidagi elementlarni chiziqi ro‘yxatini ifodalaydovchi ketma-ketlik (sequence) bilan ishlash uchun mo‘ljallangan.

Iteratorlar (iterators) – bu konteynerga nisbatan ko‘rsatkich sifatida bo‘lgan ob’ektlar. Ular massiv elementlariga ruxsat oluvchi ko‘rsatkichlar kabi, konteyner ichidagiga ruxsat olish imkoni beradi.

Sinf-konteynerlar

STL da quyidagi sinf-konteynerlar aniqlangan:

Asosiy konteynerlar

vector \<vector.h> dinamk massiv

list \<list.h> chiziqli ro‘yxat

deque \<deque.h> ikki tarafli dvustoronnyaya tartib

set \<set.h> to‘plam

multiset \<set.h> xar bir elementi noyob bo‘lishi shart emas to‘plam

map \<map.h> kalit/ qiymat juftlikni saqlash uchun assotsiativ ro‘yxat. Bunda xar bir kalit bitta qiymat bilan bog‘langan.

multimap \<map.h> xar bir kalit bilan ikkita yoki ko‘proq qiymatlar bog‘langan

Xosila konteynerlar

stack \<stack.h> stek

queue \<queue.h> tartib

priority\_queue \<queue.h> birinchi o‘rindagi tartib

Konstruktorlar

Ixtiyoriy sinf-konteyner ko‘rsatilmagan xolda konstruktor va destruktorni nusxalovchi konstruktorga ega.

Masalan, vektor sinf-konteynerning konstruktori va destruktori:

| vector\<elem> c                         | bitta xam elementga ega bo‘lmagan bo‘sh vektorni yaratadi;                                       |
| --------------------------------------- | ------------------------------------------------------------------------------------------------ |
| vector\<elem> c1(c2)                    | ko‘rsatilgan tipdagi boshqa vektorning nusxasini yaratadi (barcha elementlarni nusxasini oladi); |
| vector\<elem> c(n)                      | konstruktor orqali ko‘rsatilmagan xolda yaratilgan n elementli vektorni yaratadi;                |
| <p>vector&#x3C;elem> c(n,x)</p><p> </p> | x elementning n nusxalari yordamida initsializatsiya etilgan vektorni yaratadi;                  |
| \~vector\<elem>()                       | barcha elementlarni o‘chiradi va xotirani bo‘shatadi.                                            |

&#x20;

Ixtiyoriy ob’ekt uchun ko‘rsatilmagan xolda konteynerda saqlanuvchi konstruktor mavjud bo‘lishi shart. Undan tashqari, ob’ekt uchun < va == operatorlar aniqlanish lozim.

Iteratorlar

Itaratorlar bilan ko‘rsatkichlar kabi ishlash mumkin. Ularga \*, inkrement, dekrement operatorlarni qo‘llash mumkin. Iterator tipi sifatida xar xil konteynerlarda aniqlangan iterator tip elon qilinadi.

Itoratorlarning beshta tipi mavjud:

&#x20;   1\. Kiritish iteratorlar (input\_iterator) tenglik, nomini o‘zgartirish va inkrementa operatsiyalarni qo‘llaydi.

\==, !=, \*i, ++i, i++, \*i++

Kiritish iteratsiyasining maxsus xolati istream\_iterator iborat.

&#x20;   2\. Chiqarish iteratorlar (output\_iterator) o‘zlashtirish operatorning chap tarafidan imkon bo‘lgan isimning o‘zgartirish va inkrementa operatsiyalar qo‘llanadi.

\++i, i++, \*i=t, \*i++=t

Chiqarish iteratsiyasining maxsus xolati ostream\_iterator.

&#x20;  3\. Bitta yo‘nalishdagi iteratorlar (forward\_iterator) kiritish/chiqarish operatsiyalarning barchasini qo‘llaydi, bundan tashqari chegarasiz o‘zlashtirishning imkonini beradi.

\==, !=, =, \*i, ++i, i++, \*i++

&#x20;   4\. Ikki yo‘nalishdagi iteratorlar (biderectional\_iterator) forward-iteratorlarning barcha xususiyatlariga ega, bundan tashqari, konteynerni ikkita yo‘nalishi bo‘yicha o‘tish imkonini beradigan qo‘shimcha dekrementa (--i, i--, \*i--) operatsiyasiga ega.

&#x20;   5\. Ixtiyoriy ruxsatga ega bo‘lgan iteratorlar (random\_access\_iterator) biderectional-iteratorlarning barcha xususiyatlariga ega, bundan tashqari solishtirish va manzil arifmetikasi operatsiyalarni qo‘llaydi.

i+=n, i+n, i-=n, i-n, i1-i2, i\[n], i1\<i2, i1<=i2, i1>i2, i1>=i2

Shuningdek, STLda teskari iteratorlar (reverse iterators) qo‘llaniladi. Ketma-ketlikni teskari yo‘nalishda o‘tuvchi ikki yo‘nalishli yoki ixtiyoriy ruxsatga ega bo‘lgan iteratorlar teskari iteratoralar bo‘lishi mumkin.

Xotirani taqsimlovchilar, predikatlar va solishtirish funksiyalari

&#x20;Konteynerlarga, algoritmlarga va STLdagi iteratorlarga qo‘shimcha bir nechta standart komponentalar xam qo‘llaniladi. Ulardan asoslari esa xotira taqsimlovchilar, predikatlar,va solishtirish funksiyalaridir.

Xar bir konteynerda uning uchun aniqlangan va konteyner uchun xotirani belgilash jarayonini boshqaradigan xotira taqsimlovchisi (allocator) mavjud.

Ko‘rsatilmagan xolda esa xotira taqsimlovchisi allocator sinf ob’ektidir. Xususiy taqsimlovchini tavsiflash mumkin.

Ba’zi bir algoritmlar va konteynerlarda muxim tipdagi predikat ataluvchi funksiyalar ishlatiladi. Predikatlar unar va binar bo‘lishi mumkin. U yoki bu qiymatni olish aniq shartlari dasturchi orqali aniqlanadi. Unar predikatlarning tipi – UnPred, binar predikatlarning esa - BinPred. Argumentlar tipi konteynerda saqlanuvchi ob’ektlar tipiga mos.

Ikkita elementlarni solishtirish uchun binar predikatlarning maxsus tipi aniqlangan. U solishtirish funksiya (comparison function) deyiladi. Agarda birinchi element ikinchidan kichik bo‘lsa, unda funksiya rost qiymatni qaytaradi. Comp tip funksiya tipidir. STL da ob’ekt-funksiyalar o‘ziga xos axamiyatga ega.

Ob’ekt-funksiyalar – bu sinfda «kichik qavslar» () operatsiyasi aniqlangan sinf nusxalari. Ba’zi bir xollarda funksiyalarni ob’ekt-funksiyalarga almashtirish qulay deb xisoblanadi. Ob’ekt-funksiya funksiya sifatida ishlatilsa, unda uni chaqirish uchun operator () operator ishlatiladi.

Vector-vektor konteynerlari

STL da vector vektor dinamik massiv sifatida aniqlanadi. Massiv elementlariga indeks orqali ruxsat beriladi.

vector sinfida quyidagi konstruktorlar aniqlangan:

Birinchi shakl bo‘sh vektor konstruktorini tavsiflaydi.

Konstruktor vektorning ikkinchi shaklida elementlar soni – bu son, xar bir elementi esa qiymat qiymatiga teng. Qiymat parametri ko‘rsatilmagan xoldagi qiymat bo‘lishi mumkin.

Konstruktor vektorning uchinchi shakli – bu nusxalash konstruktori.

To‘rtinchi shakli – bosh va oxirgi iteratorlar orqali elementlar diapazonini o‘z ichiga olgan konstruktor vektor.

Vektorda saqlanadigan ixtiyoriy ob’ekt uchun ko‘rsatilmagan xolda konstruktor aniqlash zarur. Bundan tashqari, ob’ekt uchun < va == operatorlar aniqlanishi lozim.

Vektor sinfi uchun quyidagi solishtirish operatorlari mavjud:

\==, <, <=, !=, >, >=.

Bundan tashqari, vector sinf uchun \[] indeks operatori aniqlangan.

Ikki yo‘nalishli tartib (Deque)

deque – vektor kabi, ixtiyoriy ruxsat iteratorlarni qo‘llovchi ketma-ketlik ko‘rinishi. Bundan tashqari, u o‘zgarmas vaqtda boshida yoki oxirida kiritish va ochirish operatsiyalarni qo‘llaydi. O‘rtada kiritish va o‘chirish chiziqli vaqtni egallaydi. Xotirani boshqarishiga ishlov berish esa vektorlar kabi avtomatik ravishda bajariladi.

Ruyxat(List)

Ro’yxat – ikki yo‘nalishli iteratorlarni qo‘llaydigan xamda kiritish va o‘chirish operatsiyalarni o‘zgarmas vaqtda ketma-ketlikni ixtiyoriy joyida bajaradigan, shuningdek, xotirani boshqarishiga avtomatik ravishda ishlov beruvchi ketma-ketlik ko‘rinishi. Vektorlar va ikkitarafli tartiblardan farqi shundaki elementlar ro‘yxatiga tez va ixtiyoriy ro‘xsat qo‘llanmaydi, lekin ko‘pgina algoritmlarga esa ketma-ketlik ruxsat zarur.

Assotsiativ konteynerlar (massivlar)

Assotsiativ massiv juft qiymatlardan iborat. (key) kalit deb atalgan bitta qiymatni bilib (mapped value) aks etuvchi qiymat deb atalgan ikkinchi qiymatga ruxsat olishimiz mumkin.

Assotsiativ massivni massiv indekslari butun tiplardan iborat bo‘lmagan massiv sifatida tavsiflash mumkin:

V& operator\[]\(const K&) K ga mos keluvchi V ga ilovani qaytaradi.

Assotsiativ konteynerlar – bu assotsiativ massivning umumiy tushunchasi.

map assotsiativ konteyner - bu kalit yordamida qiymatga tez ega bo‘lish imkonini yaratadigan juftlik (kalit, qiymat) ketma-ketligi. map konteyneri ikki yo‘nalishli iteratorni tavsif etadi.

map assotsiativ konteyneri kalit tiplari uchun “<” operatsiyasi mavjudligini talab qiladi. U kalit bo‘yicha saralangan o‘z elementlarini saqlaydi. Saralash almashuvi esa tartib bo‘yicha bajariladi.

map sinfida quyidagi knstruktorlar aniqlangan:

birinchi shakli bo‘sh assotsiativ konteynerning konstruktorini tavsiflaydi. Ikkinchi shakli – konstruktor nusxasi, uchinchisi – elementlar diapazonini kamrab olgan assotsiativ konteynerning konstruktori.

O‘zgartirish operatsiyasi aniqlangan:

map& operator=(const map&);

quyidagi operatsiyalar aniqlangan: ==, <, <=, !=, >, >=.

mapda kalit/qiymat juftliklar pair tiplagi ob’ektlar ko‘rinishida saqlanadi.

Kalit/qiymat juftliklarni faqatgina pair sinf konstruktorlari yordamida, balki pair tipdagi ob’ektlarni yaratuvchi va ma’lumotlar tiplaridan parametrlar sifatida foydalanuvchi make\_pair funksiya yordamida yaratish mumkin.

Assotsiativ konteyner uchun o‘ziga xos operatsiya – bu (\[]) indeksatsiyalash operatsiyasi yordamida assotsiativ qidiruv.

mapped\_type& operator\[]\(const key\_type& K);

set to‘plamini assotsiativ massiv sifatida ko‘rish mumkin. Unda qiymatlar axamiyatga ega emas, shuning uchun faqat kalitlarni ko‘zatish mumkin.

to‘plamlar assotsiativ massiv kabi T tip uchun (<) “kichik” operatsiyani mavjudligini talab etadi. U o‘z elementlarini saralangan xolda saqlaydi. saralash almashuvi esa tartibda bajariladi.

Konteyner usullari

Iteratorlarni olish usullari

begin() birinchi elementga ko‘rsatadi;

end() oxiridan keyingi elementga ko‘rsatadi;

rbegin() teskari ketma-ketlikdagi birinchi elementni ko‘rsatadi;

rend() teskari ketma-ketlikdagi oxirgidan keyingi elementni ko‘rsatadi

Elementlarga ruxsat

front() birinchi elementga ilova;

Back() oxiri elementga ilova;

operator\[]\(i) tekshirishsiz indeks bo‘yicha ruxsat;

at(i) tekshirish bilan indeks bo‘yicha ruxsat.

front() birinchi elementga ilova;

Elementlarni kiritish usullari

insert(p,x) r ko‘rsatgan elementdan oldin xni qo‘shish

insert(p,n,x) rdan oldin xning n nusxalarini qo‘shish

insert(p,first,last) rdan oldin \[first:last]dagi elementlarni qo‘shish

push\_back(x) oxiriga xlarni qo‘shish

push\_front(x) yangi birinchi elementni qo‘shish (ikta uchga ega bo‘lgan tartiblar va ro‘yxatlar uchun)

Elementlarni o‘chirish usullari

erase(p) r pozitsiyadagi elementni o‘chirish;

erase(first,last) \[first:last]dan elementlarni o‘chirish;

pop\_back() oxirgi elementni o‘chirish;

pop\_front() birinchi elementni o‘chirish (ikta uchga ega bo‘lgan tartiblar va ro‘yxatlar uchun)

O‘zlashtirish usullari

operator=(x) konteynerga x konteynerni elementlari o‘zlashtiriladi;

assign(n,x) konteynerga x elementning n nusxasi o‘zlashtiriladi (assotsiativ bo‘lmagan konteynerlar uchun);

assign(first,last) \[first:last] diapazondagi elementlarni o‘zlashtirish

Assotsiativ usullari

find(elem) elem qiymatga ega bo‘lgan birinchi elementni pzitsiyasi topadi

lower\_bound(elem) element qo‘yish mumkin bo‘lgan birinchi pozitsiyani to‘padi

upper\_bound(elem) element qo‘yish mumkin bo‘lgan oxirgi pozitsiyani to‘padi

equal\_range(elem) element qo‘yish mumkin bo‘lgan birinchi va oxirgi pozitsiyalarni to‘padi

Assotsiativ usullar

operator\[]\(k) k kalitli elementga ruxsat;

find(k) k kalitli element pozitsiyasini topadi;

lower\_bound(k) k kalitli elementning birinchi pozitsiyasini topadi;

upper\_bound(k) kdan katta bo‘lgan kalitli birinchi elementni to‘padi;

equal\_range(k) k kalitli elementni lower\_bound (kuyi chegarasini) va upper\_bound (yuqori chegarasini) topadi.

Boshqa usullar

size() elementlar soni;

empty() konteyner bo‘shmi?

capacity() vektor uchun ajratilgan xotira (faqat vektorlar uchun);

reserve(n) n elementdan iborat bo‘lgan konteyner uchun xotira ajratadi;

swap(x) ikkita konteynerlarni joyini almashtirish;

\==, !=, < solishtirish operatorlari
