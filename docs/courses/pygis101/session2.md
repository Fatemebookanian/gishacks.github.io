---
title: جلسه ۲ - وکتور

---

## مفاهیم
### مقایسه لیست و دیکشنری در پایتون


| ویژگی                     | 🧾 `list`                              | 🗂️ `dict`                                 |
|--------------------------|----------------------------------------|-------------------------------------------|
| تعریف                   | `my_list = [1, 2, 3]`                 | `my_dict = {'a': 1, 'b': 2}`              |
| دسترسی به داده          | `my_list[0] → 1`                    | `my_dict['a'] → 1`                      |
| افزودن عنصر             | `my_list.append(4)`                   | `my_dict['c'] = 3`                        |
| حذف عنصر                | `my_list.remove(2)`                   | `del my_dict['b']`                        |
| بررسی وجود              | `if 2 in my_list:`                        | `if 'a' in my_dict:`                          |
| پیمایش                  | `for x in my_list:`                   | `for k, v in my_dict.items():`           |
| تعداد عناصر             | `len(my_list) → 3`                  | `len(my_dict) → 2`                     |
| ترتیب                   | مرتب است                              | از ۳.۷ به بعد، ترتیب درج حفظ می‌شود     |
| تکرار                    | مقادیر می‌توانند تکراری باشند        | کلیدها باید یکتا باشند                   |
| مرتب‌سازی               | `my_list.sort()`                      | ندارد (باید کلیدها جداگانه مدیریت شود) |

---

!!! نکته

    - استفاده از `list` زمانی مفید است که ترتیب و تکرار عناصر مهم باشد.
    - استفاده از `dict` زمانی مفید است که به ساختار «کلید-مقدار» برای نگهداری داده نیاز باشد.
    - برای جستجوی سریع، `dict` مناسب‌تر است.


برای درک بهتر تفاوت لیست و دیکشنری حدوداً می‌توان گفت که در جدول ستون‌ها به صورت لیست می‌توان فراخواند و ردیف‌ها را به صورت دیکشنری. برای مثل در جدول زیر:

| Name  | Age |  City    |
|-------|-----|-------|
| Alice | 25  | New York |
| Bob   | 30  | London   |

```
# Columns
Name = ['Alice', 'Bob']
Age = [25,30]
City = ['New York', 'London']

#Rows
alice = {'Name':'Alice', 'Age': 25, 'City': 'New York'}
bob = {'Name':'Bob', 'Age': 30, 'City': 'London'}
```

## کار با Pandas
### ۱. نصب

برای نصب کتابخانه Pandas بعد از فعال کردن محیط مجازی پرژه دستور زیر را در ترمینال وارد کنید:

```
pip install pandas
```

!!! نکته
    در محیط Jupyter Notebook با قرار دادن علامت تعجب قبل از دستور فوق کتابخانه در محیط فعال Jupyter نصب می‌شود
    
    ```
    ! pip install pandas
    ```
    

### ۲. استفاده از دستورهای Pandas
برای استفاده از دستورهای کتابخانه Pandas در کد پایتون باید ابتدا آن را با دستور زیر فرا بخوانید

```python
import pandas as pd
```
از این پس هرجا از مخفف pd استفاده می‌کنید، دستورهای pandas فراخوانده می‌شود.


### ۳. کار با پایگاه‌های داده

1. دانلود فایل نمونه

    داده مربوط به زمین‌لرزه‌های یک ماه اخیر را از طریق [این لینک](https://earthquake.usgs.gov/earthquakes/search/) با فرمت csv دانلود و در آدرس repo خود ذخیره کنید.

2. خواندن فایل

    با دستور زیر می‌توانید فایل csv دانلود شده را در قالب یک DataFrame ذخیره کنید.

    ```python
    df = pd.read_csv('query.csv')
    ```
3. اطلاعات کلی درباره فایل

    با دستورهای زیر می‌توانید اطلاعات کلی از DataFrame تعریف شده دریافت کنید.

    ```python
    df.head()
    df.columns
    df.shape
    df.describe()
    df.info()
    df.iloc[0]
    ```
4. گزارش گیری

    با دستورهای زیر می‌توانید از جدول مدنظر خود گزارش بگیرید.
    ```python
    df.groupby('magSource').mean('mag')
    df.sort_values('mag', ascending=False)
    df['rank']=df['mag'].rank(ascending=False)
    ```
5. فیلتر کردن 

    با دستورهای زیر می‌توانید جدول خود بر اساس مشخصات مدنظر فیلتر کنید.
    ```python
    filrered = df[df['mag']>5]
    filrered = df[df['place'].str.contains('Iran')]
    ```
6. خروجی گرفتن

    با دستور زیر می‌توانید از DataFrame مدنظرتان خروجی بگیرید.
    ```python
    filrered.to_csv('alert.csv', index=False)
    ```



## کار با Shapely
### ۱. نصب و فراخواندن
برای نصب کتابخانه‌ Shapely بعد از فعال کردن محیط مجازی پرژه دستور زیر را در ترمینال وارد کنید:

```
pip install shapely
```

برای فراخوانی بخشی از یک کتابخانه می‌توانید از قالب دستوری `from` استفاده کنید.
```python
from shapely.geometry import Point, LineString, Polygon
```
### ۲. ایجاد عوارض جغرافیایی
برای ایجاد عوارض جغرافیایی به صورت نقطه، خط، یا سطح می‌توانید از دستورهای زیر استفاده کنید:

```python
p1 = Point(0, 0)
p2 = Point(10, 20)

ln = LineString([(0, 0), (1, 2), (2, 0)])

pg = Polygon([(0, 0), (1, 1), (1, 0)])
```

### ۳. محاسبه ویژگی‌های هندسی
برای محاسبه ویژگی‌های هندسی عوارض ساخته شده می‌توانید از دستورهای زیر استفاده کنید:

```python
print(p.x, p.y)            # Coordinates
print(ln.length)         # Length of line
print(pg.area)           # Area of polygon
print(pg.bounds)         # Bounding box (minx, miny, maxx, maxy)
```

!!! نکته
    سایر دستورات کاربری Shapely

    ```python
    #Distance
    print(p1.distance(p2))     # → 5.0

    #Buffer
    circle = p1.buffer(1.0)     # Radius 1 around point p

    #Intersection / Union / Difference:

    pg1 = Polygon([(0, 0), (2, 0), (1, 2)])
    pg2 = Polygon([(1, 1), (3, 1), (2, 3)])

    intersection = pg1.intersection(pg2)
    union = pg1.union(pg2)
    difference = polpg1y1.difference(pg2)

    # Select by location
    # Contains / Within / Intersects
    if pg.contains(p):           # True/False
    if p.within(pg):             # True/False
    if pg.intersects(line):      # True/False

    ```





## کار با GeoPandas و MatPlotLib
### ۱. نصب و فراخواندن


برای نصب کتابخانه‌های GeoPandas و MatPlotLib بعد از فعال کردن محیط مجازی پرژه دستور زیر را در ترمینال وارد کنید:

```
pip install geopandas
pip install matplotlib
```
برای استفاده از دستورهای کتابخانه GeoPandas در کد پایتون باید ابتدا آن را با دستور زیر فرا بخوانید

```python
import geopandas as gpd
import matplotlib.pyplot as plt
```

### ۲. خواندن فایل‌های مکانی
با دستور زیر می‌توانید فایل‌های مکانی را به عنوان GeoDataFrame در کد خود فرا بخوانید.
```python
sample_shp = gpd.read_file(r"smaple.shp")
```
### ۳. تبدیل جدول دارای طول و عرض چغرافیایی به نقاط جغرافیایی

```python
df = pd.read_csv('eq.csv')

geometry = []
for xy in zip(df['longtitude'],df['latitude']):
    geometry.append(xy)

gdf = gpd.GeoDataFrame(df, geometry=geometry)
gdf.set_crs(epsg=4326, inplace=True)

```

!!! نکته
    دستور [zip](https://www.w3schools.com/python/ref_func_zip.asp) تناظر یک به یک بین عناصر هم جایگاه در دو [tuple](https://www.w3schools.com/python/python_tuples.asp) را ایجاد می‌کند.
### ۴. گرفتن خروجی تصویری از نقشه
با دستور زیر می‌توانید از DataFrame مدنظر خود خروجی نقشه به صورت عکس بگیرید و به صورت عکس ذخیره کنید.

```python
gdf.plot("mag", cmap="Reds")
plt.savefig('eq_map.jpg')
```
    
!!! نکته
    سایر دستورهای GIS با GeoPandas

    1. Spatial Join

        ```python
        joined_data = gpd.sjoin(parcels1,parcels2)
        ```
    2. Summerize

        علاوه بر groupby می‌توانید با دستور زیر از قابلیت pivot برای گزارش‌گیری استفاده کنید.        
        ```python
        parcels.pivot_table(index='Landuse', columns='Area', aggfunc='sum')
        ```


## تمرین
در کد زیر x و y چه چیز ویژگی از قطعه را در خود ذخیره می‌کنند.

```python
import geopandas as gpd
import shapely
import math
parcels = gpd.read_file("parcel.shp")
for idx, feature in parcels.iterrows():
    parcel = feature['geometry'].simplify(tolerance=0.05)
    coords = list(parcel.boundary.coords)
    temp = []
    for a, b in zip(coords,coords[1:]):
        c = shapely.LineString([a,b]).length
        d = math.degrees(math.atan2(b[1]-a[1], b[0]-a[0]))
        temp.append({'c': c, 'd':d})    
    e = max(temp, key=lambda x: x['c'])
    parcels.loc[idx, 'x']= e['c']
    parcels.loc[idx, 'y']= e['d']
parcels.to_file('parcelx.shp')
```

!!! نکته
    
    کتابخانه [math](https://docs.python.org/3/library/math.html) برای انجام محاسبات ریاضی استفاده می‌شود. این کتابخانه از کتابخانه‌های درونی پایتون است و همراه با پایتون نصب می‌شود.
