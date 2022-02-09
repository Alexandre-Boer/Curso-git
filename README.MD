# Curso de git e github

Esse repositório foi criado para o curso de git e github realizado pelo Dev Aprender.  
[Link do curso](https://www.youtube.com/watch?v=kB5e-gTAl_s)  
[Canal do Dev Aprender](https://www.youtube.com/c/DevAprender/featured)  
  

## O que é git
Git é um sistema de controle de versões distribuido, muito utilizado no processo de desenvolvimento de *software*.

## Como inicializar um repositório
- Caso você já possua um diretório que está trabalhando, pode inicializar o respositório abrindo o terminal no diretório que deseja e digitar o comando:  
    ```
    git init
    ```  
  
- Caso queira criar um novo diretório para o projeto bastar utilizar:  
    ```
    git init NomeDoDiretorio
    ```  
  
## Como adicionar arquivos ao controle de versão  
Para adicionar os arquivos que estão dentro do seu repositório ao git podemos utilizar os seguintes comandos:  
- Caso queira adicionar apenas 1 arquivo específico:
    ```
    git add "Arquivo especifico.txt"
    ```
- Caso queira adicionar todos os arquivos do repositório ao git:
    ```
    git add .
    ```
  
## Como criar versões do código com commit  
O `git commit` serve para salvar as alterações feitas no arquivo e versionar as mudanças realizadas.  
Quando for realizar o primeiro *commit*, devemos configurar o nome e email que deverá ser usado no *commit*, para isso utilizamos os comandos:
```
git config --global user.name "Seu Nome"
git config --global user.email "seu_email@email.com"
```
Após ter configurado o nome e e-mail para o *commit* podemos de fato realizar o *commit* com o seguinte comando:
```
git commit -m "commit incial"
```
Uma boa pratica ao realizar commits é sempre comentar o que foi alterado naquele *commit*, para que facilite o controle das versões.  
  
## Como enviar alterações usando git push
Uma vez que adicionamos os arquivos com o `git add` e salvamos as alterações com o `git commit` precisamos enviar as alterações para o servidor, para isso utilizamos o `git push`:  
  
- Caso seja a primeira vez que iremos fazer o *Push* devemos especificar em qual *branch* o código deve ser enviado. Fazemos isso com o comando:  
    ```
    git push --set-upstream origin Master
    ```
    No caso do comando acima as alterações devem ser enviadas para a *branch* Master  

- Depois do primeiro *push* podemos enviar as próximas alterações somente utilizando o comando:  
    ```
    git push
    ```

## Como verificar histórico de atualizações  
Para verificar o histórico de atualizações (*commits*) do projeto, basta rodar o comando:  
```
git reflog
```
Com esse comando conseguimos ver o *ID* de cada alteração e o que foi alterado (comentário que fizemos no *commit*).  
  
## Como navegar entre versões do seu código  
Caso precise voltar para uma versão anterior do arquivo podemos fazer da seguinte maneira:  

1. Verifique o histórico de atualizações:  
    ```
    git reflog
    ```
2. Copie o *ID* da alteração que deseja voltar e use no seguinte comando:  
    ```
    git reset --hard 0f50e90
    ```
    substitua o *0f50e90* pelo ID da versão que deseja.  

## O que são e como criar *branches*  
Uma *branch* é uma ramificação do nosso repositório onde podemos editar os arquivos sem que isso influencie na *branch* principal.  
- Consultar *branches* existentes  
  ```
  git branch
  ```
- Criar uma nova *branch*
  ```
  git branch staging
  ```
- Mudar de *branch*
  ```
  git checkout staging
  ```

## Como unir o código - `git merge`
Para realizar o merge de código, devemos seguir os seguintes passos:  
1. Entrar na *branch* que irá receber as atualizações;
2. Fazer o `git pull` (para atualizar com o código mais recente);
3. Fazer o *merge* com a *branch* de onde desejamos receber as atualizações;
4. Fazer o *push* da atualização na *branch* principal.
```
git branch
git checkout master
git pull
git merge staging
git push
```
No exemplo acima estamos fazendo o *merge* na *branch* master das mudanças feitas na *branch* staging.  

## Um merge democrático - `pull request`
1. Fazer o `git pull` da *branch* atual;
2. Gerar uma nova *branch* a partir da *branch* atual;
3. Trabalhar nas novas funcionalidades que adicionou a nova *branch*;
4. Finalizar o trabalho na *branch* temporaria;
5. Realizar o `git push` da *branch* temporaria;
6. No github clique em “Compare & pull request”;
7. Clicar em "Create pull request";
8. Caso o *request* seja rejeitado, faça as correções e realize um novo *commit*.  
