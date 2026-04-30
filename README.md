# 🚂 Localizador de Paradas de Trens | CCO - Malha Sul

Um sistema web ágil e responsivo desenvolvido para o Centro de Controle Operacional (CCO) da Malha Sul. Este aplicativo tem como objetivo otimizar o tempo de resposta em ocorrências ferroviárias, permitindo a localização exata de trens ou veículos de via e o despacho imediato de equipes de atendimento via WhatsApp, com cálculo automático de rotas rodoviárias.

🔗 **[Acessar o Painel Ao Vivo](https://ewertonmedeiros.github.io/localizador-de-paradas/)**

---

## 🚀 Funcionalidades

*   **Busca Precisa por Coordenadas:** Inserção de Latitude e Longitude para plotagem instantânea da ocorrência no mapa.
*   **Identificação de Frota:** Campo obrigatório para o Prefixo do trem/veículo (ex: M12), garantindo que a equipe saiba exatamente o que irá atender.
*   **Despacho via WhatsApp (One-Click):** Geração automática de mensagens formatadas com dados da ocorrência, alertas de segurança e um link inteligente.
*   **Roteamento Inteligente (Equipe de Campo):** Leitura de URL com parâmetros (`?prefixo=&lat=&lng=`) que preenche os dados automaticamente para a equipe em campo.
*   **Cálculo de Rota e ETA:** Integração com a API OSRM para calcular a distância rodoviária e o tempo estimado de chegada (ETA) a partir da localização via GPS do celular do funcionário.
*   **Integração com GPS Nativo:** Opção de abrir a rota diretamente no Google Maps/Waze do smartphone para navegação curva a curva.
*   **Interface UI/UX Unificada:** Design responsivo (Desktop/Mobile) que segue a identidade visual do *Monitor Systemp*, garantindo padronização e profissionalismo.

---

## 🛠️ Tecnologias Utilizadas

Este projeto foi construído focando em alta disponibilidade e zero custo de infraestrutura (sem necessidade de chaves de API pagas):

*   **Frontend:** HTML5, CSS3 (Variáveis, Flexbox, Media Queries), JavaScript Vanilla.
*   **Mapas:** [Leaflet.js](https://leafletjs.com/) utilizando os tiles de alta performance da **CartoDB** (evitando bloqueios de CORS em arquivos locais).
*   **Roteamento:** [OSRM API](http://project-osrm.org/) (Open Source Routing Machine) para cálculo de distância e tempo via malha rodoviária.
*   **Geolocalização:** API nativa do navegador (`navigator.geolocation`).

---

## 🔄 Como Funciona o Fluxo de Operação?

O sistema funciona como uma aplicação de mão dupla (CCO ↔ Equipe de Campo):

1.  **Ação do CCO (Desktop):** O operador do CCO recebe a informação de um trem avariado. Ele insere o Prefixo, Latitude e Longitude no sistema. O sistema plota o mapa.
2.  **Despacho:** O operador clica em *"Deslocar Equipe (WhatsApp)"*. O sistema gera um link encapsulando as informações na própria URL.
3.  **Ação da Equipe (Mobile):** O mecânico/técnico clica no link recebido no WhatsApp. O aplicativo abre já preenchido e centralizado na ocorrência.
4.  **Deslocamento:** O técnico clica em *"Traçar Minha Rota"*. O sistema pega o GPS do celular dele, calcula a quilometragem e o tempo até o trem, e libera o botão para iniciar a navegação no Google Maps.

---

## ⚙️ Como Executar o Projeto

Por ser uma aplicação inteiramente baseada em tecnologias client-side (Frontend), a execução é extremamente simples:

1. Clone este repositório:
   ```bash
   git clone [https://github.com/seu-usuario/nome-do-repositorio.git](https://github.com/seu-usuario/nome-do-repositorio.git)
