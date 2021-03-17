# atv_lab

#CODIGO UTILIZADO#

cd atv_lab
curl https://api.github.com/repos/[dono do repositorio]/[nome do repositório]/pulls?state=closed | grep “login”: | sed 's/"login"://g' | sed 's/[" ,   ]//g' | tail -n 200 | sort | uniq -c | sort -nrk1,1 |  awk '{ print $2 ", " $1}'  >[linguagem]_[nome do repositório].csv

#PARA IMPORTAR OS ARQUIVOS PARA O GITHUB#

git init
git add  *
git commit -m ‘arquivos csv’
git remote add origin https://github.com/elia-so/atv_lab
git remote -v
git push -u origin master
