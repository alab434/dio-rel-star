## Solução do Desafio - Modelando um Dashboard de E-commerce com Power BI Utilizando Fórmulas DAX

### Etapas do processo:
1. Renomeada a tabela *financials* para *financials_origem*, e ocultada da visualização de relatório;
2. Duplicação da tabela *financials* para *F_Vendas*;
3. *F_Vendas*: Criação da coluna SK_ID, ID_Produtos, ajustes nos formatos dos dados, remoção de colunas desnecessárias;
4. Duplicação da tabela *F_Vendas* para *D_Detalhes*, remoção de colunas desnecessárias;
5. Duplicação da tabela *F_Vendas* para *D_Descontos*, remoção de colunas desnecessárias, remoção de linhas duplicadas;
6. Duplicação da tabela *F_Vendas* para *D_Produtos*, agrupamento dos produtos e criação das agregações;
7. Duplicação da tabela *F_Vendas* para *D_Produtos_Detalhes*, remoção de colunas desnecessárias, remoção de linhas duplicadas;
8. Duplicação da tabela *F_Vendas* para *D_Descontos*, remoção de colunas desnecessárias, remoção de linhas duplicadas;
9. Criação da tabela *D_Calendário* e colunas usando o DAX CALENDAR();
```sql
D_Calendário = CALENDAR(
  DATE(2013,1,1),
  DATE(2014,12,31)
)
Ano = YEAR('D_Calendário'[Data])
Dia da Semana = WEEKDAY('D_Calendário'[Data])
Mês = FORMAT('D_Calendário'[Data], "MMMM")
Nome do Dia = FORMAT('D_Calendário'[Data],"DDDD")
Número do Mês = MONTH('D_Calendário'[Data])
Semana = WEEKNUM('D_Calendário'[Data])
Trimestre = QUARTER('D_Calendário'[Data])
```
10. Verificação das Relações

---
![Solução](https://github.com/alab434/dio-rel-star/blob/main/solu%C3%A7%C3%A3o%20desafio%20--%20Modelando%20um%20Dashboard%20de%20E-commerce%20com%20Power%20BI%20Utilizando%20F%C3%B3rmulas%20DAX.png)
