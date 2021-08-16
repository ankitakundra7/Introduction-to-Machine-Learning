## **Visual story telling part 1: Green Buildings**

### **Problem:**

An Austin real-estate developer is interested in the possible economic
impact of “going green” in her latest project: a new 15-story mixed-use
building on East Cesar Chavez, just across I-35 from downtown. Will
investing in a green building be worth it, from an economic perspective?
The baseline construction costs are $100 million, with a 5% expected
premium for green certification.

The developer has had someone on her staff, who’s been described to her
as a “total Excel guru from his undergrad statistics course,” run some
numbers on this data set and make a preliminary recommendation. Here’s
how this person described his process:

> I began by cleaning the data a little bit. In particular, I noticed
> that a handful of the buildings in the data set had very low occupancy
> rates (less than 10% of available space occupied). I decided to remove
> these buildings from consideration, on the theory that these buildings
> might have something weird going on with them, and could potentially
> distort the analysis. Once I scrubbed these low-occupancy buildings
> from the data set, I looked at the green buildings and non-green
> buildings separately. The median market rent in the non-green
> buildings was $25 per square foot per year, while the median market
> rent in the green buildings was $27.60 per square foot per year: about
> $2.60 more per square foot. (I used the median rather than the mean,
> because there were still some outliers in the data, and the median is
> a lot more robust to outliers.) Because our building would be 250,000
> square feet, this would translate into an additional $250000 x 2.6 =
> $650000 of extra revenue per year if we build the green building.

> Our expected baseline construction costs are $100 million, with a 5%
> expected premium for green certification. Thus we should expect to
> spend an extra $5 million on the green building. Based on the extra
> revenue we would make, we would recuperate these costs in
> $5000000/650000 = 7.7 years. Even if our occupancy rate were only 90%,
> we would still recuperate the costs in a little over 8 years. Thus
> from year 9 onwards, we would be making an extra $650,000 per year in
> profit. Since the building will be earning rents for 30 years or more,
> it seems like a good financial move to build the green building. Goal:
> The developer listened to this recommendation, understood the
> analysis, and still felt unconvinced. She has therefore asked you to
> revisit the report, so that she can get a second opinion.

### **Solution:**

As we can see, the person described as “total Excel guru from his
undergraduate course” has considered the rent of the building to be
entirely dependent on whether it is a Green building or not. But rent
may also be dependent on other factors like age of the building, quality
of the building, size of the building etc. Let’s try to understand the
interaction between these variables with the help of suitable plots:

### **Visualizations**

<img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-4-1.png" width="50%" /><img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-4-2.png" width="50%" /><img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-4-3.png" width="50%" /><img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-4-4.png" width="50%" /><img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-4-5.png" width="50%" /><img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-4-6.png" width="50%" />

**Observations**

-   Rent is correlated with the cluster rent. The correlation seems to
    be similar for both green building and non-green buildings.
-   There is a correlation between rent and height (stories) of the
    building
-   Rent per square foot has a correlation with the size
-   Most of the class A buildings are also younger
-   Age does not have a strong correlation with rent. Also, most of the
    green buildings are younger
-   Class A buildings get higher rent as they are premium buildings

<!-- -->

    ## Warning: `fun.y` is deprecated. Use `fun` instead.

<img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-5-1.png" width="50%" /><img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-5-2.png" width="50%" /><img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-5-3.png" width="50%" /><img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-5-4.png" width="50%" />

**Observations**

-   The green buildings are mostly younger than non-green buildings
-   Class A buildings are higher in proportion in green buildings than B
    or C buildings
-   The distribution of size for both green and non-green buildings is
    skewed to the right.
-   The is a significant difference in the of rent for green and
    non-green building in case of class A buildings

<img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-6-1.png" width="50%" /><img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-6-2.png" width="50%" /><img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-6-3.png" width="50%" /><img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-6-4.png" width="50%" /><img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-6-5.png" width="50%" /><img src="exam_stats_2_files/figure-markdown_strict/unnamed-chunk-6-6.png" width="50%" />

**Observations**

-   There are no green building older than 116 years. Between average
    ages of 15 and 90 years, median rent for green building is more than
    non-green building. Otherwise, median rent for non-green building is
    more.
-   For a size of 250,000 sqft, the green buildings have a higher rent
    when it is a class A building
-   The rent of green buildings is lower than non-green ones when they
    are not class a buildings
-   The rent difference is not uniform across different sizes and ages

### **Insights and Recommendations**

Hence, we can conclude from the above analysis that “Excel Guru” has
given a flawed logic behind recommending a go ahead to the project. He
fails to account for all the other factors that affect the rent besides
whether it is a green building or not. We have seen that the quality of
the house and its size play an important part in determining its rent.

**Calculations**

-   The rent difference is not uniform across different sizes and age,
    so we cannot assume that the differnce in rent for a green building
    and a non-green building will be a fixed number.
-   The building to be constructed would be 250,000 square feet. Hence,
    we consider the buildings that have sizes between 200k and 300k
    sq.ft in our dataset only.
-   Instead of assuming the occupany to be 90% as done by “Excel Guru”,
    we used the median leasing rate of such buildings
-   The data provided does not have information about class A buildings
    with sizes ranging from 200k sq.ft to 300k sq.ft. So let’s use
    average 5 year return to arrive at final recommendations

**Final recommendation**

-   If the building to be constructed is not a Class-A building, it is
    not wise to invest in a green building since the average returns for
    5 years are negative
-   The builder should invest in a Class-A green building to yield
    positive returns
-   We can expect a occupancy rate of 91.6% on such buildings
-   The average difference in rent for green and non-green buildings
    that are class A and whose sizes ranging from 200k to 300k is 3.097
-   Hence, for a 250k sq.ft building at 91.6% occupancy, we expect to
    recuperate the costs in 7.05 years, given the premium on green
    building is 5% of 100 million uSD

## **Visual story telling part 2: Flights at ABIA**

### **Problem**

Consider the data in ABIA.csv, which contains information on every
commercial flight in 2008 that either departed from or landed at
Austin-Bergstrom Interational Airport. Your task is to create a figure,
or set of related figures, that tell an interesting story about flights
into and out of Austin. Provide a clear annotation/caption for each
figure, but the figure should be more or less stand-alone, in that you
shouldn’t need many, many paragraphs to convey its meaning. Rather, the
figure together with a concise caption should speak for itself as far as
possible.

### **Solution:**

    ## 
    ## ── Column specification ────────────────────────────────────────────────────────
    ## cols(
    ##   .default = col_double(),
    ##   UniqueCarrier = col_character(),
    ##   TailNum = col_character(),
    ##   Origin = col_character(),
    ##   Dest = col_character(),
    ##   CancellationCode = col_character()
    ## )
    ## ℹ Use `spec()` for the full column specifications.

**Flights Departed from/Landed at Austin in 2008 by Carrier**

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-10-1.png) We
can see Southwest(WN) is the largest carrier in Austin, followed by AA.
As expected, equal number of flights are arriving to and departing from
Austin

**Flights Arriving to Austin**

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-11-1.png)

These are the top 10 origins with flights landing at Austin. DAL and DFW
(Dallas) have majority of flights to Austin

**Flights Departing from Austin**

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-12-1.png)

Most of the flights starting from Austin are directed towards the above
mentioned top 10 destinations. Again majority of the flights are for
Dallas

Now lets see the frequency of the flights from these top 10 locations to
Austin

**Distribution of Flights for top-10 Origin Cities Across the Year**

    ## Warning in RColorBrewer::brewer.pal(n, pal): n too large, allowed maximum for palette Dark2 is 8
    ## Returning the palette you asked for with that many colors

    ## Warning: Removed 24 row(s) containing missing values (geom_path).

    ## Warning: Removed 24 rows containing missing values (geom_point).

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-13-1.png)

The flights originating from Dallas are reducing after June. The flights
from other regions show no such drastic decline

**Distribution of Flights for top-10 Destination Cities Across the
Year**

    ## Warning in RColorBrewer::brewer.pal(n, pal): n too large, allowed maximum for palette Dark2 is 8
    ## Returning the palette you asked for with that many colors

    ## Warning: Removed 24 row(s) containing missing values (geom_path).

    ## Warning: Removed 24 rows containing missing values (geom_point).

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-14-1.png)
Similar drop in Austin to Dallas flights can be seen from June.

We try to evaluate the reason for the sudden drop in flights departing
from or arriving at Dallas from June

**Flights Originating from or Arriving at Dallas by Carrier**

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-15-1.png) MQ
carrier stopped its service after June and that explains the drop in the
Dallas flights

Now, checking frequency of short and long distance flights

**Arrival/Departure by Day of the Week**
![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-16-1.png)

Thus, Saturdays and Sundays seem to have lesser number of flights
arriving to or departing from Austin

**Long Distance/Short Distance Flights**
![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-17-1.png)

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-18-1.png)

Now, let’s find out the month with the highest fraction of delays:

**Month with highest Delays**

    ##      rn Delayed Undelayed  fraction
    ##  1: Jan    1562      7026 0.1818817
    ##  2: Feb    1613      6372 0.2020038
    ##  3: Mar    2039      6660 0.2343948
    ##  4: Apr    1363      6910 0.1647528
    ##  5: May    1620      7286 0.1818998
    ##  6: Jun    1836      7143 0.2044771
    ##  7: Jul    1562      7279 0.1766768
    ##  8: Aug    1516      6942 0.1792386
    ##  9: Sep     741      6569 0.1013680
    ## 10: Oct     802      6844 0.1048914
    ## 11: Nov     800      6198 0.1143184
    ## 12: Dec    1791      5373 0.2500000

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-19-1.png)

December has the maximum delays with 25% of the flights in December
getting delayed

The best month to travel to minimize delays are the months of September,
October and November.

The worst month to travel is March and December which makes sense
because December includes travel for the holidays and March includes
travel for Spring Break. These time periods typically see an influx of
travellers, which could be a factor contributing to an increase in
fraction of flight delays.

Let’s see the pattern of delay in a week

**Day of the Week with highest Delays**

    ##     rn Delayed Undelayed  fraction
    ## 1: Mon    2587     12029 0.1769978
    ## 2: Tue    2371     12143 0.1633595
    ## 3: Wed    2246     12372 0.1536462
    ## 4: Thu    2751     11806 0.1889812
    ## 5: Fri    3041     11530 0.2087022
    ## 6: Sat    1733      9571 0.1533086
    ## 7: Sun    2516     11151 0.1840931

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-20-1.png)

We can see that 21% of the flights gets delayed on a Friday  
Wednesdays and Saturdays are the best days to travel since they seem to
be having minimum delays.

Let’s find out the busiest time of the day

**Time Period with highest Delays**

    ##         rn Delayed Undelayed   fraction
    ## 1: 1pm-5pm    5199     20294 0.20393834
    ## 2: 5am-9am    1459     21918 0.06241177
    ## 3: 5pm-9pm    6205     16820 0.26948969
    ## 4: 9am-1pm    3513     19720 0.15120733
    ## 5: 9pm-1am     869      1850 0.31960280

    ## 
    ## Attaching package: 'scales'

    ## The following object is masked from 'package:mosaic':
    ## 
    ##     rescale

    ## The following object is masked from 'package:purrr':
    ## 
    ##     discard

    ## The following object is masked from 'package:readr':
    ## 
    ##     col_factor

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-21-1.png)

We see that 32% of flights get delayed if they are departing from Austin
between 9pm and 1am.

The best time to travel is between 5am and 9am with around 6% of delays.

Now, let’s evaluate the reasons for delay of the flights originating
from Austin - to top 10 airports\*\*

**Flights with Carrier Delay as the Contributing Factor**

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-22-1.png)

**Flights with Weather Delay as the Contributing Factor**

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-23-1.png)

## **Portfolio Modeling**

### **Problem:**

Suppose you have $100,000 in capital. Your task is to:

> Construct three different possibilities for an ETF-based portfolio,
> each involving an allocation of your $100,000 in capital to somewhere
> between 3 and 10 different ETFs. You can find a big database of ETFs
> here. Download the last five years of daily data on your chosen ETFs,
> using the functions in the quantmod package, as we used in class.
> Note: make sure to choose ETFs for which at least five years of data
> are available. There are tons of ETFs and some are quite new! Use
> bootstrap resampling to estimate the 4-week (20 trading day) value at
> risk of each of your three portfolios at the 5% level. Write a report
> summarizing your portfolios and your VaR findings.

You should assume that your portfolios are rebalanced each day at zero
transaction cost. For example, if you’re allocating your wealth evenly
among 5 ETFs, you always redistribute your wealth at the end of each day
so that the equal five-way split is retained, regardless of that day’s
appreciation/depreciation.

### **Solution:**

The ETFs have been selected ensuring differential levels of risks posed
by them.

1.  SPY is one of the safest and largest ETFs around. It is a proxy for
    S&P 500

2.  Invesco DB Oil Fund (DBO) has been selected since it diversifies our
    portfolio by tracking index of crude oil future contracts. This fund
    is particularly prone to geo-political risks. It is able to
    dynamically approach the roll yield problem in a way which greatly
    benefits holders.

3.  XHB ETF is an investment that corresponds to the total return
    performance of an index derived from the homebuilding segment of a
    U.S. total market composite index. It helps to diversify our
    portfolio by tracking US homebuilders. It is a medium risk
    investment.

4.  XLE ETF is an investment in energy sector. It is a low risk fund.
    Thus, investment in this stock helps to increase liquidity of our
    portfolio.

5.  CPER: United States Copper Index Fund tracks Copper Prices. Copper
    can be a very solid investment, but it also has the potential to be
    more volatile than other precious metals.

In total, we have selected 5 ETFs - SPY“,”DBO“,”XHB“,”XLE“,”CPER". We
have considered 5 years of ETF data starting from 01-Jan-2016 to
01-Jan-2021.

    ## 'getSymbols' currently uses auto.assign=TRUE by default, but will
    ## use auto.assign=FALSE in 0.5-0. You will still be able to use
    ## 'loadSymbols' to automatically load data. getOption("getSymbols.env")
    ## and getOption("getSymbols.auto.assign") will still be checked for
    ## alternate defaults.
    ## 
    ## This message is shown once per session and may be disabled by setting 
    ## options("getSymbols.warning4.0"=FALSE). See ?getSymbols for details.

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query1.finance.yahoo.com/v7/finance/download/SPY?
    ## period1=-2208988800&period2=1629072000&interval=1d&events=split&crumb=jSmRgSfIeUq'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query1.finance.yahoo.com/v7/finance/download/SPY?
    ## period1=-2208988800&period2=1629072000&interval=1d&events=split&crumb=jSmRgSfIeUq'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query2.finance.yahoo.com/v7/finance/download/DBO?
    ## period1=-2208988800&period2=1629072000&interval=1d&events=div&crumb=jSmRgSfIeUq'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query2.finance.yahoo.com/v7/finance/download/DBO?
    ## period1=-2208988800&period2=1629072000&interval=1d&events=split&crumb=jSmRgSfIeUq'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query1.finance.yahoo.com/v7/finance/download/DBO?
    ## period1=-2208988800&period2=1629072000&interval=1d&events=split&crumb=jSmRgSfIeUq'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query2.finance.yahoo.com/v7/finance/download/XHB?
    ## period1=-2208988800&period2=1629072000&interval=1d&events=split&crumb=jSmRgSfIeUq'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query2.finance.yahoo.com/v7/finance/download/XHB?
    ## period1=-2208988800&period2=1629072000&interval=1d&events=split&crumb=jSmRgSfIeUq'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query1.finance.yahoo.com/v7/finance/download/XLE?
    ## period1=-2208988800&period2=1629072000&interval=1d&events=split&crumb=jSmRgSfIeUq'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query2.finance.yahoo.com/v7/finance/download/XLE?
    ## period1=-2208988800&period2=1629072000&interval=1d&events=split&crumb=jSmRgSfIeUq'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query2.finance.yahoo.com/v7/finance/download/CPER?
    ## period1=-2208988800&period2=1629072000&interval=1d&events=div&crumb=jSmRgSfIeUq'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query1.finance.yahoo.com/v7/finance/download/CPER?
    ## period1=-2208988800&period2=1629072000&interval=1d&events=split&crumb=jSmRgSfIeUq'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query1.finance.yahoo.com/v7/finance/download/CPER?
    ## period1=-2208988800&period2=1629072000&interval=1d&events=split&crumb=jSmRgSfIeUq'

**Sample Data for SPY using quantmode library**

    ##            DBO.Open DBO.High  DBO.Low DBO.Close DBO.Volume DBO.Adjusted
    ## 2015-01-02 14.90152 15.17263 14.66914  14.79501     329600     14.79501
    ## 2015-01-05 14.36898 14.38834 13.96231  13.97199     848000     13.97199
    ## 2015-01-06 13.77834 13.86548 13.31357  13.38135     901400     13.38135
    ## 2015-01-07 13.52659 13.82675 13.36199  13.60405     713900     13.60405
    ## 2015-01-08 13.54596 13.89453 13.36199  13.74929     978400     13.74929
    ## 2015-01-09 13.64278 13.74929 13.21675  13.55564     742900     13.55564

    ##               ClCl.SPYa   ClCl.DBOa    ClCl.XHBa    ClCl.XLEa   ClCl.CPERa
    ## 2015-01-05 -0.018059641 -0.05562827 -0.010647737 -0.041368050  0.000000000
    ## 2015-01-06 -0.009418967 -0.04227304 -0.008669686 -0.014690386 -0.014721346
    ## 2015-01-07  0.012461170  0.01664255  0.027442702  0.002129872  0.000000000
    ## 2015-01-08  0.017745025  0.01067616  0.024068066  0.022449549 -0.003201708
    ## 2015-01-09 -0.008013570 -0.01408451  0.001146489 -0.007925166 -0.003747270
    ## 2015-01-12 -0.007833567 -0.05214286  0.004294360 -0.028810856  0.000000000

Now, let’s see the relationships between these stocks:

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-27-1.png)

As we can see from the above pair-plot, CEPR does not have a correlation
with any of the other stocks. There seems to be a high correlation
between all the other stocks but it is not perfectly linear.

Now, let us look at the volatility of ETFs over these 5 years period.

**Volatility of the 5 ETFs over the past 5 years**

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-28-1.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-28-2.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-28-3.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-28-4.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-28-5.png)

We see that CPER has the minimum volatility but it also gives lesser
returns. We also observe that ups and dows of the stocks do not
necessarily coincide.

Now, let us evalute different possibilities of the ETF based portfolio:

**Simulation 1: Equal Weihted Portfolio of ETFs: **

We begin our simulation by taking equal weights of all the 5 ETFs

    ##              [,1]     [,2]     [,3]     [,4]     [,5]     [,6]     [,7]
    ## result.1 125050.1 125123.2 124266.3 124850.6 126615.3 126790.4 124750.6
    ## result.2 123425.4 125659.1 124433.3 123939.3 121843.3 122700.6 122620.6
    ## result.3 126065.6 125057.3 125110.4 124885.5 125210.7 126099.6 125004.1
    ## result.4 124833.5 125168.9 124543.5 129958.4 130436.0 130481.5 129565.6
    ## result.5 125643.6 126010.8 126276.0 127252.4 127334.0 128176.1 130858.0
    ## result.6 125850.3 126136.1 128079.5 127245.9 128202.4 126326.0 126483.7
    ##              [,8]     [,9]    [,10]    [,11]    [,12]    [,13]    [,14]
    ## result.1 124585.3 123576.9 123863.6 124749.4 125712.7 126525.0 126797.2
    ## result.2 122472.8 123435.6 123465.6 124992.0 125105.6 125006.1 124750.5
    ## result.3 125093.2 128085.9 128194.9 126772.8 127831.7 128802.3 125374.0
    ## result.4 128695.2 129042.6 129905.3 129111.0 130671.1 130285.1 130464.1
    ## result.5 130649.7 130568.7 131019.5 131576.9 130476.6 129827.8 129826.8
    ## result.6 126773.6 124002.4 125000.6 124220.3 125176.9 125113.5 125752.9
    ##             [,15]    [,16]    [,17]    [,18]    [,19]    [,20]
    ## result.1 128165.1 127644.3 127120.2 128359.8 128014.5 130523.4
    ## result.2 124262.6 124268.3 124013.1 121444.1 121081.5 121251.4
    ## result.3 125208.1 125363.6 125649.1 124496.2 125082.8 126222.8
    ## result.4 133035.3 131692.4 130537.0 130601.5 130822.1 133019.0
    ## result.5 130291.3 127717.2 128122.6 128962.2 129206.5 128399.8
    ## result.6 123269.3 124305.1 121271.8 121241.6 119253.7 117493.4

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-30-1.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-30-2.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-30-3.png)

    ## Confidence Interval from Bootstrap Distribution (5000 replicates)

    ## 
    ## Average return of investement after 20 days 125500.2

    ## 
    ## 5% Value at Risk for equal weighted portfolio- 16452.39

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-32-1.png)

    ## [1] 25500.24

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-33-1.png)

    ##       5% 
    ## 16452.39

**Simulation 2: Safe Portfolio of ETFs: **

Now we take more weightage(60%) of the safe portfolio i.e CEPR and 10%
each of the other 4 portfolios

    ##               [,1]      [,2]      [,3]      [,4]      [,5]      [,6]      [,7]
    ## result.1  99498.80  98403.59  97979.12  97056.22  97388.60  98193.00  98496.64
    ## result.2 100803.65 100014.37  98117.25  97618.00  99533.28 102938.29 102381.90
    ## result.3  99507.19 100603.20 100148.06 100196.73  98354.95  97711.31  97970.83
    ## result.4 101959.54  99877.70  99306.90  97649.59  97840.19  95935.36  96357.17
    ## result.5 100951.11 101123.94 100366.76 101266.92 102549.05 103032.74 102306.37
    ## result.6  99351.29 100157.25 100722.93 101370.92 101386.56 101340.08  99684.12
    ##               [,8]      [,9]     [,10]     [,11]     [,12]     [,13]     [,14]
    ## result.1  98041.21  98374.54  97984.88  98585.81  98492.40  98389.06  97613.96
    ## result.2 104283.95 103255.10 103085.81 103726.98 103561.15 104105.47 102849.78
    ## result.3  98016.57  96814.17  97247.46  99136.52  99066.50 101551.75 101087.23
    ## result.4  95917.43  95122.14  94576.50  94835.93  95189.18  96055.80  96047.04
    ## result.5 101860.11 101475.39 101115.55 101734.93 101868.28 101923.12 100788.26
    ## result.6  99468.39  98473.55  98610.40 100978.75 100390.29 100672.37 100592.98
    ##              [,15]     [,16]     [,17]     [,18]     [,19]     [,20]
    ## result.1  98221.43  97916.25  98704.90  98775.05  98916.70  98443.36
    ## result.2 104012.62 103541.94 103414.76 102939.19 103164.04 104559.91
    ## result.3 101681.29 100633.72 100760.42 100336.21 100507.13 100327.08
    ## result.4  96579.33  97110.26  97189.35  95784.83  95982.26  96635.58
    ## result.5 101192.79 102373.46 102147.77 103443.88  99839.85 100319.53
    ## result.6 100324.45 100067.63 100331.36 102830.71 102395.82 101361.73

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-35-1.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-35-2.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-35-3.png)

    ## Confidence Interval from Bootstrap Distribution (5000 replicates)

    ## 
    ## Average return of investement after 20 days 100460.5

    ## 
    ## 5% Value at Risk for safe portfolio- -7710.431

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-37-1.png)

**Simulation 3: High Risk Portfolio of ETFs**

Now, we take only 4% of the safe portfolio i.e CEPR and 24% each of the
other 4 portfolios

    ##               [,1]      [,2]      [,3]      [,4]      [,5]      [,6]      [,7]
    ## result.1  99129.36  99387.61  99163.03  99998.23  99231.40  99468.24 100042.88
    ## result.2  98811.33  98708.56  98290.61  97030.54  95816.63  96090.46  95863.57
    ## result.3 100505.12 100235.26 100441.77 100767.42 101233.19 100087.84 100258.04
    ## result.4 100601.89 101274.73 101549.86 100378.01  98417.56  98145.66  97317.13
    ## result.5  99646.09  99166.15  99298.01  99546.36  97901.83 100191.34  98757.69
    ## result.6  99563.25 100396.14  99002.74 101141.55 101202.66 101474.33 102807.55
    ##               [,8]      [,9]     [,10]     [,11]     [,12]     [,13]     [,14]
    ## result.1  99809.55  99759.52  99965.90  99723.36  97606.25  97361.37  95619.53
    ## result.2  95955.14  94679.09  96277.92  96247.71  96048.01  96447.38  95773.31
    ## result.3 100305.15 101157.17  99739.02  99497.83  98239.76  99255.67  99763.37
    ## result.4  97738.78  97606.54  97969.69 100372.27  98907.36 100009.17  99567.01
    ## result.5  98505.72  98197.75  98661.54  98292.08  98755.86  99411.91 100024.90
    ## result.6 104125.31 105335.13 105023.82 105752.26 105899.24 106245.65 105950.63
    ##              [,15]     [,16]     [,17]     [,18]     [,19]     [,20]
    ## result.1  95071.50  94792.66  94739.36  94069.80  95124.17  93234.63
    ## result.2  96069.84  96491.58  96513.55  96409.78  97300.03  97454.74
    ## result.3  99734.75 100426.49  99778.72  99818.67 101122.81 101789.17
    ## result.4  99183.57  99965.41  98506.07  97875.51  97810.67  97547.66
    ## result.5 101819.73 102234.85 104351.99 105433.82 105408.83 107097.07
    ## result.6 106110.70 107632.54 107405.15 108362.21 109116.67 109913.29

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-39-1.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-39-2.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-39-3.png)

    ## Confidence Interval from Bootstrap Distribution (5000 replicates)

    ## 
    ## Average return of investement after 20 days 100438.3

    ## 
    ## 5% Value at Risk for high risk portfolio- -7068.364

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-41-1.png)

For the equal weighted portfolio, we are observing the maximum return of
investment but it also has the highest 5% VaR. The safe portfolio gives
us moderate returns but low 5% VaR.

## **Market Segmentation**

### **Problem: **

The data collected in the course of a market-research study using
followers of the Twitter account of a large consumer brand that shall
remain nameless—let’s call it “NutrientH20” just to have a label. The
goal here was for NutrientH20 to understand its social-media audience a
little bit better, so that it could hone its messaging a little more
sharply. Each row of the data represents one user, labeled by a random
(anonymous, unique) 9-digit alphanumeric code. Each column represents an
interest, which are labeled along the top of the data file. The entries
are the number of posts by a given user that fell into the given
category.

> The task is to analyze this data as you see fit, and to prepare a
> concise report for NutrientH20 that identifies any interesting market
> segments that appear to stand out in their social-media audience.

### **Solution: **

    ## Warning: Missing column names filled in: 'X1' [1]

    ## 
    ## ── Column specification ────────────────────────────────────────────────────────
    ## cols(
    ##   .default = col_double(),
    ##   X1 = col_character()
    ## )
    ## ℹ Use `spec()` for the full column specifications.

The aim of this exercise is to assist NutrientH2O identify strategic
market segmentations that emerge based on their social media audience on
Twitter. Hence, we can perform text-based analysis which can help
NutrientH2O to identify consumers that can be segmented and targeted
directly and efficiently. This report will show the process of
uncovering insights from the market-research data, as well as provide
interesting and well-supported conclusions about the audience for
NutrientH2O.

**Data Cleaning:** Before applying any clustering algrorithm on our
data, we need to explore and clean our data so as to completely
understand the business problem. While exploring the data, we found
categories like: “Spam”, “Chatter”, “Un-Categorized”, “Adult”. No
business value can be derived from these variables and hence, they have
been dropped from the dataset before proceeding with the further
analysis of the dataset.

**Data Exploration: **

We created a correlation matrix to have an intial identification of
potential market segmentation. Correlation matrices help us in getting
the extent of linear relationship between variables, in turn helping us
to better understand the dataset.

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-45-1.png)

Let us try to interpret the results of correlation matrix. We can see
strong correlation between some variables. “Personal Fitness” and
“Health Nutrition” seem to be highly correlated, which makes business
sense. Other examples include: ‘News and Politics’, ‘Shopping and Photo
Sharing, ’Parents, Religion, and Sports Fandom’. We can thus cluster
these correlated variables together.

**Data Analysis: **

**K-Means Clustering: **

We begin our analysis with K Means Clustering. The data is standardized
before performing Kmeans. This is because K-Means makes use of Euclidian
Distance and without standardization, impact of some variables may be
more emphasized than others.

We begin our analysis by identifying the number of clusters from the
Scree Plot. The Scree Plot helps us to visualize the ideal number of
clusters based on the point where the slope of the line begins to level
off, also known as the elbow point.

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-48-1.png)

As we can see from the above scree plot, the leveling off phenomena
seems to be natural once the number of clusters reaches 11. Therefore,
we made a decision to choose 11 as our k-value for further analysis.
Hence, we have a general awareness of the number of market segmentations
to look for as we dive deeper into the text data.

**Visualzing Clusters Identified by K-Means:**

Now we fit the model with k = 11 clusters and run the model

Now that the k-means algorithm has generated a proposed number of
clusters to be 11, we wanted to visualize this concept to see where
specifically these clusters can be identified in the dataset. These 11
clusters are:

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-50-1.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-50-2.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-50-3.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-50-4.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-50-5.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-50-6.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-50-7.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-50-8.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-50-9.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-50-10.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-50-11.png)

Based on the charts given above, here are the segments identified using
K-Means:

1.  Dating, School, Fashion, Photosharing -
2.  Food, Religion, Parenting, Sports Fandom
3.  Politics, Travel, News, Computers
4.  Photo Sharing, Shopping, Current Events
5.  Photo Sharing, Travel, Health & Nutrition
6.  Cooking, Photo Sharing, Beauty, Fashion
7.  TV & Film, Art
8.  Online Gaming, College/University, Sports Playing
9.  TV & Film, College/University, Music
10. Health & Nutrition, Personal Fitness, Cooking, Outdoors
11. News, Automotive, Politics

**Principal Component Analysis: **

When faced with a large set of correlated variables, principal
components allow us to summarize this set with a smaller number of
representative variables that collectively explain most of the
variability in the original set. We now try reducing the variable
dimensionality using PCA, identify the important Principal components
and then run Hierarchical clustering on these components

    ## Importance of components:
    ##                           PC1     PC2     PC3     PC4     PC5     PC6     PC7
    ## Standard deviation     2.0987 1.66483 1.59119 1.52912 1.46728 1.28477 1.21616
    ## Proportion of Variance 0.1376 0.08661 0.07912 0.07307 0.06728 0.05158 0.04622
    ## Cumulative Proportion  0.1376 0.22426 0.30338 0.37645 0.44372 0.49531 0.54153
    ##                            PC8     PC9    PC10    PC11    PC12    PC13    PC14
    ## Standard deviation     1.17377 1.05325 0.99329 0.96596 0.96133 0.93945 0.92125
    ## Proportion of Variance 0.04305 0.03467 0.03083 0.02916 0.02888 0.02758 0.02652
    ## Cumulative Proportion  0.58458 0.61925 0.65008 0.67924 0.70812 0.73570 0.76222
    ##                           PC15    PC16    PC17    PC18    PC19    PC20    PC21
    ## Standard deviation     0.90796 0.84582 0.80888 0.75382 0.69548 0.68732 0.65389
    ## Proportion of Variance 0.02576 0.02236 0.02045 0.01776 0.01512 0.01476 0.01336
    ## Cumulative Proportion  0.78798 0.81034 0.83079 0.84854 0.86366 0.87842 0.89178
    ##                           PC22    PC23    PC24    PC25    PC26    PC27    PC28
    ## Standard deviation     0.64963 0.63916 0.63190 0.61729 0.59925 0.59437 0.55190
    ## Proportion of Variance 0.01319 0.01277 0.01248 0.01191 0.01122 0.01104 0.00952
    ## Cumulative Proportion  0.90497 0.91774 0.93022 0.94212 0.95335 0.96439 0.97390
    ##                           PC29    PC30    PC31    PC32
    ## Standard deviation     0.48581 0.47790 0.43861 0.42223
    ## Proportion of Variance 0.00738 0.00714 0.00601 0.00557
    ## Cumulative Proportion  0.98128 0.98842 0.99443 1.00000

The variance explained by each principal component and the cumulative
variance explained can be seen in the graph below

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-52-1.png)

As we can see, first few components are not sufficient to explain the
variability in the data. 80% of the variability of our data can be
explained with 16 principal components

**Hierarchical Clustering:**

To provide more clarity and confirm the result of 11 potential market
segmentations from the k-means method, we performed a Hierarchical
Clustering algorithm to compare and determine what similarities would
emerge. We use 16 principal components from PCA to perform heirarchical
clustering. Since it is a market segment problem, we use correlation
based distance and we try to experiment with three linkage methods :
Single, Complete and Average

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-53-1.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-53-2.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-53-3.png)

We decide to go with Average linkage method(or group method) clustering
as it provides a trade off between the senstivity of complete linkage
clustering to outliers and the tendency of single linkage clustering to
form long chains that do not correspond to the intuitive notion of the
clusters as compact, spherical objects

Looking at the tree, we can cut the tree at the height of 0.9 and then
identify the clusters and no of entries in each cluster

    ## hc_clust_avg
    ##    1    2    3    4    5    6    7    8    9   10   11   12 
    ##  987  993  364 2114  430  526  734  260   63  537  354  520

Now we want to visualize the segments identified by hierarchical
clustering

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-55-1.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-55-2.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-55-3.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-55-4.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-55-5.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-55-6.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-55-7.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-55-8.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-55-9.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-55-10.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-55-11.png)

Based on the charts given above, here are the segments identified using
Hierarchical Clustering:

1.  Health & Nutrition, Personal Fitness, Cooking, Outdoors
2.  Food, Religion, Parenting, Sports Fandom
3.  TV & Film, Art
4.  Photo Sharing, Shopping, Current Events, Travel
5.  Politics, Travel, News, Computers
6.  Cooking, Photo Sharing, Beauty, Fashion
7.  Dating, School, Fashion, Photo Sharing
8.  Home & Garden, Health Nutrition, College/University
9.  Online Gaming, College/University, Sports Playing
10. TV & Film, College/University, Music
11. News, Automotive, Politics, Sports Fandom

**Observations:**

The comprehensive approach described above was the analysis that went
into uncovering insights that could be beneficial for NutrientH2O for
the purposes of providing meaningful market segmentation. We used a
cluster approach to define various market segments from the social media
data presented.

The market segmentation can help NutrientH2O in customized advertising.
Based on the K-Means and Hierarchical Clustering algorithms, we come
with following 9 broad Market Segments:

1.  Dating, School, Fashion, Photo Sharing
2.  Food, Religion, Parenting, Sports Fandom
3.  Politics, Travel, News, Computers
4.  Photo Sharing, Shopping, Current Events, Travel
5.  Cooking, Photo Sharing, Beauty, Fashion
6.  Online Gaming, College/University, Sports Playing
7.  TV & Film, College/University, Music
8.  Health & Nutrition, Personal Fitness, Cooking, Outdoors
9.  News, Automotive, Politics, Sports Fandom

**Recommendations:**

As stated above, NutrientH2O can design customized marketing campaigns
for these 9 distinct segment of population. The likes and dislikes of
each group may be different and targeted marketing will help us to
target the customers the right way.

Case in point: The demographic information for segment \#5 - ‘Cooking,
Photo Sharing, Beauty, Fashion’ is likely to be different than the
demographic makeup of segment \#6 - ‘Online Gaming, College/University,
Sports Playing’. Going with the gender stereotypes, one segment is
likely to have more composition of females while other segment is likely
to have more composition of males. This is certainly a sexist assumption
but might fairly work for the purpose of targeting campaigning. Hence,
NutrientH2O can use this market segmentation knowledge to their
advantage by designing two separate marketing campaigns to address
members of each segment \#5 and \#6 to convey the most compelling
message.

## **Author Attribution**

### **Problem: **

Revisit the Reuters C50 corpus that we explored in class. Your task is
to build the best model you can, using any combination of tools you see
fit, for predicting the author of an article on the basis of that
article’s textual content. Describe clearly what models you are using,
how you constructed features, and so forth. Yes, this is a supervised
learning task, but it potentially draws on a lot of what you know about
unsupervised learning, since constructing features for a document might
involve dimensionality reduction.

### **Solution: **

    ## Warning in tm_map.SimpleCorpus(., content_transformer(tolower)): transformation
    ## drops documents

    ## Warning in tm_map.SimpleCorpus(., content_transformer(removeNumbers)):
    ## transformation drops documents

    ## Warning in tm_map.SimpleCorpus(., content_transformer(removePunctuation)):
    ## transformation drops documents

    ## Warning in tm_map.SimpleCorpus(., content_transformer(stripWhitespace)):
    ## transformation drops documents

    ## Warning in tm_map.SimpleCorpus(my_documents_train,
    ## content_transformer(removeWords), : transformation drops documents

    ## <<DocumentTermMatrix (documents: 2500, terms: 32570)>>
    ## Non-/sparse entries: 537861/80887139
    ## Sparsity           : 99%
    ## Maximal term length: 52
    ## Weighting          : term frequency (tf)

    ## <<DocumentTermMatrix (documents: 2500, terms: 3393)>>
    ## Non-/sparse entries: 422971/8059529
    ## Sparsity           : 95%
    ## Maximal term length: 52
    ## Weighting          : term frequency (tf)

    ## Warning in tm_map.SimpleCorpus(., content_transformer(tolower)): transformation
    ## drops documents

    ## Warning in tm_map.SimpleCorpus(., content_transformer(removeNumbers)):
    ## transformation drops documents

    ## Warning in tm_map.SimpleCorpus(., content_transformer(removePunctuation)):
    ## transformation drops documents

    ## Warning in tm_map.SimpleCorpus(., content_transformer(stripWhitespace)):
    ## transformation drops documents

    ## Warning in tm_map.SimpleCorpus(my_documents_test,
    ## content_transformer(removeWords), : transformation drops documents

    ## <<DocumentTermMatrix (documents: 2500, terms: 33373)>>
    ## Non-/sparse entries: 545286/82887214
    ## Sparsity           : 99%
    ## Maximal term length: 51
    ## Weighting          : term frequency (tf)

    ## <<DocumentTermMatrix (documents: 2500, terms: 3448)>>
    ## Non-/sparse entries: 428509/8191491
    ## Sparsity           : 95%
    ## Maximal term length: 51
    ## Weighting          : term frequency (tf)

We begin the exercise by reading all the 50 documents in both the
training folder and the test folder. Each document is then broken into
token of words removing puncuations, stop words, white spaces and all
the words are then converted into lower cases. We get 32570 terms for
the training dataset and 33373 terms for the test dataset. We then
remove those words which have a count of 0 in more than 99% of the
documents. This leaves us with 3393 terms in training dataset and 3448
terms in test dataset.

We then construct TF IDF weights for both train and test dataset which
can be useful if we want to use these as features in predictive modeling

**Principal Component Analysis:**

We use Principal component analysis to: (1) extract relevant features
from the huge set of variables (2) eliminate the effect of
multicollinearity while not losing out on relevant information from the
correlated variables

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   0.000   1.064   1.629   2.315   2.848  19.789

**Intersection of Words in the two Documents:**

    ## [1] 7435000

    ## [1] 7435000

Thus, we see that there is perfect intersection of words between test
and train data for 7435000 elements. We remove other elements for the
prediction putrposes.

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-69-1.png)![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-69-2.png)

**4. Classification techniques to attribute the documents to its
authors**

**(A) Random Forest Technique**

1853 documents have their authors rightly classified; which provides an
accuracy/classification rate of 74.9%\*

**(B) Naive Baye’s**

    ## 
    ## Attaching package: 'caret'

    ## The following object is masked from 'package:mosaic':
    ## 
    ##     dotPlot

    ## The following object is masked from 'package:purrr':
    ## 
    ##     lift

    ## [1] 814

    ## [1] 32.56

814 documents have their authors rightly classified; which provides an
accuracy/classification rate of 32.6%\*

\*B.3.Comparing train and test accuracy\*\*

**(C) K Nearest Neighbors**

    ## 
    ## Attaching package: 'class'

    ## The following object is masked from 'package:igraph':
    ## 
    ##     knn

    ## [1] 816

    ## [1] 32.64

The Classification/accuracy rate obtained from KNN method is 32.6% with
a k-choice of 1. i.e., 816 documents rightly classified\*

**Conclusion**

We used 3 different classification techniques to predict the author for
the documents. We observe: a) Random forest provides the best accuracy
out of the three methods, with an accuracy of 75%. The other two methods
provide much lower accuracies at around 33% b) Other classification
algorithms like Multinomial logistic regression or other tree based
methods can also be applied for this attribution task.

## **Association Rule Mining**

### **Problem:**

Use the data on grocery purchases in groceries.txt and find some
interesting association rules for these shopping baskets. Pick your own
thresholds for lift and confidence; just be clear what these thresholds
are and how you picked them. Do your discovered item sets make sense?
Present your discoveries in an interesting and concise way.

### **Solution:**

We begin the exercise by displaying the structure of the data:

**The structure of the Raw Dataset**

    ## [1] "citrus fruit,semi-finished bread,margarine,ready soups"             
    ## [2] "tropical fruit,yogurt,coffee"                                       
    ## [3] "whole milk"                                                         
    ## [4] "pip fruit,yogurt,cream cheese ,meat spreads"                        
    ## [5] "other vegetables,whole milk,condensed milk,long life bakery product"
    ## [6] "whole milk,butter,yogurt,rice,abrasive cleaner"

We cast the data as a “transactions” class before applying the apriori
algorithm.

The summary of the dataset reveals the following: 1. There are total of
9835 transactions in our dataset 2. Whole milk is present in 2513
baskets and is the most frequently bought item. This is followed by
other vegetables and rolls/buns. 3. Half of the transactions have 3 or
lesser items per basket (given by median) 4. The mean transactions are
~4.5 items

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-82-1.png)

Let’s now explore ‘apriori’ algorithm’ using 3 differet supoort and
confidence levels:

**Apriori’ Algorithm: **

**1) Support &gt; 0.05, confidence &gt; 0.1 and length &lt;= 2**

    ##     lhs                   rhs                support    confidence coverage 
    ## [1] {yogurt}           => {whole milk}       0.05602440 0.4016035  0.1395018
    ## [2] {whole milk}       => {yogurt}           0.05602440 0.2192598  0.2555160
    ## [3] {rolls/buns}       => {whole milk}       0.05663447 0.3079049  0.1839349
    ## [4] {whole milk}       => {rolls/buns}       0.05663447 0.2216474  0.2555160
    ## [5] {other vegetables} => {whole milk}       0.07483477 0.3867578  0.1934926
    ## [6] {whole milk}       => {other vegetables} 0.07483477 0.2928770  0.2555160
    ##     lift     count
    ## [1] 1.571735 551  
    ## [2] 1.571735 551  
    ## [3] 1.205032 557  
    ## [4] 1.205032 557  
    ## [5] 1.513634 736  
    ## [6] 1.513634 736

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-84-1.png)

There are only 6 rules generated because of the high support and low
confidence level. We also notice that most relationships in this item
set include whole milk, yogurt and rolls/buns which is consistent with
the transaction frequency plot we saw earlier. These are some of the
most frequently bought items.

**2) support &gt; 0.02, confidence &gt; 0.2 and length &lt;= 2**\*

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-86-1.png)

This item set contains 72 rules and includes a lot more items. However,
whole milk still seems to be a common occurence.

**Support &gt; 0.0015, confidence &gt; 0.8 and length &lt;= 2**

![](exam_stats_2_files/figure-markdown_strict/unnamed-chunk-88-1.png)

**Summary** From the association rules, following conclusions can be
drawn: 1. People are likely to buy vegetables if they buy vegetable
juices. 2. People are more likely to buy bottled beer if they purchase
red wine or liquor 3. People who buy root vegetables are more likely to
buy other kinds of vegetables 4. Whole milk is the most common item
purchased by customers

So placing the those items next to each other will make shoppings more
convenient.
