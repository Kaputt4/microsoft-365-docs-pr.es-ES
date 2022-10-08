---
title: Consideraciones especiales para stream y eventos en directo en entornos VPN
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: Consideraciones especiales para stream y eventos en directo en entornos VPN
ms.openlocfilehash: 7325c228c3b9bd7ffb808a56da09415709d3fdfb
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68187897"
---
# <a name="special-considerations-for-stream-and-live-events-in-vpn-environments"></a>Consideraciones especiales para stream y eventos en directo en entornos VPN

>[!NOTE]
>Este artículo forma parte de un conjunto de artículos que abordan la optimización de Microsoft 365 para usuarios remotos.

>- Para obtener información general sobre el uso de la tunelización dividida de VPN para optimizar la conectividad de Microsoft 365 para usuarios remotos, consulte [Información general: Túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-split-tunnel.md).
>- Para obtener instrucciones detalladas sobre la implementación de la tunelización dividida de VPN, consulte [Implementación de la tunelización dividida de VPN para Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md).
>- Para obtener una lista detallada de escenarios de tunelización dividida de VPN, consulte [Escenarios comunes de tunelización dividida de VPN para Microsoft 365](microsoft-365-vpn-common-scenarios.md).
>- Para obtener instrucciones sobre cómo proteger el tráfico multimedia de Teams en entornos de tunelización dividida de VPN, consulte [Protección del tráfico multimedia de Teams para la tunelización dividida de VPN](microsoft-365-vpn-securing-teams.md).
>- Para obtener información sobre cómo optimizar el rendimiento de los inquilinos de Microsoft 365 en todo el mundo para los usuarios de China, consulte [Optimización del rendimiento de Microsoft 365 para los usuarios de China](microsoft-365-networking-china.md).

El tráfico de Eventos en directo de Microsoft 365 (esto incluye los asistentes a eventos en directo producidos por Teams y los producidos con un codificador externo a través de Teams, Stream o Yammer) y el tráfico de Stream a petición se clasifica actualmente como **Predeterminado** frente a **Optimizar** en la [lista de direcciones URL/IP del servicio](urls-and-ip-address-ranges.md). Estos puntos de conexión se clasifican como **predeterminados** porque se hospedan en redes CDN que también pueden usar otros servicios. Por lo general, los clientes prefieren proxy de este tipo de tráfico y aplican cualquier elemento de seguridad que se realice normalmente en puntos de conexión como estos.

Muchos clientes han solicitado los datos de DIRECCIÓN URL/IP necesarios para conectar a sus usuarios a Stream/Live Events directamente desde su conexión local a Internet, en lugar de enrutar el tráfico de alto volumen y sensible a la latencia a través de la infraestructura de VPN. Normalmente, esto no es posible sin espacios de nombres dedicados e información de IP precisa para los puntos de conexión, que no se proporciona para los puntos de conexión de Microsoft 365 clasificados como **Predeterminado**.

Siga estos pasos para habilitar la conectividad directa para el servicio Stream/Live Events desde clientes mediante una VPN de túnel forzado. Esta solución está diseñada para proporcionar a los clientes una opción para evitar el enrutamiento del tráfico de Live Events a través de VPN mientras hay un tráfico de red elevado debido a escenarios de trabajo desde casa. Si es posible, se recomienda acceder al servicio a través de un proxy de inspección.

>[!NOTE]
>Con esta solución, puede haber elementos de servicio que no se resuelven en las direcciones IP proporcionadas y, por tanto, atraviesan la VPN, pero la mayor parte del tráfico de gran volumen, como los datos de streaming, debería. Puede haber otros elementos fuera del ámbito de Live Events/Stream que se detecten mediante esta descarga, pero estos deben estar limitados, ya que deben cumplir tanto el _FQDN como_ la coincidencia ip antes de ir directamente.

>[!IMPORTANT]
>Se recomienda a los clientes que sopesan el riesgo de enviar más tráfico que omite la VPN sobre la ganancia de rendimiento de Live Events.

Para implementar la excepción de túnel forzado para Teams Live Events y Stream, se deben aplicar los pasos siguientes:

## <a name="1-configure-external-dns-resolution"></a>1. Configurar la resolución DNS externa

Los clientes necesitan una resolución DNS externa y recursiva para estar disponibles para que los siguientes nombres de host se puedan resolver en direcciones IP.

- \*.azureedge.net
- \*.media.azure.net
- \*.bmc.cdn.office.net

**\*.azureedge.net** se usa para eventos de Stream ([Configurar codificadores para streaming en directo en Microsoft Stream: Microsoft Stream | Microsoft Docs](/stream/live-encoder-setup)).

**\*.media.azure.net** y **\*.bmc.cdn.office.net** se usan para eventos en directo producidos por Teams (eventos de inicio rápido, RTMP-In eventos admitidos [id. de hoja de ruta 84960]) programados desde el cliente de Teams.

 Algunos de estos puntos de conexión se comparten con otros elementos fuera de Stream/Live Events, no se recomienda usar estos FQDN para configurar la descarga de VPN incluso si técnicamente es posible en la solución VPN (por ejemplo, si funciona en el FQDN en lugar de la dirección IP).

Los FQDN no son necesarios en la configuración de VPN, son puramente para su uso en archivos PAC en combinación con las direcciones IP para enviar el tráfico directo pertinente.

## <a name="2-implement-pac-file-changes-where-required"></a>2. Implementar cambios de archivo PAC (cuando sea necesario)

Para las organizaciones que usan un archivo PAC para enrutar el tráfico a través de un proxy mientras se encuentra en VPN, esto normalmente se logra mediante FQDN. Sin embargo, con Stream/Live Events, los nombres de host proporcionados contienen caracteres comodín como **\*.azureedge.net**, que también abarca otros elementos para los que no es posible proporcionar listas IP completas. Por lo tanto, si la solicitud se envía directamente en función de la coincidencia de caracteres comodín dns solo, el tráfico a estos puntos de conexión se bloqueará, ya que no hay ninguna ruta a través de la ruta de acceso directa para ella en el [paso 3](#3-configure-routing-on-the-vpn-to-enable-direct-egress) más adelante en este artículo.

Para solucionar esto, podemos proporcionar las siguientes direcciones IP y usarlas en combinación con los nombres de host en un archivo PAC de ejemplo, como se describe en [el paso 1](#1-configure-external-dns-resolution). El archivo PAC comprueba si la dirección URL coincide con las usadas para Stream/Live Events y, a continuación, si lo hace, también comprueba si la dirección IP devuelta desde una búsqueda DNS coincide con las proporcionadas para el servicio. Si _ambos_ coinciden, el tráfico se enruta directamente. Si ninguno de los elementos (FQDN/IP) coincide, el tráfico se envía al proxy. Como resultado, la configuración garantiza que todo lo que se resuelva en una dirección IP fuera del ámbito de la dirección IP y los espacios de nombres definidos atravesará el proxy a través de la VPN de la forma habitual.

### <a name="gathering-the-current-lists-of-cdn-endpoints"></a>Recopilación de las listas actuales de puntos de conexión de CDN

Live Events usa varios proveedores de CDN para transmitirlos a los clientes, con el fin de proporcionar la mejor cobertura, calidad y resistencia. Actualmente, se usan tanto Azure CDN de Microsoft como Verizon. Con el tiempo, esto podría cambiarse debido a situaciones como la disponibilidad regional. Este artículo es un origen que le permite mantenerse al día sobre los intervalos IP.

En el caso de Azure CDN de Microsoft, puede descargar la lista de [Descarga de intervalos IP y etiquetas de servicio de Azure en la nube pública desde el Centro de descarga oficial de Microsoft](https://www.microsoft.com/download/details.aspx?id=56519) ; tendrá que buscar específicamente la etiqueta de servicio *AzureFrontdoor.Frontend* en JSON; *addressPrefixes mostrará las subredes* IPv4/IPv6. Con el tiempo, las direcciones IP pueden cambiar, pero la lista de etiquetas de servicio siempre se actualiza antes de que se usen.

Para Azure CDN de Verizon (Edgecast) puede encontrar una lista exhaustiva mediante [Nodos perimetrales - Lista](/rest/api/cdn/edge-nodes/list) (haga clic en **Probar** ) - tendrá que buscar específicamente la sección  **Premium\_Verizon**  . Tenga en cuenta que esta API muestra todas las direcciones IP de Edgecast (origen y Anycast). Actualmente no hay un mecanismo para que la API distinga entre el origen y Anycast.

Para implementar esto en un archivo PAC, puede usar el ejemplo siguiente que envía el tráfico directo de Optimización de Microsoft 365 (que se recomienda) a través del FQDN y el tráfico crítico de Stream/Live Events directamente a través de una combinación del FQDN y la dirección IP devuelta. El nombre del marcador de posición _Contoso_ tendría que editarse en el nombre del inquilino específico en el que _contoso_ procede de contoso.onmicrosoft.com

#### <a name="example-pac-file"></a>Archivo PAC de ejemplo

Este es un ejemplo de cómo generar los archivos PAC:

1. Guarde el script siguiente en el disco duro local como _Get-TLEPacFile.ps1_.
1. Vaya a la [dirección URL de Verizon](/rest/api/cdn/edge-nodes/list#code-try-0) y descargue el JSON resultante (copie péguelo en un archivo como cdnedgenodes.json)
1. Coloque el archivo en la misma carpeta que el script.
1. En una ventana de PowerShell, ejecute el siguiente comando. Cambie el nombre del inquilino por otra cosa si quiere las direcciones URL de SPO. Este es el tipo 2, por lo que **optimizar** y **permitir** (el tipo 1 es solo optimizar).

   ```powershell
   .\Get-TLEPacFile.ps1 -Instance Worldwide -Type 2 -TenantName <contoso> -CdnEdgeNodesFilePath .\cdnedgenodes.json -FilePath TLE.pac
   ```

5. El archivo TLE.pac contendrá todos los espacios de nombres y direcciones IP (IPv4/IPv6).

##### <a name="get-tlepacfileps1"></a>Get-TLEPacFile.ps1

```powershell
# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License.

<#PSScriptInfo

.VERSION 1.0.4

.AUTHOR Microsoft Corporation

.GUID 7f692977-e76c-4582-97d5-9989850a2529

.COMPANYNAME Microsoft

.COPYRIGHT
Copyright (c) Microsoft Corporation. All rights reserved.
Licensed under the MIT License.

.TAGS PAC Microsoft Microsoft365 365

.LICENSEURI

.PROJECTURI http://aka.ms/ipurlws

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES

#>

<#

.SYNOPSIS

Create a PAC file for Microsoft 365 prioritized connectivity

.DESCRIPTION

This script will access updated information to create a PAC file to prioritize Microsoft 365 Urls for
better access to the service. This script will allow you to create different types of files depending
on how traffic needs to be prioritized.

.PARAMETER Instance

The service instance inside Microsoft 365.

.PARAMETER ClientRequestId

The client request id to connect to the web service to query up to date Urls.

.PARAMETER DirectProxySettings

The direct proxy settings for priority traffic.

.PARAMETER DefaultProxySettings

The default proxy settings for non priority traffic.

.PARAMETER Type

The type of prioritization to give. Valid values are 1 and 2, which are 2 different modes of operation.
Type 1 will send Optimize traffic to the direct route. Type 2 will send Optimize and Allow traffic to
the direct route.

.PARAMETER Lowercase

Flag this to include lowercase transformation into the PAC file for the host name matching.

.PARAMETER TenantName

The tenant name to replace wildcard Urls in the webservice.

.PARAMETER ServiceAreas

The service areas to filter endpoints by in the webservice.

.PARAMETER FilePath

The file to print the content to.

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -DefaultProxySettings "PROXY 4.4.4.4:70" -FilePath type1.pac

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -Instance China -Type 2 -DefaultProxySettings "PROXY 4.4.4.4:70" -FilePath type2.pac

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -Instance WorldWide -Lowercase -TenantName tenantName -ServiceAreas Sharepoint

#>

#Requires -Version 2

[CmdletBinding(SupportsShouldProcess=$True)]
Param (
    [Parameter(Mandatory = $false)]
    [ValidateSet('Worldwide', 'Germany', 'China', 'USGovDoD', 'USGovGCCHigh')]
    [String] $Instance = "Worldwide",

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [guid] $ClientRequestId = [Guid]::NewGuid().Guid,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [String] $DirectProxySettings = 'DIRECT',

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [String] $DefaultProxySettings = 'PROXY 10.10.10.10:8080',

    [Parameter(Mandatory = $false)]
    [ValidateRange(1, 2)]
    [int] $Type = 1,

    [Parameter(Mandatory = $false)]
    [switch] $Lowercase = $false,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $TenantName,

    [Parameter(Mandatory = $false)]
    [ValidateSet('Exchange', 'SharePoint', 'Common', 'Skype')]
    [string[]] $ServiceAreas,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $FilePath,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $CdnEdgeNodesFilePath
)

##################################################################################################################
### Global constants
##################################################################################################################

$baseServiceUrl = "https://endpoints.office.com/endpoints/$Instance/?ClientRequestId={$ClientRequestId}"
$directProxyVarName = "direct"
$defaultProxyVarName = "proxyServer"
$bl = "`r`n"

##################################################################################################################
### Functions to create PAC files
##################################################################################################################

function Get-PacClauses
{
    param(
        [Parameter(Mandatory = $false)]
        [string[]] $Urls,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String] $ReturnVarName
    )

    if (!$Urls)
    {
        return ""
    }

    $clauses =  (($Urls | ForEach-Object { "shExpMatch(host, `"$_`")" }) -Join "$bl        || ")

@"
    if($clauses)
    {
        return $ReturnVarName;
    }
"@
}

function Get-PacString
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [array[]] $MapVarUrls
    )

@"
// This PAC file will provide proxy config to Microsoft 365 services
//  using data from the public web service for all endpoints
function FindProxyForURL(url, host)
{
    var $directProxyVarName = "$DirectProxySettings";
    var $defaultProxyVarName = "$DefaultProxySettings";

$( if ($Lowercase) { "    host = host.toLowerCase();" })

$( ($MapVarUrls | ForEach-Object { Get-PACClauses -ReturnVarName $_.Item1 -Urls $_.Item2 }) -Join "$bl$bl" )

$( if (!$ServiceAreas -or $ServiceAreas.Contains('Skype')) { Get-TLEPacConfiguration })

    return $defaultProxyVarName;
}
"@ -replace "($bl){3,}","$bl$bl" # Collapse more than one blank line in the PAC file so it looks better.
}

##################################################################################################################
### Functions to get and filter endpoints
##################################################################################################################

function Get-TLEPacConfiguration {
    param ()
    $PreBlock = @"
    // Don't Proxy Teams Live Events traffic

    if(shExpMatch(host, "*.azureedge.net")
    || shExpMatch(host, "*.bmc.cdn.office.net")
    || shExpMatch(host, "*.media.azure.net"))
    {
        var resolved_ip = dnsResolveEx(host);

"@
    $TLESb = New-Object 'System.Text.StringBuilder'
    $TLESb.Append($PreBlock) | Out-Null

    if (![string]::IsNullOrEmpty($CdnEdgeNodesFilePath) -and (Test-Path -Path $CdnEdgeNodesFilePath)) {
        $CdnData = Get-Content -Path $CdnEdgeNodesFilePath -Raw -ErrorAction SilentlyContinue | ConvertFrom-Json | Select-Object -ExpandProperty value | 
            Where-Object { $_.name -eq 'Premium_Verizon'} | Select-Object -First 1 -ExpandProperty properties | 
            Select-Object -ExpandProperty ipAddressGroups
        $CdnData | Select-Object -ExpandProperty ipv4Addresses | ForEach-Object {
            if ($TLESb.Length -eq $PreBlock.Length) {
                $TLESb.Append("        if(") | Out-Null
            }
            else {
                $TLESb.AppendLine() | Out-Null
                $TLESb.Append("        || ") | Out-Null
            }
            $TLESb.Append("isInNetEx(resolved_ip, `"$($_.BaseIpAddress)/$($_.prefixLength)`")") | Out-Null
        }
        $CdnData | Select-Object -ExpandProperty ipv6Addresses | ForEach-Object {
            if ($TLESb.Length -eq $PreBlock.Length) {
                $TLESb.Append("        if(") | Out-Null
            }
            else {
                $TLESb.AppendLine() | Out-Null
                $TLESb.Append("        || ") | Out-Null
            }
            $TLESb.Append("isInNetEx(resolved_ip, `"$($_.BaseIpAddress)/$($_.prefixLength)`")") | Out-Null
        }
    }
    $AzureIPsUrl = Invoke-WebRequest -Uri "https://www.microsoft.com/en-us/download/confirmation.aspx?id=56519" -UseBasicParsing -ErrorAction SilentlyContinue  | 
            Select-Object -ExpandProperty Links | Select-Object -ExpandProperty href | 
            Where-Object { $_.EndsWith('.json') -and $_ -match 'ServiceTags' } | Select-Object -First 1
    if ($AzureIPsUrl) {
        Invoke-RestMethod -Uri $AzureIPsUrl -ErrorAction SilentlyContinue | Select-Object -ExpandProperty values | 
            Where-Object { $_.name -eq 'AzureFrontDoor.Frontend' } | Select-Object -First 1 -ExpandProperty properties |
            Select-Object -ExpandProperty addressPrefixes | ForEach-Object {
                if ($TLESb.Length -eq $PreBlock.Length) {
                    $TLESb.Append("        if(") | Out-Null
                }
                else {
                    $TLESb.AppendLine() | Out-Null
                    $TLESb.Append("        || ") | Out-Null
                }
                $TLESb.Append("isInNetEx(resolved_ip, `"$_`")") | Out-Null
            }
    }
    if ($TLESb.Length -gt $PreBlock.Length) {
        $TLESb.AppendLine(")") | Out-Null
        $TLESb.AppendLine("        {") | Out-Null
        $TLESb.AppendLine("            return $directProxyVarName;") | Out-Null
        $TLESb.AppendLine("        }") | Out-Null
    }
    else {
        $TLESb.AppendLine("        // no addresses found for service via script") | Out-Null
    }
    $TLESb.AppendLine("    }") | Out-Null
    return $TLESb.ToString()
}

function Get-Regex
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $Fqdn
    )

    return "^" + $Fqdn.Replace(".", "\.").Replace("*", ".*").Replace("?", ".?") + "$"
}

function Match-RegexList
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $ToMatch,

        [Parameter(Mandatory = $false)]
        [string[]] $MatchList
    )

    if (!$MatchList)
    {
        return $false
    }
    foreach ($regex in $MatchList)
    {
        if ($regex -ne $ToMatch -and $ToMatch -match (Get-Regex $regex))
        {
            return $true
        }
    }
    return $false
}

function Get-Endpoints
{
    $url = $baseServiceUrl
    if ($TenantName)
    {
        $url += "&TenantName=$TenantName"
    }
    if ($ServiceAreas)
    {
        $url += "&ServiceAreas=" + ($ServiceAreas -Join ",")
    }
    return Invoke-RestMethod -Uri $url
}

function Get-Urls
{
    param(
        [Parameter(Mandatory = $false)]
        [psobject[]] $Endpoints
    )

    if ($Endpoints)
    {
        return $Endpoints | Where-Object { $_.urls } | ForEach-Object { $_.urls } | Sort-Object -Unique
    }
    return @()
}

function Get-UrlVarTuple
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $VarName,

        [Parameter(Mandatory = $false)]
        [string[]] $Urls
    )
    return New-Object 'Tuple[string,string[]]'($VarName, $Urls)
}

function Get-MapVarUrls
{
    Write-Verbose "Retrieving all endpoints for instance $Instance from web service."
    $Endpoints = Get-Endpoints

    if ($Type -eq 1)
    {
        $directUrls = Get-Urls ($Endpoints | Where-Object { $_.category -eq "Optimize" })
        $nonDirectPriorityUrls = Get-Urls ($Endpoints | Where-Object { $_.category -ne "Optimize" }) | Where-Object { Match-RegexList $_ $directUrls }
        return @(
            Get-UrlVarTuple -VarName $defaultProxyVarName -Urls $nonDirectPriorityUrls
            Get-UrlVarTuple -VarName $directProxyVarName -Urls $directUrls
        )
    }
    elseif ($Type -eq 2)
    {
        $directUrls = Get-Urls ($Endpoints | Where-Object { $_.category -in @("Optimize", "Allow")})
        $nonDirectPriorityUrls = Get-Urls ($Endpoints | Where-Object { $_.category -notin @("Optimize", "Allow") }) | Where-Object { Match-RegexList $_ $directUrls }
        return @(
            Get-UrlVarTuple -VarName $defaultProxyVarName -Urls $nonDirectPriorityUrls
            Get-UrlVarTuple -VarName $directProxyVarName -Urls $directUrls
        )
    }
}

##################################################################################################################
### Main script
##################################################################################################################

$content = Get-PacString (Get-MapVarUrls)

if ($FilePath)
{
    $content | Out-File -FilePath $FilePath -Encoding ascii
}
else
{
    $content
}
```

El script analizará automáticamente la lista de Azure en función de la [dirección URL de descarga](https://www.microsoft.com/download/details.aspx?id=56519) y las claves fuera de **AzureFrontDoor.Frontend**, por lo que no es necesario obtenerla manualmente.

De nuevo, no se recomienda realizar la descarga de VPN con solo los FQDN; Usar **los** FQDN y las direcciones IP de la función ayuda a limitar el uso de esta descarga a un conjunto limitado de puntos de conexión, incluidos Live Events/Stream. La forma en que se estructura la función dará lugar a que se realice una búsqueda DNS para el FQDN que coincida con las enumeradas directamente por el cliente, es decir, la resolución DNS de los espacios de nombres restantes permanece sin cambios.

Si desea limitar el riesgo de descarga de puntos de conexión no relacionados con Live Events y Stream, puede quitar el **\*dominio .azureedge.net** de la configuración, que es donde se encuentra la mayor parte de este riesgo, ya que se trata de un dominio compartido que se usa para todos los clientes de Azure CDN. La desventaja de esto es que cualquier evento que use un codificador externo no se optimizará, pero los eventos generados o organizados en Teams serán.

## <a name="3-configure-routing-on-the-vpn-to-enable-direct-egress"></a>3. Configurar el enrutamiento en la VPN para habilitar la salida directa

El último paso es agregar una ruta directa para las direcciones IP de eventos en directo descritas en **Recopilación de las listas actuales de puntos de conexión de RED CDN** en la configuración de VPN para asegurarse de que el tráfico no se envía a través del túnel forzado a la VPN. Puede encontrar información detallada sobre cómo hacerlo para los puntos de conexión de Microsoft 365 Optimize en la sección [Implementar tunelización dividida de VPN](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) de [Implementación de la tunelización dividida de VPN para Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md). El proceso es exactamente el mismo para las direcciones IP de Stream/Live Events enumeradas en este documento.

Tenga en cuenta que solo se deben usar las direcciones IP (no LOS FQDN) de [Recopilación de las listas actuales de puntos de conexión de RED CDN](#gathering-the-current-lists-of-cdn-endpoints) para la configuración de VPN.

## <a name="faq"></a>Preguntas más frecuentes

### <a name="will-this-send-all-my-traffic-to-the-service-direct"></a>¿Esto enviará todo mi tráfico al servicio directamente?

No, esto enviará el tráfico de streaming sensible a la latencia para un evento en directo o streaming de vídeo directo, cualquier otro tráfico seguirá usando el túnel VPN si no se resuelven en las direcciones IP publicadas.

### <a name="do-i-need-to-use-the-ipv6-addresses"></a>¿Necesito usar las direcciones IPv6?

No, la conectividad solo puede ser IPv4 si es necesario.

### <a name="why-are-these-ips-not-published-in-the-microsoft-365-urlip-service"></a>¿Por qué estas direcciones IP no se publican en el servicio de dirección URL/IP de Microsoft 365?

Microsoft tiene controles estrictos en torno al formato y el tipo de información que se encuentra en el servicio para garantizar que los clientes puedan usar la información de forma confiable para implementar un enrutamiento seguro y óptimo en función de la categoría de punto de conexión.

La categoría Punto de conexión **predeterminado** no tiene información de IP proporcionada por numerosas razones (los puntos de conexión predeterminados pueden estar fuera del control de Microsoft, pueden cambiar con demasiada frecuencia o estar en bloques compartidos con otros elementos). Por este motivo, los puntos de conexión predeterminados están diseñados para enviarse a través del FQDN a un proxy de inspección, como el tráfico web normal.

En este caso, los puntos de conexión anteriores son redes CDN que pueden usar elementos no controlados por Microsoft que no sean Live Events o Stream, por lo que enviar el tráfico directo también significará cualquier otra cosa que se resuelva en estas direcciones IP también se enviará directamente desde el cliente. Debido a la naturaleza única de la crisis global actual y para satisfacer las necesidades a corto plazo de nuestros clientes, Microsoft ha proporcionado la información anterior para que los clientes puedan usar como consideren oportuno.

Microsoft está trabajando para volver a configurar los puntos de conexión de Live Events para permitir que se incluyan en las categorías de punto de conexión Allow/Optimize en el futuro.

### <a name="do-i-only-need-to-allow-access-to-these-ips"></a>¿Solo necesito permitir el acceso a estas direcciones IP?

No, el acceso a todos los puntos de conexión marcados **requeridos** en [el servicio URL/IP](urls-and-ip-address-ranges.md) es esencial para que el servicio funcione. Además, se requiere cualquier punto de conexión opcional marcado para Stream (id. 41-45).

### <a name="what-scenarios-will-this-advice-cover"></a>¿Qué escenarios cubrirá este consejo?

1. Eventos en directo generados dentro de la aplicación teams
2. Visualización del contenido hospedado de Stream
3. Eventos generados por dispositivos externos (codificador)

### <a name="does-this-advice-cover-presenter-traffic"></a>¿Este consejo cubre el tráfico del moderador?

No lo hace, el consejo anterior es puramente para aquellos que consumen el servicio. Al presentar desde Teams, verá el tráfico del moderador fluyendo a los puntos de conexión UDP marcados de Optimización que aparecen en la fila 11 del servicio URL/IP con consejos detallados de descarga de VPN descritos en la sección [Implementación de túnel dividido de VPN](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) de [Implementación de la tunelización dividida de VPN para Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md).

### <a name="does-this-configuration-risk-traffic-other-than-live-events-amp-stream-being-sent-direct"></a>¿Esta configuración corre el riesgo de que el tráfico que no sea Live Events &amp; Stream se envíe directamente?

Sí, debido a los FQDN compartidos que se usan para algunos elementos del servicio, esto es inevitable. Normalmente, este tráfico se envía a través de un proxy corporativo que puede aplicar la inspección. En un escenario de túnel dividido de VPN, el uso de los FQDN y las direcciones IP limitará este riesgo al mínimo, pero seguirá existiendo. Los clientes pueden quitar el **\*dominio .azureedge.net** de la configuración de descarga y reducir este riesgo a un mínimo, pero esto quitará la descarga de eventos en directo compatibles con Stream (eventos de codificador externos programados por Teams, eventos de Yammer producidos en Teams, eventos de codificador externo programados para Yammer y eventos programados de Stream o visualización a petición desde Stream). Los eventos programados y producidos en Teams no se ven afectados.

## <a name="related-articles"></a>Artículos relacionados

[Información general: Túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[Implementación de la tunelización dividida de VPN para Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)

[Escenarios comunes de tunelización dividida de VPN para Microsoft 365](microsoft-365-vpn-common-scenarios.md)

[Protección del tráfico multimedia Teams para la tunelización dividida VPN](microsoft-365-vpn-securing-teams.md)

[Optimización del rendimiento de Microsoft 365 para usuarios de China](microsoft-365-networking-china.md)

[Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Evaluar la conectividad de red de Microsoft 365](assessing-network-connectivity.md)

[Optimización de rendimiento y red de Microsoft 365](network-planning-and-performance.md)

[Formas alternativas para que los profesionales de seguridad y de TI logren controles de seguridad modernos en los escenarios de trabajo remoto específicos (blog del Equipo de Seguridad de Microsoft)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Mejorando el rendimiento de la VPN en Microsoft: usando perfiles de VPN de Windows 10 para permitir conexiones automáticas ](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Funcionando con VPN: cómo Microsoft mantiene conectado a su personal remoto](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Red global de Microsoft](/azure/networking/microsoft-global-network)
