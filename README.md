# autocomplete

````javascirpt
Install-Module PSReadLine -Force
Import-Module PSReadLine
````
#segundo passo
````javascirpt
code $PROFILE
````
cola isso
````javascirpt
$MaximumHistoryCount = 20000

# Importar módulos
Import-Module PSReadLine
Import-Module DockerCompletion

# Configurar o PSReadLine para usar a função de completamento com a tecla Tab
Set-PSReadLineKeyHandler -Key Tab -Function AcceptSuggestion

# Verificar se o arquivo starship.toml existe e inicializar o Starship
if (Test-Path $env:USERPROFILE\starship.toml) {
    Invoke-Expression (& starship init powershell)
}

# Verificar se a variável STARSHIP_SESSION_KEY está vazia e inicializar o Starship se necessário
if (-not $env:STARSHIP_SESSION_KEY) {
    & starship init powershell | Invoke-Expression
}



````
