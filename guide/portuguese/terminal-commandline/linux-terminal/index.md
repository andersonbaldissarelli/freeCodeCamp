
## Terminal Linux

A maioria dos usuários preferem interagir com o sistema através da interface gráfica, porém essa apresenta muitas limitações quando o assunto é alterações que o usuário poderá realizar no sistema. Para o usuário sair dessa limitação e ter o controle total existe uma ferramenta poderosa chamada terminal, também conhecido como linha de comando ou shell. O terminal do Linux permite que o usuário faça alterações avançadas no sistema por meio do acesso root, quando um usuário se torna root significa que ele passa a ser superusuário ou administrador do sistema. 

Para quem nunca utilizou o terminal, no começo pode acha-lo um pouco intimidador mas depois que você for praticando vai perceber que é mais eficiente e até mais fácil que usar a interface gráfica (sim, você irá achar isso).

A seguir veremos uma lista de comandos básicos e utéis que são muito utilizados não apenas por aqueles que chegaram no mundo do linux, mas também por usuários experiêntes.

(Antes de começar, você pode abrir o terminal usando o atalho CTRL+ALT+T ou pode pesquisar por terminal no dash)

#### man: 
O comando man deveria estar no topo de toda lista de comandos importantes do Linux. A razão é muito simples: basta executá-lo para carregar uma página de manual (man page) sobre os comandos do sistema, com definições não apenas do uso de cada ferramenta, mas também descrições detalhadas dos inúmeros parâmetros do software e exemplos de uso.

Para ler as man pages é muito fácil e basta executar o man seguindo do nome do comando que você deseja buscar ajuda. Não se esqueça de pressionar a tecla Enter após digitar o comando, caso contrário ele não será executado. 

```
man cp
```

Ao executar o comando acima, você poderá ler todas as instruções para o uso do comando cp.


#### ls
Para listar os arquivos existentes em algum diretório, basta usar o comando ls. Se executado sem parâmetros, ele listará o conteúdo do diretório em que você se encontra, mas você pode indicar um caminho para ele.

```
ls /usr/local/bin
```
Também é possível usar o ls para conferir o tamanho e a data de criação de cada arquivo ou pasta. Para isso, use o parâmetro -l e se você também quiser listar os arquivos ocultos, que começam com um ponto, use:

```
ls -lha /usr/local/bin
```


#### cd
Para pular de pasta em pasta, não precisa abrir o gerenciador de arquivos. No próprio terminal é possível navegar pelo sistema de arquivos usando o comando cd seguido do 
caminho que você deseja seguir.

```
cd /usr/local
```

Vale a pena notar que existem alguns atalhos que podem facilitar a vida do usuário. Se você executar o comando cd sem parâmetros, ele retorna para a pasta do usuário, localizada em /home. Para voltar um nível acima na árvore de diretório, use:

```
cd ..
```
Dessa forma, se você estiver em /usr/local e executar "cd ..", voltará para o diretório /usr.

#### cp
Copiar um arquivo pelo terminal, use o comando cp seguindo do arquivo de origem e o destino para ele, que pode ser tanto uma nova pasta quando um novo arquivo, com nome diferente.

```
cp arquivo1.txt e arquivo2.txt
```

ou, então

```
cp arquivo1.txt pastanova/
```

Para copiar um diretório todo, não se esqueca de inserir o parâmetro -r. Se quiser clonar uma pasta, use:

```
cp -r pasta1 pasta2
```

#### mv
Para mover arquivos existe o comando mv e ele pode ser usado tanto para remanejar arquivos como para renomeá-los. Se quiser enviar o arquivo de uma pasta para outra, basta usar:

```
mv pasta1/arquivo1 pasta2/
```

Se preferir apenas renomeá-lo, use:

```
mv arquivo1 arquivo2
```

#### more
Caso você precise ler o conteúdo de um arquivo de texto, use o comando more seguido do caminho e nome do arquivo.

```
more /home/user/arquivo.txt
```

Todo conteúdo do arquivo será exibido no terminal, preenchendo a tela com texto. Para prosseguir com a leitura, pressione a barra de espaço e, caso precise voltar uma ou mais páginas, use a tecla "b". Se quiser sair antes do fim do arquivo, pressione "q".

#### df
Para saber qual é o espaço total e quantos GB disponíveis existem em cada partição do sistema, usamos:

```
df -h
```

A opção -h, aliás, quer dizer human-readable, ou seja, legível para humanos. Se você executar o comando sem ela, as informações serão exibidas em kilobytes e será necessário convertê-las mentalmente para outras unidades.

#### sudo
Por razões de segurança, o Linux trabalha com permissões de usuários. Por isso, determinados comandos ou arquivos são acessíveis apenas pelo próprio dono ou pelo usuário administrador (root). Para que você não tenha que trocar de usuário a todo instante, existe o comando sudo, que garante credenciais de usuário root temporariamente, mediante a informação de uma senha.

Para fazer o teste, tente executar o comando:

```
ls /root
```

Você reberá um aviso de permissão negada. Em seguida, execute:

```
sudo ls /root
```

Depois de informar a senha do seu próprio usuário (no caso do Ubuntu), o comando será executado normalmente e os arquivos a pasta root serão listados no terminal.

#### grep
Imagine a seguinte situação: você tem um arquivo de texto com cerca de 200 nomes de alunos de certa escola, mas não tem certeza se um nome em específico está listado. O grep ajuda você a procurar por esse aluno e a fazer muito mais com a ajuda de expressões regulares. Caso você não tenha certeza se o nome do aluno foi escrito respeitando as letras maiúsculas, adicione o parâmetro -i para que grep passe a ignorar essa distinção durante a busca.

```
grep isadora -i arquivo.txt
```

#### clear
Por último, um comando que ajuda a organizar um pouco a confusão de letras que ficam no terminal depois de horas de uso. Para limpar toda a ela, execute o comando clear. Depois, é só voltar a usar o terminal normalmente, como se nada tivesse acontecido.

