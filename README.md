# -Ger-ek-Hayat-Verileriyle-Kira-Fiyat-Tahmini-oklu-Do-rusal-Regresyon-Analizi
#]REM KARAGVZ VZEL KONU
#k|t|phaneler
if (!require("car")) install.packages("car")  
if (!require("ggplot2")) install.packages("ggplot2")  

library(car)
library(ggplot2)

#Veri
data <- data.frame(
  Y = c(18.9, 17, 20, 18.25, 20.07, 11.2, 22.12, 21.47, 34.7, 30.4),  # Galon Ba~}na Mil
  X1 = c(350, 350, 250, 351, 225, 440, 231, 262, 89.7, 96.9),        # Motor Hacmi
  X2 = c(165, 170, 105, 143, 95, 215, 110, 110, 70, 75)              # Beygir G|c|
)

#Goklu regresyon 
model <- lm(Y ~ X1 + X2, data = data)

summary(model)

#ANOVA 
anova_results <- anova(model)
print(anova_results)

#Hata deperleri igin normallik testi (Shapiro-Wilk Testi)
residuals <- residuals(model)
shapiro_test <- shapiro.test(residuals)
print(shapiro_test)

#Rezid|ler igin QQ grafipi 
qqnorm(residuals)
qqline(residuals, col = "red")

#EKK  yvntemiyle grafik
data$Predicted_Y <- predict(model)

ggplot(data, aes(x = Predicted_Y, y = Y)) +
  geom_point(color = "blue") +
  geom_abline(intercept = 0, slope = 1, color = "red") +
  labs(
    title = "Gergek Deperler ve Tahmin Edilen Deperler",
    x = "Tahmin Edilen Deperler",
    y = "Gergek Deperler"
  ) +
  theme_minimal()


