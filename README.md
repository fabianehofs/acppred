# acppred

By Fabiane Hofs

a tool to predict anticancer peptides

## Setup

```
$ make setup
```


A seguir alguns comandos utilizados na execução do projeto:


setup.py >>  especifica o conteúdo de um módulo para que ele possa executar as ações apropriadas (como localizar dependências) durante a primeira instalação do módulo. É um script Python normalmente incluído em bibliotecas ou aplicativos escritos em Python. Seu objetivo é garantir que o programa seja instalado corretamente.

        name = nome do projeto (acppred)
        version: 0.0.1 =é a versão de lançamento.
        author= 'Fabiane Hofs' (autor do projeto)
        

server.py >> arquivo python para o servidor

	  Flask  >> é um micro framework que utiliza a linguagem Python para criar aplicativos Web.
  
requirements.txt. >> O arquivo "requirements. txt" contém as informações e versões dos pacotes necessários para rodar algum script ou projeto. São arquivos de dependência do projeto. Constitui um arquivo de texto, contendo uma lista de itens/pacotes para serem instalados durante o pip install.

               scikit-learn >> é uma biblioteca da linguagem Python desenvolvida especificamente para aplicação prática de machine learning. Dispõe de ferramentas simples e     eficientes para análise preditiva de dados, é reutilizável em diferentes situações, possui código aberto, sendo acessível a todos.
               
               umap-learning >> O UMAP é um algoritmo para redução de dimensão baseado em várias técnicas de aprendizado e análise de dados. 
imbalanced-learn: se concentra em como um sistema inteligente pode aprender quando recebe dados desequilibrados. Resolver problemas de aprendizagem desequilibrados é crítico em vários sistemas de rede com uso intensivo de dados, incluindo vigilância, segurança, internet, finanças etc.

              plotly >> é uma biblioteca de visualização de dados em Python, com ela é possível construir gráficos interativos de maneira simples. Para construir o Scatter plot utiliza-se a função 'scatter' e com apenas uma linha de código é gerado o gráfico.

              pandas >> é uma ferramenta de análise e manipulação de dados de código aberto rápida, poderosa, flexível e fácil de usar.  O Pandas geralmente é um dos mais poderosos e eficientes para análise exploratória de dados.
              
              numpy >> fornece um grande conjunto de funções e operações de biblioteca que ajudam os programadores a executar facilmente cálculos numéricos. Instalado utilizando o comando: pip install numpy.
              
              biopython >> é uma biblioteca Python para análise de dados biológicos, possui um conjunto de classes e métodos para análises de alinhamentos de sequências, estruturas de proteínas, consulta de bancos de dados biológicos, genética de populações, filogenia, entre outros.
              
              pytest >> é um framework usado para a criação de testes de uma maneira mais dinâmica e rápida. Seus testes devem ser desenvolvidos em python (todos os arquivos devem ser salvos com a extensão . py), o que faz com que o código fique menor, seja mais legível e fácil de dar manutenção.
              
              flask >> é um framework, ou seja, é um conjunto de ferramentas do Python usado para desenvolvimento web.
              gunicorn (“Green Unicorn”) >> é um servidor WSGI para Unix, feito em python; ele disponibilizará a aplicação web.
              
              environment.yml :  é um arquivo de texto que contém uma lista de dependências e quais canais serão priorizados para baixá-los. 

.gitignore >> é um arquivo de texto que diz ao Git quais arquivos ou pastas ele deve ignorar (não devem ser rastreados) em um projeto. Um arquivo .gitignore local geralmente é colocado no diretório principal de um projeto. 

.gitkeep >> em um diretório vazio em que se deseja que o Git realize o rastreio. Este arquivo é criado com o . na frente para ser um arquivo oculto.

 __init__.py >>  necessário para que o Python trate diretórios contendo o arquivo como pacotes. Isso previne que diretórios com um nome comum, como string, ocultem, involuntariamente, módulos válidos que ocorrem posteriormente no caminho de busca do módulo.
 
             from . import predict >> A declaração de importação permite que seja importado todas as funções de um módulo para o código. No entanto, se quisermos importar apenas algumas funções ou apenas uma; pode-se utilizar a instrução from.
 
models.py >> Modelos são objetos em Python que definem a estrutura dos dados de um aplicativo e fornecem mecanismos para gerenciar (adicionar, modificar e excluir) e consultar registros no banco de dados.

            sklearn.ensemble: O módulo ensemble inclui dois algoritmos de média baseados em ‘árvores de decisão aleatórias’: o algoritmo RandomForest e o método Extra-Trees.

	          RandomForestClassifier: Uma floresta aleatória é um meta estimador que ajusta vários classificadores de árvore de decisão em várias subamostras do conjunto de dados e usa a média para melhorar a precisão preditiva e controlar o ajuste excessivo.

	          EX: from sklearn.ensemble import RandomForestClassifier >> importar do módulo sklearn.ensemble, o algoritmo RandomForest.
            
            class Model: >> Para definir uma classe.

	Def  >> serve para criar um método. O construtor é um método reservado chamado _init>. A tarefa dos construtores é inicializar (atribuir valores) aos membros de dados da classe quando um objeto da classe é criado. Como os métodos, um construtor também contém uma coleção de instruções que são executadas no momento da criação do objeto.

        Ex: def __init__(self, estimator, positive_peptides, negative_peptides):  >> Essa classe define um estimador para predição de peptídeo anticâncer.

      	Args: >> são argumentos não nomeados.

	                        - estimator: um estimador scikit-learn
                          -Positive_peptides: um arquivo contendo peptídeos anticancerígenos
                           -Negative_peptides: um arquivo contendo peptídeos não anticancerígenos.

          def train (self):  >> treina um modelo preditivo para peptídeos anticâncer.

          def predict (self, sequence):  >> Prediz a atividade anticâncer por ser peptídeo.

          def save(self,filename): >> Salva o modelo em um arquivo.

          def load (filename):  >> Carrega um objeto de modelo treinado.
          
          Predict.py >> predição do modelo.

          Def main(): a função “main” serve como ponto de partida para a execução do programa; geralmente controla a execução direcionando as chamadas para outras funções no programa.

          argument_parser.add_argument('--input', required=True, help='Input FASTA file'):

              argument_parser >> analisa os argumentos. Permite que o usuário de seu programa forneça valores para variáveis em tempo de execução. É um meio de comunicação entre o criador de um programa e o usuário.

              add_argument >> criou um argumento posicional. Para argumentos posicionais para uma função Python, a ordem é importante. O primeiro valor passado da linha de comando torna-se o primeiro argumento posicional. O segundo valor passado torna-se o segundo argumento posicional.

             train.py  >> utilizado no treinamento do modelo de classificação de peptídeos anticancerígenos.

default >> é um parâmetro que tem um valor associado na declaração da função, ou seja, o valor é atribuído ao parâmetro dentro do parêntesis. No caso do nosso projeto, os valores atribuídos foram: peptídeos positivos: 'um arquivo contendo peptídeos anticancerígenos'; peptídeos negativos: 'um arquivo contendo peptídeos não anticancerígenos'.

utils.py >> é uma coleção de pequenas funções e classes Python que tornam os padrões comuns mais curtos e fáceis. No nosso projeto, foram descritos os aminoácidos permitidos: 'ARNDCEQGHILKMFPSTWYV'


Breve resumo de alguns comandos utilizados na execução do projeto construído ao longo da disciplina:



git config   --global user.name “Fabiane Hofs” >>Define o nome do usuário para o Git.

git config –global user.email fabianehofs.ufpel@gmail.com >>Define o e-mail do usuário para o git.

git init >> inicializa um repositório Git.

git push -u origin master >> envia os arquivos modificados e “commitados” para o repositório do github
	-u >> faz com que o Git armazene esse comando e da próxima vez basta utilizarmos git push.
	-origin >> diz que o repositório no github possui o mesmo nome do projeto/diretório que está sendo enviado.
	-master >> nome da Branch.
  
git pull origin master >> verifica as mudanças efetuadas por outros colaboradores do projeto.

git checkout  - arquivo.txt >> Desfaz a ultima alteração feita no arquivo.

Commit >> é um grupo de alterações no código. Um commit contém as alterações que foram feitas nele e uma mensagem descritiva, além de informações meta (data, autor, etc).

git add >> arquivos a serem adicionados ao commit.

git commit >> O comando "commit" é usado para salvar suas alterações no repositório local.

git add . >> adiciona todos os arquivos alterados num repositório.

Branch >> Branches são separações de código. O Branch padrão do projeto é o principal.

git branch [nome da branch] >> para criar um Branch.

git checkout [branch de destino] >> para trocar de Branch.

git pull >>  é usado para buscar e baixar conteúdo de um repositório remoto e atualizar imediatamente o repositório local para corresponder a esse conteúdo.










