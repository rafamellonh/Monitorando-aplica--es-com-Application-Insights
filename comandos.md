## APP Insigths

#Download APP
https://github.com/smartstore/SmartStoreNET/releases/download/3.2.2/SmartStoreNET.Community.3.2.2.zip


#Download Extension APP Insights
https://www.powershellgallery.com/packages/Az.ApplicationMonitor/1.1.2


#Configurar pacote APP Insights
$pathToNupkg = "C:\Temp\az.applicationmonitor.1.1.2.nupkg" #alterar para o caminho do seu download
$pathToZip = ([io.path]::ChangeExtension($pathToNupkg, "zip"))
$pathToNupkg | rename-item -newname $pathToZip
$pathInstalledModule = "$Env:ProgramFiles\WindowsPowerShell\Modules\Az.ApplicationMonitor"
Expand-Archive -LiteralPath $pathToZip -DestinationPath $pathInstalledModule


#Add InstrumentationKey na aplicação
Enable-ApplicationInsightsMonitoring -ConnectionString 'InstrumentationKey=68b741-f064-42f6-b2d1-e7122c2654a7;IngestionEndpoint=https://eastus-8.in.applicationinsights.azure.com/'


#Validar a APP com InstrumentationKey
Get-ApplicationInsightsMonitoringStatus