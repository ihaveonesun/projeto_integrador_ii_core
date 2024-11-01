# Projeto Objeto Fila
projeto_integrador_ii_core_fila

# Projeto de Sistema de Fila com Prioridades e Gestão de Riscos

Este projeto implementa um subsistema de filas para organização de usuários, com base em critérios de **idade**, **especialidade** e **grau de risco**. 
Utilizando conceitos de programação orientada a objetos (POO), o sistema separa os usuários em filas com diferentes prioridades, garantindo que aqueles com maior necessidade sejam atendidos primeiro.

Sendo apenas um componente de projeto maior. Cuja etapa de implementação poderá sofrer alterações.

## Estrutura do Projeto

O sistema utiliza uma classe `Fila`, que implementa as operações de uma fila convencional, permitindo:
- Inserção e remoção de usuários.
- Armazenamento e cálculo de tempo médio de espera total (TMA) da fila.
- A inserção dos usuários em posições específicas, dependendo do grau de risco.

### Principais Funcionalidades

1. **Cadastro e Estratificação de Usuários**:
    - Os usuários são cadastrados com informações como **data de nascimento**, **especialidade** e **grau de risco**.
    - A idade é calculada automaticamente com base na data de nascimento fornecida.
    - Uma senha é gerada para o usuário, indicando sua prioridade na fila.

2. **Estruturação de Filas com Priorização**:
    - A organização das filas considera a idade e a prioridade do usuário:
        - **Fila Normal**: Usuários sem prioridade específica.
        - **Fila Prioridade 1**: Usuários acima de 60 anos ou com prioridade especial.
        - **Fila Prioridade Extra**: Usuários acima de 80 anos, que recebem o nível máximo de prioridade.
    - O sistema permite a inserção de usuários em posições específicas dentro de cada fila, baseando-se no grau de risco.

3. **Cálculo e Gestão do Tempo de Espera (TMA)**:
    - A classe `Fila` mantém um registro do tempo médio de atendimento dos usuários (TMA) e calcula o tempo total de espera de cada fila, fornecendo uma métrica para monitoramento do atendimento.

## Classes e Funções Principais

- **Classe `Fila`**: Representa uma fila com métodos para inserção, remoção, exibição e cálculo de tempo de espera.
    - `inserir`: Insere um usuário na posição especificada.
    - `remover`: Remove um usuário, retornando o primeiro da fila ou o da posição indicada.
    - `topo`: Exibe o próximo usuário a ser atendido.
    - `vazio`: Verifica se a fila está vazia.
    - `quantidade`: Retorna o número de usuários na fila.
    - `exibir`: Retorna uma lista com todos os usuários na fila.
    - `tempo_espera`: Calcula o tempo total de espera com base no TMA.

- **Funções Auxiliares**:
    - `calc_idade`: Calcula a idade com base na data de nascimento do usuário.
    - `inserir_usuario`: Realiza o cadastro do usuário, gera a senha e insere na fila correta com base na prioridade.
    - `manejar_risco`: Determina a posição de inserção do usuário na fila, de acordo com o grau de risco.

## Exemplo de Uso

1. **Cadastro de Usuário**:
    ```python
    usuario = {
        'Nome': 'João Silva',
        'Nascimento': datetime.date(1950, 5, 12),
        'Especialidade': 'Cardiologia',
        'Risco': 3,
        'Prioridade': False,
        'TMA': 15
    }
    inserir_usuario(usuario)
    ```

2. **Visualização de Filas**:
    - Obtenha a lista de usuários na fila de prioridade 1:
    ```python
    fila_prioridade_1.exibir()
    ```

## Requisitos do Projeto

- **Python** >= 3.6
- **Bibliotecas**: `datetime`, `pandas` (opcional, dependendo do formato de dados dos usuários)

## Observações Finais

Este sistema é projetado para simular um atendimento com prioridades e pode ser expandido para incluir novas filas ou ajustes nos critérios de priorização. Sinta-se à vontade para modificar o código conforme as necessidades do seu caso de uso.

---
