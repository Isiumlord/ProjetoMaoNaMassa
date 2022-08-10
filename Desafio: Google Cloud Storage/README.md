![nivel](https://img.shields.io/static/v1?label=Nível&message=Básico&color=?style=plastic)
# Desafio: Google Cloud Storage
<i>Executar passos abaixo no ambiente gráfico do Google Cloud Storage e em linhas de comando.</i>  <p>
  
<br>
  
:one: Criar 2 buckets com o nome `{seu_nome}_bucket1` e `{seu_nome}_bucket2` sendo:
> - **Classe:** STANDARD
> - **Localização:** us-central1

:two: Listar os buckets para conferir se foram criados

:three: Copiar 1 arquivo local para cada bucket criado, sendo: 
 > - bucket1: um arquivo .jpg
 > - bucket2: um arquivo .txt

:four: Listar os objetos de cada bucket e conferir se os arquivos estão presentes

:five: Criar 1 bucket com o nome `{seu_nome}_bucket3`

:six: Copiar os arquivos .jpg e .txt dos buckets 1 e 2, para o bucket3

:seven: Listar objetos do bucket3 e conferir

:eight: Fazer download dos objetos do bucket3 para uma pasta local

:nine: Deletar os 3 buckets com modo recursivo

:keycap_ten: Listar buckets do projeto e conferir se ainda existem

:ticket: Documentar passo a passo e gerar PDF
  
<br>  

## :wrench: Ferramentas e Tecnologias: 
![windows](https://img.shields.io/static/v1?label=&message=Windows&color=lightgrey&logo=windows)
![linux](https://img.shields.io/static/v1?label=&message=Linux&color=lightgrey&logo=linux)
![google-cloud](https://img.shields.io/static/v1?label=&message=Google-Cloud&color=lightgrey&logo=google-cloud)
![powershell](https://img.shields.io/static/v1?label=&message=Powershell&color=lightgrey&logo=powershell)
![python](https://img.shields.io/static/v1?label=&message=Python&color=lightgrey&logo=python)

## :minidisc: Instalação
Instalar Google Cloud SDK e definir variáveis de ambiente  
https://cloud.google.com/sdk/docs/install-sdk

## :busts_in_silhouette: Autenticação
Opção 1: Sem uma conta de serviço  
https://cloud.google.com/sdk/docs/initializing
```bash
gcloud auth login
```

Opção 2: Com uma conta de serviço  
https://cloud.google.com/docs/authentication/production?hl=pt-br#create-service-account-gcloud

## :memo: Documentação
Criar conta de serviço *(vá direto ao passo 4)*:  
https://support.google.com/a/answer/7378726?hl=pt-BR

Comandos básicos para Google Cloud Storage:  
https://cloud.google.com/storage/docs/discover-object-storage-gsutil

## :mega: Bônus
Linha de comando interativa do Google Cloud: Auto complete  
https://cloud.google.com/sdk/docs/interactive-gcloud

Gerenciando componentes no Google Cloud:  
https://cloud.google.com/sdk/docs/components
