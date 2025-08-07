# OPERATIONS_DA_AdheranceIndicatorGoalGeneration-Performer

Processo que realiza o preenchimento das metas semanais na aba semanal atual na planilha de controle

## 1. Informações de configuração

  ### 1.1. Assets
  | **Nome**            |  **Tipo** |
  | :-------------------| :-------: |
  | SmarthisMailSupport | String    |

  ### 1.2. Credentials
  | **Nome**                 |
  | :----------------------- |
  | ClientSecretOffice365App |
  | ClientIdOffice365App     |
  | TenantIdOffice365App     |

  ### 1.3. Queues
  | **Nome**                                       | **Unique Ref.** | **Auto Retry** |
  | :--------------------------------------------- | :-------------: | :------------: |
  | OPERATIONS_DA_AdheranceIndicatorGoalGeneration | Não há          | Não há         |

  ### 1.4. Parâmetros
  | **Nome**                            |  **Tipo**    | **Valor** | **Descrição**                                                                                    |
  | :---------------------------------- | :-----:      | --------: | --------------------------------------------------------------------------------------------- |
  | in_processQueueName                 | String       | -         | Fila do orquestrador responsável por armazenar os itens do processo                           |
  | in_processQueueFolder               | String       | -         | Folder responsável pela organização de pastas do processo dentro do orquestrado               |
  | in_shouldReport                     | Boolean      | True      | Variável booleana responsável pela execução do report de erros da automação                   |
  | in_shouldUseConfigFromStorageBucket | Boolean      | True      | Variável booleana responsável pela tomada de decisão de ler o config do Starage Bucket ou não |

## 2. Especificações do Projeto

O projeto foi feito utilizando o template de Performer da Smarthis. O Process é responsável por obter a data final da meta do meterial na aba semanal anterior, buscar o arquivo relativo a essa data na pasta de planejamento, realizar a leitura desse arquivo e preencher as informações na região relativa ao material.
