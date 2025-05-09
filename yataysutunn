library(ggplot2)

nedenler <- data.frame(
  Neden = c("Yeterli is bulunamamasi", 
            "Tecrube eksikligi", 
            "Egitim yetersizligi", 
            "Kadinlarin ev ici sorumluluklari", 
            "Bolgesel ekonomik durgunluk", 
            "Is begememe", 
            "Ulasim zorluklari"),
  Yuzde = c(32.5, 21.0, 15.8, 10.6, 9.4, 6.3, 4.4)
)

# Siralama
nedenler$Neden <- factor(nedenler$Neden, levels = nedenler$Neden[order(nedenler$Yuzde)])

# Grafik
ggplot(nedenler, aes(x = Neden, y = Yuzde, fill = Yuzde)) +
  geom_col(width = 0.7) +
  geom_text(aes(label = paste0(Yuzde, "%")), 
            hjust = -0.1, size = 4.5, color = "black") +
  coord_flip() +
  labs(
    title = "2025'te Issizlige Yol Acan Baslica Nedenler",
    subtitle = "Anket verilerine gore en cok bildirilen nedenler",
    x = "Neden",
    y = "Oran (%)",
    caption = "Kaynak: TUİK Anket Verileri 2025"
  ) +
  theme_minimal(base_size = 12) +
  scale_fill_gradient(low = "#A9CCE3", high = "#2E86C1") +
  theme(
    plot.title = element_text(face = "bold", size = 12, hjust = 0.5),
    plot.subtitle = element_text(size = 12, hjust = 0.5),
    plot.caption = element_text(size = 9, hjust = 0),
    legend.position = "none"
  ) +
  ylim(0, max(nedenler$Yuzde) + 5)
