# Big-Error
# - مشکل نسبتا برزگ تازه کار های لینوکسی ( مثل خودم :) )
گاهی وقتا میخواین از دستور زیر ااستفاده کنید اما به ارور میخورید :
```Bash
sudo apt update
```
حتی بعضی وقتا میخواین یک پکیج یا ماژولی رو نصب کنید که باز هم به خطا میخورید..اما شما یک کاربر صبور لینوکسی هستید و باید مشکلتون رو حل کنید ( برای مثال ممکنه این دستور بهتون ارور بده ) :
```Bash
sudo apt install golang-go
```
اما علت این مشکل چیه ؟ 
1: زیادی مسخره به نظر میرسه ولی مشکل میتونه اتصالات اینترنت باشه..برسی کنید ببینید اصلا سیستمون وصله ؟ وصل نیست ؟ . میتونید با دستور زیر اتصالتون رو برسی کنید :
```Bash
ping www.google.com
```
همچنین دستور sudo رو با فیلتر شکن و پروکسی تست کنید..اکر نشد نا امید نشید !


2 : مشکلات کلید GPG(public key)  که شایع ترین دلیل هستش و برای سیستم منم همین مورد ارور درست میکرد...برخی از مخازن، به خصوص PPAها، برای تأیید اعتبار بسته‌ها به کلیدهای عمومی GPG نیاز دارند. اگر این کلیدها نصب نشده باشند، apt نمی‌تواند بسته‌ها را به درستی شناسایی کند و خطا می‌دهد. در خروجی apt update معمولاً خطایی مانند "NO_PUBKEY" مشاهده خواهید کرد... برای حل این مشکل دستور زیر رو بزنید : 
```Bash
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys ABCDEF1234567890
```
نکته : دستور رو یکبار با VPN و اگر کار نکرد بدون VPN تست کنید.
اگر به طور کلی دستور بالا کار نکرد بیاید سراغ این دستور : 
```Bash
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys ED65462EC8D5E4C5
```
نکته : دستور رو یکبار با VPN و اگر کار نکرد بدون VPN تست کنید.

تکرار میکنم : من با همین دستور تونستم مشکلم رو حل کنم..

این ارور میتونه دلایل دیگه هم داشته باشه که من مهمترینش رو عنوان کردم...در آخر براتون یک فیلتر شکن خوب تدارک دیدم >_+ که میتونه براتون کانکشن خوبی براقرار کنه. همچنین داخل فایل Config براتون کانفیگ های لازم رو برای کار با فیلتر شکن اماده کردم.

لینک دانلود فیلتر شکن حرفه ای تقدیمت »    
https://github.com/MatsuriDayo/nekoray/releases/download/3.26/nekoray-3.26-2023-12-09-linux64.zip
