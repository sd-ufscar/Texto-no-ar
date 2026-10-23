# Validação e preservação — Texto-no-ar

Verificações estáticas realizadas em **23 de outubro de 2026**. A publicação preserva a organização interna da pasta local, a lógica, os parâmetros e as conexões dos circuitos.

## Integridade dos arquivos locais

| Conferência | Resultado |
|---|---|
| Arquivos locais inventariados | 160 |
| Arquivos da pasta original versionados | 34 |
| Intermediários e estado local ignorados | 126 |
| Dependências espelhadas na raiz | 6 |
| Resumos de compilação originais preservados | 3 |
| Alterações de bytes nas fontes locais ou nas cópias | Nenhuma |
| ROM conferida | 64 endereços, 8 bits, todos preenchidos |
| Referências verificadas a partir do QSF ativo | 30 |

O [inventário completo](inventario-local.csv) registra cada caminho, tamanho, SHA-256 e decisão de versionamento. As cópias publicadas devem conservar os hashes correspondentes. As referências superiores `../lab_04.qip` e `../lab_04.mif` são atendidas por seis cópias idênticas na raiz do repositório. Nenhuma fonte ou parâmetro foi editado.

## Conteúdo preexistente no repositório

Base anterior: `efa69c06bd7b649d5c0d23860048e3d010d5c292`. As movimentações foram realizadas com `git mv`. O conteúdo de cada arquivo foi preservado:

| Caminho anterior | Destino | SHA-256 |
|---|---|---|
| `lab_04.7z` | [comprimido/lab_04.7z](../comprimido/lab_04.7z) | `6d05092a20bea5b583efa2b652c5918c04774aa17885dd73d6a44a706220f233` |

Nenhum arquivo preexistente foi descartado, recompactado ou substituído. Uma referência local de backup conserva o commit anterior; o histórico remoto não é reescrito.

## Dependências e configuração

A revisão é `lab_04`, o topo é `lab_04A` e o dispositivo é `5CSXFC6D6F31C6`. Foram conferidos os arquivos de IP relacionados pelo QSF, seus arquivos gerados, símbolos e inicialização da ROM. As referências ativas ficam contidas no repositório; o modelo geral `Arquivo_Pinos_DE10_2V5.qsf` não é importado pela revisão ativa.

O QPF, a última versão do QSF e os IPs registram a família de versões 23.1.

Os arquivos `.v` preservados pertencem aos componentes gerados pelo ambiente gráfico do Quartus. A implementação do experimento permanece em BDF; não foi adicionada uma reimplementação HDL.

## Exclusões do versionamento

| Grupo | Justificativa |
|---|---|
| `db/`, `incremental_db/`, `greybox_tmp/` | Bancos, bloqueios e intermediários regenerados pelo Quartus |
| `output_files/` | Relatórios, netlists e arquivos de programação regeneráveis; três resumos históricos preservados em `docs/relatorios-originais/` |
| `*.bak` | Cópias de edição que não integram a revisão ativa |
| `*.qws` | Estado local da interface Quartus |
| `simulation/questa/*.vo` e `*.sft` | Netlist de simulação e arquivos de apoio gerados; não são estímulos originais ou configurações de IP |

Não foram ignorados globalmente `.v`, `.qpf`, `.qsf`, `.bdf`, `.bsf`, `.qip`, `.mif`, `.hex`, `.cmp` ou `.inc`. A cópia local integral permanece preservada; as exclusões tratam do conteúdo enviado ao GitHub.

## Relatórios e limites da validação

Os resumos originais de [síntese](relatorios-originais/lab_04.map.summary), [Fitter](relatorios-originais/lab_04.fit.summary) e [temporização](relatorios-originais/lab_04.sta.summary) registram a compilação de **22 de setembro de 2026**. O Fitter consta como concluído, mas o Timing Analyzer apresenta folgas negativas. Esses registros não certificam fechamento temporal nem uma compilação executada durante a publicação.

O Quartus Prime não foi encontrado no PATH ou nos diretórios usuais do ambiente. Não foram realizados abertura dos projetos no Quartus, nova síntese, simulação, gravação ou ensaio físico. O funcionamento descrito no [README](../README.md) é fundamentado nos esquemáticos, nos parâmetros dos IPs, no MIF e nos registros originais, com os cálculos teóricos identificados.

Foram conferidos os links relativos, os hashes de preservação e os tamanhos dos arquivos preparados para commit. A inspeção automática do conteúdo novo não detectou padrões usuais de tokens, chaves privadas ou caminhos pessoais. Os arquivos preexistentes em `comprimido/` mantêm o conteúdo que já estava publicado.
