---
title: Consideraciones especiales para stream y eventos en directo en entornos VPN
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: Consideraciones especiales para stream y eventos en directo en entornos VPN
ms.openlocfilehash: eb2e57b844f06bc3b1e005aa1095794b176bba94
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331356"
---
# <a name="special-considerations-for-stream-and-live-events-in-vpn-environments"></a>Consideraciones especiales para stream y eventos en directo en entornos VPN

>[!NOTE]
>Este artículo forma parte de un conjunto de artículos que abordan la optimización Microsoft 365 usuarios remotos.

>- Para obtener información general sobre cómo usar el túnel dividido de VPN para optimizar la conectividad Microsoft 365 usuarios remotos, vea [Overview: VPN split tunneling for Microsoft 365](microsoft-365-vpn-split-tunnel.md).
>- Para obtener instrucciones detalladas sobre cómo implementar el túnel dividido de VPN, consulte [Implementing VPN split tunneling for Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md).
>- Para obtener una lista detallada de escenarios de túnel dividido de VPN, consulte [Escenarios de túnel dividido de VPN comunes para Microsoft 365](microsoft-365-vpn-common-scenarios.md).
>- Para obtener instrucciones sobre cómo proteger el Teams de medios en entornos de túnel dividido de VPN, consulte [Securing Teams media traffic for VPN split tunneling](microsoft-365-vpn-securing-teams.md).
>- Para obtener información sobre cómo optimizar Microsoft 365 el rendimiento de los inquilinos en todo el mundo para los usuarios de China, [vea optimización Microsoft 365 rendimiento para los usuarios de China](microsoft-365-networking-china.md).

Microsoft 365 tráfico de eventos en directo (esto incluye los asistentes Teams eventos en directo producidos por Teams y los producidos con un codificador externo a través de Teams, Stream o Yammer) y el tráfico de secuencia a petición se clasifica actualmente como Predeterminado frente a **Optimizar** en la lista  [url/IP](urls-and-ip-address-ranges.md) del servicio. Estos puntos de conexión se clasifican como **predeterminados** porque están hospedados en las CDN que también pueden usar otros servicios. Por lo general, los clientes prefieren proxy de este tipo de tráfico y aplicar los elementos de seguridad que normalmente se realizan en puntos de conexión como estos.

Muchos clientes han solicitado los datos url/IP necesarios para conectar a sus usuarios a eventos stream/live directamente desde su conexión a Internet local, en lugar de enrutar el tráfico de alto volumen y sensible a la latencia a través de la infraestructura VPN. Normalmente, esto no es posible sin espacios de nombres dedicados e información IP precisa para los puntos de conexión, que no se proporciona para los puntos de conexión Microsoft 365 categorizados como **Predeterminados**.

Siga estos pasos para habilitar la conectividad directa para el servicio Stream/Live Events desde clientes que usan una VPN de túnel forzada. Esta solución está diseñada para proporcionar a los clientes una opción para evitar el enrutamiento del tráfico de eventos en directo a través de VPN mientras hay un tráfico de red alto debido a escenarios de trabajo desde casa. Si es posible, se recomienda tener acceso al servicio a través de un proxy de inspección.

>[!NOTE]
>Con esta solución, puede haber elementos de servicio que no se resuelven en las direcciones IP proporcionadas y, por lo tanto, atraviesan la VPN, pero la mayor parte del tráfico de alto volumen, como los datos de streaming, deberían hacerlo. Puede haber otros elementos fuera del ámbito de Live Events/Stream que se capturan por esta descarga, pero estos deben ser limitados, ya que deben cumplir tanto el _FQDN como_ la coincidencia IP antes de ir directo.

>[!IMPORTANT]
>Se recomienda a los clientes sopesar el riesgo de enviar más tráfico que omite la VPN sobre la ganancia de rendimiento de los eventos en directo.

Para implementar la excepción de túnel forzado para Teams Live Events y Stream, se deben aplicar los siguientes pasos:

## <a name="1-configure-external-dns-resolution"></a>1. Configurar la resolución dns externa

Los clientes necesitan que la resolución dns recursiva y externa esté disponible para que los siguientes nombres de host se puedan resolver en direcciones IP.

- \*.azureedge.net
- \*.media.azure.net
- \*.bmc.cdn.office.net

**\*.azureedge.net** se usa para eventos Stream (Configurar codificadores para streaming en directo en [Microsoft Stream - Microsoft Stream | Microsoft Docs](/stream/live-encoder-setup)).

**\*.media.azure.net** **\*y .bmc.cdn.office.net** se usan para eventos en directo producidos por Teams (eventos de inicio rápido, eventos compatibles con RTMP-In [Id. de hoja de ruta 84960]) programados desde el Teams cliente.

 Algunos de estos puntos de conexión se comparten con otros elementos fuera de Stream/Live Events, no se recomienda usar estos FQDN para configurar la descarga de VPN incluso si técnicamente es posible en la solución VPN (por ejemplo, si funciona en el FQDN en lugar de ip).

Los FQDN no son necesarios en la configuración de VPN, son puramente para su uso en archivos PAC en combinación con los IP para enviar el tráfico relevante directo.

## <a name="2-implement-pac-file-changes-where-required"></a>2. Implementar cambios en el archivo PAC (cuando sea necesario)

Para las organizaciones que usan un archivo PAC para enrutar el tráfico a través de un proxy mientras están en VPN, esto se logra normalmente con FQDN. Sin embargo, con Stream/Live Events, los nombres de host proporcionados **\*** contienen caracteres comodín como .azureedge.net, que también incluye otros elementos para los que no es posible proporcionar listas de IP completa. Por lo tanto, si la solicitud se envía directamente en función solo de la coincidencia de caracteres comodín dns, el tráfico a estos puntos de conexión se bloqueará, ya que no hay ninguna ruta a través de la ruta directa para ella en el paso [3](#3-configure-routing-on-the-vpn-to-enable-direct-egress) más adelante en este artículo.

Para solucionar esto, podemos proporcionar las siguientes direcciones IP y usarlas en combinación con los nombres de host en un archivo PAC de ejemplo, tal como se describe en [el paso 1](#1-configure-external-dns-resolution). El archivo PAC comprueba si la dirección URL coincide con las usadas para los eventos Stream/Live y, si lo hace, también comprueba si la IP devuelta de una búsqueda DNS coincide con las proporcionadas para el servicio. Si _ambos_ coinciden, el tráfico se enruta directamente. Si cualquiera de los elementos (FQDN/IP) no coincide, el tráfico se envía al proxy. Como resultado, la configuración garantiza que cualquier cosa que se resuelva en una DIRECCIÓN IP fuera del ámbito de la IP y los espacios de nombres definidos atravesará el proxy a través de la VPN de forma normal.

### <a name="gathering-the-current-lists-of-cdn-endpoints"></a>Recopilación de las listas actuales de CDN de conexión

Live Events usa varios CDN para transmitir a los clientes, para proporcionar la mejor cobertura, calidad y resistencia. Actualmente, se Azure CDN de Microsoft y de Verizon. Con el tiempo, esto podría cambiarse debido a situaciones como la disponibilidad regional. Este artículo es un origen que le permite mantenerse al día en los intervalos IP.

Para Azure CDN de Microsoft, puede descargar la lista desde Descargar [intervalos IP de Azure y etiquetas](https://www.microsoft.com/download/details.aspx?id=56519) de servicio : nube pública desde el Centro de descarga oficial de Microsoft: tendrá que buscar específicamente la etiqueta de servicio *AzureFrontdoor.Frontend* en json; *addressPrefixes mostrará las subredes* IPv4/IPv6. Con el tiempo, las direcciones IP pueden cambiar, pero la lista de etiquetas de servicio siempre se actualiza antes de que se pongan en uso.

For Azure CDN from Verizon (Edgecast) you can find an exhaustive list using [https://docs.microsoft.com/rest/api/cdn/edge-nodes/list](/rest/api/cdn/edge-nodes/list) (click **Try It** ) - you will need to look specifically for the **Premium\_ Verizon** section. Tenga en cuenta que esta API muestra todas las IP de edgecast (origin y Anycast). Actualmente no hay un mecanismo para que la API distinga entre origin y Anycast.

Para implementar esto en un archivo PAC, puede usar el siguiente ejemplo que envía el tráfico directo de optimización de Microsoft 365 (que se recomienda práctica recomendada) a través del FQDN, y el tráfico crítico de stream/live events directamente a través de una combinación del FQDN y la dirección IP devuelta. El nombre del marcador _de posición Contoso_ tendría que editarse en el nombre del inquilino específico donde _contoso_ es de contoso.onmicrosoft.com

#### <a name="example-pac-file"></a>Archivo PAC de ejemplo

Este es un ejemplo de cómo generar los archivos PAC:

1. Guarde el script siguiente en el disco duro local como _Get-TLEPacFile.ps1_.
1. Vaya a la [dirección URL de Verizon](/rest/api/cdn/edge-nodes/list#code-try-0) y descargue el JSON resultante (cópielo en un archivo como cdnedgenodes.json)
1. Coloque el archivo en la misma carpeta que el script.
1. En una ventana de PowerShell, ejecute el siguiente comando. Cambie el nombre del inquilino para otra cosa si desea las direcciones URL de SPO. Este es el tipo 2, por lo que **optimizar** y **permitir** (el tipo 1 es optimizar solamente).

   ```powershell
   .\Get-TLEPacFile.ps1 -Instance Worldwide -Type 2 -TenantName <contoso> -CdnEdgeNodesFilePath .\cdnedgenodes.json -FilePath TLE.pac
   ```

5. El archivo TLE.pac contendrá todos los espacios de nombres e IP (IPv4/IPv6).

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

El script analizará automáticamente la lista de Azure en función de la [dirección URL](https://www.microsoft.com/download/details.aspx?id=56519) de descarga y las claves de **AzureFrontDoor.Frontend**, por lo que no es necesario obtenerla manualmente.

De nuevo, no se recomienda realizar la descarga de VPN con solo los FQDN; usar **los** FQDN y las direcciones IP de la función ayuda a limitar el uso de esta descarga a un conjunto limitado de puntos de conexión, incluidos Live Events/Stream. La forma en que se estructura la función dará como resultado que se haga una búsqueda dns para el FQDN que coincida con los enumerados por el cliente directamente, es decir, la resolución DNS de los espacios de nombres restantes permanece sin cambios.

Si desea limitar el riesgo de descargar puntos de conexión que no están relacionados con Live Events y Stream, **\*** puede quitar el dominio .azureedge.net de la configuración, que es donde se encuentra la mayor parte de este riesgo, ya que se trata de un dominio compartido que se usa para todos los clientes de Azure CDN. La desventaja de esto es que cualquier evento que use un codificador externo no se optimizará, pero los eventos producidos o organizados dentro de Teams lo estarán.

## <a name="3-configure-routing-on-the-vpn-to-enable-direct-egress"></a>3. Configurar el enrutamiento en la VPN para habilitar la salida directa

El último paso es agregar una ruta directa para las IP de eventos en directo **descritas en Recopilación** de las listas actuales de puntos de conexión de CDN en la configuración de VPN para asegurarse de que el tráfico no se envía a través del túnel forzado a la VPN. Encontrará información detallada sobre cómo hacerlo para los puntos de conexión de optimización de Microsoft 365 en la sección Implementar túnel dividido de [VPN](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) de Implementar túnel [dividido de VPN para Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md). El proceso es exactamente el mismo para las IP de stream/live events enumeradas en este documento.

Tenga en cuenta que solo los IP (no FQDN) de [Recopilar](#gathering-the-current-lists-of-cdn-endpoints) las listas actuales de puntos de conexión CDN deben usarse para la configuración de VPN.

## <a name="faq"></a>Preguntas más frecuentes

### <a name="will-this-send-all-my-traffic-to-the-service-direct"></a>¿Esto enviará todo mi tráfico al servicio directamente?

No, esto enviará el tráfico de streaming sensible a la latencia de un evento live o directo de vídeo Stream, cualquier otro tráfico seguirá usando el túnel VPN si no se resuelven en las IP publicadas.

### <a name="do-i-need-to-use-the-ipv6-addresses"></a>¿Necesito usar las direcciones IPv6?

No, la conectividad solo puede ser IPv4 si es necesario.

### <a name="why-are-these-ips-not-published-in-the-microsoft-365-urlip-service"></a>¿Por qué estas direcciones IP no se publican en el servicio Microsoft 365 URL/IP?

Microsoft tiene controles estrictos en torno al formato y el tipo de información que está en el servicio para garantizar que los clientes puedan usar de forma confiable la información para implementar un enrutamiento seguro y óptimo en función de la categoría de extremo.

La **categoría** de extremo predeterminado no proporciona información IP por numerosas razones (Los extremos predeterminados pueden estar fuera del control de Microsoft, cambiar con demasiada frecuencia o estar en bloques compartidos con otros elementos). Por este motivo, los extremos predeterminados están diseñados para enviarse a través de FQDN a un proxy de inspección, como el tráfico web normal.

En este caso, los puntos de conexión anteriores son CDN que pueden usar elementos que no son controlados por Microsoft que no sean Live Events o Stream, por lo que enviar el tráfico directo también significará cualquier otra cosa que se resuelva en estas IP también se enviará directamente desde el cliente. Debido a la naturaleza única de la crisis global actual y para satisfacer las necesidades a corto plazo de nuestros clientes, Microsoft ha proporcionado la información anterior para que los clientes puedan usarlo según lo que es conveniente.

Microsoft está trabajando para volver a configurar los puntos de conexión de eventos en directo para permitir que se incluyan en las categorías de extremo Permitir/optimizar en el futuro.

### <a name="do-i-only-need-to-allow-access-to-these-ips"></a>¿Solo necesito permitir el acceso a estas IP?

No, el acceso a todos los puntos de **conexión marcados** requeridos en el servicio [URL/IP](urls-and-ip-address-ranges.md) es esencial para que el servicio funcione. Además, se requiere cualquier extremo opcional marcado para Stream (id. 41-45).

### <a name="what-scenarios-will-this-advice-cover"></a>¿Qué escenarios abarcará este consejo?

1. Eventos en directo producidos dentro de la Teams app
2. Visualización del contenido hospedado de Stream
3. Eventos producidos por dispositivo externo (codificador)

### <a name="does-this-advice-cover-presenter-traffic"></a>¿Este consejo cubre el tráfico de moderador?

No es así, el consejo anterior es puramente para aquellos que consumen el servicio. La presentación desde dentro de Teams verá el tráfico del moderador fluyendo a los puntos de conexión UDP marcados optimizar enumerados en la fila 11 del servicio URL/IP con el asesoramiento detallado de descarga de VPN descrito en la sección Implementar túnel dividido de [VPN](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) de Implementar túnel dividido de [VPN para Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md).

### <a name="does-this-configuration-risk-traffic-other-than-live-events-amp-stream-being-sent-direct"></a>¿Esta configuración arriesga el tráfico que no sea Live Events &amp; Stream que se envía directamente?

Sí, debido a los FQDN compartidos usados para algunos elementos del servicio, esto es inevitable. Este tráfico normalmente se envía a través de un proxy corporativo que puede aplicar la inspección. En un escenario de túnel dividido de VPN, el uso de los FQDN y los IP reducirá este riesgo al mínimo, pero seguirá existiendo. Los clientes pueden quitar el dominio .azureedge.net de la configuración de descarga y reducir este riesgo al mínimo, pero esto quitará la descarga de eventos en directo compatibles con Stream (eventos de codificador externos programados por Teams, eventos Yammer producidos en Teams, eventos de codificador externo programados por Yammer y Eventos programados de stream o visualización a petición de Stream).**\*** Los eventos programados y producidos en Teams no se ven afectados.

## <a name="related-articles"></a>Artículos relacionados

[Información general: Túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[Implementación de túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)

[Escenarios comunes de túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-common-scenarios.md)

[Proteger el tráfico Teams multimedia para el túnel dividido de VPN](microsoft-365-vpn-securing-teams.md)

[Microsoft 365 optimización del rendimiento para usuarios de China](microsoft-365-networking-china.md)

[Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Evaluar la conectividad de red de Microsoft 365](assessing-network-connectivity.md)

[Microsoft 365 de red y rendimiento](network-planning-and-performance.md)

[Formas alternativas para que los profesionales de seguridad y de TI logren controles de seguridad modernos en los escenarios de trabajo remoto específicos (blog del Equipo de Seguridad de Microsoft)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Mejorando el rendimiento de la VPN en Microsoft: usando perfiles de VPN de Windows 10 para permitir conexiones automáticas ](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Funcionando con VPN: cómo Microsoft mantiene conectado a su personal remoto](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Red global de Microsoft](/azure/networking/microsoft-global-network)
