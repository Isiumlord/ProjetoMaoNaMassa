# RESOLUÇÃO DO DESAFIO: Google Cloud Storage
Para resolver o desafio [Google Cloud Storage]() mesclou-se tanto o ambiente gráfico quanto o uso de linhas de comando. Foram usados 5 passos principais para realizar as ações pedidas pelo desafio. A baixo segue o passo a passo de como foi realizada toda a solução.

## PASSO 1 - Criar duas buckets usando o ambiente gráfico da Google Cloud Plataform.
> 1.	Logar na sua conta ***Google Cloud Plataform***;
> 2.	No menu principal do ***Console*** ir até a área ***Cloud Storage > Navegador***;
> 3.	Clicar em **CRIAR INTERVALO** para criar a bucket;
> 4.	Adicionar os dados necessários: ***nome, localização e classe da bucket***;
> 5.	Clicar em **CRIAR** para terminar de criar a bucket.

> IMAGEM COLOCAR

 Repetindo o primeiro passo foi criado as buckets:
*	`isidoro_bucket1, us-central1, standard`
> IMAGEM COLOCAR
*	`isidoro_bucket2, us-central1, standard`
> IMAGEM COLOCAR
 

## PASSO 2 – Fazer o upload de arquivos nas buckets criadas via ambiente gráfico.
*	Na área do ***Cloud Storage > Navegador*** clicar na bucket que irá acessar;
*	Na área da bucket clicar em **FAZER UPLOAD DE ARQUIVOS**;
*	Selecionar o arquivo que irá fazer upload;
*	Fazer o upload do arquivo.
 > IMAGEM COLOCAR
 
 
Repetindo o segundo passo alimentamos as duas buckets com arquivos diferentes:
*	`isidoro_bucket1 > Storage.png`
 > IMAGEM COLOCAR
*	`isidoro_bucket2 > Isidoro.txt`
 > IMAGEM COLOCAR
 


## PASSO 3 – Acessar o Google Cloud Plataform via Google Cloud SDK Shell.
* Instalar o **Google Cloud SDK Shell** no seu computador;
* Depois de instalado o **Google Cloud SDK Shell** execute-o;
*	Peça acesso a sua conta no ***Google Cloud Plataform*** utilizando a linha de comando:
```bash
gcloud auth login
```

 > IMAGEM COLOCAR

*	Forneça Login e Senha;
*	Permita o acesso do **Google Cloud SDK Shell** a sua conta no ***Google Cloud Plataform***.
> IMAGEM COLOCAR
 
## PASSO 4 – Com acesso a Google Cloud Plataform via SDK crie o terceiro bucket e faça as demais ações pedidas no desafio via linha de comando.

* Crie a terceira bucket *isidoro_bucket3, us-central1, standard* utilizando o comando:
```bash
gsutil mb -p data-labs-358422 -c standard -l us-central1 -b on gs://isidoro_bucket3
```
 > IMAGEM COLOCAR

*	Liste as buckets para ver se elas constam no projeto utilizando o comando:
```bash
gsutil ls
```
<br>

*	Para confirmar o resultado da listagem acesse via ambiente gráfico o ***Cloud Storage > Navegador*** para ter a visão das **3 buckets** listadas.
> IMAGEM COLOCAR
<br>

*	Consulte os arquivos de todas as buckets criadas utilizando os comandos:
```bash
gsutil ls -r gs://isidoro_bucket1
gsutil ls -r gs://isidoro_bucket2
gsutil ls -r gs://isidoro_bucket3
```
<br>

*	Copie os arquivos encontrados em `isidoro_bucket1` e `isidoro_bucket2` para a `isidoro_bucket3` utilizando os comandos:
```bash
gsutil cp gs://isidoro_bucket1/Storage.png gs://isidoro_bucket3/Storage-copy.png
gsutil cp gs://isidoro_bucket2/Isidoro.txt gs://isidoro_bucket3/Isidoro-copy.txt
```
<br>

* Consulte os arquivos da `bucket Isidoro_bucket3` para confirmar se os arquivos foram devidamente copiados usando o comando:
```bash
gsutil ls -r gs://isidoro_bucket3
```
<br>

* Para confirmar o resultado das cópias acesse via ambiente gráfico o ***Cloud Storage > Navegador > isidoro_bucket3***.

 > IMAGEM COLOCAR
<br>

* Exclua as buckets `isidoro_bucket1` e `isidoro_bucket2` e todos os seus arquivos de forma recursiva utilizando os comandos:
```bash
gsutil rm -r gs://isidoro_bucket1
gsutil rm -r gs://isidoro_bucket2
```
<br>

* Liste as buckets para ver se elas foram excluídas realmente do projeto utilizando o comando:
```bash
gsutil ls
```
<br> 

* Para confirmar o resultado da listagem acesse via ambiente gráfico o ***Cloud Storage > Navegador*** tendo a visão apenas da bucket listada.
<br>
 
* Faça download dos arquivos da bucket `isidoro_bucket3` para a ***Área de Trabalho*** do seu computador utilizando os comandos:
```bash
gsutil cp gs://isidoro_bucket3/Isidoro-copy.txt C:\Users\isidoro.brito_multie\Desktop
gsutil cp gs://isidoro_bucket3/Storage-copy.png C:\Users\isidoro.brito_multie\Desktop
```
<br>

## PASSO 5 – Excluir o último Bucket via ambiente gráfico.

1. Na área do ***Cloud Storage > Navegador***;
2. Selecione a Bucket `isidoro_bucket3`;
3. Selecione a opção **EXCLUIR**;
4. Preencha o campo com **DELETE**;
5. Clique em **EXCLUIR**.

 

* Volte a área do ***Cloud Storage > Navegador*** para ver se o ambiente esta sem nenhuma Bucket.

 

