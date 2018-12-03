# Regresi
#Dwiko Nugroho Dani 17523115
#Rio Galang Jati R 17523118

linear <- read.csv(file="guru1.csv", header=TRUE, sep=",")
linear

#membuat model

model <- lm(negeri ~ swasta, data=linear)
summary(model)


plot(negeri ~ swasta, data=linear)
abline(model, col = "red", lwd = 1)

poly_model <- lm(negeri ~ poly(swasta,degree=2), data = linear)
summary(poly_model)



x <- with(linear, seq(min(swasta), max(swasta), length.out=2000))
y <- predict(poly_model, newdata = data.frame(swasta = x))

plot(negeri ~ swasta, data = linear)
lines(x, y, col = "red")

#Kesimpulan
Code-code tersebut bertujuan untuk mencari bentuk hubungan peubah bebas(x) dan peubah tak bebas(y).
Selain itu code-code tersebut digunakan untuk memprediksi data-data yang bersifat kuantitatif.
