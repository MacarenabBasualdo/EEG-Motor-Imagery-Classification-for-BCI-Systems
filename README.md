#  EEG Motor Imagery Classification for BCI Systems

[Español](#-español) | [English](#-english) | [Português](#-português)

---

## 🇪🇸 Español

Este trabajo está enfocado en el desarrollo de un pipeline completo en Python para la clasificación de **Imaginación Motora** (*Mano Izquierda vs. Mano Direita*) a partir de señales EEG. Se contrasta el paradigma clásico de Machine Learning (ingeniería de características manual) contra el paradigma conexionista (Deep Learning sobre señal cruda), con foco especial en la robustez y generalización de los modelos ante distintos sujetos y bases de datos.

El proyecto utiliza dos bases de datos públicas de EEG para tareas de Imaginación Motora: Dreyer2023A, empleada como base principal para el entrenamiento y evaluación de todos los modelos (60 sujetos, registro de 3 canales motores C3/Cz/C4), y Cho2017, utilizada exclusivamente en la Fase 4 para evaluar la capacidad de generalización de los modelos ante un protocolo de adquisición y una población de sujetos completamente distintos (52 sujetos).

El pipeline está organizado en 4 fases secuenciales, cada una implementada en su propia notebook.

### 🛠️ Fases del Desarrollo

* **Fase 1 — Ingeniería de Características y Visualización (EDA):** Extracción de características multidominio (potencia espectral por banda, dimensión fractal de Katz, coeficientes autorregresivos, momentos estadísticos, entropía de permutación, correlación cruzada, coherencia MSC, Phase Locking Value) sobre los 3 canales motores (C3, Cz, C4). Reducción de dimensionalidad y visualización del espacio de características mediante PCA, t-SNE y UMAP.
* **Fase 2 — Selección de Features, Machine Learning Clásico y BCI Illiteracy:** Selección de características por consenso entre múltiples métodos (ANOVA, Mutual Information, RFE, Lasso). Entrenamiento y comparación de 5 modelos (SVM, Árbol de Decisión, Random Forest, PCA+LDA, CSP+LDA) con validación cruzada rigurosa y simulación online cronológica (verificación matemática de ausencia de Data Leakage). Cuantificación del fenómeno de *BCI Illiteracy* mediante umbral binomial y permutation test.
* **Fase 3 — Deep Learning (EEGNet):** Implementación y entrenamiento de una arquitectura EEGNet directamente sobre la señal cruda, sin ningún preprocesamiento manual, con validación cruzada estratificada y análisis de curvas de entrenamiento (Loss/Accuracy por época).
* **Fase 4 — Test de Robustez (Stress Test):** Evaluación de la capacidad de generalización de los modelos entrenados, aplicándolos a sujetos nunca vistos (*cross-subject*) y a una base de datos completamente distinta, Cho2017 (*cross-dataset*), cuantificando estadísticamente la caída de rendimiento en cada escenario.

### 💻 Tecnologías Utilizadas

* **Lenguaje:** Python (NumPy, Pandas, SciPy, Matplotlib, Seaborn)
* **Procesamiento EEG:** MNE-Python
* **Machine Learning:** scikit-learn (SVM, Random Forest, LDA, CSP, validación cruzada, métricas)
* **Deep Learning:** PyTorch (implementación de EEGNet)
* **Datasets:** Dreyer2023A y Cho2017 (Motor Imagery, públicos)
* **Entorno:** Google Colab

---

## 🇺🇸 English

This project focuses on developing a complete Python pipeline for **Motor Imagery Classification** (*Left Hand vs. Right Hand*) from EEG signals. It contrasts the classical Machine Learning paradigm (manual feature engineering) against the connectionist paradigm (Deep Learning on raw signal), with a strong emphasis on model robustness and generalization across subjects and datasets.

The project uses two public EEG Motor Imagery datasets: Dreyer2023A, used as the primary dataset for training and evaluating all models (60 subjects, 3 motor channels C3/Cz/C4), and Cho2017, used exclusively in Phase 4 to assess model generalization under a completely different acquisition protocol and subject population (52 subjects).

The pipeline is organized into 4 sequential phases, each implemented in its own notebook.

### 🛠️ Development Phases

* **Phase 1 — Feature Engineering & Visualization (EDA):** Multidomain feature extraction (band power, Katz fractal dimension, autoregressive coefficients, statistical moments, permutation entropy, cross-correlation, MSC coherence, Phase Locking Value) over 3 motor channels (C3, Cz, C4). Dimensionality reduction and visualization of the feature space using PCA, t-SNE, and UMAP.
* **Phase 2 — Feature Selection, Classical Machine Learning & BCI Illiteracy:** Feature selection by consensus across multiple methods (ANOVA, Mutual Information, RFE, Lasso). Training and comparison of 5 models (SVM, Decision Tree, Random Forest, PCA+LDA, CSP+LDA) with rigorous cross-validation and chronological online simulation (mathematical verification of no Data Leakage). Quantification of the *BCI Illiteracy* phenomenon via binomial threshold and permutation testing.
* **Phase 3 — Deep Learning (EEGNet):** Implementation and training of an EEGNet architecture directly on raw signal, with no manual preprocessing, using stratified cross-validation and training curve analysis (Loss/Accuracy per epoch).
* **Phase 4 — Robustness Test (Stress Test):** Evaluation of the trained models' generalization capacity, applying them to unseen subjects (*cross-subject*) and to a completely different dataset, Cho2017 (*cross-dataset*), statistically quantifying the performance drop in each scenario.

### 💻 Technologies Used

* **Language:** Python (NumPy, Pandas, SciPy, Matplotlib, Seaborn)
* **EEG Processing:** MNE-Python
* **Machine Learning:** scikit-learn (SVM, Random Forest, LDA, CSP, cross-validation, metrics)
* **Deep Learning:** PyTorch (EEGNet implementation)
* **Datasets:** Dreyer2023A and Cho2017 (Motor Imagery, public)
* **Environment:** Google Colab

---

## 🇧🇷 Português

Este projeto está focado no desenvolvimento de um pipeline completo em Python para a classificação de **Imaginação Motora** (*Mão Esquerda vs. Mão Direita*) a partir de sinais de EEG. Contrasta-se o paradigma clássico de Machine Learning (engenharia de características manual) com o paradigma conexionista (Deep Learning sobre sinal bruto), com foco especial na robustez e generalização dos modelos frente a diferentes sujeitos e bancos de dados.

O projeto utiliza dois bancos de dados públicos de EEG para tarefas de Imaginação Motora: Dreyer2023A, usado como base principal para o treinamento e avaliação de todos os modelos (60 sujeitos, registro de 3 canais motores C3/Cz/C4), e Cho2017, utilizado exclusivamente na Fase 4 para avaliar a capacidade de generalização dos modelos frente a um protocolo de aquisição e uma população de sujeitos completamente diferentes (52 sujeitos).

O pipeline está organizado em 4 fases sequenciais, cada uma implementada em seu próprio notebook.

### 🛠️ Fases do Desenvolvimento

* **Fase 1 — Engenharia de Características e Visualização (EDA):** Extração de características multidomínio (potência espectral por banda, dimensão fractal de Katz, coeficientes autorregressivos, momentos estatísticos, entropia de permutação, correlação cruzada, coerência MSC, Phase Locking Value) sobre os 3 canais motores (C3, Cz, C4). Redução de dimensionalidade e visualização do espaço de características via PCA, t-SNE e UMAP.
* **Fase 2 — Seleção de Features, Machine Learning Clássico e BCI Illiteracy:** Seleção de características por consenso entre múltiplos métodos (ANOVA, Mutual Information, RFE, Lasso). Treinamento e comparação de 5 modelos (SVM, Árvore de Decisão, Random Forest, PCA+LDA, CSP+LDA) com validação cruzada rigorosa e simulação online cronológica (verificação matemática da ausência de Data Leakage). Quantificação do fenômeno de *BCI Illiteracy* por meio de limiar binomial e permutation test.
* **Fase 3 — Deep Learning (EEGNet):** Implementação e treinamento de uma arquitetura EEGNet diretamente sobre o sinal bruto, sem nenhum pré-processamento manual, com validação cruzada estratificada e análise de curvas de treinamento (Loss/Accuracy por época).
* **Fase 4 — Teste de Robustez (Stress Test):** Avaliação da capacidade de generalização dos modelos treinados, aplicando-os a sujeitos nunca vistos (*cross-subject*) e a um banco de dados completamente distinto, Cho2017 (*cross-dataset*), quantificando estatisticamente a queda de desempenho em cada cenário.

### 💻 Tecnologias Utilizadas

* **Linguagem:** Python (NumPy, Pandas, SciPy, Matplotlib, Seaborn)
* **Processamento de EEG:** MNE-Python
* **Machine Learning:** scikit-learn (SVM, Random Forest, LDA, CSP, validação cruzada, métricas)
* **Deep Learning:** PyTorch (implementação do EEGNet)
* **Datasets:** Dreyer2023A e Cho2017 (Motor Imagery, público)
* **Ambiente:** Google Colab

---

## 📂 Contenido del Repositorio / Repository Content / Conteúdo do Repositório

```text
├── Fase_1_EDA.ipynb                        # Extracción de características y análisis exploratorio (EDA)
├── Fase_2_Seleccion_de_Features.ipynb      # Selección de features, modelos clásicos y BCI Illiteracy
├── Fase_2_1_ML.ipynb                       # Entrenamiento de modelos 
├── Fase_3_DL.ipynb                         # Entrenamiento y evaluación de EEGNet
├── Fase_4_.ipynb                           # Test de Robustez (cross-subject / cross-dataset)
└── README.md                               # Documentación del proyecto
