# Introdução
 
> **Nome provisório do projeto:** **Smart Wash — Gestão Inteligente de Lavanderias Compartilhadas**  
> **Eixo temático:** consumo responsável, eficiência no uso de recursos e conscientização climática  
> **Objetivos de Desenvolvimento Sustentável relacionados:** ODS 12 e ODS 13
 
Lavanderias compartilhadas instaladas em condomínios, residenciais, estabelecimentos autônomos e lojas de autosserviço utilizam um conjunto limitado de máquinas para atender vários usuários. Nesses ambientes, a qualidade do serviço não depende apenas da lavagem das roupas, mas também da disponibilidade dos equipamentos, da rotatividade entre os ciclos, da retirada das roupas após o término e da capacidade do responsável pelo espaço de compreender custos e padrões de utilização.
 
Na situação que motivou este projeto, essas informações são fragmentadas. O usuário normalmente precisa deslocar-se até a lavanderia para verificar se existe máquina livre, controlar por conta própria o horário estimado de término e retornar para retirar as roupas. Quando a retirada não ocorre em tempo adequado, a máquina permanece fisicamente ocupada mesmo depois de concluir o ciclo. Como consequência, o próximo usuário pode ter de esperar, retornar posteriormente, remover roupas de terceiros ou solicitar a intervenção de um síndico, funcionário ou operador.
 
A gestão também apresenta limitações. Contas de energia elétrica e água costumam demonstrar o consumo agregado do imóvel ou do estabelecimento, sem informar quanto cada máquina consumiu, quantos ciclos foram realizados, quanto tempo o equipamento permaneceu em uso ou indisponível e qual foi seu custo operacional aproximado. Essa falta de granularidade dificulta comparar máquinas, identificar anomalias, estimar a margem por ciclo e tomar decisões sobre preço, manutenção, substituição de equipamentos e horários de funcionamento.
 
A relevância da gestão energética pode ser contextualizada pelo Balanço Energético Nacional 2025, ano-base 2024. Segundo a Empresa de Pesquisa Energética, o consumo final de eletricidade no Brasil cresceu 5,5% em 2024; o setor residencial apresentou crescimento de 8% e o comercial, de 7,4% (EPE, 2025). Esses dados não medem especificamente lavanderias, mas demonstram a importância de soluções que tornem o consumo de energia mais visível e gerenciável nos ambientes residenciais e comerciais.
 
O projeto propõe o desenvolvimento de uma aplicação móvel integrada a dispositivos de Internet das Coisas — inicialmente, a tomada inteligente Tapo P110 — para acompanhar a disponibilidade das máquinas, registrar sessões de uso, monitorar energia elétrica, identificar o provável término de ciclos, notificar usuários e apresentar indicadores operacionais aos responsáveis pela lavanderia. A página oficial do fabricante informa que a Tapo P110 oferece monitoramento de energia em tempo real, controle remoto, agendamento e temporizador. O equipamento é especificado para carga máxima de 2.400 W e 10 A, o que exige conferência da placa elétrica e das características de cada lavadora antes da instalação (TP-LINK, s.d.).
 
O consumo de água não é medido pela tomada inteligente. No escopo inicial, esse valor será identificado como **estimativa**, calculada a partir do modelo da máquina e do programa selecionado, quando esses dados estiverem disponíveis. Uma medição direta exigiria hidrômetro ou sensor de fluxo dedicado. A separação entre valor medido e valor estimado é necessária para evitar que indicadores gerenciais apresentem precisão inexistente.
 
A proposta relaciona-se principalmente às metas 12.2, 12.6 e 12.8 do ODS 12, por buscar uso mais eficiente de recursos, disponibilizar informações de sustentabilidade para a gestão e ampliar a conscientização dos usuários. A contribuição ao ODS 13 é indireta e concentra-se especialmente na meta 13.3, por transformar dados de consumo em informação compreensível e apoiar educação e conscientização sobre mitigação dos impactos ambientais (NAÇÕES UNIDAS BRASIL, s.d.-a; s.d.-b). O projeto não pressupõe que a aplicação, isoladamente, reduzirá emissões ou consumo, esses efeitos deverão ser avaliados durante o piloto.
 
## Problema
 
O processo atual de utilização de lavanderias compartilhadas apresenta uma assimetria de informação entre usuários, máquinas e gestores. Antes de chegar ao espaço, o usuário não dispõe de uma fonte confiável e atualizada que indique se uma máquina está livre, em funcionamento, com ciclo concluído ou indisponível. A verificação ocorre presencialmente e, quando não existe equipamento disponível, o deslocamento não gera o resultado esperado.
 
Depois que a lavagem é iniciada, o acompanhamento depende do visor da própria máquina, de um alarme pessoal ou de uma estimativa feita pelo usuário. O tempo programado pode não coincidir exatamente com o tempo real por causa do modelo da lavadora, programa escolhido, balanceamento da carga, entrada de água ou outras condições de operação. Sem uma comunicação objetiva sobre o término, as roupas podem permanecer no equipamento, impedindo a utilização por outra pessoa mesmo quando a máquina já não está executando o ciclo.
 
A ocupação após o término produz efeitos operacionais e sociais: aumento do tempo de espera, redução da rotatividade, deslocamentos adicionais, conflitos sobre a retirada de pertences de terceiros e necessidade de intervenção do responsável pelo local. Em condomínios, o síndico ou funcionário passa a intermediar uma situação de uso coletivo. Em lavanderias comerciais, a indisponibilidade percebida pode reduzir a capacidade de atendimento e prejudicar a experiência do cliente.
 
No nível gerencial, o consumo de energia e água é normalmente conhecido por meio de faturas agregadas ou estimativas gerais. Sem associação entre máquina, sessão e período, torna-se difícil responder a questões básicas, como:
 
- qual equipamento realizou mais ciclos em determinado dia;
- qual máquina apresentou consumo atípico;
- qual é o custo aproximado de energia por ciclo;
- quanto tempo cada equipamento permaneceu ocupado após o término;
- quais horários apresentam maior demanda;
- qual é a contribuição operacional estimada de cada máquina;
- quando uma queda de uso pode indicar falha, manutenção ou perda de demanda.
 
A ausência de histórico também limita a definição de preços e o planejamento de manutenção. O gestor pode conhecer o faturamento total e as contas mensais, mas não consegue relacionar, com precisão suficiente, receita, utilização e consumo por equipamento.
 
Diante desse contexto, o problema de pesquisa pode ser expresso da seguinte forma:
 
> **Como reduzir a incerteza sobre a disponibilidade das máquinas e melhorar a rastreabilidade de uso, consumo e custos em lavanderias compartilhadas e autônomas, considerando que usuários e gestores não dispõem de informações oportunas e confiáveis por máquina e por ciclo?**
 
A frequência e a intensidade das ocorrências descritas constituem hipóteses iniciais levantadas pelo grupo e deverão ser verificadas por entrevistas, questionários e observação do processo real. Não se deve apresentar percentuais de conflito, espera ou desperdício antes dessa validação.
 
### Síntese de causas e consequências
 
| Causa observada ou hipótese inicial | Consequência para o usuário | Consequência para a gestão |
|---|---|---|
| Disponibilidade verificada apenas no local | Deslocamento sem garantia de uso e maior tempo de espera | Reclamações e baixa previsibilidade da demanda |
| Controle manual do término | Esquecimento ou retorno fora do horário | Máquina concluída, mas ainda ocupada |
| Ausência de aviso de retirada | Conflitos e dificuldade de acessar o equipamento | Necessidade de intervenção operacional |
| Contas de utilidades agregadas | Usuário não conhece o impacto do próprio ciclo | Custo por máquina e por ciclo apenas estimado |
| Falta de histórico por equipamento | Pouca transparência sobre o uso | Dificuldade para precificar, comparar e planejar manutenção |
| Falha ou perda de conectividade sem sinalização | Estado da máquina pode ser interpretado de forma incorreta | Indicadores incompletos e resposta tardia a incidentes |
 
## Objetivos
 
### Objetivo geral
 
Desenvolver e avaliar uma aplicação móvel integrada a dispositivos de Internet das Coisas para apoiar a utilização e a gestão de lavanderias compartilhadas, disponibilizando informações sobre máquinas, ciclos, consumo de energia, estimativas de água, notificações e indicadores operacionais.
 
### Objetivos específicos
 
1. Mapear e validar o processo atual de uso e gestão das lavanderias por meio de entrevistas, questionários e observação com usuários e responsáveis pelos espaços.
2. Permitir que o usuário consulte o estado operacional das máquinas antes de se deslocar até a lavanderia.
3. Registrar a associação entre usuário, máquina, horário de início, horário de término e duração da sessão de uso.
4. Identificar o provável término do ciclo por regras configuráveis baseadas no comportamento de potência da máquina, mantendo mecanismos de confirmação e tratamento de erro.
5. Notificar o usuário quando o ciclo terminar e emitir lembretes de retirada após um prazo de tolerância definido pelo estabelecimento.
6. Medir o consumo de energia elétrica por máquina e por sessão, distinguindo leituras reais de valores calculados ou estimados.
7. Estimar o consumo de água por ciclo a partir do modelo e do programa da lavadora, apresentando explicitamente a natureza estimada desse indicador quando não houver sensor de vazão.
8. Calcular indicadores de utilização, custo de energia, custo estimado de água, receita e contribuição operacional estimada por máquina e período.
9. Apoiar gestores na identificação de anomalias de consumo, falhas de comunicação, ociosidade e necessidade de manutenção.
10. Avaliar, em um projeto-piloto, a precisão da identificação de término, a completude da telemetria, a usabilidade da aplicação e a variação do tempo entre o fim do ciclo e a retirada das roupas.
 
## Justificativa
 
A proposta foi escolhida porque combina um problema cotidiano de coordenação de recursos compartilhados com uma oportunidade concreta de monitoramento ambiental e gestão operacional. O usuário necessita de informação simples e tempestiva; o gestor necessita de dados históricos e comparáveis. A mesma infraestrutura de coleta pode atender aos dois objetivos sem exigir que o usuário interprete gráficos técnicos ou que o gestor acompanhe manualmente cada ciclo.
 
Sob a perspectiva social e operacional, a disponibilização do estado das máquinas pode reduzir deslocamentos sem resultado e tornar mais previsível o uso do espaço. A notificação de término e o lembrete de retirada atuam sobre o período em que a máquina já concluiu a lavagem, mas permanece bloqueada pelas roupas. O benefício, porém, deve ser demonstrado por métricas do piloto, como tempo médio de retirada, quantidade de lembretes, tempo de indisponibilidade pós-ciclo e percepção dos usuários.
 
Sob a perspectiva econômica, a medição por equipamento permite substituir parte das estimativas gerais por dados associados a sessões reais. O gestor poderá calcular o custo elétrico por meio da energia consumida e da tarifa cadastrada, comparar períodos, identificar equipamentos com comportamento diferente e avaliar a utilização. A margem apresentada pelo sistema deverá ser denominada **contribuição operacional estimada**, pois lucro contábil exige considerar outros elementos, como aluguel, tributos, depreciação, manutenção, detergentes, pessoal e custos financeiros.
 
Sob a perspectiva ambiental, o ODS 12 estabelece, entre outras metas, alcançar a gestão sustentável e o uso eficiente dos recursos naturais, incentivar práticas empresariais sustentáveis e ampliar o acesso a informações relevantes sobre estilos de vida em harmonia com a natureza. O ODS 13 inclui o aumento da educação e da conscientização sobre mitigação e redução de impactos. O projeto contribui para essas metas ao registrar, organizar e comunicar indicadores de consumo; não deve, entretanto, ser apresentado como solução suficiente para todos os objetivos dos ODS 12 e 13 (NAÇÕES UNIDAS BRASIL, s.d.-a; s.d.-b).
 
A variação de eficiência entre equipamentos reforça a necessidade de dados específicos por modelo. Como referência internacional, o programa ENERGY STAR informa que lavadoras certificadas utilizam, em média, cerca de 20% menos energia e 30% menos água do que modelos comuns, além de adotar indicadores próprios de eficiência energética e hídrica. Esses percentuais pertencem ao contexto do programa norte-americano e não devem ser transferidos automaticamente para a realidade brasileira; sua utilidade no projeto é demonstrar que uma estimativa universal de água ou energia por lavagem seria inadequada (ENERGY STAR, s.d.).
 
A viabilidade técnica inicial é apoiada pelas funcionalidades declaradas para a Tapo P110: monitoramento de energia, estimativa de conta, controle remoto, agendamento e temporizador. A tomada opera em 100–240 V e possui limite de 2.400 W e 10 A. Portanto, o dispositivo não pode ser instalado de forma indiscriminada: cada máquina deve ter sua corrente, potência, tipo de tomada, aterramento e condições do circuito avaliados antes do piloto (TP-LINK, s.d.). Lavadoras-secadoras ou modelos com aquecimento podem ultrapassar os limites do dispositivo.
 
A tomada inteligente mede grandezas elétricas, mas não conhece diretamente o programa selecionado, a presença física das roupas nem a retirada ao final. Também não se deve presumir que ligar a tomada inicia a lavagem, pois muitas máquinas exigem acionamento manual no painel e podem não retomar o ciclo após uma interrupção. Por segurança e integridade das roupas, o MVP não realizará desligamento automático durante um ciclo detectado como ativo.
 
A página comercial documenta as funções disponíveis no aplicativo do fabricante, mas não comprova, por si só, que todas elas possam ser integradas diretamente a um software acadêmico próprio. Por isso, a interface programática, os mecanismos de autenticação e as permissões de uso deverão ser verificados em uma prova de conceito com meios autorizados. Caso a integração direta não seja viável, o projeto deverá utilizar um adaptador compatível, um protótipo próprio de telemetria ou dados simulados para demonstrar a arquitetura sem contornar mecanismos de segurança.
 
Pesquisas sobre feedback de consumo recomendam cautela na promessa de economia. Kelly e Knottenbelt (2016), em revisão de 12 estudos, encontraram redução média de 4,5% no consumo com feedback desagregado, mas alertaram para viés de adesão e para a ausência de evidência robusta de que a desagregação seja superior ao feedback agregado. Esse resultado sustenta uma decisão metodológica importante: a economia não será tratada como consequência automática da aplicação. O projeto medirá comportamento e consumo antes e depois do piloto e apresentará os resultados observados, inclusive quando não houver redução.
 
Dessa forma, a justificativa do trabalho não depende de uma promessa antecipada de economia. Sua relevância está na melhoria da informação, na coordenação de um recurso compartilhado, na criação de rastreabilidade operacional e na possibilidade de testar, com dados, se essas mudanças produzem benefícios ambientais, econômicos e de experiência do usuário.
 
### Indicadores propostos para avaliação do piloto
 
| Dimensão | Indicador | Forma de cálculo ou verificação |
|---|---|---|
| Disponibilidade | Percentual do tempo em cada estado | Tempo no estado ÷ tempo monitorado |
| Rotatividade | Tempo pós-ciclo até a retirada | Confirmação de retirada − término detectado |
| Adoção | Sessões acompanhadas pela aplicação | Sessões registradas ÷ sessões observadas |
| Confiabilidade | Completude da telemetria | Leituras válidas ÷ leituras esperadas |
| Precisão | Erro de identificação do término | Comparação entre término detectado e término observado |
| Energia | kWh por ciclo e por máquina | Leitura final − leitura inicial da sessão |
| Custo | Custo elétrico estimado | kWh da sessão × tarifa cadastrada |
| Água | Litros estimados por ciclo | Parâmetro do modelo/programa; marcado como estimativa |
| Experiência | Percepção de utilidade e facilidade | Questionário após o uso |
| Operação | Ocorrências de máquina bloqueada | Contagem antes e durante o piloto |
 
## Público-Alvo
 
O público-alvo é composto por pessoas que utilizam, administram, operam ou mantêm lavanderias de uso compartilhado. Os perfis apresentam níveis diferentes de familiaridade com tecnologia e necessidades distintas de informação. A solução deverá ser compreensível para usuários que sabem utilizar aplicativos básicos, mas não possuem conhecimento técnico sobre energia, redes ou Internet das Coisas.
 
### Perfis principais
 
#### Usuários de lavanderias condominiais e residenciais
 
São moradores ou ocupantes de prédios, residenciais estudantis, imóveis por temporada e outros espaços com máquinas compartilhadas. Podem utilizar a lavanderia em horários restritos, à noite ou nos fins de semana. Em geral, possuem smartphone e familiaridade com mensagens e notificações, mas não devem ser obrigados a interpretar unidades elétricas para executar tarefas básicas. Valorizam disponibilidade, rapidez, instruções simples, privacidade e confirmação clara do estado da máquina.
 
#### Clientes de lavanderias autônomas e de autosserviço
 
São pessoas que se deslocam até lojas de rua ou estabelecimentos sem acompanhamento permanente de funcionários. Podem usar o serviço de forma recorrente ou eventual. Necessitam compreender rapidamente quais máquinas estão livres, em uso ou indisponíveis, além de receber orientações sem depender de treinamento prévio. O fluxo precisa considerar usuários com diferentes idades, níveis de letramento digital e necessidades de acessibilidade.
 
#### Síndicos, administradores e operadores de lavanderias
 
São responsáveis por regras de utilização, cadastro de máquinas, tratamento de reclamações, acompanhamento de custos e decisões de manutenção. Podem possuir conhecimento digital intermediário, mas não necessariamente conhecimento de engenharia elétrica ou análise de dados. Precisam de visão consolidada, alertas objetivos, histórico auditável e indicadores que não confundam medições com estimativas.
 
#### Proprietários e gestores de lavanderias comerciais
 
Acompanham preço por ciclo, faturamento, ocupação, custo e desempenho dos equipamentos. Necessitam comparar máquinas, dias e horários, detectar queda de utilização e avaliar intervenções. Sua decisão tem impacto financeiro e operacional, razão pela qual fórmulas, parâmetros e limitações dos indicadores devem ser transparentes.
 
#### Técnicos de manutenção e suporte
 
Atuam na instalação, conectividade, diagnóstico e manutenção dos equipamentos. Possuem maior conhecimento técnico e precisam visualizar falhas de comunicação, última leitura, potência observada e histórico de incidentes. Seu acesso deve ser limitado às informações necessárias para o diagnóstico, evitando exposição indevida de dados pessoais dos usuários.
 
### Relação com a tecnologia e níveis de acesso
 
| Perfil | Familiaridade tecnológica esperada | Necessidade principal | Visão de informação adequada |
|---|---|---|---|
| Usuário ou cliente | Básica a intermediária | Disponibilidade, início, término e retirada | Próprias sessões e estado das máquinas |
| Síndico ou operador | Intermediária | Regras, conflitos, utilização e incidentes | Visão operacional do local |
| Proprietário ou gestor | Intermediária | Custos, receita, comparação e planejamento | Indicadores consolidados e históricos |
| Técnico de manutenção | Intermediária a avançada | Diagnóstico de máquina, rede e dispositivo | Telemetria técnica e incidentes autorizados |
| Equipe do projeto/suporte | Avançada | Configuração, auditoria e correção | Acesso controlado e rastreável conforme necessidade |






## Referências
 
ENERGY STAR. **Clothes Washers**. Washington, DC: U.S. Environmental Protection Agency, [s.d.]. Disponível em: <https://www.energystar.gov/products/clothes_washers>. Acesso em: 23 ago. 2026.
 
EMPRESA DE PESQUISA ENERGÉTICA — EPE. **Balanço Energético Nacional 2025: Relatório Síntese — ano-base 2024**. Rio de Janeiro: EPE, 2025. Disponível em: <https://www.epe.gov.br/sites-pt/publicacoes-dados-abertos/publicacoes/PublicacoesArquivos/publicacao-885/topico-767/BEN_S%C3%ADntese_2025_PT.pdf>. Acesso em: 23 ago. 2026.
 
KELLY, Jack; KNOTTENBELT, William. **Does disaggregated electricity feedback reduce domestic electricity consumption? A systematic review of the literature**. arXiv:1605.00962, 2016. Disponível em: <Does disaggregated electricity feedback reduce domestic...>. Acesso em: 23 ago. 2026.
 
NAÇÕES UNIDAS BRASIL. **Objetivo de Desenvolvimento Sustentável 12: Consumo e produção responsáveis**. [s.d.-a]. Disponível em: <https://brasil.un.org/pt-br/sdgs/12>. Acesso em: 23 ago. 2026.
 
NAÇÕES UNIDAS BRASIL. **Objetivo de Desenvolvimento Sustentável 13: Ação contra a mudança global do clima**. [s.d.-b]. Disponível em: <https://brasil.un.org/pt-br/sdgs/13>. Acesso em: 23 ago. 2026.
 
SOUZA, Thales Ruano Barros de et al. **Residential smart plug with bluetooth communication**. arXiv:2103.15757, 2021. Disponível em: <Residential smart plug with bluetooth communication>. Acesso em: 23 ago. 2026.
 
TP-LINK. **Tapo P110: Tomada Inteligente Wi-Fi 10A Bivolt**. [S.l.]: TP-Link Tecnologia do Brasil, [s.d.]. Disponível em: <Tapo P110 | Tomada Inteligente Wi-Fi 10A Bivolt | TP-Link Brasil>. Acesso em: 23 ago. 2026.
 
 
