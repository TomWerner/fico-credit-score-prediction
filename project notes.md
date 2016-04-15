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
BC35 | 
BC36 | 
BC98 | 
PB20 | 
PB21
PB35
RT20
RT21
RT34
RT35
RT36
UR20
UR21
UR35
DS21
DS35
G051
G089
G095
G102
S004
S027
S046
S061
S062
S078
S079
AGE


