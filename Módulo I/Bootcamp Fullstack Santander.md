bootcamp - campo de treinamento (jornadas intensas e completas)

#O pensamento computacional é baseado em 4 pilares:
	- decomposição: reduzir a problemas menores
	- reconhecimento de padrões: linhas de raciocínio que levem à solução do problema
	- abstração: sintetizar para uma fotms generalista (parametrizar)
	- design de algoritmo: passo a passo para chegar à solução
	
Esse processo é contínuo, ainda com algoritmos prontos e executáveis, para que sempre haja seu refinamento (refinamento + teste + análise).

** Pensamento sistemático - analítico

# Habilidades Complementares
	- Raciocínio Lógico: é uma forma de pensamento estruturado, ou raciocínio que permite encontrar a conclusão ou determinar a resolução de um problema.
	
		Classificado em: Indução (inferência - indução a partir de um fenômeno observado), Dedução (inverso à indução, parte de leis e teorias para supor fenômenos reais) e Abdução (parte-se de uma premissa, baseado na observação/percepção)

	- Aperfeiçoamento: Melhoramento - Aprimoramento - Refinamento - Ato de aperfeiçoar
	
# Pilares
	
	## Decomposição 
		Segmentar o problema, 'quebrar em problemas menores'
		Processo de quebrar e determinar partes menores e gerenciáveis
		Combinar os elementos recompondo o problema original
		
		
		Como decompor:
			* Identificar ou coletar dados
			*Agregar os dados
			*Funcionalidade
			
			--> Identificar os componentes --> Papel de cada componente --> Interdependência das peças
			
	## Padrões
		Reconhecimento de Padrões: modelo base, estrutura invariante e repetições
		
		
		
# Funções

	São blocos de instruções (código), identificados por nomes e parâmetros.
	
	Dados --> Função --> Resultado!
	
Modulo 1

#Comandos básicos de sistemas operacionais

	* Windows
	listar diretórios/conteúdo da pasta atual: dir 
	navegar entre as pastas: cd / (voltar na pasta raíz)
	voltar uma pasta: cd ..
	limpar a tela do terminal: cls
	criar uma pasta: mkdir <nome>
	para jogar um comando dentro de um arquivo sem entrar nele, basta usar (echo 'o que se deseja inserir' > 'arquivo') que é um redirecionador de fluxo, exemplo: echo hello > hello.txt
	deletar um arquivo: del <nome> # se esse comando for usado em uma pasta, será detetado todos os arquivos presentes nela, mas a pasta não será a apagada
	deletar uma pasta: rmdir <nome> /S /Q 	#/S:inclui todas os subdiretórios e arquivos; /Q:modo silencioso, não solicita confirmação para excluir. /q só funcionará se /s for especificado
	
	

	
	* Linux
	pedir permissão para execução do usuário como administrador: sudo su
	listar diretórios/conteúdo da pasta atual: ls
	navegar entre as pastas: cd / (voltar na pasta raíz)
	voltar uma pasta: cd ..
	limpar a tela do terminal: clear ou Ctrl L 
	criar uma pasta: mkdir <nome>
	para jogar um comando dentro de um arquivo sem entrar nele, basta usar (echo 'o que se deseja inserir' > 'arquivo') que é um redirecionador de fluxo, exemplo: echo hello > hello.txt
	deletar uma pasta: rm -rf <nome>	#rf: modo forçado e recursivo, apaga tudo que houver na pasta
	
	
# Funcionamento do GIT

SHA1: (Security Hash Algoritm) algoritmo de encriptação, gera um hash -chave (conjunto de caracteres de 40 dígitos), muito útil e importante para verificar se sofreu alterações e se é realmente o conteúdo esperado.

Para gerar o hash de um arquivo no Git: openssl sha1 <arquivo>

# Objetos internos do GIT

O GIT é um Sistema Distribuído Seguro, pois garante integridade e dificultam a possibilidade de serem alterados. Estrutura altamente confiável.

# Autenticação do GIT 

## Chave SSH no Windows

	Forma de estabelecer uma conexão remota segura e encriptada (máquina do usuário e servidor do GitHub) - """"assinatura""""
	
	### Criar a chave
	
		-> no terminal gitbash
			ssh-keygen -t ed25519 -C <email cadastrado>
			cadastrar senha
			cd /c/User/User/.ssh   #local onde foi guradada as chaves pública e privada
			cat id_ed25519.pub
			_mostrar a chave pública_ *copiar*
			
		-> no GitHub, na caixa para adicionar a chave pública gerada na máquina:
			dar um título
			colar a chave
	
		-> no Git Bash
			cd /c/User/User/.ssh  
			eval $(ssh-agent -s)			#reinicializando o protocolo ssh
			ssh-add id_ed25519 		#passar o caminho de onde está a chave privada para decriptografar os arquivos que chegarem criptografados com a chave pública
			_digitar senha_
			
	### Usando a Chave SSH
		
		-> no GitHub
			entar no repositório > Code > SSH > copiar url ssh
			
		-> no Git Bash	
			git clone <colar caminho ssh>
			yes
			

## Chave SSH no Linux

	Forma de estabelecer uma conexão remota segura e encriptada (máquina do usuário e servidor do GitHub) - """"assinatura""""
	
	### Criar a chave
	
		-> no terminal gitbash
			ssh-keygen -t ed25519 -C <email cadastrado>
			cadastrar senha
			cd /c/User/User/.ssh   #local onde foi guradada as chaves pública e privada
			cat id_ed25519.pub
			_mostrar a chave pública_ *copiar*
			
		-> no GitHub, na caixa para adicionar a chave pública gerada na máquina:
			dar um título
			colar a chave
	
		-> no Git Bash
			cd /c/User/User/.ssh  
			eval $(ssh-agent -s)			#inicializa o protocolo ssh
			ssh-add id_ed25519 		#passar o caminho de onde está a chave privada para decriptografar os arquivos que chegarem criptografados com a chave pública
			_digitar senha_
			
	### Usando a Chave SSH
		
		-> no GitHub
			entar no repositório > Code > SSH > copiar link ssh
			
		-> no Git Bash	
			git clone <colar caminho ssh>
			yes
			
## Token

	-> no GitHub
		perfil > Developer Settings > Personal Access Token> Generate New Token > marcar 'repo' > Generate Token > copiar o token gerado e salvar em um arquivo no computador
		
	### Usando o Token
	
		-> no GitHub
			entar no repositório > Code > HTTPS > copiar link https
			
		-> no Git Bash	
			git clone <colar caminho http>
			inserir o token 
			

# Iniciando um GIT

git init: inicializar o GIT
ls -a: mostra arquivos ocultos
git add * 	#manda para área de staging
git commit -m "commit inicial"		#'commita'
git push origin master (mandar/empurra para a nuvem (repositório remoto) do github)

# Clonar um GIT

-> copiar o endereço https dele
-> ir para o bash
git clone <url https>

GIT : sistema de versionamento de código distribuído

# Resolvendo conflitos 

## Conflito de Merge 
		
		* Abrir o arquivo manualmente e ir na linha do conflito * 
		
		git init: inicializar o GIT
		ls -a: mostra arquivos ocultos
		git add * 	#manda para área de staging
		git commit -m "commit inicial"		#'commita'
		git push origin master (mandar/empurra para a nuvem (repositório remoto) do github)
		git pull origin master (puxa a última versão do github)
			abrir o arquivo indicado com conflito
			Apagar o que não deve estar no código naquela linha
			salvar
		git status
		git add *
		git commit -m "Resolve conflitos"
		git push origin master 
		
		git remote - v		#indica para onde o repositório está apontado (nuvem)
		

		

