# Cenários comuns, exemplos, tutoriais e instruções passo a passo para os Aplicativos Lógicos do Azure

- Artigo
- 22/08/2024
- 8 colaboradores

Comentários

Neste artigo[Pontos de partida comuns para fluxos de trabalho de aplicativo lógico](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-examples-and-scenarios#common-starting-points-for-logic-app-workflows)[Recursos de tratamento de erro e fluxo de controle](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-examples-and-scenarios#control-flow-and-error-handling-capabilities)[Criar conectores e APIs personalizados](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-examples-and-scenarios#create-custom-apis-and-connectors)[Criar soluções B2B (entre empresas)](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-examples-and-scenarios#build-business-to-business-b2b-solutions)Mostrar mais 7

Os [Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-overview) ajudam a orquestrar e integrar diferentes serviços, fornecendo centenas de conectores pré-definidos e prontos para uso, desde o SQL Server e o SAP até os serviços de IA do Azure. Os Aplicativos Lógicos do Azure são "sem servidor", portanto, você não precisa se preocupar com escala ou instâncias. Tudo o que você precisa fazer é definir um fluxo de trabalho com um gatilho e as ações que o fluxo de trabalho executa. A plataforma subjacente lida com a escala, disponibilidade e desempenho. Os Aplicativos Lógicos do Azure são especialmente úteis para casos de uso e cenários em que você precisa coordenar ações em vários sistemas e serviços.

Para ajudá-lo a aprender sobre os recursos e padrões suportados pelos Aplicativos Lógicos do Azure, este guia descreve pontos de partida, exemplos e cenários comuns.



## Pontos de partida comuns para fluxos de trabalho de aplicativo lógico

Todo fluxo de trabalho começa com um único [*gatilho*](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-overview#logic-app-concepts), que é disparado quando a condição do disparo é atendida, executa o fluxo de trabalho e passa todas as saídas do gatilho para ações subsequentes no fluxo de trabalho. Muitos conectores fornecem gatilhos, que têm um dos tipos a seguir:

- Gatilho de *sondagem*: verifica um ponto de extremidade de serviço em busca de dados ou um evento que atenda à condição de disparo, com base na programação especificada. Se a condição de disparo for atendida naquele momento, o gatilho será acionado, criando e executando uma nova instância de fluxo de trabalho que usa quaisquer saídas de gatilho como entradas para o fluxo de trabalho.
- Gatilho de *envio*: escuta e espera em um ponto de extremidade de serviço em busca de dados ou um evento que atenda à condição de disparo. Nesse momento, o gatilho é disparado imediatamente, criando e executando uma nova instância de fluxo de trabalho que usa quaisquer saídas de gatilho como entradas para o fluxo de trabalho.



### Exemplos de gatilho de sondagem

Expandir a tabela

| Gatilho                                                      | Descrição                                                    | Mais informações                                             |
| :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| [**Gatilho** de Recorrência](https://learn.microsoft.com/pt-br/azure/connectors/connectors-native-recurrence) | Defina a recorrência para a execução do fluxo de trabalho, incluindo a data e a hora de início. Por exemplo, você pode selecionar os dias da semana e os horários do dia. | - [Agende e execute tarefas, processos e fluxos de trabalho automatizados recorrentes com os Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/concepts-schedule-automated-recurring-tasks-workflows)  - [Tutorial: criar fluxos de trabalho recorrentes automatizados e baseados em agendamento usando os Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/tutorial-build-schedule-recurring-logic-app-workflow) |
| **Quando um email é recebido**                               | Verifique se há novos emails de qualquer provedor de email suportado pelos Aplicativos Lógicos do Azure, por exemplo, [Office 365 Outlook](https://learn.microsoft.com/pt-br/azure/connectors/connectors-create-api-office365-outlook), [Gmail](https://learn.microsoft.com/pt-br/connectors/gmail/), [Outlook.com](https://learn.microsoft.com/pt-br/connectors/outlook/) e assim por diante. | **Importante**: se você quiser usar o conector do Gmail, somente as contas empresariais do G-Suite podem usar esse conector sem restrições nos Aplicativos Lógicos do Azure. Se você tiver uma conta de consumidor do Gmail, poderá usar esse conector somente com serviços específicos do Google aprovados ou poderá [criar um aplicativo cliente do Google para usar para autenticação com o conector do Gmail](https://learn.microsoft.com/pt-br/connectors/gmail/#authentication-and-bring-your-own-application). Para obter mais informações, confira [Políticas de privacidade e segurança de dados para os conectores do Google nos Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/connectors/connectors-google-data-security-privacy-policy).  Para ver tutoriais sobre gatilhos relacionados a email, consulte a documentação a seguir:  - [Tutorial: criar fluxos de trabalho automatizados baseados em aprovação usando os Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/tutorial-process-mailing-list-subscriptions-workflow)  - [Tutorial: automatizar tarefas para processar emails usando os Aplicativos Lógicos do Azure, o Azure Functions e o Armazenamento do Microsoft Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/tutorial-process-email-attachments-workflow) |
| [**Gatilho** HTTP](https://learn.microsoft.com/pt-br/azure/connectors/connectors-native-http) | Chamar um ponto de extremidade de serviço por HTTP ou HTTPS. | [Chamar, disparar ou aninhar fluxos de trabalho usando pontos de extremidade HTTP](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-http-endpoint) |



### Exemplos de gatilho de envio

Expandir a tabela

| Gatilho                                                      | Descrição                                                    |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [**Gatilho** de solicitação](https://learn.microsoft.com/pt-br/azure/connectors/connectors-native-reqres) | Recebe as solicitações HTTPS de entrada.                     |
| [**Gatilho** de Webhook HTTP](https://learn.microsoft.com/pt-br/azure/connectors/connectors-native-webhook) | Inscreva-se em um ponto de extremidade de serviço registrando uma *URL de retorno de chamada* com esse serviço. Dessa forma, o serviço pode apenas notificar o gatilho quando o evento especificado ocorrer, para que o gatilho não precise sondar o serviço. |

Após adicionar o gatilho, continue construindo seu fluxo de trabalho adicionando uma ou mais ações. Os inícios rápidos a seguir ajudam você a criar seu primeiro fluxo de trabalho do aplicativo lógico de Consumo, que é executado nos Aplicativos Lógicos do Azure multilocatário e globais:

- [Início Rápido: Criar um exemplo de fluxo de trabalho de aplicativo lógico de Consumo nos Aplicativos Lógicos do Azure multilocatário — Portal do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/quickstart-create-example-consumption-workflow)
- [Início Rápido: criar e gerenciar fluxos de trabalho de aplicativos lógicos automatizados usando o Visual Studio Code](https://learn.microsoft.com/pt-br/azure/logic-apps/quickstart-create-logic-apps-visual-studio-code)

Os guia de instruções a seguir ajudam você a criar um fluxo de trabalho do aplicativo lógico Standard executado nos Aplicativos Lógicos do Azure de locatário único:

- [Criar um exemplo de fluxo de trabalho de aplicativo lógico Standard nos Aplicativos Lógicos do Azure de locatário único - Portal do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/create-single-tenant-workflows-azure-portal)
- [Criar um exemplo de fluxo de trabalho de aplicativo lógico Standard nos Aplicativos Lógicos do Azure de locatário único - Visual Studio Code](https://learn.microsoft.com/pt-br/azure/logic-apps/create-single-tenant-workflows-visual-studio-code)



## Recursos de tratamento de erro e fluxo de controle

Os Aplicativos Lógicos do Azure incluem recursos avançados para fluxo de controle avançado, como condições, comutadores, loops e escopos. Para garantir soluções resilientes, implemente também a manipulação de erros e exceções em seus fluxos de trabalho.

- Executar ações diferentes com base em [instruções condicionais](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-control-flow-conditional-statement) e [alternar instruções](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-control-flow-switch-statement)
- [Repetir as etapas ou processar itens em matrizes e coleções com loops](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-control-flow-loops)
- [Agrupar ações com os escopos](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-control-flow-run-steps-group-scopes)
- [Adicionar manipulação de erro e exceções do autor no fluxo de trabalho](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-exception-handling)



## Criar conectores e APIs personalizados

Para sistemas e serviços que não possuem conectores publicados, você também pode estender os Aplicativos Lógicos do Azure para criar APIs e conectores personalizados:

- [Criar APIs personalizadas para fazer chamadas dos Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-create-api-app)
- [Conectores personalizados nos Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/custom-connector-overview)



## Criar soluções B2B (entre empresas)

Para soluções de integração empresarial e comunicação direta entre organizações, você pode criar fluxos de trabalho escalonáveis automatizados para esses cenários usando o EIP (Enterprise Integration Pack) com os Aplicativos Lógicos do Azure. Embora as organizações usem diferentes protocolos e formatos, elas podem trocar mensagens eletronicamente. O EIP transforma formatos diferentes em um formato que os sistemas de sua organização podem processar e dá suporte a protocolos padrão do setor, incluindo o AS2, X12, EDIFACT e o RosettaNet. Para criar essas soluções, você cria uma conta de integração, que é um recurso separado do Microsoft Azure que fornece um contêiner seguro, escalonável e gerenciável para os artefatos que você define e usa com seus fluxos de trabalho de aplicativo lógico. Por exemplo, os artefatos incluem parceiros comerciais, contratos, mapas, esquemas, certificados e configurações de lote.

- [Visão geral: soluções de integração empresarial B2B com os Aplicativos Lógicos do Azure e o Enterprise Integration Pack](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-overview)
- [Criar e gerenciar contas de integração para integrações empresariais B2B nos Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-create-integration-account)



## Acessar recursos de rede virtual do Azure

Às vezes, o fluxo de trabalho do aplicativo lógico pode precisar de acesso a recursos protegidos, como máquinas virtuais (VMs) em uma rede virtual do Azure. Para acessar diretamente esses recursos, [crie um fluxo de trabalho de aplicativo lógico Standard](https://learn.microsoft.com/pt-br/azure/logic-apps/create-single-tenant-workflows-azure-portal). Esse tipo de fluxo de trabalho de aplicativo lógico é executado nos Aplicativos Lógicos do Azure de locatário único, separadamente dos fluxos de trabalho de aplicativos lógicos de Consumo nos Aplicativos Lógicos do Azure multilocatário e usa armazenamento dedicado e outros recursos. Com essa opção, você pode reduzir o impacto que outros locatários do Azure podem ter no desempenho de seus aplicativos, que também é conhecido como o efeito "vizinhos barulhentos".



## Implantar, gerenciar e monitorar fluxos de trabalho de aplicativos lógicos

Você pode desenvolver e implantar totalmente recursos de aplicativos lógicos com o Azure DevOps ou qualquer outra ferramenta de controle de origem e criação automatizada. Para dar suporte à implantação de fluxos de trabalho e conexões dependentes em um modelo de recurso, os recursos de aplicativos lógicos usam os modelos de implantação de recursos do Azure. Para receber notificação e logs de diagnóstico para status de execução de fluxo de trabalho, os Aplicativos Lógicos do Azure também fornecem monitoramento e alertas.



### Implantar

- [Configurar slots de implantação para habilitar a implantação de tempo de inatividade zero nos Aplicativos Lógicos do Azure de locatário único](https://learn.microsoft.com/pt-br/azure/logic-apps/set-up-deployment-slots)
- [Implantação do DevOps para aplicativos lógicos Standard em Aplicativos Lógicos do Azure com locatário único](https://learn.microsoft.com/pt-br/azure/logic-apps/devops-deployment-single-tenant-azure-logic-apps)
- [Configurar a implantação do DevOps para aplicativos lógicos Standard nos Aplicativos Lógicos do Azure com locatário único](https://learn.microsoft.com/pt-br/azure/logic-apps/set-up-devops-deployment-single-tenant-azure-logic-apps)
- [Automatizar a compilação e implantação com o Azure DevOps para aplicativos lógicos Standard](https://learn.microsoft.com/pt-br/azure/logic-apps/automate-build-deployment-standard)
- [Visão geral: automatizar a implantação do aplicativo lógico com modelos do Azure Resource Manager](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-azure-resource-manager-templates-overview)
- [Criar modelos do Azure Resource Manager para automatizar a implantação para Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-create-azure-resource-manager-templates)
- [Implantar modelos do Azure Resource Manager para Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-deploy-azure-resource-manager-templates)
- [Amostra: configurar uma ação do Gerenciamento de API para os Aplicativos Lógicos do Azure](https://github.com/Azure-Samples/azure-logic-apps-deployment-samples/tree/master/api-management-actions)
- [Amostra: organizar o Azure Pipelines usando os Aplicativos Lógicos do Azure](https://github.com/Azure-Samples/azure-logic-apps-pipeline-orchestration)
- [Amostra: conectar-se a contas do Armazenamento do Microsoft Azure a partir dos Aplicativos Lógicos do Azure e implantar com o Azure Pipelines no Azure DevOps](https://github.com/Azure-Samples/azure-logic-apps-deployment-samples/tree/master/storage-account-connections)
- [Amostra: conectar-se a filas do barramento de serviço do Azure a partir dos Aplicativos Lógicos do Azure e implantar com o Azure Pipelines no Azure DevOps](https://github.com/Azure-Samples/azure-logic-apps-deployment-samples/tree/master/service-bus-connections)
- [Amostra: configurar uma ação do Azure Functions para Aplicativos Lógicos do Azure e implantar com o Azure Pipelines no Azure DevOps](https://github.com/Azure-Samples/azure-logic-apps-deployment-samples/tree/master/function-app-actions)
- [Amostra: conectar-se a contas de integração a partir dos Aplicativos Lógicos do Azure e implantar com o Azure Pipelines no Azure DevOps](https://github.com/Azure-Samples/azure-logic-apps-deployment-samples/tree/master/integration-account-connections)



### Gerenciar

- [Planejar e gerenciar custos](https://learn.microsoft.com/pt-br/azure/logic-apps/plan-manage-costs)
- [Gerenciar aplicativos lógicos no portal do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/manage-logic-apps-with-azure-portal)
- [Criar e gerenciar contas de integração para integrações empresariais B2B](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-create-integration-account)
- [Mover recursos de aplicativo lógico para outros grupos de recursos, regiões ou assinaturas do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/move-logic-app-resources)



### Monitoramento

- [Monitorar o status de execução, examinar o histórico de gatilho e configurar alertas para aplicativos lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/monitor-logic-apps)
- [Exibir métricas de integridade e desempenho](https://learn.microsoft.com/pt-br/azure/logic-apps/view-workflow-metrics)
- [Monitorar e coletar dados de diagnóstico para fluxos de trabalho nos Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/monitor-workflows-collect-diagnostic-data)
- [Monitore fluxos de trabalho de aplicativos lógicos no Microsoft Defender para Nuvem](https://learn.microsoft.com/pt-br/azure/logic-apps/healthy-unhealthy-resource)
- [Monitore mensagens B2B com os Logs do Azure Monitor nos Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/monitor-b2b-messages-log-analytics)
- [Crie consultas de monitoramento e acompanhamento nos Logs do Azure Monitor para os Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/create-monitoring-tracking-queries)



## Lidando com tipos de conteúdo, conversões e transformações

Você pode acessar, converter e transformar vários tipos de conteúdo usando diversas funções na [linguagem de definição de fluxo de trabalho](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-workflow-definition-language) dos Aplicativos Lógicos do Azure. Por exemplo, você pode converter entre uma cadeia de caracteres, JSON e XML com as expressões de fluxo de trabalho `@json()` e `@xml()`. Os Aplicativos Lógicos do Azure preservam os tipos de conteúdo para dar suporte à transferência de conteúdo sem perdas entre os serviços.

- [Lidar com tipos de conteúdo em Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-content-type), como `application/`, `application/octet-stream`, e `multipart/formdata`
- [Guia de referência do uso de funções em expressões para os Aplicativos Lógicos do Azure e o Power Automate](https://learn.microsoft.com/pt-br/azure/logic-apps/workflow-definition-language-functions-reference)
- [Esquema de linguagem de definição de fluxo de trabalho para os Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-workflow-definition-language)



## Outros recursos e integrações

Os aplicativos lógicos integram muitos serviços, como o Azure Functions, o Gerenciamento de API do Azure, Serviço de Aplicativo do Azure e pontos de extremidade HTTP personalizados, por exemplo, o REST e o SOAP.

- [Chamar o Azure Functions a partir dos Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/call-azure-functions-from-workflows)
- [Tutorial: criar de um painel de informações do cliente em streaming com Aplicativos Lógicos do Azure e Azure Functions](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-scenario-social-serverless)
- [Tutorial: criar uma função que se integra ao Aplicativos Lógicos do Azure e aos serviços de IA do Azure para analisar o sentimento de postagens do X](https://learn.microsoft.com/pt-br/azure/azure-functions/functions-twitter-email)
- [Tutorial: criar um painel social alimentado por IA usando o Power BI e Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/shows/)
- [Tutorial: Monitorar as alterações de máquinas virtuais usando a Grade de Eventos do Azure e os Aplicativos Lógicos](https://learn.microsoft.com/pt-br/azure/event-grid/monitor-virtual-machine-changes-logic-app)
- [Tutorial: Monitoramento remoto IoT e notificações com Aplicativos Lógicos do Azure conectando o Hub IoT e a caixa de correio](https://learn.microsoft.com/pt-br/azure/iot-hub/iot-hub-monitoring-notifications-with-azure-logic-apps)
- [Blog: chamar serviços SOAP usando Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/archive/blogs/logicapps/using-soap-services-with-logic-apps)



## Cenários de ponta a ponta

- [Whitepaper: integração de ponta a ponta do gerenciamento de casos com os serviços do Azure, como os Aplicativos Lógicos do Azure](https://aka.ms/enterprise-integration-e2e-case-management-utilities-logic-apps)



## Relatos de clientes

Saiba como os Aplicativos Lógicos do Azure, juntamente com outros serviços do Azure e produtos da Microsoft, ajudaram [estas empresas](https://aka.ms/logic-apps-customer-stories) a melhorar a agilidade e a concentração em seus negócios essenciais simplificando, organizando, automatizando e coordenando processos complexos.



## Próximas etapas

- [O que são os conectores nos Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/connectors/introduction)
- [Cenários de integração empresarial B2B com os Aplicativos Lógicos do Azure](https://learn.microsoft.com/pt-br/azure/logic-apps/logic-apps-enterprise-integration-overview)