# DIET-AIBA POS — o'rnatuvchi

Kassa dasturini Windows kompyuterga o'rnatish uchun.

**Bu repoda dastur kodi YO'Q va bo'lmaydi.** Bu yerda faqat o'rnatuvchini
yig'adigan workflow turadi. Manba kod yopiq GitLab'da qoladi.

## Yuklab olish

**https://github.com/Jamshid-Khamroyev/diet-aiba-pos/releases/latest**

Havola hech qachon o'zgarmaydi — har yangi build shu sahifadagi faylni
yangilaydi.

## O'rnatish
1. `DIET-AIBA-POS-Setup-*.exe` ni yuklab oling va ikki marta bosing.
2. Windows «noma'lum nashriyot» desa: **Batafsil -> Baribir ishga tushirish**.
   Bu normal: o'rnatuvchi raqamli imzolanmagan.
3. Birinchi ishga tushirishda server manzili va terminal kodi so'raladi —
   ularni menejeringiz beradi.

## Qanday yangilanadi
GitLab'dagi `main` ga push qilinsa, 15 daqiqa ichida shu yerda yangi `.exe`
paydo bo'ladi. Darhol kerak bo'lsa: Actions -> Build -> Run workflow.

Egasi uchun sozlash: [SOZLASH.md](SOZLASH.md).
