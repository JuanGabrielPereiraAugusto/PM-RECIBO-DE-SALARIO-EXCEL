# 💵 Recibo de Pagamento de Salário no Excel

Planilha que monta um **recibo de pagamento (holerite)** a partir de um **cadastro de funcionários**, usando **PROCV** para buscar os dados e **fórmulas** para calcular descontos, totais e **valor líquido**.

| Arquivo | O que é |
|---|---|
| 📗 [`Recibo_de_Pagamento_Salario.xlsx`](Recibo_de_Pagamento_Salario.xlsx) | Cadastro de funcionários e o recibo de pagamento |

---

## 🗂️ Abas da planilha

| Aba | Conteúdo |
|---|---|
| **Table1** | Cadastro de 20 funcionários fictícios: nome, salário, data de admissão, CBO e função |
| **Planilha4** | O **recibo de pagamento** do mês (Março/2023) |

---

## 🔎 Busca dos dados com PROCV

O nome do funcionário é digitado no recibo, e o salário, a data de admissão e o CBO vêm do cadastro. O último argumento `0` exige **correspondência exata** do nome:

```excel
Salário:           =PROCV(C8; Table1!B1:F21; 2; 0)
Data de admissão:  =PROCV(C8; Table1!B1:F21; 3; 0)
CBO:               =PROCV(C8; Table1!B1:F21; 4; 0)
```

---

## 🧮 Cálculos do recibo

| Descrição | Referência | Fórmula | Valor |
|---|:---:|---|---:|
| Salário do mês | 30 dias | `=D8` | R$ 4.000,00 |
| FGTS | 8% | `=D8*0,08` | R$ 320,00 |
| Vale-transporte | 6% | `=D8*0,06` | R$ 240,00 |
| IRRF | 22,5% | `=D8*0,225` | R$ 900,00 |
| Desconto INSS | 8% | `=D8*0,08` | R$ 320,00 |

| Totais | Fórmula | Valor |
|---|---|---:|
| **Total de vencimentos** | `=SOMA(I15:I24)` | R$ 4.000,00 |
| **Total de descontos** | `=SOMA(K15:K19)` | R$ 1.780,00 |
| **Valor líquido** | `=I26-K26` | **R$ 2.220,00** |

No rodapé, o recibo também calcula o **salário-base**, o **salário de contribuição do INSS**, as **bases de cálculo do FGTS e do IRRF** e o **FGTS do mês**.

---

## 🧠 Conceitos praticados

- **PROCV** entre abas
- **Referências** entre células e **fórmulas percentuais**
- **SOMA** de intervalos
- **Mesclagem**, bordas e formatação de um documento para impressão

---

## 🎓 Informações acadêmicas

| | |
|---|---|
| **Instituição** | Fatec Taquaritinga |
| **Curso** | Análise e Desenvolvimento de Sistemas — 1º semestre |
| **Disciplina** | Microinformática |
| **Ano** | 2025 |

## 👤 Autor

**Juan Gabriel Pereira Augusto**
GitHub: [@JuanGabrielPereiraAugusto](https://github.com/JuanGabrielPereiraAugusto)
