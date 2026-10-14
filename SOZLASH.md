# Sozlash (egasi uchun, bir marta)

Build serveri kodni yopiq aiba GitLab'dan o'qiy olishi uchun **ikkita secret**
kerak. Kalitni o'zingiz yaratasiz va hech kimga/hech qayerga yubormaysiz.

## 1. GitLab'da faqat-o'qish kaliti
Asl repo egasi boshqa odam, shuning uchun deploy token (Maintainer kerak)
yasab bo'lmaydi. Buning o'rniga **o'z hisobingizdan** token oling:

`gitlab.aiba.uz` -> avatar -> Preferences -> **Access tokens** -> Add new token
-> Name `github-build`, scope **faqat `read_repository`**, muddat qo'ying
-> Create. Tokenni nusxa oling (bir marta ko'rsatiladi).

Bu token siz o'qiy oladigan loyihalarni o'qiydi: asl repo ham, shaxsiy
nusxa ham.

## 2. GitHub'ga secret sifatida yozish
Repo -> Settings -> Secrets and variables -> Actions -> **Secrets** -> New:

| Nomi | Qiymati |
|---|---|
| `GITLAB_USER` | `j.xamroyev` (GitLab foydalanuvchi nomingiz) |
| `GITLAB_TOKEN` | 1-qadamdagi token |

## 3. (Ixtiyoriy) Manba loyihani almashtirish
Standart manba — asl repo `a.asalbayev/diet-aiba-pos`. Shaxsiy nusxadan
yig'ish kerak bo'lsa: **Variables** bo'limida `GITLAB_PATH` =
`j.xamroyev/diet-aiba-pos.git`.
DIQQAT: shaxsiy nusxa o'zi YANGILANMAYDI (bir martalik nusxa) — undan yig'sangiz
yangi kod `.exe` ga tushmaydi. Nusxani qo'lda yangilash:
`git fetch <asl-repo> main` va `git push <shaxsiy-nusxa> main`.

## 4. Birinchi ishga tushirish
Actions -> **Build** -> Run workflow (`force` ni belgilang).
10-15 daqiqada Releases'da `DIET-AIBA-POS-Setup-*.exe` chiqadi.

## Tavsiya etilgan xavfsizlik sozlamalari (Settings)
- Actions -> General -> **Workflow permissions: Read repository contents**.
- Actions -> General -> **Fork pull request workflows**: tasdiq talab qilinsin.
- Branches -> `main` uchun **force push va o'chirishni taqiqlash**.
- Code security -> **Secret scanning** va **Push protection** yoqing.
- Hisobingizda **2FA** yoqilgan bo'lsin.

## Nosozlik bo'lsa
- Build **qizil** — "GitLab'da topilmadi yoki kirish rad etildi": token
  eskirgan/huquqi yetmaydi -> 1-qadamni takrorlang.
- Token chat yoki kodga yozilmasin. Sizib chiqsa — GitLab'da o'chirib,
  yangisini yarating.
- Yangi kod `.exe` ga tushmayapti — GitLab'da o'zgarish `main` ga merge
  qilinganini tekshiring (boshqa shox kuzatilmaydi).
