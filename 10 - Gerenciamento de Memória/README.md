| Característica                | Java (GC Automático)                                | C (malloc/free Manual)                          |
|------------------------------|------------------------------------------------------|-------------------------------------------------|
| Tipo de gerenciamento        | Automático (Garbage Collector)                      | Manual (Programador gerencia com malloc e free)  |
| Alocação de memória          | new para objetos (heap)                             | malloc, calloc, realloc (heap)                   |
| Liberação de memória         | Feita automaticamente pelo Garbage Collector        | Responsabilidade do programador (free)           |
| Risco de vazamento de memória| Baixo (mas ainda possível se houver referências não liberadas) | Alto (se free não for usado corretamente)  |
| Risco de uso de memória inválida | Baixo (uso após liberação não é possível diretamente) | Alto (uso de ponteiros para memória já liberada)|
| Controle de ponteiros        | Não há acesso direto a ponteiros                    | Controle completo de ponteiros                   |
| Performance                  | Leve impacto por coleta automática                  | Alto desempenho se bem gerenciado                |
| Segurança                    | Mais seguro contra erros de memória                 | Mais propenso a bugs de alocação/liberação       |
| Complexidade para o programador | Baixa (GC cuida da limpeza)                       | Alta (programador cuida de toda a gestão)       |
