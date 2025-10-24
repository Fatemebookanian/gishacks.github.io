---
title: جلسه ۳ - تهیه نقشه از طریق نمایش داده‌ها
---

## 🎯 هدف جلسه

در این جلسه یاد می‌گیریم چطور داده‌هایی که در اختیار داریم را به زیبایی در نقشه نمایش بدهیم تا خواناتر و کاربردی‌تر شوند.  
از اضافه کردن نقشه پایه (Basemap) تا انواع مختلف سیمبولوژی برای رنگ‌بندی، اندازه‌ها و نمادگذاری داده‌ها را تمرین خواهیم کرد.

---

## 🗺️ اضافه کردن Basemap دلخواه

نقشه پایه یا **Basemap** پس‌زمینه‌ای است که تمام داده‌های مکانی روی آن نمایش داده می‌شود.  
گاهی به نقشه‌های ماهواره‌ای نیاز داریم و گاهی به نقشه‌های شماتیک.

**مراحل کار:**
1. از نوار ابزار گزینه **Add data** را انتخاب می‌کنیم.  
2. وارد بخش **From path** می‌شویم.  
3. لینک **OpenStreetMap** را از [بخش ترفندها](https://gishacks.ir/hacks/basemaps/) کپی می‌کنیم.  
4. لینک را در قسمت **Path** پیست می‌کنیم تا نقشه پایه اضافه شود.

![Basemap](https://github.com/user-attachments/assets/3d627871-79bd-430d-8b4d-81fc254a8ac6)

![Basemap Add Data](https://github.com/user-attachments/assets/bdda6dc0-53ce-4a61-b845-ec128f98b13f)

---

## 🎨 آشنایی با Symbology (سیمبولوژی)

سیمبولوژی یعنی نمایش معنادار داده‌ها با رنگ، اندازه و نماد متفاوت. هدف این است که با یک نگاه، بیننده بتواند تفاوت‌ها و الگوهای پنهان در داده‌ها را ببیند.

---

### 🟡 Single Symbol  
زمانی استفاده می‌شود که فقط می‌خواهیم موقعیت داده‌ها را نمایش دهیم، نه تفاوت‌ها.  
مثلاً نمایش تمام ایستگاه‌های مترو با یک رنگ ثابت.

![Single Symbol](https://www.dropbox.com/scl/fi/wdfo9ro98rsr1t39jpjky/Screenshot-2025-10-06-235505.png?rlkey=4abvsjrdwe5mx2dktswgdyp1a&st=sficgngl&dl=1)

---

### 🌈 Unique Values  
این روش برای داده‌های **طبقه‌ای یا کیفی** مثل کاربری زمین به‌کار می‌رود. هر نوع کاربری رنگ مخصوص خود دارد.  

![Unique Values Example](https://www.dropbox.com/scl/fi/9xxk3ti58jq0botx3afe0/Screenshot-2025-10-06-232430.png?rlkey=uc69vpca7436aiuw6nibwvmjq&st=bourxqt3&dl=1)

---

### 🔺 Graduated Symbols  
برای داده‌های عددی استفاده می‌شود.  
به‌عنوان مثال، راه‌های اصلی و فرعی را با خطوط ضخیم یا نازک و رنگ مشابه می‌توان نمایش داد.

![Graduated Symbol](https://www.dropbox.com/scl/fi/mpiv979aab53skvpioji8/Screenshot-2025-10-07-000704.png?rlkey=6zen9vqsn7uzzzvy4qkankm18&st=mxdoo4ol&dl=1)

---

## 📊 نمایش داده‌ها با نمودار و چگالی

### 1. Pie Chart (نمودار دایره‌ای)
از مسیر **Symbology → Charts → Pie Chart**، می‌توان نسبت جمعیت مرد و زن را در محدوده‌های جمعیتی نمایش داد.

![Pie Chart](https://github.com/user-attachments/assets/e5c39d9a-f9b8-4c26-9187-2252d3185538)

---

### 2. Dot Density (چگالی نقطه‌ای)
هر نقطه نمایانگر تعدادی از جمعیت است.  
با گزینه **Dot Size** اندازه نقطه‌ها قابل تغییر است.

![Dot Density](https://github.com/user-attachments/assets/35aff595-151e-458a-a341-447c6cfa600a)

---

### 3. Proportional Symbols (نمادهای نسبتی)
دایره‌ها متناسب با مقدار عددی بزرگ‌تر یا کوچک‌تر می‌شوند.  
در این حالت دسته‌بندی وجود ندارد.

![Proportional Symbols](https://github.com/user-attachments/assets/98759789-2619-4736-ab96-c72e41cdf171)

**تفاوت Proportional و Graduated:**  
در Graduated داده‌ها به کلاس تبدیل می‌شوند، ولی در Proportional اندازه نماد دقیقاً متناسب با مقدار واقعی است.

---

## 🔥 Heat Map (نقشه حرارتی)

Heatmap برای نمایش شدت یا تراکم داده‌های نقطه‌ای مثل زلزله، جرم یا تراکم جمعیت کاربرد دارد.

![Heatmap](https://github.com/user-attachments/assets/1c1f3d08-4bf3-4d7a-aedc-ea5591465948)

**تنظیمات مهم:**
- **Weight Field:** ویژگی داده‌ها (مثلاً ZMAG برای شدت زلزله)
- **Method:** می‌تواند **Constant** یا **Dynamic** باشد. حالت Dynamic با بزرگ‌نمایی (Zoom) به‌صورت خودکار بازآرایی می‌شود.

![Weight Field](https://github.com/user-attachments/assets/dadda9e3-85e6-4b44-85d6-9973bd7ba43b)

---

## 🎬 ساخت انیمیشن (Time Series)

وقتی در داده زمان داریم (مثل تاریخ وقوع زلزله)، می‌توانیم انیمیشن زمانی بسازیم.

1. روی لایه زلزله راست‌کلیک کرده و [translate:Properties → Time] را انتخاب کنید.  
2. گزینه **Filter layer content based on attribute values** را فعال کنید.  
3. از تب **View → Animation → Add** شمای کلی تایم‌لاین را بسازید.  
4. برای تنظیم گام‌های زمانی (Number of steps) و بازه‌ها تنظیمات را اصلاح کنید.  

![Enable Time](https://github.com/user-attachments/assets/B6b4qZfZ/Screenshot-361.png)

### 🎞️ خروجی گرفتن از انیمیشن
1. از تب **Animation → Export → Movie** استفاده کنید.  
2. فرمت خروجی را **.gif** انتخاب کنید تا حجم و سرعت مناسب شود.

![Export](https://github.com/user-attachments/assets/TwbGy71F/Screenshot-362.png)

📍 **نمونه خروجی:**  
[ویدیو نمونه Heatmap زلزله ایران (Dropbox)](https://www.dropbox.com/scl/fi/f5dugs300q7rax5fbfbmo/Map1.mp4?rlkey=4ctv5j2k27r2dlwbj8ovi2jnx&st=1g0mltrd&dl=1)

---

## ✨ جمع‌بندی

در این جلسه یاد گرفتیم:
- چطور **Basemap** دلخواه را اضافه کنیم.  
- با انواع **Symbology** ظاهر داده‌ها را تنظیم کنیم.  
- از روش‌های **Heat Map** و **Proportional Symbols** برای نمایش داده‌های کمی استفاده کنیم.  
- و در آخر چطور یک **انیمیشن زمانی** از داده‌ها بسازیم تا در طول زمان تغییرات مکانی را ببینیم.

---

## 🔗 تمرین پیشنهادی

لایه‌ای از داده‌های جمعیتی یا زلزله‌های ایران را انتخاب کن و سه نوع نمایش زیر را اجرا کن:
1. Unique Value  
2. Graduated Symbol  
3. Heatmap  

در پایان از هر نقشه اسکرین‌شات بگیر و در گزارش خودت قرار بده.
