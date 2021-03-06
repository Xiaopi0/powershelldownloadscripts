[![Gitpod ready-to-code](https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod)](https://gitpod.io/#https://github.com/Xiaopi0/powershelldownloadscripts)

# powershelldownloadscripts
scripts for downloading files with powershell

## Invoke-WebRequest
This method uses Invoke-WebRequest to download files. Code:
 ```powershell
 $url = Read-Host -Prompt 'input link'
 $output = Read-Host -Prompt 'input destination(with file-name)'
 $start_time = Get-Date

 Invoke-WebRequest -Uri $url -OutFile $output
 Write-Output "Time taken: $((Get-Date).Subtract($start_time).Seconds) second(s)"
```
## System.Net.WebClient
This method uses System.Net.WebClient to download files. Code:
```powershell
$url = Read-Host -Prompt 'input link'
$output = Read-Host -Prompt 'input destination(with file-name)'
$start_time = Get-Date

$wc = New-Object System.Net.WebClient
$wc.DownloadFile($url, $output)

Write-Output "Time taken: $((Get-Date).Subtract($start_time).Seconds) second(s)"
```
## BitsTransfer
This method uses BitsTransfer to download files. Code:
```powershell
$url = Read-Host -Prompt 'input link'
$output = Read-Host -Prompt 'input destination(with file-name)'
$start_time = Get-Date

Import-Module BitsTransfer
Start-BitsTransfer -Source $url -Destination $output

Write-Output "Time taken: $((Get-Date).Subtract($start_time).Seconds) second(s)"
```
