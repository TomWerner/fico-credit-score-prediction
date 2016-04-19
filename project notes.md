# FICO Credit Score Project
## Data Cleaning / Preprocessing
### Missing Data
The dataset has a substantial number of features with missing values  


Feature | Description | Action | Reason  
--- | --- | --- | ---  
AT20 | Months since oldest account opened | Impute median | Skewed distribution  
AT21 | Months since most recent account opened | Impute median | Skewed distribution  
AT34 | Ratio - balance to high credit | Impute median | Skewed distribution  
AT35 | Average balance of all accounts | Impute median | Skewed distribution  
AT36 | Months since most recent delinquency | Impute median | Skewed distribution  
BR20 | Months since oldest bank card revolving accounts opened | Impute median | Skewed distribution  
FR35 | Average balance of all finance co. revolving accounts | Set 0 | Mode is 0  
RE20 | Months since oldest revolving account opened | Impute median | Skewed distribution  
RE34 | Revolving balance to high credit | Set 0 | Mode is 0  
RE35 | average balance of all revolving accounts | Set 0 | Mode is 0  
BL20 | Months since oldest bank card installment account opened | Impute median | Skewed distribution  
IN21 | Months since most recent installment accounts opened | Impute median | Skewed distribution  
IN34 | Installment balance to high credit | Impute median | Skewed distribution  
MT20 | Months since most oldest mortgage account opened | Impute median | Skewed distribution  
MT21 | Months since most recent mortgage account opened | Impute median | Skewed distribution  
MT22 | Months since most recent mortgage account updated | Impute mode | Single extremely common value  
MT34 | Ratio Balance to high credit on mortgage accounts | Impute median | Skewed distribution  
MT35 | Average balance of mortgage accounts | Impute median | Skewed distribution  
MT36 | Months since most recent mortage deal | Impute median | Skewed distribution  
MT55 | Highest delinquency ever on mortgage account | Impute median | Skewed distribution  
PF34 | Ratio - personal finance balance to high credit | Impute median | Skewed distribution  
OF20 | Months since oldest other finance account opened | Impute median | Skewed distribution  
OF36 | months since most recent delinquency - all other finance | Impute median | Skewed distribution  
ON20 | Months since oldest oil & national account opened | Impute median | Skewed distribution  
ON34 | Ratio - oil & national balance to high credit | Impute mode | Tricky one, bimodal at 0 and 100, but higher at 100  
BC21 | Months since most recent bank card account opened | Impute mode | High value at single point, drastic fall off  
BC30 | percent of bank card accounts >50% of limit | Impute mean | **VERY TRICKY** Modes at 0, 50, 100  
BC31 | percent of bank card accounts >75% of limit | Impute mean | **VERY TRICKY** Modes at 0, 50, 100  
BC34 | Ratio - of bank card balance to high credit | Impute mode | Bimodal at two distinct points  
BC35 | Average balance of all bank card accounts| Impute mode | Single extremely common value  
BC36 | Months since most recent bank card delinquency | Impute median | Skewed distribution  
BC98 | totel open to buy on revolving bank card accounts | Impute mode | Single extremely common value  
PB20 | Months since oldest premium bank card account opened | Impute median | Skewed distribution  
PB21 | Months since latest premium bank card account opened | Impute median | Skewed distribution  
PB35 | Average balance of all premium bank card accounts | Impute mode | Single extremely common value  
RT20 | Months since oldest retail account opened | Impute median | Skewed distribution, two close modes  
RT21 | Months since most recent retail account opened | Impute mode | Single extremely common value  
RT34 | Ratio - retail balance to high credit | Impute mode | Single extremely common value  
RT35 | Average balance of all retail accounts | Impute mode | Single extremely common value  
RT36 | Months since most recent retail delinquency | Impute median | Skewed distribution  
UR20 | Months since oldest upscale retail account opened | Impute median | Skewed distribution  
UR21 | Months since recent upscale retail account opened | Impute median | Skewed distribution  
UR35 | Average balance of upscale retail accounts | Impute mode | Single extremely common value  
DS21 | Months since most recent department store account | Impute median | Skewed distribution  
DS35 | Average balance of all department store accounts | Impute mode | Single extremely common value  
G051 | Percent of accounts never delinquent | Impute median | Skewed distribution
G089 | Highest delinquency ever on account | Impute mode | **VERY TRICKY** Either high or low
G095 | Months since most recent derogatory public record | Impute median | Skewed distribution  
G102 | Months since most recent inquiry | Impute median | Skewed distribution  
S004 | Average number of months accounts on file | Impute median | Skewed distribution  
S027 | Months since most recent financial account opened | Impute mode | Single extremely common value  
S046 | Percent of active accounts with positive balance | Impute mode | Single extremely common value  
S061 | Months since most recent 60+ day rating | Impute median | Skewed distribution  
S062 | Months since most recent 90+ day rating | Impute median | Skewed distribution  
S078 | Ratio - balance/high credit for personal finance trades verified in 12 months | Set 0 | **VERY TRICKY** two high values at 0 and 100
S079 | Ratio - balance/high credit for department/clothing verified in 12 months | Impute mode | Single extremely common value  
AGE | Calculated AGE from S002 | Impute median | Skewed distribution  

### Business Case
We only want to give loans to customers we feel confident will pay us back. To achieve this,
we will deny loans to customers with a credit score of less than 650. We've coded this in our dataset appropriately.


## Modeling
### Decision Trees

Complexity | Average Class Error (Validation set)
--- | ---
0 | .11
.0001 | .10 
.0002 | .10
.0003 | .09
.0004 | .10

Based one these results, we chose a decision tree built with a complexity of .0003.

This tree uses 44 variables,  

[ 1] AGE      AT10     AT29     BC13     BC29     FI01     G006     G009    
[ 9] G017     G018     G020     G041     G042     G043     G057     G059    
[17] G061     G065     G066     G093     G096     G098     G103     ICN_RE34
[25] ICN_RE35 IMD_AT20 IMD_AT21 IMD_AT34 IMD_AT36 IMD_BC98 IMD_G051 IMD_G095
[33] IMD_G102 IMD_RT36 IMD_S004 IMD_S061 IMD_S062 IMO_BC34 IMO_G089 INCOME  
[41] RE28     S043     S059     S064 

which is a significant pruning from the nearly 300 variables our dataset had.






