# Lineární regrese HDP

## Jednotlivé kroky v kódu

### Import knihoven

Načtou se knihovny pandas a statsmodels

### Načtení dat

Data jsou načtena z Excelového souboru.

### Kontrola dat

Vypíší se první řádky tabulky a názvy sloupců, aby bylo vidět, zda se
data načetla správně.

### Definice cílové proměnné

Proměnná **Hdp** je uložena jako výstupní (y), kterou se model snaží
vysvětlit.

### Výběr vstupních proměnných

Z tabulky se vyberou sloupce, které budou použity jako prediktory (X):\
zahraniční obchod, průmysl, nezaměstnanost, inflace a mzda.

### Přidání konstanty

Do modelu se přidá konstanta, aby regresní rovnice měla volnou
konstantní složku.

### Vytvoření a natrénování modelu

Pomocí OLS se vytvoří a spočítá lineární regresní model.

### Výpis výsledků

Funkce **summary()** vypíše kompletní výsledky modelu.

------------------------------------------------------------------------

## Předběžná analýza výsledků regrese

### R-squared

Hodnota **R-squared = 0.737**\
Model vysvětluje přibližně 73,7 % variability HDP.

**Adjusted R-squared = 0.660**\
Model má solidní, ale ne perfektní vysvětlující schopnost.

### F-statistic

**F-statistic = 9.544**\
**Prob(F-statistic) = 0.000178**\
Model je jako celek statisticky významný.

------------------------------------------------------------------------

## Koeficienty jednotlivých proměnných

### Zahraniční obchod

-   Koeficient: **0.2023**\
-   P-hodnota: **0.062**\
    Mírně zvyšuje HDP, nejsilnější efekt ze všech proměnných.

### Průmysl

-   Koeficient: **0.1477**\
-   P-hodnota: **0.197**

### Nezaměstnanost

-   Koeficient: **-0.3142**\
-   P-hodnota: **0.199**

### Inflace

-   Koeficient: **0.0528**\
-   P-hodnota: **0.799**

### Mzda

-   Koeficient: **0.3231**\
-   P-hodnota: **0.095**

### Konstanta

-   Koeficient: **1.188**

------------------------------------------------------------------------

## Výsledky regrese (výpis z terminálu)

    Rok Hdp Zahraniční obchod Průmysl Nezaměstnanost Inflace Mzda
    0 2001 2.917240 9.426906 11.3 8.1 4.7 3.9
    1 2002 1.513443 0.896110 -0.4 7.3 1.8 6.1
    2 2003 3.300836 8.841053 3.3 7.8 0.1 5.7
    3 2004 4.736346 29.732160 15.6 8.3 2.8 3.4
    4 2005 6.375039 18.349075 6.2 7.9 1.9 3.0
    ['Rok', 'Hdp', 'Zahraniční obchod', 'Průmysl', 'Nezaměstnanost', 'Inflace', 'Mzda']

    OLS Regression Results
    ==============================================================================
    Dep. Variable: Hdp                R-squared: 0.737
    Model: OLS                      Adj. R-squared: 0.660
    Method: Least Squares            F-statistic: 9.544
    Date: Fri, 12 Dec 2025           Prob (F-statistic): 0.000178
    Time: 17:03:17                   Log-Likelihood: -42.275
    No. Observations: 23            AIC: 96.55
    Df Residuals: 17                BIC: 103.4
    Df Model: 5
    Covariance Type: nonrobust
    =====================================================================================
                              coef    std err          t      P>|t|      [0.025      0.975]
    -------------------------------------------------------------------------------------
    const                  1.1880      1.756      0.676      0.508      -2.517       4.893
    Zahraniční obchod      0.2023      0.101      2.000      0.062      -0.011       0.416
    Průmysl                0.1477      0.110      1.343      0.197      -0.084       0.380
    Nezaměstnanost        -0.3142      0.235     -1.336      0.199      -0.810       0.182
    Inflace                0.0528      0.204      0.259      0.799      -0.378       0.483
    Mzda                   0.3231      0.183      1.768      0.095      -0.062       0.709
    ==============================================================================
    Omnibus: 2.988   Durbin-Watson: 2.385
    Prob(Omnibus): 0.225   Jarque-Bera (JB): 1.519
    Skew: -0.579   Prob(JB): 0.468
    Kurtosis: 3.495   Cond. No. 67.3
    ==============================================================================
