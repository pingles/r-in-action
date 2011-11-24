# Data Frames

A bit like Matrices but allow mixed data-types.

    > patient_ids <- c(10291, 99928, 56019)
    > ages <- c(29, 40, 13)
    > diabetes <- c("Type1", "Type2", "Type1")
    > status <- c("Poor", "Improved", "Excellent")
    > data <- data.frame(patient_ids, ages, diabetes, status, row.names=patient_ids)
    > data
          patient_ids ages diabetes    status
    10291       10291   29    Type1      Poor
    99928       99928   40    Type2  Improved
    56019       56019   13    Type1 Excellent

Variables can be described as one of:

* Nominal. Categorical with no implied order. For example, Type 1 or Type 2 Diabetes.
* Ordinal. Imply order but not amount. Poor < Improved < Excellent.
* Continuous. A value in some range, both order and amount are specified.

Both Nominal and Ordinal can be considered categorical variables. In R these
are known as factors.

### Nominal Factor

The below turns diabetes into a nominal factor.

    > diabetes <- factor(diabetes)
    > diabetes
    [1] Type1 Type2 Type1
    Levels: Type1 Type2

### Ordinal Factor

The below turns status into an ordinal factor

    > status <- factor(status, order=TRUE,
                     levels=c("Poor", "Improved", "Excellent"))
    > status
    [1] Poor      Improved  Excellent
    Levels: Excellent < Improved < Poor
    