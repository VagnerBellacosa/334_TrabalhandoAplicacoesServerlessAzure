# O que são Aplicativos Lógicos do Azure?

- Artigo
- 14/06/2024
- 13 colaboradores

Comentários

Neste artigo[Principais termos](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-overview#key-terms)[Por que usar os Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-overview#why-use-azure-logic-apps)[Como os Aplicativos Lógicos do Azure diferem do Functions, dos WebJobs e do Power Automate?](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-overview#how-does-azure-logic-apps-differ-from-functions-webjobs-and-power-automate)[Como os Aplicativos Lógicos do Azure diferem dos Runbooks de Automação do Azure?](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-overview#how-does-azure-logic-apps-differ-from-azure-automation-runbooks)Mostrar mais 5

Os Aplicativos Lógicos do Azure são uma plataforma de nuvem onde você pode criar e executar fluxos de trabalho automatizados com pouco ou nenhum código. Usando o designer visual e selecionando operações pré-criadas, você pode criar rapidamente um fluxo de trabalho que integra e gerencia seus aplicativos, dados, serviços e sistemas.

Os Aplicativos Lógicos do Azure simplificam a maneira como você conecta sistemas herdados, modernos e de ponta em ambientes de nuvem, locais e híbridos. Você pode usar ferramentas de baixo código sem código para desenvolver soluções de integração altamente escalonáveis que dão suporte a cenários corporativos e de negócios para empresas (B2B).

Esta lista descreve apenas alguns exemplos de tarefas, processos de negócios e cargas de trabalho que você pode automatizar usando os Aplicativos Lógicos do Azure:

- Agende e envie notificações por email usando o Office 365 quando ocorrer um evento específico, por exemplo, um novo arquivo for carregado.
- Encaminhe e processe pedidos de clientes entre sistemas locais e serviços de nuvem.
- Mova arquivos carregados de um servidor SFTP ou FTP para o Armazenamento do Azure.
- Monitore tweets, analise o sentimento e crie alertas ou tarefas para itens que exigem revisão.

O fluxo de trabalho empresarial de exemplo parcial a seguir usa condições e opções para determinar a próxima ação. Suponha que você tenha um sistema de pedidos e seu fluxo de trabalho processe pedidos de entrada. Você deseja revisar manualmente os pedidos acima de um determinado custo. O fluxo de trabalho já tem etapas anteriores que determinam quanto custa um pedido de entrada. Portanto, você cria uma condição inicial com base nesse valor de custo, por exemplo:

[![A captura de tela mostra o designer de fluxo de trabalho e um fluxo de trabalho empresarial de exemplo que usa opções e condições.](https://learn.microsoft.com/pt-br/azure/logic-apps/media/logic-apps-overview/example-enterprise-workflow.png)](https://learn.microsoft.com/pt-br/azure/logic-apps/media/logic-apps-overview/example-enterprise-workflow.png#lightbox)

 Dica

Para saber mais, você pode fazer estas perguntas ao Copilot no Azure:

- *Quais problemas posso resolver com os Aplicativos Lógicos do Azure?*
- *Quais benefícios os Aplicativos Lógicos do Azure oferecem?*

Para localizar o Copilot no Azure, na barra de ferramentas do [portal do Azure](https://portal.azure.com/), selecione **Copilot**.

Se você estiver pronto para tentar criar seu primeiro fluxo de trabalho do aplicativo lógico, veja [Introdução](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-overview#get-started).

Para continuar aprendendo mais, experimente este vídeo:

<iframe src="https://learn-video.azurefd.net/vod/player?show=azure-friday&amp;ep=integrate-your-mainframes-and-midranges-with-azure-logic-apps&amp;locale=pt-br&amp;embedUrl=%2Fazure%2Flogic-apps%2Flogic-apps-overview" frameborder="0" allowfullscreen="true" data-linktype="external" style="box-sizing: inherit; outline-color: inherit; margin: 0px; padding: 0px; border: 0px; width: 640px; height: 360px; inset: 0px;"></iframe>

Para obter mais informações, visite [Aplicativos Lógicos do Azure no site do Azure](https://azure.microsoft.com/services/logic-apps) e em outros [Serviços de integração do Azure](https://azure.microsoft.com/product-categories/integration/).





## Principais termos

A tabela a seguir define brevemente os principais conceitos e terminologia nos Aplicativos Lógicos do Azure.

Expandir a tabela

| Termo                   | Descrição                                                    |
| :---------------------- | :----------------------------------------------------------- |
| **Aplicativo lógico**   | O recurso do Azure que você cria quando deseja criar um fluxo de trabalho. Basicamente, você pode criar os seguintes tipos de recursos de aplicativo lógico:  – Um recurso de aplicativo lógico de **consumo** que dá suporte a um único fluxo de trabalho, que é hospedado e executado em Aplicativos Lógicos multilocatários globais do Azure  - Um recurso de aplicativo lógico **Standard** que dá suporte a vários fluxos de trabalho, que são hospedados e executados em Aplicativos Lógicos do Azure de locatário único  Saiba mais sobre [tipos de recursos de aplicativo lógico, juntamente com seus respectivos modelos de recursos de computação e cobrança](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-overview#resource-environment-differences). |
| **Fluxo de trabalho**   | Uma série de operações que definem uma tarefa, um processo empresarial ou uma carga de trabalho. Cada fluxo de trabalho sempre começa com uma única operação de gatilho, após a qual você deve adicionar uma ou mais operações de ação. |
| **Gatilho**             | A primeira operação em qualquer fluxo de trabalho que especifica os critérios a serem executados antes de executar as operações subsequentes nesse fluxo de trabalho. Por exemplo, um evento de gatilho pode estar recebendo um email em sua caixa de entrada ou detectando um novo arquivo em uma conta de armazenamento. |
| **Ação**                | Cada operação subsequente que segue o gatilho no fluxo de trabalho. |
| **Conector interno**    | Esse tipo de operação ou conector é "integrado" ao runtime dos Aplicativos Lógicos do Azure para que as operações sejam executadas nativamente e diretamente com o runtime para um desempenho mais rápido, em comparação com os conectores gerenciados pela Microsoft que são hospedados e executados no Azure.  As operações internas fornecem maneiras de controlar a agenda ou a estrutura do fluxo de trabalho, executar seu próprio código, gerenciar e manipular dados, enviar ou receber solicitações para um ponto de extremidade e concluir outras tarefas em seu fluxo de trabalho.  Por exemplo, você pode iniciar quase qualquer fluxo de trabalho em um agendamento ao usar o gatilho de **recorrência**. Ou você pode fazer com que o fluxo de trabalho aguarde até ser chamado quando usar o gatilho **Solicitação**. Essas operações geralmente não exigem que você crie uma conexão com base no fluxo de trabalho.  Embora a maioria das operações internas não esteja associada a nenhum serviço ou sistema, algumas operações internas estão disponíveis para serviços específicos, como o Azure Functions, o Armazenamento de Blobs do Azure, o Serviço de Aplicativo do Azure e muito mais. A disponibilidade dessas operações internas depende se você está trabalhando em um fluxo de trabalho de Consumo ou aplicativo lógico Standard. Para obter mais informações e exemplos, consulte [conectores internos para Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/connectors/built-in). |
| **Conector gerenciado** | Esse tipo de operação ou conector é publicado Microsoft, gerenciado, hospedado e executado no Azure e é um proxy ou wrapper predefinido para um serviço ou para a API REST do sistema, que você pode usar para acessar um aplicativo, dados, serviço ou sistema específicos. Para usar a maioria dos conectores gerenciados, primeiro, crie uma conexão por meio do fluxo de trabalho e autentique sua identidade.  Por exemplo, você pode iniciar um fluxo de trabalho com um gatilho ou executar uma ação que funciona com um serviço, como Office 365, Salesforce ou servidores de arquivo. Para saber mais, confira [Conectores gerenciados para Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/connectors/managed). |
| **Conta de integração** | Crie este recurso do Azure quando desejar definir e armazenar artefatos B2B para uso em seus fluxos de trabalho. Depois de [criar e vincular uma conta de integração](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-create-integration-account) ao aplicativo lógico, seus fluxos de trabalho podem usar os artefatos B2B. Os fluxos de trabalho também podem trocar mensagens que seguem os padrões EDI (Electronic Data Interchange) e EAI (Enterprise Application Integration).  Por exemplo, você pode definir parceiros comerciais, contratos, esquemas, mapas e outros artefatos B2B. Você pode criar fluxos de trabalho que usam esses artefatos e trocar mensagens por protocolos como AS2, EDIFACT, X12 e RosettaNet. |



## Por que usar os Aplicativos Lógicos do Azure

A plataforma de integração dos Aplicativos Lógicos do Azure fornece [mais de 1.000 conectores predefinidos](https://learn.microsoft.com/pt-br/connectors/connector-reference/connector-reference-logicapps-connectors) para que você possa se conectar e integrar aplicativos, dados, serviços e sistemas com mais facilidade e rapidez. Você pode se concentrar mais na criação e implementação da lógica e funcionalidade de negócios da sua solução, enquanto gasta menos energia para descobrir como acessar seus recursos.

Para se comunicar com qualquer ponto de extremidade de provedor, execute seu próprio código, controle sua estrutura de fluxo de trabalho, manipule dados ou conecte-se a serviços comumente usados com melhor desempenho, você pode usar [operações de conector interno](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-overview#logic-app-concepts). Essas operações são executadas nativamente no runtime dos Aplicativos Lógicos do Azure para obter um desempenho mais rápido.

Para acessar e trabalhar com recursos em serviços como Azure, Microsoft, outros aplicativos e serviços Web externos ou sistemas locais, você pode usar [operações de conector gerenciadas pela Microsoft (hospedadas no Azure)](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-overview#logic-app-concepts). Escolha entre [mais de 1.0000 conectores em um ecossistema do Azure em constante expansão](https://learn.microsoft.com/pt-br/connectors/connector-reference/connector-reference-logicapps-connectors), por exemplo:

- Serviços do Azure, como Armazenamento de Blobs e Barramento de Serviço
- Serviços do Office 365, como Outlook, Excel e SharePoint
- Servidores de banco de dados, como SQL e Oracle
- Sistemas corporativos, como SAP e IBM MQ
- Compartilhamentos de arquivos, como FTP e SFTP

Para saber mais, confira a seguinte documentação:

- [Sobre conectores nos Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/connectors/introduction)
- [Conectores internos](https://learn.microsoft.com/pt-br/azure/connectors/built-in)
- [Conectores gerenciados](https://learn.microsoft.com/pt-br/azure/connectors/managed)

Ao criar fluxos de trabalho nos Aplicativos Lógicos do Azure, você geralmente não precisa escrever nenhum código. No entanto, se você precisar escrever algum código, poderá adicionar e executar snippets de código JavaScript ou scripts C# em seu fluxo de trabalho usando a ação **Código Embutido** para [JavaScript](https://learn.microsoft.com/pt-br/azure/logic-apps/add-run-javascript) ou [C#](https://learn.microsoft.com/pt-br/azure/logic-apps/add-run-csharp-scripts), respectivamente. Você também pode adicionar e executar código usando o [Azure Functions](https://learn.microsoft.com/pt-br/azure/azure-functions/functions-overview). Se o fluxo de trabalho precisar interagir com eventos dos serviços do Azure, aplicativos personalizados ou outras soluções, você poderá monitorar, rotear e publicar eventos usando a [Grade de Eventos do Azure](https://learn.microsoft.com/pt-br/azure/event-grid/overview) ou os [Hubs de Eventos do Azure](https://learn.microsoft.com/pt-br/azure/event-hubs/event-hubs-about).

Os Aplicativos Lógicos do Azure são totalmente gerenciados pelo Microsoft Azure, o que livra você de preocupações sobre hospedagem, dimensionamento, gerenciamento, monitoramento e manutenção de soluções com esses serviços. Ao usar essas funcionalidades para criar [aplicativos e soluções "sem servidor"](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-serverless-overview), você pode apenas se concentrar na funcionalidade e na lógica de negócios. Esses serviços são dimensionados automaticamente de acordo com as suas necessidades, para fazer integrações mais rapidamente e ajudar você a criar aplicativos de nuvem robustos usando pouco ou nenhum código.

Para saber como outras empresas aprimoraram a agilidade e o foco nos negócios principais ao combinar os Aplicativos Lógicos do Azure com outros serviços do Azure e produtos da Microsoft, confira estas [histórias dos clientes](https://aka.ms/logic-apps-customer-stories).



## Como os Aplicativos Lógicos do Azure diferem do Functions, dos WebJobs e do Power Automate?

Todos esses serviços ajudam você a conectar e reunir sistemas diferentes. Cada serviço tem suas vantagens e benefícios, e combinar seus recursos é a melhor maneira de criar rapidamente um sistema de integração completa escalonável. Para obter mais informações, consulte [Escolher entre Aplicativos Lógicos do Azure, Azure Functions, Azure WebJobs e Microsoft Power Automate](https://learn.microsoft.com/pt-br/azure/azure-functions/functions-compare-logic-apps-ms-flow-webjobs).



## Como os Aplicativos Lógicos do Azure diferem dos Runbooks de Automação do Azure?

Os [Runbooks de Automação do Azure](https://learn.microsoft.com/pt-br/azure/automation/automation-runbook-types) fornecem uma solução leve e econômica para correções simples, como reiniciar máquinas virtuais. Por outro lado, os Aplicativos Lógicos do Azure são ideais para fluxos de trabalho e orquestrações entre vários serviços, sistemas, aplicativos e dados. incluindo cargas de trabalho que executam código personalizado ou exigem lógica complexa que usa estruturas de controle, como loops, ramificação, condições e muito mais.



## Com que rapidez posso incrementar minhas soluções com os Aplicativos Lógicos do Azure?

Comece discretamente com seus serviços e seus sistemas atuais e cresça incrementalmente no seu ritmo. Quando você estiver pronto, os Aplicativos Lógicos do Azure ajudarão você a implementar e escalar verticalmente cenários de integração mais maduros fornecendo os seguintes recursos e benefícios.



### Crie e edite fluxos de trabalho visualmente com ferramentas fáceis de usar

Economize tempo e simplifique processos complexos usando as ferramentas de design visual dos Aplicativos Lógicos do Azure. Crie seus fluxos de trabalho do início ao fim usando o designer de fluxo de trabalho dos Aplicativos Lógicos do Azure no portal do Azure ou no Visual Studio Code. Basta iniciar o fluxo de trabalho com um gatilho e adicionar várias ações por meio da [galeria de conectores](https://learn.microsoft.com/pt-br/connectors/connector-reference/connector-reference-logicapps-connectors).



### Conectar diferentes sistemas em vários ambientes

Alguns padrões e processos são fáceis de descrever, mas difíceis de implementar no código. Os Aplicativos Lógicos do Azure ajudam você a conectar perfeitamente sistemas diferentes em ambientes de nuvem, locais e híbridos. Por exemplo, você pode conectar uma solução de marketing de nuvem a um sistema de cobrança local ou centralizar as mensagens entre APIs e sistemas usando o Barramento de Serviço do Azure. Os Aplicativos Lógicos do Azure fornecem uma forma rápida, confiável e consistente de fornecer soluções reutilizáveis e reconfiguráveis para esses cenários.





### Criar e implantar em ambientes diferentes

Com base em seu cenário, requisitos de solução e recursos desejados, escolha se deseja criar um fluxo de trabalho de aplicativo lógico Standard ou de Consumo. Com base nessa escolha, o fluxo de trabalho é executado em Aplicativos Lógicos do Azure multilocatários, aplicativos lógicos do Azure de locatário único ou em um Ambiente do Serviço de Aplicativo (v3). Com os Aplicativos Lógicos do Azure de locatário único, seus fluxos de trabalho podem acessar com mais facilidade recursos protegidos por redes virtuais do Azure. Se você criar fluxos de trabalho baseados em locatário único usando aplicativos lógicos habilitados para Azure Arc, também poderá executar fluxos de trabalho em contêineres. Para obter mais informações, consulte [Locatário único versus multilocatário nos Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/single-tenant-overview-compare) e [O que são os Aplicativos Lógicos habilitados para Arc](https://learn.microsoft.com/pt-br/azure/logic-apps/azure-arc-enabled-logic-apps-overview)?

A tabela a seguir resume brevemente as diferenças entre um fluxo de trabalho de aplicativo lógico de consumo e padrão. Você também aprenderá as diferenças entre o ambiente multilocatário, o ambiente de locatário único e o AMBIENTE do Serviço de Aplicativo v3 (ASEv3) para implantação, hospedagem e execução de fluxos de trabalho de aplicativo lógico.

Expandir a tabela

| Opção de hospedagem                                          | Benefícios                                                   | Uso e compartilhamento de recursos                           | [Modelo de preço e cobrança](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-pricing) | [Gerenciamento de limites](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-limits-and-config) |
| :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| **Consumo**  Ambiente de host: Aplicativos Lógicos do Azure multilocatário | – Mais fácil de começar a usar  – Pague apenas pelo que você usar  – Totalmente gerenciado | Um recurso de aplicativo lógico individual pode ter *apenas um* fluxo de trabalho.  Todos os aplicativos lógicos *nos locatários do Microsoft Entra* compartilham o mesmo processamento (computação), armazenamento, rede etc.  Para fins de redundância, os dados são replicados na [região emparelhada](https://learn.microsoft.com/pt-br/azure/reliability/cross-region-replication-azure). Para alta disponibilidade, o [GRS (armazenamento com redundância geográfica)](https://learn.microsoft.com/pt-br/azure/storage/common/storage-redundancy#geo-redundant-storage) está habilitado. | [Consumo](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-pricing#consumption-pricing) (pagamento por execução) | Os Aplicativos Lógicos do Azure gerenciam os valores padrão desses limites, mas você pode alterar alguns desses valores, se essa opção existir para um limite específico. |
| **Standard (plano de serviço de fluxo de trabalho)**  Ambiente de host: Aplicativos Lógicos do Azure de locatário único  **Observação**: se seu cenário exigir contêineres, [crie aplicativos lógicos baseados em locatário único usando os Aplicativos Lógicos habilitados para Azure Arc](https://learn.microsoft.com/pt-br/azure/logic-apps/azure-arc-enabled-logic-apps-create-deploy-workflows). Para obter mais informações, confira [O que são Aplicativos Lógicos habilitados para Azure Arc](https://learn.microsoft.com/pt-br/azure/logic-apps/azure-arc-enabled-logic-apps-overview)? | – Mais conectores internos hospedados no runtime de locatário único para maior taxa de transferência e custos mais baixos em escala  – Mais controle e funcionalidade de ajuste em relação às configurações de runtime e desempenho  – Suporte integrado para redes virtuais e pontos de extremidade privados.  – Crie seus próprios conectores integrados. | Um recurso de aplicativo lógico individual pode ter vários fluxos de trabalho [*com estado* e *sem monitoração de estado*](https://learn.microsoft.com/pt-br/azure/logic-apps/single-tenant-overview-compare#stateful-stateless).  Os fluxos de trabalho *em um único aplicativo lógico e locatário* compartilham o mesmo processamento (computação), armazenamento, rede e assim por diante.  Os dados permanecem na mesma região em que você implanta seu aplicativo lógico. | [Standard](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-pricing#standard-pricing), com base em um plano de hospedagem com um tipo de preço selecionado.  Se você executar fluxos de trabalho *com estado*, que usam [armazenamento externo](https://learn.microsoft.com/pt-br/azure/azure-functions/storage-considerations#storage-account-requirements), o runtime dos Aplicativos Lógicos do Azure farão as transações de armazenamento que acompanham o [preço do Armazenamento do Azure](https://azure.microsoft.com/pricing/details/storage/). | Você pode alterar os valores padrão para muitos limites com base nas necessidades do cenário.  **Importante**: alguns limites têm máximos rígidos. No Visual Studio Code, as alterações feitas nos valores de limite padrão nos arquivos de configuração do projeto do aplicativo lógico não serão exibidas na experiência do designer. Para obter mais informações, confira [Editar configurações de aplicativo e ambiente para aplicativos lógicos nos Aplicativos Lógicos do Azure de locatário único](https://learn.microsoft.com/pt-br/azure/logic-apps/edit-app-settings-host-settings). |
| **Standard (Ambiente do Serviço de Aplicativo v3)**  Ambiente de host: [ASEv3 (Ambiente do Serviço de Aplicativo v3) – Somente planos do Windows](https://learn.microsoft.com/pt-br/azure/app-service/environment/overview) | Alguns recursos como locatário único *mais* estes benefícios:  – Isole totalmente seus aplicativos lógicos.  – Crie e execute mais aplicativos lógicos do que nos Aplicativos Lógicos do Azure de locatário único.  – Pague apenas pelo plano do Serviço de Aplicativo do ASE, independentemente do número de aplicativos lógicos que você criar e executar.  – Possibilidade de habilitar o dimensionamento automático ou de dimensionar manualmente com mais instâncias de máquina virtual ou um plano do Serviço de Aplicativo diferente.  – Herde a configuração de rede do ASEv3 selecionado. Por exemplo, quando você faz a implantação em um ASE interno, os fluxos de trabalho podem acessar os recursos em uma rede virtual associada ao ASE e ter pontos de acesso internos.  **Observação**: se acessado de fora de um ASE interno, os históricos de execução dos fluxos de trabalho nesse ASE não poderão acessar entradas e saídas de ação. | Um único aplicativo lógico pode ter vários fluxos de trabalho [*com estado* e *sem estado*](https://learn.microsoft.com/pt-br/azure/logic-apps/single-tenant-overview-compare#stateful-stateless).  Os fluxos de trabalho *em um único aplicativo lógico e locatário* compartilham o mesmo processamento (computação), armazenamento, rede e assim por diante.  Os dados continuam na mesma região em que você implanta os aplicativos lógicos. | [Plano do Serviço de Aplicativo](https://azure.microsoft.com/pricing/details/app-service/windows/) | Você pode alterar os valores padrão para muitos limites com base nas necessidades do cenário.  **Importante**: alguns limites têm máximos rígidos. No Visual Studio Code, as alterações feitas nos valores de limite padrão nos arquivos de configuração do projeto do aplicativo lógico não serão exibidas na experiência do designer. Para obter mais informações, confira [Editar configurações de aplicativo e ambiente para aplicativos lógicos nos Aplicativos Lógicos do Azure de locatário único](https://learn.microsoft.com/pt-br/azure/logic-apps/edit-app-settings-host-settings). |



### Suporte de primeira classe para cenários de Enterprise Integration e B2B

As empresas e as organizações comunicam-se eletronicamente entre si usando o padrão do setor, mas diferentes protocolos e formatos de mensagens, como EDIFACT, AS2, X12 e RosettaNet. Usando as [funcionalidades de integração corporativa](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-overview) com suporte dos Aplicativos Lógicos do Azure, você pode criar fluxos de trabalho que transformam os formatos de mensagem usados por parceiros comerciais em formatos que podem ser interpretados e processados pelos sistemas da sua organização. Os Aplicativos Lógicos do Azure tratam dessas trocas sem problemas e com segurança, usando assinaturas digitais e criptografia. Para cenários de integração B2B, os Aplicativos Lógicos do Azure incluem recursos do [BizTalk Server](https://learn.microsoft.com/pt-br/biztalk/core/introducing-biztalk-server). Para definir artefatos B2B (business-to-business ), crie uma [*conta de integração*](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-overview#logic-app-concepts) na qual você armazenará esses artefatos. Depois de vincular essa conta ao recurso de aplicativo lógico, o fluxo de trabalho poderá usar esses artefatos B2B e trocar mensagens que estejam em conformidade com os padrões EDI (Electronic Data Interchange) e EAI (Enterprise Application Integration).

Para saber mais, confira a seguinte documentação:

- Integrar e criar soluções baseadas no [Microsoft BizTalk Server](https://learn.microsoft.com/pt-br/biztalk/core/introducing-biztalk-server), no [Barramento de Serviço do Azure](https://learn.microsoft.com/pt-br/azure/service-bus-messaging/service-bus-messaging-overview), no [Azure Functions](https://learn.microsoft.com/pt-br/azure/azure-functions/functions-overview), no [Gerenciamento de API do Azure](https://learn.microsoft.com/pt-br/azure/api-management/api-management-key-concepts), entre outros.
- Trocar mensagens usando os protocolos [EDIFACT](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-edifact), [AS2](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-as2), [X12](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-x12) e [RosettaNet](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-rosettanet).
- Processar [mensagens XML](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-xml) e [arquivos simples](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-flatfile).
- Criar uma [conta de integração](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-create-integration-account) para armazenar e gerenciar artefatos B2B, como [parceiros comerciais](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-partners), [contratos](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-agreements), [mapas](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-maps), [esquemas](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-schemas), entre outros.

Por exemplo, se você usar o Microsoft BizTalk Server, os fluxos de trabalho poderão se comunicar com o BizTalk Server usando o [conector do BizTalk Server](https://learn.microsoft.com/pt-br/azure/connectors/managed#on-premises-connectors). Em seguida, você poderá executar ou estender operações semelhantes ao BizTalk nos fluxos de trabalho usando os [conectores da conta de integração](https://learn.microsoft.com/pt-br/azure/connectors/managed#integration-account-connectors). Na outra direção, o BizTalk Server pode se comunicar com seus fluxos de trabalho usando o[Adaptador do Microsoft BizTalk Server para Aplicativos Lógicos do Azure](https://www.microsoft.com/download/details.aspx?id=54287). Saiba como [configurar e usar o Adaptador do BizTalk Server](https://learn.microsoft.com/pt-br/biztalk/core/logic-app-adapter) em seu BizTalk Server.



### Gravar uma vez, reutilizar frequentemente

Crie seus aplicativos lógicos como modelos do Azure Resource Manager para [configurar e automatizar as implantações](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-azure-resource-manager-templates-overview) em uma variedade de ambientes e regiões.



### Extensibilidade integrada

Se nenhum conector adequado estiver disponível para executar o código desejado, você poderá criar e executar snippets de código do fluxo de trabalho usando a ação **Código Embutido** para [JavaScript](https://learn.microsoft.com/pt-br/azure/logic-apps/add-run-javascript)ou [scripts C#](https://learn.microsoft.com/pt-br/azure/logic-apps/add-run-csharp-scripts). Você também pode usar o [Azure Functions](https://learn.microsoft.com/pt-br/azure/azure-functions/functions-overview). Ou, então, crie [APIs](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-create-api-app) e [conectores personalizados](https://learn.microsoft.com/pt-br/azure/logic-apps/custom-connector-overview)que podem ser chamados a partir dos seus fluxos de trabalho.



### Acesso direto a recursos em redes virtuais do Azure

Os fluxos de trabalho do aplicativo lógico podem acessar recursos protegidos, como máquinas virtuais, outros serviços e sistemas que estão dentro de uma [rede virtual do Azure](https://learn.microsoft.com/pt-br/azure/virtual-network/virtual-networks-overview) quando você usa os [Aplicativos Lógicos do Azure (Standard)](https://learn.microsoft.com/pt-br/azure/logic-apps/single-tenant-overview-compare). Os Aplicativos Lógicos do Azure (Standard) são uma instância de locatário único dos Aplicativos Lógicos do Azure que usa recursos dedicados e são executados separadamente dos Aplicativos Lógicos do Azure globais e multilocatários.

Hospedar e executar fluxos de trabalho de aplicativo lógico em sua própria instância dedicada ajuda a reduzir o impacto que outros locatários do Azure podem ter no desempenho do aplicativo, também conhecido como o [efeito "vizinhos barulhentos"](https://en.wikipedia.org/wiki/Cloud_computing_issues#Performance_interference_and_noisy_neighbors).

Os Aplicativos Lógicos do Azure (Standard) oferecem os seguintes benefícios:

- Seus próprios endereços IP estáticos, que são separados dos endereços IP estáticos que os aplicativos lógicos compartilham nos Aplicativos Lógicos do Azure multilocatários. Você também pode configurar um único endereço IP de saída público, estático e previsível para se comunicar com os sistemas de destino. Dessa forma, você não precisa configurar aberturas adicionais do firewall nesses sistemas de destino.
- Aumento dos limites de duração da execução, retenção de armazenamento, taxa de transferência, tempos limite de solicitação e resposta HTTP, tamanhos de mensagem e solicitações de conector personalizado. Para obter mais informações, examine [Limites e configuração dos Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-limits-and-config).





## Como funcionam os aplicativos lógicos

Um fluxo de trabalho de aplicativo lógico sempre começa com um único [gatilho](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-overview#logic-app-concepts). O gatilho é acionado quando uma condição é atendida, por exemplo, quando ocorre um evento específico ou quando os dados atendem a critérios específicos. Muitos gatilhos incluem [recursos de agendamento](https://learn.microsoft.com/pt-br/azure/logic-apps/concepts-schedule-automated-recurring-tasks-workflows) que controlam a frequência com que o fluxo de trabalho é executado. Após o disparo do gatilho, uma ou mais [ações](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-overview#logic-app-concepts) executam operações que processam, manipulam ou convertem dados que percorrem o fluxo de trabalho ou que avançam o fluxo de trabalho para a próxima etapa.

Os Aplicativos Lógicos do Azure implementam e usam a semântica de entrega de mensagens "pelo menos uma vez". Raramente o serviço entrega uma mensagem mais de uma vez, mas nenhuma mensagem é perdida. Se sua empresa não manipular ou não puder lidar com mensagens duplicadas, você precisará implementar a *idempotência*, que é a capacidade de aceitar mensagens idênticas ou duplicadas, preservando a integridade dos dados e a estabilidade do sistema. Dessa forma, as repetições da mesma operação não alteram o resultado após a primeira execução.

A seção a seguir descreve a lógica do fluxo de trabalho empresarial de exemplo, que faz parte de um sistema de pedidos em que o fluxo de trabalho processa pedidos de entrada. O fluxo de trabalho já tem etapas que determinam quanto custa um pedido de entrada. Sua meta é revisar manualmente os pedidos acima de um determinado custo, para que você crie uma condição inicial com base nesse valor de custo, por exemplo:

- Se o pedido estiver abaixo de um determinado valor, a condição será false. Portanto, o fluxo de trabalho processa o pedido.
- Se a condição for true, o fluxo de trabalho enviará um email para revisão manual. Uma opção determina a próxima etapa.
  - Se o revisador aprovar, o fluxo de trabalho continuará a processar o pedido.
  - Se o revisador escalonar, o fluxo de trabalho enviará um email de escalonamento para saber mais sobre o pedido.
    - Se os requisitos de escalonamento são atendidos, a condição de resposta é true. Portanto, o pedido é processado.
    - Se a condição de resposta for false, um email será enviado sobre o problema.

[![A captura de tela mostra o designer de fluxo de trabalho e um fluxo de trabalho empresarial de exemplo que usa opções e condições.](https://learn.microsoft.com/pt-br/azure/logic-apps/media/logic-apps-overview/example-enterprise-workflow.png)](https://learn.microsoft.com/pt-br/azure/logic-apps/media/logic-apps-overview/example-enterprise-workflow.png#lightbox)

Você pode criar fluxos de trabalho visualmente usando o designer de fluxo de trabalho dos Aplicativos Lógicos do Azure no portal do Azure ou no Visual Studio Code. Cada fluxo de trabalho também tem uma definição subjacente que usa o formato JSON (JavaScript Object Notation). Se preferir, edite fluxos de trabalho alterando essa definição JSON. Para algumas tarefas de criação e gerenciamento, os Aplicativos Lógicos do Azure dão suporte a comandos do Azure PowerShell e da CLI do Azure. Para implantação automatizada, os Aplicativos Lógicos do Azure dão suporte a modelos do Azure Resource Manager.



## Opções de preços

Cada tipo de recurso de aplicativo lógico (multilocatário, locatário único, Ambiente do Serviço de Aplicativo (ASE v3)) tem um [modelo de preços](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-pricing) diferente. Por exemplo, fluxos de trabalho de aplicativo lógico de Consumo multilocatário seguem o modelo de preços de consumo, enquanto os fluxos de trabalho do aplicativo lógico Standard de locatário único seguem o modelo de preços Standard. Saiba mais sobre os [preços e a medição](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-pricing) dos Aplicativos Lógicos do Azure.



## Introdução

Antes de começar a usar os Aplicativos Lógicos do Azure, você precisa ter uma assinatura do Azure. Se você não tem uma assinatura, [inscreva-se em uma conta gratuita do Azure](https://azure.microsoft.com/free/?WT.mc_id=A261C142F).

Quando estiver pronto, experimente um ou mais dos seguintes guias de início rápido para Aplicativos Lógicos do Azure:

- [Criar um fluxo de trabalho de aplicativo lógico de Consumo multilocatário no portal do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/quickstart-create-example-consumption-workflow)
- [Criar um fluxo de trabalho de aplicativo lógico de Consumo multilocatário no Visual Studio Code](https://learn.microsoft.com/pt-br/azure/logic-apps/quickstart-create-logic-apps-visual-studio-code)

Você também pode querer explorar outros guias de início rápido para os Aplicativos Lógicos do Azure:

- [Criar um fluxo de trabalho de aplicativo lógico de Consumo multilocatário usando um modelo do ARM](https://learn.microsoft.com/pt-br/azure/logic-apps/quickstart-create-deploy-azure-resource-manager-template)
- [Criar um fluxo de trabalho de aplicativo lógico de Consumo multilocatário usando a CLI do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/quickstart-logic-apps-azure-cli)



## Próximas etapas

- [Início Rápido: criar um exemplo de fluxo de trabalho de aplicativo lógico de Consumo nos Aplicativos Lógicos do Azure multilocatário no portal do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/quickstart-create-example-consumption-workflow)