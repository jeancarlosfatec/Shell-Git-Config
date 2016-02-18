#!/bin/bash
menu(){
clear 
echo "Script Config Basica do Git"
echo "Script by M3nin0"

echo "Lembre-se"
echo "ESTE SCRIPT DEVE SER EXECUTADO NA PASTA ONDE SERÁ UTILIZADO O GIT"
sleep 4

echo "Selecione o que deseja fazer:"
echo "1 - Configurar usuario e email"
echo "2 - Iniciar repositorio"
echo "3 - Adicionar todos os arquivos"
echo "4 - Adicionar arquivos expecificos"
echo "5 - Fazer Commit"
echo "6 - SAIR"
read menu
case $menu in
1)
echo "Configurando o usuario e o email"
echo "Insira seu nome: "
read name
echo "Insira seu email: "
read email
echo "Fazendo a configuração"
git config --global user.name "$name" 2>/dev/null
git config --global user.email "$email" 2>/dev/null
echo "Pronto!"
;;

2)
echo "Inicinado repositorio"
git init
sleep 2
echo "Veja os arquivos do GIT criados"
ls -la
sleep 2
echo "Repositorio Criado com sucesso!"
;;

3)
echo "Adicionando todos os arquivos 'UNTRACKED' "
echo "Deseja mesmo adicionar todos os arquivos para a stage area?"
echo "Os arquivos são"
git status
read resposta

if [ "$resposta" == "sim" ];then
git add .

else
echo "Então volte e selecione os arquivos expecificos"
sleep 2
menu
exit
fi

;;
4)
echo "Adicionando arquivos expecificos"
echo "Os arquivos a serem adicionados são"
git status
sleep 5
echo "Para adicionar, digite seus nomes:"
read adic

git add $adic
echo "Adição feita com sucesso!"
echo "Agora falta apenas fazer o commit!"
echo "Os arquivos adicionados são esses: "
git status
echo "Deseja fazer os commit agora?"
read resposta

if [ "$resposta" == "sim" ];then
echo "Escreva o nome de seu commit"
read commit
git commit -m "$commit"
else
echo "Então OK"
fi
;;
5)
echo "Commit"
echo "Os arquivos a serem comitados são: "
git status
echo "Tem certeza que deseja fazer o COMMIT?"
read res

if [ "$res" == "sim" ];then
echo "Insira o nome de seu commit"
read commit
git commit -m "$commit"

else
echo "Faça a analise novamente do que esta em seu commit"
break 
fi

;;

6)
echo "Valeu!!!"
exit
;;

*)
echo "COMANDO INVALIDO"
echo "VOlte ao menu"
sleep 3 
menu
esac
}
menu
