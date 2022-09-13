# Monitorando-aplicações-com-Application-Insights

👉 
🔖 

🔖 O que é o Application Insights?

👉 O Application Insights é um recurso do Azure monitor que fornece gerenciamento de desempenho de aplicativo
(APM) extensível e monitoramento para aplicativos em real time.

![mon01](/images/mon01.png)

🔖 Características Application Insights

👉 Para usar o application insights, é necessário instalar um pequeno pacote de instrumentação (SDK) em seu 
aplicativo ou habilitar o application insights usando o agente do Application insights.

A instrumentação monitora seu aplicativo e direciona os dados de telemetria para um recurso do application insights
usando uma chave de instrumentação exclusiva. O impacto no desempenho do seu aplicativo é pequeno.

👉 Suporta uma ampla variedade de plataformas, incluindo ASP.NET, ASP.NET Core, Node.js, Java e Python.

👉 Funciona para aplicativos hospedados localmente, híbridos ou em qualquer nuvem pública.

👉 Integra-se com processo DevOps.

👉 Possui pontos de conexão para muitas ferramentas de desenvolvimento.

👉 Pode monitorar e analisar a telemetria de aplicativos móveis integrando-se ao Visual Studio App Center.


🔖 O que pode ser monitorado com o Application Insights

* Taxas de solicitação de resposta e taxas de falha
* Descubra quais páginas são mais populares, em que horas do dia e onde os usuários estão. Veja quais páginas
  apresentam melhor desempenho. Se os tempos de resposta e as taxas de falha forem altos quando houver mais
  solicitações, pode haver um problema de recursos.
* Taxas de dependências, tempos de resposta e taxas de falha, para mostrar se os serviços externos estão diminuindo 
  o desempenho.
* Exceções
* Visualizações de página e desempenho de carregamento relatados pelos navegadores dos usuários.
* Contagens de usuários e sessões.
* Contadores de desempenho de máquinas de servidor Windows ou Linux, como CPU, memória e uso de rede.
* Diagnóstico de host do Docker ou do Azure.
* Logs de rastreamento de diagnóstico de aplicativos, para que você possa correlacionar eventos de rastreamento com 
  solicitações.
* Eventos e métricas personalizadas no código do cliente ou servidor que rastreiam eventos de negócios, como itens vendidos.

🔖 OBS
  Ao ativarmos o Application Insights na aplicação, a mesma irá ter perda de performance, mas nada que interfira no desempenho.