---
description: Comandos para uso do git via linha de comando.
---

# Comandos do Git

### Criando repositório

```
	git init
```

### Clonando repositório

```
	git clone endereço-do-repositório
```

ou para repositórios com links para outros repositórios

```
	git clone --recursive endereço-do-repositório
	
```

ou para ramos (branch) no repositório

```
	git clone --branch nome-do-ramo endereço-do-repositório
```

***

### Subir Mudanças para repositório

![](../../../.gitbook/assets/fluxo\_de\_trabalho\_no\_git.png)

#### Adicionar mudanças no **index**

```
	git add <arquivo>
	ou
	git add *
	
```

depois confirmar as mudanças fazer um commit:

```
	git commit -m "comentário das alterações"
```

isso manda o arquivo para o **head**

***

### Enviando alterações para o repositório

```
	git push origin <master ou o nome-do-ramo>
```

***

### Sobre ramos (branch)

#### para criar um novo ramo

```
	git checkout -b nome-do-ramo-ou-funcionalidade
	
```

#### para retornar ao master

```
	git checkout master
	
```

#### remover ramo

```
	git branch -d nome-do-ramo-ou-funcionalidade
	
```

#### enviar branch para repositório remoto

```
	git push origin nome-do-ramo-ou-funcionalidade
	
```

#### renomear um ramo

* mude para o ramo a ser renomeado

```
git checkout <nome_antigo>
```

* renomeie no novo ramo

```
git branch -m <novo_nome>
```

* Suba o ramo \<novo\_nome>

```
git push origin -u <novo_nome>
```

* Delete o ramo \<nome\_antigo>

```
git push origin --delete <nome_antigo>
```

***

### Atualizar e mesclar

#### Atualizar repositório local mesclando com atualizações remotas

```
	git pull
	
```

#### para mesclar outro brach ao seu branch ativo (ex. master)

```
	git merge <branch>
```

### Links Relacionados:&#x20;

* [https://www.atlassian.com/br/git/tutorials/setting-up-a-repository/git-clone ](https://www.atlassian.com/br/git/tutorials/setting-up-a-repository/git-clone)
* [https://rogerdudler.github.io/git-guide/index.pt\_BR.html](https://rogerdudler.github.io/git-guide/index.pt\_BR.html)
* [https://githowto.com/pt-BR/creating\_a\_branch](https://githowto.com/pt-BR/creating\_a\_branch)
