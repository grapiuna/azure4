# Desafio Azure DIO 4 - Pesquisa Cognitiva do Azure
Plataforma de mineração de conhecimento alimentada po IA do Azure
Exemplos:
Blob Storage containers;
Data Lake Storage Gen2
Table Storage



## Foram testados os recursos do "Azure Cognitive Search"
Os arquivos testados estão na pasta inputs e os resultados estão abaixo.

### Passo a passo
1-Clique em "Create a resource", pesquise por "AI search" e clique em "Create"
2-Clique em "Continue", selecione seu "Resource group", o nome e clique em "Review+create", espere e clique em "Create".
3-Após concluir a criação, crie o recurso "Azure AI services", escolhe o resource group, coloque o nome, Price tier em "Standard", marque o checkbox e depois clique em "Review+create", espere e clique em "Create". Ao terminar clique em Home.
4-Crie uma nova conta de armazenamento, clique em "Storage Accounts", "Create", nome da "Storage", Performance em Standard, Redundancy em LRS, clique em Review, depois em create. Ao terminar clique em Home.
5-Nas configurações do Storage Account criado habilite o acesso de Blob anônimos para este teste.
6-Em Containers, adicione um novo container com o nome e nível de acesso anônimo Container.
7-Acesse este container e adicione os arquivos docx do teste https://aka.ms/mslearn-coffee-reviews
8-Vá no AI Search criado e em importe os dados do container na aba "Import data", conforme o tópico "Index the documents" on https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html
9-Pesquise os dados no Search Explorer, por exemplo, search=locations:'Miami'
Resultado
```
{
  "@odata.context": "https://teste4.search.windows.net/indexes('azureblob-index')/$metadata#docs(*)",
  "value": []
}
```
sentiment:'negative':
```
{
  "@odata.context": "https://teste4.search.windows.net/indexes('azureblob-index')/$metadata#docs(*)",
  "value": [
    {
      "@search.score": 0.2876821,
      "content": "Review: Today I was truly disappointed with how long I had to wait for the pastries I ordered ahead of time. When I got my box, some of the pastries seemed stale. Terrible experience!  \nDate: October 23, 2018\nLocation: Chicago, Illinois \n\n",
      "metadata_storage_path": "aHR0cHM6Ly90ZXN0ZTRhLmJsb2IuY29yZS53aW5kb3dzLm5ldC90ZXN0ZS9yZXZpZXctOC5kb2N40",
      "locations": [
        "Chicago",
        "Illinois"
      ],
      "keyphrases": [
        "Terrible experience",
        "Review",
        "pastries",
        "time",
        "box",
        "Date",
        "October",
        "Location",
        "Chicago",
        "Illinois"
      ],
      "sentiment": "[\"negative\"]",
      "merged_content": "Review: Today I was truly disappointed with how long I had to wait for the pastries I ordered ahead of time. When I got my box, some of the pastries seemed stale. Terrible experience!  \nDate: October 23, 2018\nLocation: Chicago, Illinois \n\n",
      "text": [],
      "layoutText": [],
      "imageTags": [],
      "imageCaption": []
    }
  ]
}
```
