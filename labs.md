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

👉 Realize o download da aplicação e realize extração para dentro da pasta do IIS. 

 [SmartStore](https://github.com/smartstore/SmartStoreNET/releases/download/3.2.2/SmartStoreNET.Community.3.2.2.zip
)

👉 Crie um novo Application Pools dentro do IIS e um novo site apontando o mesmo para o Application Pools criado.
Também pare o site default por causa que o mesmo utiliza a porta 80.

![mon11](/images/mon11.png)
![mon12](/images/mon12.png)

👉 Ajuste as configurações NTFS na pasta onde está o site.

![mon13](/images/mon13.png)

👉 Abra o navegador e entre em http://localhost e preencha os campos e após, clique em install.

![mon14](/images/mon14.png)

👉 Configurar o Application Insights para a VM WEB
    OBS: Processo manual.

Faça o download do nupkg a partir do link na guia comandos.

![mon15](/images/mon15.png)

👉 Após isso, rode no powershell o script que está na guia comandos.

``` 
$pathToNupkg = "C:\Temp\az.applicationmonitor.1.1.2.nupkg" #alterar para o caminho do seu download
$pathToZip = ([io.path]::ChangeExtension($pathToNupkg, "zip"))
$pathToNupkg | rename-item -newname $pathToZip
$pathInstalledModule = "$Env:ProgramFiles\WindowsPowerShell\Modules\Az.ApplicationMonitor"
Expand-Archive -LiteralPath $pathToZip -DestinationPath $pathInstalledModule

 ``` 

 👉 No azure, pegue a ``` connection string ``` que está abaixo de  ``` Instrumentation Key  ``` 

 Insira o conteúdo aqui : 

 #Add InstrumentationKey na aplicação

``` Enable-ApplicationInsightsMonitoring -ConnectionString 'InstrumentationKey=f44160a0-4496-4d07-a035-3879bde5f0c2;IngestionEndpoint=https://brazilsouth-1.in.applicationinsights.azure.com/;LiveEndpoint=https://brazilsouth.livediagnostics.monitor.azure.com/'   ```

Rode o comando, ele irá fazer todas as alterações necessárias para o funcionamento.


👉 Atualize a página da aplicação e execute o comando :

``` Get-ApplicationInsightsMonitoringStatus ``` terá que ter o retorno semelhante:

![mon16](/images/mon16.png)

👉 Verifique no Azure se o Live Metrics está parecido com a imagem abaixo, ela irá "dizer" se está recebendo informações.

![mon17](/images/mon17.png)

👉 Em Application map iremos validar a performance do APP (site)

![mon18](/images/mon18.png)

🔖 Smart Deection 

É um item que consegue nos trazer automaticamente alguns alertas
    Entre nas configurações dele e coloque um e-mail para receber os alertas.

![mon19](/images/mon19.png)

🔖 Transaction search

Onde podemos verificar tudo o que está sendo transicionado dentro do site.
    Exemplo, ele está tenta mais tráfego com uma dependência que é o banco de dados
    e também mais detalhes sobre cada requisição.

![mon20](/images/mon20.png)
![mon21](/images/mon21.png)