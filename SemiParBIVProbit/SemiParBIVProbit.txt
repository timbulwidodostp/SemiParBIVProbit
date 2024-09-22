# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Semiparametric Copula bivariate probit binary models (modelling) Use SemiParBIVProbit With (In) R Software
install.packages("remotes")
remotes::install_github("cran/SemiParBIVProbit")
library("SemiParBIVProbit")
SemiParBIVProbit = read.csv("https://raw.githubusercontent.com/timbulwidodostp/SemiParBIVProbit/main/SemiParBIVProbit/SemiParBIVProbit.csv",sep = ";")
# Estimation Semiparametric Copula bivariate probit binary models (modelling) Use SemiParBIVProbit With (In) R Software
# CLASSIC BIVARIATE PROBIT
SemiParBIVProbit_1  <- SemiParBIVProbit(list(y1 ~ x1 + x2 + x3, y2 ~ x1 + x2 + x3), data = SemiParBIVProbit)
conv.check(SemiParBIVProbit_1)
summary(SemiParBIVProbit_1)
AIC(SemiParBIVProbit_1)
BIC(SemiParBIVProbit_1)
# SEMIPARAMETRIC BIVARIATE PROBIT
SemiParBIVProbit_2  <- SemiParBIVProbit(list(y1 ~ x1 + s(x2, bs = "tp", k = 10, m = 2) + s(x3), y2 ~ x1 + s(x2) + s(x3)), data = SemiParBIVProbit)
conv.check(SemiParBIVProbit_2)
summary(SemiParBIVProbit_2)
AIC(SemiParBIVProbit_2)
# Semiparametric Copula bivariate probit binary models (modelling) Use SemiParBIVProbit With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished