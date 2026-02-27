# 🌊 BAZOFIA_MONITOR (Protótipo)

O **BAZOFIA_MONITOR** é um dashboard de monitorização hidrológica em tempo real Da bacia do Mondego, zona de Coimbra (e possívelmente Baixo Mondego). O projeto utiliza dados públicos para prever e alertar sobre potenciais cenários de cheia em pontos críticos.

---

## Funcionalidades Principais

* **Monitorização em Tempo Real:** Integração via proxy com dados da APA (Agência Portuguesa do Ambiente) e IPMA/Tideschart( ainda por testar).
* **Cálculo Dinâmico de Risco:** Algoritmo que cruza o caudal afluente ($Q$), a cota do Açude de Coimbra ($hA$) e a influência das marés na Figueira da Foz.
* **Visualização Geográfica:** Mapa interativo baseado em Leaflet.js com indicadores visuais (pulsação em pontos de cheia).
* **Segmentação de Regimes:** * **Regime A:** Focado no núcleo urbano de Coimbra (influência direta do Açude).
    * **Regime B:** Focado no Baixo Mondego (influência mista de caudal e maré).

---

## Tecnologias Utilizadas

* **Frontend:** HTML5, CSS3 (Modern Dark UI), JavaScript (ES6+).
* **Mapas:** [Leaflet.js](https://leafletjs.com/) com tiles Dark Mode da CartoDB.
* **Dados:** Fetch API com integração de proxies para contornar políticas de CORS em dados da APA e IPMA.
* **IA:** Desenvolvido com auxílio de Inteligência Artificial para otimização de lógica e estruturação de dados geográficos.

---

##  Indicadores de Estado

O sistema classifica cada ponto monitorizado em quatro estados distintos:

| Estado | Descrição | Cor |
| :--- | :--- | :--- |
| **SECO** | Nível de água abaixo da cota do solo. | Verde |
| **RISCO** | Nível de água a menos de 0.5m da cota de transbordo. | Amarelo |
| **REFLUXO** | Água ao nível do solo, possível entrada via saneamento. | Laranja |
| **GALGAMENTO** | Nível de água superior ao muro de proteção/cota máxima. | Vermelho (Pulsante) |

---

## ⚙️ Como Executar

1.  Acede à versão online: https://joaosoaresesilva.github.io/exp/monda/index.html
2.  **Nota:** O projeto utiliza o proxy `allorigins` para obter dados externos. Certifica-te de que tens ligação à internet.

---

## Isenção de Responsabilidade (Disclaimer)

Este software é um **protótipo conceptual** realizado com auxílio de IA. Os cálculos de nível e as previsões de galgamento baseiam-se em fórmulas simplificadas para fins de demonstração e não devem ser utilizados como única fonte para decisões de segurança civil ou proteção de bens. Consulta sempre os avisos oficiais da **Proteção Civil** e da **APA**.

---

**Desenvolvido por:** [João Silva/joaosoaresesilva.github.io]  
**Localização:** Coimbra, Portugal 
