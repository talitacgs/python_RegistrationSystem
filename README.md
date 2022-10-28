## < Div >ersidade Tech

### O que é
O < Div >ersidade Tech é um programa de formação em análise de dados realizado pela empresa Suzano em parceria com a escola de tecnologia Let's Code from Ada.

Esse projeto foi realizado na disciplina Lógica de Programação II pelas alunas [Talita Cavalcanti](https://github.com/talitacgs), [Celsina Azevedo](), [Carol Luz](https://github.com/CarolLuz).
### Tecnologias utilizadas

<div style="display: inline_block" align="center">

  <img width="33" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original-wordmark.svg" />
  <img width="30" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" />
  <img width="30" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" />

</div>

### O Projeto

O projeto deve conter um menu principal com as seguintes opções:

```
Boas vindas ao nosso sistema:

1 - Inserir usuário
2 - Excluir usuário
3 - Atualizar usuário
4 - Informações de um usuário
5 - Informações de todos os usuários
6 - Sair
```

E as alterações das informações devem ser salvas em um arquivo JSON. 

Para inserir um usuário, apenas o nome era obrigatório e automaticamente deveria ser gerado um ID e um Status True, por padrão. Caso o usuário tente inserir um cadastro que já existe, mas está desativado (mesmo nome, telefone e endereço), o sistema deve apenas alterar o status do cadastro antigo para True, e não criar um novo cadastro.

Para exclusão de um usuário, utilizou-se da _Exclusão Lógica_ que, em síntese, muda o _status_ do usuário de *True* para *False*. Caso o ID digitado não esteja dentro da base, deve-se imprimir uma mensagem de erro e pedir novamente o ID. Exemplo:
```
Usuário não encontrado!

Insira o ID do usuário:
```

Para atualização de um usuário, deve ser solicitado o ID e imprimir uma mensagem caso não o encontre na base. Ao inseri um ID correto, deve-se imprimir o seguinte sub menu:
```
Qual informação deseja alterar?
1 - Nome
2 - Tefone
3 - Endereço
```
E ao escolher a opção peça a nova informação da seguinte forma:

```
1
Insira o nome:
```

Para exibir as informações de um usuário, deve-se imprimir o seguinte sub-menu

```
4
Insira o ID do usuário:
```

E deverá ser inserido o ID do usuário que deseja imprimir.
Se o ID inserido não for encontrado na base imprima uma mensagem de erro e peça o _id_ novamente. Exemplo:
```
Usuário não encontrado!

Insira o ID do usuário:
```

No momento que inserir um ID válido imprimir:

```
Nome: Davi Nascimento
Tefone: 2345678
Endereço: Rua Boa
```

A opção de 5 deve imprimir na tela as informações de todos os usuários ativos e a opção Sair deverá encerrar o programa e salvar todas as alterações.

### Solução

Para esse projeto foi utilizado a biblioteca json através de:

```
import json
```
E uma função para salvar as alterações no arquivo

```
def atualizarArquivo():
    json_object = json.dumps(usuarios, indent=4)
    with open("projetoModuloII.json", "w") as outfile:
        outfile.write(json_object)
    print('\nAlterações salvas com sucesso')
```
Para cada item do menu foi criada uma função específica, porém algumas delas precisavam chamar outras funções que retornavam, por exemplo, se o usuário estava ativo/inativo, alterava o Status para _true_ ou formata o texto para exibição.


<font size="2"><p align="center"> Realizado: Out, 2022  </p></font>