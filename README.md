# 📈 Comparação de Yield Curves: 2007 vs 2020

Neste mini-projeto, comparo as curvas de juros ("yield curves") dos títulos do Tesouro dos Estados Unidos em dois momentos históricos:

- **Julho de 2007**: antes da crise financeira global
- **Julho de 2020**: durante a pandemia da COVID-19

A curva de juros mostra a taxa de retorno (yield) em função do tempo até o vencimento dos títulos. É um gráfico essencial para entender a percepção do mercado sobre crescimento, inflação e juros futuros.

---

## 🔢 Dados utilizados

| Maturidade | 16 Jul 2007 | 16 Jul 2020 |
|------------|-------------|-------------|
| 1 mês      | 4.75%       | 0.12%       |
| 3 meses    | 4.98%       | 0.11%       |
| 6 meses    | 5.08%       | 0.13%       |
| 1 ano      | 5.01%       | 0.14%       |
| 2 anos     | 4.89%       | 0.16%       |
| 3 anos     | 4.89%       | 0.17%       |
| 5 anos     | 4.95%       | 0.28%       |
| 7 anos     | 4.99%       | 0.46%       |
| 10 anos    | 5.05%       | 0.62%       |
| 20 anos    | 5.21%       | 1.09%       |
| 30 anos    | 5.14%       | 1.31%       |

Fonte: U.S. Department of the Treasury

---

## 🧪 Código em Python (Matplotlib)

```python
import matplotlib.pyplot as plt
import numpy as np
from IPython.core.pylabtools import figsize

labels = ['1 Mo','3 Mo','6 Mo','1 Yr','2 Yr','3 Yr','5 Yr','7 Yr','10 Yr','20 Yr','30 Yr']

july16_2007 = [4.75,4.98,5.08,5.01,4.89,4.89,4.95,4.99,5.05,5.21,5.14]
july16_2020 = [0.12,0.11,0.13,0.14,0.16,0.17,0.28,0.46,0.62,1.09,1.31]

fig, ax1 = plt.subplots(figsize=(10, 5))

# Eixo da esquerda - 2007
ax1.spines['left'].set_color('black')
ax1.spines['left'].set_linewidth(1)
ax1.plot(labels, july16_2007, lw=2, color="black")
ax1.set_ylabel("Yield - July 16th 2007", fontsize=10, color="black")
for label in ax1.get_yticklabels():
    label.set_color("black")

# Eixo da direita - 2020
ax2 = ax1.twinx()
ax2.spines['right'].set_color('purple')
ax2.spines['right'].set_linewidth(1)
ax2.plot(labels, july16_2020, lw=2, color="purple")
ax2.set_ylabel("Yield - July 16th 2020", fontsize=10, color="purple")
for label in ax2.get_yticklabels():
    label.set_color("purple")

plt.title("Comparação das Yield Curves: 2007 vs 2020")
plt.tight_layout()
plt.show()

