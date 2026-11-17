![banner](./assets/banner.png)

# Econy · Computational Thinking with Python

| Integrante | RM |
|---|---|
| [Guilherme Santos Nunes](https://github.com/sannunez) | RM558989 |
| [Kaique Zaffarani](https://github.com/Z4ffarani) | RM556677 |

Global Solution 2024.2 · Engenharia de Software · FIAP

---

## O projeto Econy

O **Econy** é uma empresa fictícia criada com o objetivo de contribuir para a sustentabilidade e a redução das emissões de CO2, integrando o comércio de créditos de carbono e certificações de auditoria.

### Projeto principal

[Econy](https://github.com/Z4ffarani/Econy): repositório principal do projeto.

## Esta entrega: Computational Thinking with Python

Plataforma que integra o comércio de créditos de carbono e certificações de auditoria por meio de smart contracts (contratos inteligentes) e blockchains (tecnologia de registro distribuído e descentralizado) que utilizam o algoritmo de consenso PoS (Proof-of-Stake).

O sistema simula transações de créditos de carbono, em que as empresas podem registrar suas ações e obter validações de suas práticas ambientais. As transações, registradas em blocos criptografados, podem ser validadas por participantes da rede, que ganham stakes (poder de participação para validações de blocos), garantindo a segurança e o rastreamento de cada movimentação. Além disso, a plataforma oferece uma interface interativa para empresas monitorarem suas ações e manterem conformidade com o mercado de carbono.

O programa é composto por três sistemas principais:
- **Comercialização de créditos de carbono** | Permite que empresas comprem, vendam ou cambiem créditos de carbono com o governo dos blocos econômicos a que pertencem.
- **Certificações de sustentabilidade** | Oferece uma solução para a validação de ações ambientais das empresas por meio de auditorias terceirizadas. As certificações obtidas podem ser usadas para comprovar práticas sustentáveis.
- **Blockchains** | A base de segurança e descentralização do sistema, onde transações de créditos de carbono e certificações de sustentabilidade são registradas em arquivos binários.

| Entregável | Onde |
|---|---|
| Vídeo explicativo | [youtu.be/5BdzgsT5DlY](https://youtu.be/5BdzgsT5DlY) |
| Programa principal | [`main.py`](main.py) |

## Como executar

```bash
git clone https://github.com/Z4FFARANI-EDUCATIONAL/2024-SEM2-GS-COMPUTATIONAL-THINKING-WITH-PYTHON.git
cd 2024-SEM2-GS-COMPUTATIONAL-THINKING-WITH-PYTHON
python main.py
```

1. O arquivo `main.py` exibe um menu interativo que pergunta o nome e o setor de atuação da empresa a registrar. Depois, ela pode escolher entre comprar, vender ou cambiar créditos de carbono, obter certificações, consultar blockchains ou entender mais sobre a proposta da plataforma.
2. Nas opções de comercialização de créditos de carbono, a empresa registrada escolhe o bloco econômico em que participa e informa a quantidade de créditos. O sistema converte a quantidade para dólares a partir da cotação do bloco econômico escolhido.
3. Dependendo do tipo de transação, a empresa informa o vendedor ou o comprador de créditos de carbono.
4. Quando uma transação ou certificação é finalizada, baseada no conceito de smart contracts, ela é armazenada como um bloco (objeto de dados) que contém um hash (identificador criptográfico que permite "acorrentar" os blocos) em um arquivo binário dedicado ao tipo de transação. Caso o arquivo binário ainda não exista, cria-se um novo, consolidando um genesis block (primeiro bloco de uma blockchain).

## Funções

`main.py`:
- **Block** | Classe que define um bloco na blockchain, contendo índice, timestamp, dados transacionais, hash atual e anterior, além do validador.
- **calculate_hash** | Gera um hash único para cada bloco utilizando o algoritmo SHA-256.
- **Validator** | Classe que representa participantes no processo de validação de blockchains, incluindo empresas e um centro de dados governamental.
- **initialize_validators** | Inicializa os validadores das blockchains (de acordo com a quantidade de stakes), incluindo a empresa principal e outros participantes.
- **Blockchain** | Classe que representa a estrutura principal da cadeia de blocos, armazenando as principais informações sobre transações e garantindo a validade dos dados.
- **load_chain / save_chain** | Carregam e salvam o estado da blockchain localmente em arquivos binários, garantindo persistência de dados.
- **select_validator** | Seleciona validadores para adicionar blocos à blockchain, com base na quantidade de stakes dos participantes.
- **add_block** | Adiciona novos blocos às blockchains, associando-os ao hash do bloco anterior e salvando os dados transacionais.
- **is_valid** | Valida a integridade da blockchain, verificando se os hashes de cada bloco correspondem e se a cadeia está intacta.
- **debug_chain** | Exibe detalhes da blockchain, incluindo índice, timestamp, dados e hashes, para depuração.
- **execute_transaction** | Gerencia transações de créditos de carbono, incluindo compra, venda, troca e obtenção de certificações, gerando e adicionando blocos com os dados.
- **main** | Gerencia o fluxo principal do sistema, incluindo menus interativos para consulta de saldo, transações de créditos de carbono e consulta de blockchains.

## Observações

- Este projeto não tem relação direta com algum mercado de carbono oficial, nem com as empresas, auditorias ou certificações que o compõem.
- Alguns valores dispostos no sistema não condizem com a realidade e servem apenas para fins educativos.
- Bibliotecas essenciais foram utilizadas para criação de hashes, registro de tempo, manipulação de arquivos binários, acesso raso ao sistema operacional e sorteio de variáveis.
- É possível encerrar o sistema a qualquer momento.
- Os textos exibidos durante a execução do sistema não estão indentados no arquivo `main.py` para melhor visualização.
- Três empresas fictícias foram adicionadas ao sistema para fins experimentais, além de um centro de dados governamental. Empresas com 0 stake não participam do processo de validação. Quanto maior a quantidade de stakes de uma empresa, maior a chance de ser escolhida para validação.
- É possível que a empresa inserida seja escolhida para validar um bloco. Portanto, é importante estar atento às informações de registro de blockchains.
- Arquivos binários são criados fora da pasta do projeto, sendo utilizados para armazenar e carregar todos os tipos de transações, e podem ser excluídos se for preferível.
- O sistema foi desenvolvido parcialmente com orientação a objetos.

---

## Tecnologias

[![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org)

---

## Referências

| # | Referência | Aplicação no projeto |
|---|---|---|
| 1 | [YouTube — Dá pra copiar e colar bitcoin? Entenda blockchain](https://www.youtube.com/watch?v=0Mt16eeCv78) | Conceitos de blockchain |
| 2 | [YouTube — Crie sua própria criptomoeda](https://www.youtube.com/watch?v=IkXIA1NNocY&t=13s) | Estrutura de blocos e hashes |
| 3 | [SENAI-SP — Desvendando a Blockchain](https://www.sp.senai.br/inscricaogratuita/desvendando-a-blockchain/87241/403/29279) | Conceitos de blockchain e consenso |
| 4 | [YouTube — Construa sua própria blockchain com Python: tutorial passo a passo](https://www.youtube.com/watch?v=yBuzx8akAd0) | Implementação da blockchain em Python |
| 5 | [CarbonCredits.com](https://carboncredits.com) | Contexto do mercado de créditos de carbono |
