# amazon-sales-analysis

## 1. Data Exploration, Cleaning & Challenges
I started exploring and cleaning the data by checking the basics such as

1. Data type --> All are string

2. Missing value --> 2 missing values in 'rating_count' column

3. Duplicate --> None

As I decided to move on to segment the data for further analysis, I ran into multiple code error messages, which I revisit this step to trouble shoot them with the help of AI for efficiency.

1. **Anomalous Data:** Identified only a corrupted string ('|) in 'rating' column. Remove this row of data.

2. **Numeric Conversion:** Stripped currency symbols ('₹`), percent symbols ('%'), commas (',') and period ('.') for 'actual_price', 'discounted_price', 'rating_count', 'discount_percentage' and 'rating'. Converted them to float.

## 2. Segment the products by 'discounted_price' into **Budget, Mid-Range and Premium** tiers to answer:
> *"Which price segment yields the highest customer satisfaction vs. quality consistency?"*

### 3. Visualizing the Distribution
![Price Satisfaction Boxplot](price_satisfaction_boxplot.png)

**Key Observations:**

1. **Median Parity:** All segments share a median rating of ~4.1, suggesting a balanced value-to-price ratio across platform.

2. **Premium Consistency:** The Premium segment shows the least variance (shorter box/whiskers), indicating little risk of getting a significantly low-quality product.

3. **Mid-Range Risk:** While the median is hight, the Mid-Range segment contains more low-rating outliers, representing there's a higher chance of running into a product that performs significantly below average.

### 4. Strategic Recommendations
Based on the pivor table analysis of low-rated categories:

1. **Targeted Quality Audits:** 

Low-rated products in Mid-Range categories such as

- Home&Kitchen|Kitchen&HomeAppliances|SmallKitchenAppliances|Kettles HotWaterDispensers|Kettle&ToasterSets
- Home&Kitchen|Heating,Cooling&AirQuality|RoomHeaters|FanHeaters
- Home&Kitchen|Heating,Cooling&AirQuality|RoomHeaters|ElectricHeaters 

should undergo supplier reviews to reduce the high number of low-rating outliers.

2. **Marketing Optimization:** 

High-performing Mid-Range products such as

- Computers&Accessories|Accessories&Peripherals|Keyboards,Mice&InputDevices|Mice 
- Home&Kitchen|Kitchen&HomeAppliances|SmallKitchenAppliances|EggBoilers
- Electronics|Accessories|MemoryCards|MicroSD

should be promoted as "Value Champions" since they match Premium satisfaction levels at a lower price point.
