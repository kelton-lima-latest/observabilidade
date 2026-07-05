# Métricas

## Métricas de sistema
- Quantidade de requisições
- Quantidade de erros
- Consumo de recursos
- APIs mais acessadas
- Tempo de acesso a um recurso

## Métricas de negócio
- Quantidade de usuários acessando a aplicação
- Boletos emitidos
- Compras de um produto

Negócio e sistema devem está sempre se comunicando.  
Ex.: vendas estão caindo. Informar ao marketing que o tempo de resposta estão mais lentos. Isso afeta as vendas diretamente.

Métrica não é log, ela está relacionada a:
- Dados numéricos
- Gráficos
- Agregações
- Performance

Logs
- Dados textuais
- Mensagens de erro
- Informação
- Buscáveis

## Tipos de mérticas
- Counter: Nunca é decrementado, sempre acréscimo
- Gauge: Icremento e decremento. Ex.: concusmo de cpu, memória...
- Histogram: amostragem de valor. Frequência
- Summary: Dado vinculado a porcentagem de amostragem

# Logs
Registros relacionados a eventos. Utilizado para reproduzir um passo a passo que aconteceu no sistema

## O que deve está em um log?
- Registros de requisições e respostas feitos para a aplicação
- Chamadas feitas para serviços externos
- Transformações de dados
- Eventos importantes

## Níveis de log
FATAL: Erro crítico que compromete o funcionamento do sistema. Necessário análise imediata.
ERROR: Falha no fluxo, mas não compromete o sistema. Aplicação segue funcionando, mas é preciso analisar o mais rápido possível.
WARNING: Ocorreu falha, mas houve continuidade no fluxo. É importante investigar o que aconteceu.
INFO: Evento comum de baixa importância, mas em cenários de acompanhamento do fluxo, pode ser útil.
DEBUG: Eventos utilizados em processo de desenvolvimento.

Log tradicional: Mensagem simples. Não é eficiente

Log estruturado:

Não é eficiente trabalhar com arquivos .log. Vão existir vários arquivos para consulta, com isso as informações ficam difícil de serem encontradas.

# Tracing
Rastreamento do fluxo de eventos de uma requisição entre os processos transitados. Tracing analisa todo o percurso para uma análise mais detalhada do comportamento do fluxo em si.

## Componentes tracing
- Trace
- Span
    - tags: eventos chave/valor que pode registrar em determinado span
    - logs: eventos que acontecem em determinado span
- SpanContext
    - 1. TraceID
    - 2. SpanID

Possível implementar tracing sem instrumentar código? Sim, utilizando service mesh.
Aplicação:
- Opentracins
- OpenTelemetry

Ferramenta:
- Zipkin
- Jaeger
- Grafana Tempo

