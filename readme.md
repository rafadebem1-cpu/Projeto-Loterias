
# 🎲 Análise Estatística da Mega-Sena com Python

## 📋 Descrição

Este projeto foi desenvolvido em Python com o objetivo de realizar análises estatísticas sobre os resultados históricos da Mega-Sena e Lotofacil, identificando padrões de frequência das dezenas sorteadas e gerando jogos aleatórios com base nas dezenas mais frequentes.

O projeto utiliza bibliotecas como Pandas e Matplotlib para manipulação de dados, geração de estatísticas e criação de relatórios visuais.

---

## 🎯 Finalidade

O sistema permite:

- Importar resultados históricos da Mega-Sena e Lotofacil
- Consolidar todas as dezenas sorteadas.
- Calcular a frequência de ocorrência de cada dezena.
- Identificar números mais e menos sorteados.
- Gerar jogos aleatórios utilizando as dezenas mais frequentes.
- Exportar resultados para arquivos CSV.
- Gerar tabelas em formato PNG para compartilhamento e documentação.

---

## 🛠️ Tecnologias Utilizadas

- Python 3.x
- Pandas
- NumPy
- Matplotlib
- OpenPyXL (para leitura de arquivos Excel)

---

## 📂 Estrutura do Projeto

```text
projeto-megasena/Lotofacil
│
├── dados/
│   ├── Mega_Sena.xlsx
    |__ Lotofacil.xlsx
    |
│   └── frequencia_dezenas.csv
│
├── imagens/
│   └── jogos_megasena.png
    |__ jogos_lotofavil.png
│
├── src/
│   ├── analise_frequencia.py
│   ├── gerador_jogos.py
│   └── exportacao.py
│
└── README.md
```

---

## ⚙️ Principais Funcionalidades

### 1. Leitura dos Dados

Carrega os resultados históricos da Mega-Sena e Lotofacil a partir de arquivos Excel ou CSV.

```python
df = pd.read_excel("Mega_Sena.xlsx")
```

---

### 2. Consolidação das Dezenas

Agrupa todas as colunas de dezenas em uma única estrutura para análise.

```python
dezenas = pd.concat([
    df['Bola1'],
    df['Bola2'],
    df['Bola3'],
    df['Bola4'],
    df['Bola5'],
    df['Bola6']
])
```

---

### 3. Cálculo de Frequência

Conta quantas vezes cada dezena foi sorteada.

```python
frequencia = dezenas.value_counts()
```

---

### 4. Classificação das Dezenas

Identifica:

- Mais frequentes
- Frequência média
- Menos frequentes

Exemplo:

```python
mais_frequentes = frequencia[frequencia >= 2200]
```

---

### 5. Geração de Jogos

Cria jogos aleatórios utilizando as dezenas mais frequentes.

Exemplo:

- Seleção das 60 dezenas mais frequentes.
- Geração de 10 jogos distintos.
- Cada jogo contendo 6 dezenas.

---

### 6. Exportação de Resultados

Geração de arquivos:

#### CSV

```python
df.to_csv("resultado.csv")
```

#### PNG

```python
plt.savefig("jogos_megasena.png")
```

---

## 📊 Saídas Geradas

O sistema pode produzir:

### Frequência das dezenas

| Dezena | Quantidade |
|---------|------------|
| 10 | 325 |
| 53 | 321 |
| 42 | 317 |

### Jogos Gerados

| D1 | D2 | D3 | D4 | D5 | D6 |
|----|----|----|----|----|----|
| 05 | 12 | 21 | 34 | 45 | 58 |
| 08 | 17 | 25 | 33 | 41 | 60 |

---

## 🚀 Possíveis Melhorias Futuras

- Análise por período (últimos 5 anos, 10 anos, etc.).
- Identificação de números quentes e frios.
- Análise de pares e ímpares.
- Análise de sequências numéricas.
- Dashboard interativo.
- Integração automática com resultados da Caixa.
- Machine Learning para análise exploratória.

---

## 👨‍💻 Autor

Projeto desenvolvido para fins acadêmicos e estudo de análise de dados utilizando Python.

---

## ⚠️ Observação

Este projeto possui caráter exclusivamente estatístico e educacional.

Não existe método matemático comprovado capaz de prever os números sorteados na Mega-Sena. Os resultados gerados representam apenas análises históricas dos concursos realizados.