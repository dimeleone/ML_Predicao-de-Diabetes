# 🩺 Predição Preventiva de Diabetes com ML

Modelo de Machine Learning para **triagem preventiva de diabetes** utilizando apenas dados demográficos, antropométricos e de estilo de vida — sem necessidade de exames de sangue.

---

## 📋 Sobre o Projeto

Este projeto desenvolve um sistema de triagem inteligente que identifica pessoas em risco de diabetes usando informações facilmente coletáveis como idade, IMC, histórico familiar, pressão arterial e hábitos de vida.

**Objetivo:** Criar uma ferramenta de alerta precoce que não substitui o médico, mas prioriza quem precisa fazer exames com urgência.

### 🎯 Resultados Obtidos

| Modelo                  | Recall (Diabéticos) | F1-Score | Falsos Negativos |
| ----------------------- | ------------------- | -------- | ---------------- |
| **Regressão Logística** | **99%** ⭐           | **0.72** | Apenas 10        |
| Árvore de Decisão       | 78%                 | 0.66     | 246              |
| Random Forest           | 91%                 | 0.70     | 102              |

**Modelo Vencedor:** Regressão Logística (melhor equilíbrio entre detecção e estabilidade)

---

## 🚀 Como Rodar o Projeto

### Pré-requisitos
- Python 3.8 ou superior
- pip (gerenciador de pacotes do Python)

### Passo 1: Instalar Python e pip (Windows PowerShell)

**Opção A - Via Winget (Windows 10/11):**
```powershell
# Instalar Python (já inclui pip)
winget install Python.Python.3.12
```

**Opção B - Download Manual:**
1. Acesse [python.org/downloads](https://www.python.org/downloads/)
2. Baixe e execute o instalador
3. ⚠️ **IMPORTANTE:** Marque a opção "Add Python to PATH"

**Verificar instalação:**
```powershell
python --version
pip --version
```

### Passo 2: Navegar até a Pasta do Projeto
```powershell
cd "C:\Users\Dimitri\Desktop\Projeto"
```

### Passo 3: Instalar Dependências
```powershell
pip install -r requirements.txt
```

Ou instale manualmente:
```powershell
pip install pandas numpy matplotlib seaborn scikit-learn jupyter ipykernel
```

### Passo 4: Executar o Projeto

#### Opção A - VS Code (Recomendado) 🖥️
1. Abra o VS Code
2. Instale a extensão **"Jupyter"** (se ainda não tiver)
3. Abra o arquivo `projeto.ipynb`
4. Selecione o kernel Python no canto superior direito
5. Clique em **"Run All"** (▶️▶️) para executar todas as células

#### Opção B - Jupyter Notebook no Navegador 🌐
```powershell
jupyter notebook
```
Isso abrirá o Jupyter no navegador. Navegue até `projeto.ipynb` e clique para abrir.

#### Opção C - JupyterLab 🧪
```powershell
pip install jupyterlab
jupyter lab
```

---

## 📁 Estrutura do Projeto

```
C:\Users\Dimitri\Desktop\Projeto\
├── projeto.ipynb          # Notebook principal com todo o código
├── diabetes_dataset.csv   # Dataset com 10.000 registros
├── requirements.txt       # Dependências do projeto
├── ROTEIRO_VIDEO.md       # Roteiro para apresentação em vídeo
└── README.md              # Este arquivo
```

---

## 📊 Dataset

- **Registros:** 10.000 pacientes
- **Features:** 21 variáveis (idade, sexo, IMC, pressão arterial, etc.)
- **Target:** Diabetes (baseado no critério ADA: Glicemia de Jejum ≥ 126 mg/dL)

### Features Utilizadas no Modelo:
- Idade, Sexo, Etnia
- IMC, Circunferência da Cintura, Altura, Peso
- Pressão Arterial (Sistólica e Diastólica)
- Colesterol (Total, LDL, HDL, Triglicerídeos)
- Histórico Familiar de Diabetes
- Diabetes Gestacional Prévio
- Hipertensão
- Nível de Atividade Física
- Consumo de Álcool
- Tabagismo

### ⚠️ Features Removidas (Data Leakage):
- `Fasting_Blood_Glucose` - usada para criar o target
- `HbA1c` - alta correlação com glicose

---

## 🔧 Técnicas Utilizadas

### Pré-processamento
- Correção de inconsistências (diabetes gestacional em homens)
- Tratamento de valores ausentes (moda/mediana)
- Label Encoding (variáveis binárias)
- One-Hot Encoding (variáveis categóricas)

### Modelagem
- Regressão Logística
- Árvore de Decisão (max_depth=10)
- Random Forest (n_estimators=100, max_depth=15)

### Otimizações
- Cross-Validation (5-Fold)
- Threshold Optimization
- Ensemble Voting (Hard e Soft)

---

## 👨‍💻 Autor

<img src="https://github.com/dimeleone.png" width="120" style="border-radius: 50%;" alt="Foto de Dimitri Leone">

**Dimitri Leone Simões**  
- **Matrícula:** 114  
- **Curso:** Engenharia de Software  
- **GitHub:** [github.com/dimeleone](https://github.com/dimeleone)

---

## 📝 Licença

Este projeto foi desenvolvido para fins acadêmicos.
