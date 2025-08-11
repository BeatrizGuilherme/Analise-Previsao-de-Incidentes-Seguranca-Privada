**Projeto: Análise e Previsão de Incidentes em Segurança Privada🛡️📊**

**Introdução 🚀**

Este projeto foi desenvolvido para realizar uma análise exploratória, preditiva e de monitoramento de indicadores em uma empresa fictícia de segurança privada. Utilizamos Python para o tratamento e modelagem dos dados, e Power BI para criar dashboards interativos que facilitam a tomada de decisões estratégicas.

**Dataset 📁**
* **Volume**: 5.000 registros

* **Período**: Últimos 2 anos

* **Características**: Dados simulados contemplando tipos de incidentes, regiões, clientes, tempo de resposta, custos e gravidade dos incidentes.

* **Qualidade**: Nenhum valor nulo encontrado.

**Análise Exploratória** 🔍
* Distribuição dos incidentes por cliente, região, tipo e gravidade.

* Identificação de padrões temporais, como aumento de incidentes entre jul/23 e ago/23.

* Relações entre variáveis numéricas como custo e tempo de resposta, apresentando baixa correlação.

* Insights importantes:

  * Cliente_15 com maior número de incidentes (277)

  * Zona Oeste como região com mais ocorrências (1.059)

  * Furtos e falsos alarmes dominam os registros

  * Maioria dos incidentes com gravidade baixa, mas impacto financeiro relevante em casos graves

* Código utilizado para gerar gráficos de distribuição, correlações e KPIs.

**Modelagem Preditiva** 🎯

**Problema Identificado**
Alto desbalanceamento entre classes (3,2% incidentes graves), que fazia os modelos preverem sempre a classe majoritária (não grave).

**Modelos Testados**

* Regressão Logística

* Random Forest

**Métricas Antes da Correção**

| Modelo              | Acurácia | ROC AUC | Recall Classe 1 | Observação                           |
| ------------------- | -------- | ------- | --------------- | ------------------------------------ |
| Regressão Logística | 0.8933   | 0.4834  | 0.00            | Predição sempre classe 0 (não grave) |
| Random Forest       | 0.8933   | 0.5022  | 0.00            | Mesmo problema                       |

**Correções Aplicadas**

* Uso do SMOTE para oversampling da classe minoritária

* Ajuste dos pesos das classes nos modelos

**Métricas Depois da Correção**

| Modelo              | Acurácia | ROC AUC | Recall Classe 1 | Observação                               |
| ------------------- | -------- | ------- | --------------- | ---------------------------------------- |
| Regressão Logística | 0.8222   | 0.8808  | 0.73            | Boa identificação de incidentes graves   |
| Random Forest       | 0.9570   | 0.9895  | 0.94            | Excelente desempenho, modelo recomendado |

**Insights do Modelo Corrigido** 💡

* Principais variáveis preditoras: custo da segurança, tempo de resposta, hora do incidente e número de vigilantes.

* Técnicas de balanceamento tornaram os modelos capazes de detectar incidentes graves com alta precisão.

* Random Forest destacou-se como o melhor modelo para apoio à decisão.

**Dashboards no Power BI** 📊

**Página 1**

* Cartões de resumo com custo real e previsto, além da quantidade de incidentes reais e previstos.

* Treemap de custo por região (destaque para Zona Oeste e Sul).

* Gráfico de linha mostrando custo real superior ao previsto em todos os meses.

**Página 2**

* Número de clientes (20) e vigilantes (máximo 10).

* Gráficos de incidentes por gravidade e custo real por gravidade, evidenciando maior impacto dos incidentes de baixa gravidade pelo volume.

* Incidentes por região e análise temporal destacando aumento gradual.

**Página 3**

* Custos por tipo de incidente e tecnologia, com destaque para falsos alarmes e falhas no sistema gerando custos elevados.

* Análise do tempo de resposta por tipo de incidente.

* Situação da resolução dos incidentes, com 1.000 casos ainda não resolvidos.

**Próximos Passos** 🔜

* Continuar monitoramento do modelo em produção para manter desempenho.

* Investigar tecnologias para redução de custos com falsos alarmes e falhas.

* Avaliar políticas para otimização do tempo de resposta.

* Atualizar periodicamente os dados e reavaliar variáveis importantes.

**Tecnologias utilizadas** 🧰

* Python (pandas, scikit-learn, imblearn, matplotlib, seaborn)

* Power BI Desktop

**Como rodar o projeto** 🛠️

1. Clonar este repositório.

2. Executar os scripts Python na ordem indicada (preparação dos dados, modelagem, avaliação).

3. Abrir o arquivo do Power BI para explorar os dashboards.

Qualquer dúvida ou sugestão será bem-vinda! 🙌
