# RESOLUÇÃO DO DESAFIO: Google Cloud Storage
Para resolver o desafio [Google Cloud Storage](https://github.com/Isiumlord/ProjetoMaoNaMassa/tree/main/Desafio:%20Google%20Cloud%20Storage) mesclou-se tanto o ambiente gráfico quanto o uso de linhas de comando. Foram usados 5 passos principais para realizar as ações pedidas pelo desafio. A baixo segue o passo a passo de como foi realizada toda a solução.

## PASSO 1 - Criar duas buckets usando o ambiente gráfico da Google Cloud Plataform.

> 1.	Logar na sua conta ***Google Cloud Plataform***;
> 2.	No menu principal do ***Console*** ir até a área ***Cloud Storage > Navegador***;
> 3.	Clicar em **CRIAR INTERVALO** para criar a bucket;
> 4.	Adicionar os dados necessários: ***nome, localização e classe da bucket***;
> 5.	Clicar em **CRIAR** para terminar de criar a bucket.
<br>

<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P1.png">
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P2.png">
<br>

:postbox: Repetindo a sequência do primeiro passo foi criado as buckets:
*	`isidoro_bucket1, us-central1, standard`
*	`isidoro_bucket2, us-central1, standard`
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P3.png">
<br>

## PASSO 2 – Fazer o upload de arquivos nas buckets criadas via ambiente gráfico.
> 1.	Na área do ***Cloud Storage > Navegador*** clicar na bucket que irá acessar;
> 2.	Na área da bucket clicar em **FAZER UPLOAD DE ARQUIVOS**;
> 3.	Selecionar o arquivo que irá fazer upload;
> 4.	Fazer o upload do arquivo.
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P4.png">
<br>
 
:postbox: Repetindo a sequência do segundo passo alimentamos as duas buckets com arquivos diferentes:
*	`isidoro_bucket1 > Storage.png`
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P5.png">
<br>

*	`isidoro_bucket2 > Isidoro.txt`
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P6.png">
<br>
 


## PASSO 3 – Acessar o Google Cloud Plataform via Google Cloud SDK Shell.
> 1. [Instalar o **Google Cloud SDK Shell**](https://github.com/Isiumlord/ProjetoMaoNaMassa/tree/main/Desafio:%20Google%20Cloud%20Storage#minidisc-instala%C3%A7%C3%A3o) no seu computador;
> 2. Depois de instalado o **Google Cloud SDK Shell** execute-o;
> 3.	Peça acesso a sua conta no ***Google Cloud Plataform*** utilizando a linha de comando:
```bash
gcloud auth login
```
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P7.png">
<br>

> 4.	Forneça Login e Senha;
> 5.	Permita o acesso do **Google Cloud SDK Shell** a sua conta no ***Google Cloud Plataform***.
<img align="center" alt="engen" width="500" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P8.png">
<br>



## PASSO 4 – Com acesso a Google Cloud Plataform via SDK crie o terceiro bucket e faça as demais ações pedidas no desafio via linha de comando.

1. Crie a terceira bucket `isidoro_bucket3, us-central1, standard` utilizando o comando:
```bash
gsutil mb -p data-labs-358422 -c standard -l us-central1 -b on gs://isidoro_bucket3
```
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P9.png">
<br>

2.	Liste as buckets para ver se elas constam no projeto utilizando o comando:
```bash
gsutil ls
```
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P10.png">
<br>

*	Para confirmar o resultado da listagem acesse via ambiente gráfico o ***Cloud Storage > Navegador*** para ter a visão das **3 buckets** listadas.
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P11.png">
<br>

3.	Consulte os arquivos de todas as buckets criadas utilizando os comandos:
```bash
gsutil ls -r gs://isidoro_bucket1
gsutil ls -r gs://isidoro_bucket2
gsutil ls -r gs://isidoro_bucket3
```
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P12.png">
<br>

4.	Copie os arquivos encontrados em `isidoro_bucket1` e `isidoro_bucket2` para a `isidoro_bucket3` utilizando os comandos:
```bash
gsutil cp gs://isidoro_bucket1/Storage.png gs://isidoro_bucket3/Storage-copy.png
gsutil cp gs://isidoro_bucket2/Isidoro.txt gs://isidoro_bucket3/Isidoro-copy.txt
```
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P13.png">
<br>

5. Consulte os arquivos da `bucket Isidoro_bucket3` para confirmar se os arquivos foram devidamente copiados usando o comando:
```bash
gsutil ls -r gs://isidoro_bucket3
```
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P14.png">
<br>

* Para confirmar o resultado das cópias acesse via ambiente gráfico o ***Cloud Storage > Navegador > isidoro_bucket3***.

<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P15.png">
<br>

6. Exclua as buckets `isidoro_bucket1` e `isidoro_bucket2` e todos os seus arquivos de forma recursiva utilizando os comandos:
```bash
gsutil rm -r gs://isidoro_bucket1
gsutil rm -r gs://isidoro_bucket2
```
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P16.png">
<br>

7. Liste as buckets para ver se elas foram excluídas realmente do projeto utilizando o comando:
```bash
gsutil ls
```
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P17.png">
<br>

* Para confirmar o resultado da listagem acesse via ambiente gráfico o ***Cloud Storage > Navegador*** tendo a visão apenas da bucket listada.
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P18.png">
<br>
 
8. Faça download dos arquivos da bucket `isidoro_bucket3` para a ***Área de Trabalho*** do seu computador utilizando os comandos:
```bash
gsutil cp gs://isidoro_bucket3/Isidoro-copy.txt C:\Users\isidoro.brito_multie\Desktop
gsutil cp gs://isidoro_bucket3/Storage-copy.png C:\Users\isidoro.brito_multie\Desktop
```
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P19.png">
<br>


## PASSO 5 – Excluir o último Bucket via ambiente gráfico.

> 1. Na área do ***Cloud Storage > Navegador***;
> 2. Selecione a Bucket `isidoro_bucket3`;
> 3. Selecione a opção **EXCLUIR**;
> 4. Preencha o campo com **DELETE**;
> 5. Clique em **EXCLUIR**.
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P20.png">
<br>

* Volte a área do ***Cloud Storage > Navegador*** para ver se o ambiente esta sem nenhuma Bucket.
<img align="center" alt="engen" width="980" src="https://github.com/Isiumlord/ProjetoMaoNaMassa/blob/main/Desafio:%20Google%20Cloud%20Storage/Prints/P21.png">

 

