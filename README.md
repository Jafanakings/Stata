# Stata thesis data analysis 

## Research questions
1. Within an extended expectations-augmented Phillips curve framework, do tariffs ("trade protection") exert a significant influence on inflation dynamics in developing countries?
(This version sharpens the terminology and explicitly names "tariffs" as the measure of protection.)

2. Does the inflationary effect of tariffs differ systematically across low-, middle-, and high-income developing countries?
(This version is more direct and specifies the groups, aligning with your empirical analysis.)

3. Is the relationship between tariffs and inflation mediated by the exchange rate?
(This is a classic, clear mediation hypothesis that your analysis directly tests.)

```Stata
encode country, gen(country_id)
xtset country_id year
```

-transformation
```Stata
gen du_gap = D.u_gap
gen dgovcons = D.govcons
```
* LAGS
```Stata
gen Linflation     = L.inflation
```
dropping problematic countries
```Stata
drop if country_id == 17
drop if countrycode == "SLV"
```
