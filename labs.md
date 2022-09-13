👉 
🔖 


🔖 Laboratório

👉 Crie o RG e uma VNET com subs

![mon02](/images/mon02.png)
![mon03](/images/mon03.png)

👉 Crie uma VM com SQL Server

![mon04](/images/mon04.png)
![mon05](/images/mon05.png)
![mon06](/images/mon06.png)

👉 Crie uma VM simples para Web inserindo ela na sub-apps

👉 Instalar serviços para utilizar o Application Insights

* Log Analytics Workspaces (geralmente é o custo para ter um monitoramento pois ele armazena todos os logs)
  
![mon07](/images/mon07.png)

👉 Criar o Application Insights

Selecione o Workspace criado anteriormente para ele armazenar os logs do monitoramento

![mon08](/images/mon08.png)


Aqui obtemos o ``` Instrumentation Key  ```  para configurarmos em nossas aplicações
    
![mon09](/images/mon09.png)

👉 No servidor WEB, instale o IIS.

Ative as roles conforme imagem abaixo somente para garantir o funcionamento das consultas.

![mon10](/images/mon10.png)

👉 Realize o download da aplicação : 

 [SmartStore](https://github.com/smartstore/SmartStoreNET/releases/download/3.2.2/SmartStoreNET.Community.3.2.2.zip
)