# Aprendendo GIT
1. Criando um repositório Local no Computador
    - Acessar o diretório onde se quer criar o projeto:
    
    ```
    cd /diretorio
    ```
    
2. Iniciar o repositório Git:

```
**git init**  -> esse comando cria um repositório vazio na pasta atual 
ou reinicializa um existente
```

3. Adiciona os arquivos ao repositório:

```
**git add .**  -> o ponto pode ser substituído pelo conteúdo que 
se deseja incluir no diretório
```

4. Faça o primeiro commit:

```
**git commit -m** "First commit"
```

Caso não já tenha o repositório remoto criado, criar o repositório remoto no Github para poder vincular o repositório local ao repositório do Github e enviar os arquivos

5. Vincular o repositório local ao repositório remonto no Github:

```
**git remote add origin URL_DO_SEU_REPOSITORIO_DO_GITHUB** //no caso de o repositório
estar sendo reinicializado omitir esse comando, pois provavelmente origin já deve 
existir e se esse comando for executado gerará um erro da seguinte forma:
ERROR: REMOTE ORIGIN ALREADY EXISTS!
```

6. Enviar os arquivos para o repositório remoto no Github:

```
**git push -u origin main**
```

  6.1. Caso surja algum erro quando executar os comandos 5 e 6, do tipo: 

  ```
  ! [rejected]   main -> main (fetch first)
  error: failed to push some refs to 'URL DO REPOSITORIO'
  hint: Updates were rejected because the remote contains work that you do not
  hint: have locally. This is usually caused by another repository pushing to
  hint: the same ref. If you want to integrate the remote changes, 
  use
  hint: 'git pull' before pushing again.
  hint: See the 'Note about fast-forwards' in 'git push --help' for details
  ```

  Fazer os seguintes passos para resolver:

  6.2. Faça um Pull para baixar as mudanças do repositório remoto:

  ```
  **git pull origin main --allow-unrelated-histories**
  // o parametro **--allow-unrelated-histories** é necessário se o repositório local
  e o remoto tiverem historicos diferente, é comum quando se inicia o repositorio local
  e remoto separadamente.
  ```

  6.3. Depois é só adicionar os arquivos modificados:

  ```
  **git add .**
  ```

  6.4 Faça um commit para confirmar a mesclagem:

  ```
  **git commit -m** "Resolvendo conflitos e mesclando com o repositório remoto"
  ```

  6.5 Agora é só enviar as alterações para o repositório remoto

  ```
  **git push origin main**
  ```

7. Renomeando uma branch caso necessário:

```
*# Renomeie o branch 'master' para 'main'*
git branch -m master main

*# Atualize o branch padrão no repositório remoto*
git push -u origin main

*# (Opcional) Se você quiser deletar o branch 'master' no remoto:*
git push origin --delete master
```

8. Para criar uma nova branch:
```
git branch NOME_DA_BRANCH
git checkout NOME_DA_BRANCH --> resposta: Switched to branch NOME_DA_BRANCH

# Adicione os arquivos que deseja incluir na branch
git add NOME_DOS_ARQUIVOS
git commit -m "DESCRIÇÃO DA ALTERAÇÃO FEITA"
git push -u origin NOME_DA_BRANCH
```