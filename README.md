# FastApi do zero (intro):

#### Requisitos

| Ferramenta        | Versão     | Descrição                                             |
|-------------------|------------|-------------------------------------------------------|
| Visual Code       | >= 4.9.0   | IDE de desenvolvimento padrão                         |
| Python            | >= 3.11    | linguagem                                             |
| poetry            | >= 1.5.1   | gerenciador de dependências                           |
| Docker            | >= 20.10.2 | Container Engine                                      |
| Git               | -          | Controle de versões                                   |
| Linux / Windows 10| -          | Sistema operacional                                   |

<hr />

### Como executar o projeto

- Clone este repositório.
  - `$ git clone {URL deste repositório} `
- Verifique se o python 3.11 está devidamente instalado e com as variáveis de ambiente configuradas.

  - `$ python --version`

### instalando o poetry 

- https://python-poetry.org/docs/ 

- obs depois da instalação verificar o PATH

### Comandos basicos do poetry
- entrar no ambiente virtual : poetry shell || sair do ambiente virtual : deactivate

- instalar dependencias que se encontram no arquivo poetry.lock : poetry install




### Para rodar:
- run = 'uvicorn fastapidudu.app:app --reload'
- 
- Acesse http://localhost:8000 no seu navegador, e você deve ver a mensagem "Hello, World!" em formato JSON.

### Ferramentas de desenvolvimento:

- Ruff : configuração padrão mas que siga a PEP-8 usando 80 caracteres por linha e ignorando o ambiente virtual e pasta de migrações do banco de dados(verificar o pyproject.toml [tool.ruff])

- isort: configuração no formato Black (onde coloca uma instrução 'import' por linha) assim evitando conflitos no git é tbm usar a base da PEP-8 do mesmo jeito que é usado no ruff (verificar o pyproject.toml [tool.isort])

- pytest: configuração para reconhecer o caminho base para execução dos testes na raiz do projeto '.' (verificar o pyproject.toml [tool.pytest.ini_options])
  
- blue: configuração para excluir o caminho das migrações quando essas forem utilizadas (verificar o pyproject.toml [tool.blue])
  
- Taskipy: simplificar a execução de certos comandos (verificar o pyproject.toml [tool.taskipy.tasks])
  
#### os comandos definidos atraves do taskipy:
Os comandos definidos fazem o seguinte:

- lint: executa o ruff para ver se não temos nenhum problema com o código e checa se estamos de acordo com a PEP-8
- format: formata o código usando blue e isort
- run: executa o servidor de desenvolvimento do FastAPI
- pre_test: executa a camada de lint antes de executar os teste
- test: executa os testes com pytest de forma verbosa (-vv) e adiciona nosso código como base de cobertura
- post_test: gera um report de cobertura após os testes
- Para executar um comando, é bem mais simples, precisando somente passar a palavra task <comando>.



  