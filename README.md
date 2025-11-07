# Monitoramento Meteorológico Online da Zona Rural de Charqueadas
O projeto surge a partir de uma demanda da **EMATER de Charqueadas**, instituição que presta assistência técnica essencial aos produtores rurais da região. Atualmente, a EMATER não dispõe de uma ferramenta digital para o acompanhamento agrometeorológico local, dependendo de dados manuais e dispersos — como medições de pluviômetros convencionais enviadas por e-mail. Essa limitação impacta diretamente as decisões estratégicas do agronegócio, como o planejamento de safras e a decretação de situação de calamidade pública.

Em resposta a essa necessidade, estudantes da turma de **Atividade de Extensão II** do curso de Tecnologia em Sistemas para Internet do IFSul desenvolveram uma prova de conceito de um dashboard interativo, integrando dados de fontes públicas e projetando uma futura rede de pluviômetros IoT de baixo custo conectados a uma API própria do Instituto 

Está assumido que, em cada distrito, estará instalado um pluviômetro IoT que envia medições para uma API, projetando uma futura rede de pluviômetros IoT de baixo custo, conectados a uma API própria do IFSul. A rede de pluviômetros pode ser desenvolvida por outros projetos. _A dashboard, combinada com os pluviômetros, permitirá à EMATER e aos produtores rurais o monitoramento em tempo real das condições climáticas dos principais distritos rurais de Charqueadas e, futuramente, de toda a região carbonífera._

### APIs Públicas de dados meteorológicos 

- **EMBRAPA** - a [AgroAPI](https://www.agroapi.cnptia.embrapa.br/portal/) da EMBRAPA fornece dados baseados em latitude e longitude, atualmente utilizados na demonstração da POC. Limitações: os dados se mostraram bastante imprecisos e há uma quantidade limitada de requisições gratuitas mensais.
- **INMET** - Dados do [Instituto Nacional de Meteorologia](https://tempo.inmet.gov.br/TabelaEstacoes/B812) também foram avaliados, mas o INMET não possui API pública para consulta de dados e, em Charqueadas, há apenas uma estação meteorológica. Para emular a rede de pluviômetros, um ponto de dados é insuficiente.

## Apêndice - texto dos alunos

As ferramentas e tecnologias utilizadas nos códigos para o mapa interativo foram:

1. **React + Vite** - Esta é a base do projeto. React é uma biblioteca JavaScript para construir interfaces de usuário de forma declarativa e eficiente. Vite é um "bundler" e servidor de desenvolvimento extremamente rápido que otimiza a forma como o código é empacotado para o navegador. A combinação dos dois é uma das pilhas de tecnologia mais populares e eficientes para criar aplicações web modernas.
2. **Leaflet** - É uma biblioteca JavaScript de código aberto e totalmente gratuita, projetada para criar mapas interativos. A principal vantagem do Leaflet é que ele é leve e focado em simplicidade, mas ainda assim oferece todas as funcionalidades essenciais de mapeamento, como zoom, pan e marcações, sem a necessidade de APIs pagas.
3. **React-Leaflet** - Esta biblioteca funciona como uma "ponte" entre o React e o Leaflet. Em vez de manipular o DOM diretamente como o Leaflet faz, o React-Leaflet permite que você use os recursos do Leaflet como componentes React. Isso torna a criação e o gerenciamento do mapa mais "React-like", aproveitando o sistema de componentes, o estado e as propriedades.
4. **React Router DOM** - O React Router DOM é a biblioteca padrão para gerenciar a navegação em aplicações React de página única (Single Page Applications). Ele permite que você defina diferentes rotas (URLs) para sua aplicação, como / para o mapa principal e /bairro/:nomeBairro para a página de detalhes, criando uma experiência de navegação fluida sem recarregar a página inteira.
5. **OpenStreetMap** - O OpenStreetMap (OSM) é uma fonte de dados de mapas gratuita e de código aberto, criada por uma comunidade global. É a "base" visual do mapa que aparece no seu projeto. Utilizamos os TileLayers do OSM, que são as "peças" de imagem do mapa, para preencher o fundo da sua aplicação. É uma excelente alternativa gratuita a serviços como Google Maps ou Mapbox, que costumam cobrar pelo uso.

Em resumo, a escolha dessas ferramentas foi baseada em uma combinação de fatores: elas são gratuitas, amplamente utilizadas na comunidade e se integram de forma coesa para oferecer uma solução completa e eficiente para o projeto.

### Utilizacao

** Caso erro 429, token expirou e deve ser gerado novamente. Para isso, seguir instruções do arquivo agroapi-primeiros-passos-token.pdf. **
** Após gerar token, substituir no arquivo .env **

```bash
### Instalação de Pacotes
npm install
npm install @phosphor-icons/react
npm install react-router-dom
npm install react-chartjs-2 chart.js
```bash
