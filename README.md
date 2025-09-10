# 🔬 Modelo de Predição de Diabetes - Machine Learning

## 📖 Sobre o Projeto

Este projeto foi desenvolvido como parte do curso **"Machine Learning em Inteligência Artificial"** da Rocketseat. O objetivo é criar um modelo de Machine Learning capaz de prever resultados de exames relacionados à diabetes com base em características físicas dos pacientes.

## 🎯 Objetivo

Desenvolver modelos de **Regressão Linear** para prever os resultados de exames de diabetes utilizando dados biométricos dos pacientes, comparando diferentes abordagens e features para identificar o modelo com melhor performance.

## 📊 Dataset

O dataset utilizado (`exame-diabetes.csv`) contém **100 registros** de pacientes com as seguintes características:

| Variável      | Tipo       | Descrição                                |
| ------------- | ---------- | ---------------------------------------- |
| `id_paciente` | Numérico   | Identificador único do paciente          |
| `genero`      | Categórico | Gênero do paciente (M/F)                 |
| `idade`       | Numérico   | Idade em anos                            |
| `peso`        | Numérico   | Peso em quilogramas                      |
| `altura`      | Numérico   | Altura em centímetros                    |
| `resultado`   | Numérico   | **Variável target** - Resultado do exame |

## 🛠️ Tecnologias Utilizadas

- **Python 3.x**
- **Pandas** - Manipulação e análise de dados
- **Matplotlib** - Visualização de dados
- **Seaborn** - Visualizações estatísticas avançadas
- **Scikit-learn** - Algoritmos de Machine Learning
- **Jupyter Notebook** - Ambiente de desenvolvimento

## 📈 Metodologia Aplicada

### 1. **Análise Exploratória de Dados (EDA)**

#### 🔍 Etapas Realizadas:

- **Carregamento dos dados** usando pandas
- **Análise da estrutura** com `.info()` e `.head()`
- **Remoção de features irrelevantes** (`id_paciente`)
- **Encoding de variáveis categóricas** usando One Hot Encoding para `genero`
- **Engenharia de Features**: Criação do **IMC (Índice de Massa Corporal)**

#### 📊 Visualizações Implementadas:

- **Mapa de Calor (Heatmap)** - Correlação entre todas as variáveis
- **Mapa de Correlação** específico com a variável target
- **Scatter Matrix** - Distribuição e relações entre variáveis
- **Histogramas** - Distribuição de cada variável

### 2. **Feature Engineering**

#### 🆕 Criação do IMC:

```python
# IMC = peso (kg) / altura (m)²
df_exames['imc'] = (df_exames['peso'] / ((df_exames['altura'] / 100) ** 2))
```

### 3. **Modelagem de Machine Learning**

#### 🤖 Algoritmo Utilizado: **Regressão Linear**

### **Modelo 1: Sem IMC**

- **Features**: idade, peso, altura, genero_F, genero_M
- **Target**: resultado
- **Divisão**: 70% treino / 30% teste
- **Random State**: 51 (para reprodutibilidade)

### **Modelo 2: Apenas IMC**

- **Features**: imc
- **Target**: resultado
- **Divisão**: 70% treino / 30% teste
- **Random State**: 51

## 📊 Métricas de Avaliação

### 🎯 Métricas Utilizadas:

1. **R² Score (Coeficiente de Determinação)**

   - Mede a proporção da variância explicada pelo modelo
   - Valores próximos a 1 indicam melhor ajuste

2. **MAE (Mean Absolute Error)**
   - Erro médio absoluto entre predições e valores reais
   - Valores menores indicam melhor performance

### 📈 Visualização dos Resultados:

- **Gráfico de dispersão** com linha de regressão
- **Comparação visual** entre valores reais e preditos

## 🏗️ Estrutura do Projeto

```
ml-diabetes-model/
├── datasets/
│   └── exame-diabetes.csv          # Dataset original
├── modelo_diabetes.ipynb           # Notebook principal com análises
├── Pipfile                        # Dependências do projeto
├── Pipfile.lock                   # Lock file das dependências
└── README.md                      # Este arquivo
```

## 🚀 Como Executar o Projeto

### 1. **Pré-requisitos**

- Python 3.x instalado
- Pipenv para gerenciamento de dependências

### 2. **Instalação**

```bash
# Clone o repositório (se aplicável)
git clone [URL_DO_REPO]

# Navegue até o diretório
cd ml-diabetes-model

# Instale as dependências
pipenv install

# Ative o ambiente virtual
pipenv shell
```

### 3. **Execução**

```bash
# Abra o Jupyter Notebook
jupyter notebook modelo_diabetes.ipynb
```

## 📚 Conceitos Aplicados do Curso Rocketseat

### 🧠 **Módulos do Curso Aplicados:**

#### **1. Análise Exploratória de Dados (EDA)**

- ✅ Aplicação do Pandas para manipulação de dados
- ✅ Tratamento de dados ausentes
- ✅ Análise univariada e bivariada
- ✅ Visualizações com matplotlib e seaborn

#### **2. Aprendizado de Máquina - Fundamentos**

- ✅ Algoritmos supervisionados
- ✅ Regressão Linear
- ✅ Divisão treino/teste
- ✅ Métricas de avaliação

#### **3. Algoritmos Supervisionados**

- ✅ **Regressão Linear Simples** - Modelo com uma única feature (IMC)
- ✅ **Regressão Linear Múltipla** - Modelo com múltiplas features
- ✅ Interpretação de coeficientes
- ✅ Avaliação de modelos

## 🎓 Próximos Passos Sugeridos

### 🔄 **Melhorias Possíveis:**

1. **Validação Cruzada** - Implementar k-fold cross-validation
2. **Regularização** - Testar Ridge e Lasso Regression
3. **Outros Algoritmos** - Comparar com Decision Tree, Random Forest
4. **Feature Selection** - Aplicar técnicas de seleção de features
5. **Hyperparameter Tuning** - Otimização de parâmetros

### 📖 **Módulos do Curso para Continuar:**

- **Algoritmos Supervisionados Avançados**
  - Regressão Polinomial
  - Árvore de Decisão
  - Naive Bayes
  - Regressão Logística
- **Ensemble de Modelos**
  - Random Forest
  - Gradient Boosting
  - Stacking

## 💡 Insights e Aprendizados

### ✨ **Principais Descobertas:**

- A criação do IMC como feature pode melhorar significativamente o modelo
- A correlação entre variáveis biométricas e resultados de exames é fundamental
- One Hot Encoding é essencial para variáveis categóricas
- Visualizações ajudam a entender padrões nos dados

### 🎯 **Habilidades Desenvolvidas:**

- Análise exploratória de dados
- Pré-processamento de dados
- Feature engineering
- Implementação de algoritmos de ML
- Avaliação de modelos
- Visualização de resultados

## 📖 Material de Estudo Complementar

### 🔗 **Recursos Recomendados:**

1. **Documentação Oficial:**

   - [Scikit-learn User Guide](https://scikit-learn.org/stable/user_guide.html)
   - [Pandas Documentation](https://pandas.pydata.org/docs/)
   - [Matplotlib Tutorials](https://matplotlib.org/tutorials/)

2. **Conceitos Fundamentais:**

   - Regressão Linear: Conceitos matemáticos e implementação
   - Métricas de Avaliação: R², MAE, MSE, RMSE
   - Overfitting e Underfitting
   - Validação Cruzada

3. **Próximos Algoritmos a Estudar:**
   - Regressão Polinomial
   - Regressão Logística
   - Árvores de Decisão
   - Random Forest

## 🏆 Status do Projeto

- ✅ **EDA Completa** - Análise exploratória finalizada
- ✅ **Feature Engineering** - IMC criado e aplicado
- ✅ **Modelos Básicos** - Dois modelos de regressão linear implementados
- ✅ **Avaliação** - Métricas calculadas e comparadas
- 🔄 **Em desenvolvimento** - Melhorias e otimizações

---

### 👨‍💻 **Desenvolvido como parte do curso "Machine Learning em Inteligência Artificial" da Rocketseat**

**Data de Criação:** Setembro 2025  
**Linguagem Principal:** Python  
**Tipo de Problema:** Regressão Supervisionada  
**Dataset:** Dados biométricos para predição de diabetes
