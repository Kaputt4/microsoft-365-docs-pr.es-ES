---
title: Usar búsqueda de contenido para buscar datos importados de terceros
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Use la herramienta de exhibición de documentos electrónicos de búsqueda de contenido para buscar elementos importados a buzones de correo en Microsoft 365 desde un origen de datos de terceros mediante la creación de consultas.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324576"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a>Usar la búsqueda de contenido para buscar datos de terceros importados por un conector de asociado personalizado

Puede usar la herramienta [de](content-search.md) exhibición de documentos electrónicos de búsqueda de contenido en el Centro de seguridad y cumplimiento de & para buscar elementos importados a buzones de correo en Microsoft 365 de un origen de datos de terceros. Puede crear una consulta para buscar en todos los elementos de datos de terceros importados o puede crear una consulta para buscar elementos de datos de terceros específicos. Además, también puede crear una directiva de retención basada en consultas o una retención de exhibición de documentos electrónicos basada en consultas para conservar datos de terceros.
  
Para obtener más información sobre cómo trabajar con un partner para importar datos de terceros y una lista de los tipos de datos de terceros que puede importar a Microsoft 365, vea Trabajar con un partner para archivar datos de terceros en [Office 365](work-with-partner-to-archive-third-party-data.md).

> [!IMPORTANT]
> Las instrucciones de este artículo solo se aplican a los datos de terceros importados por un conector de asociado personalizado. Este artículo no se aplica a los datos de terceros que se importan mediante los conectores de datos de terceros [en](archiving-third-party-data.md#third-party-data-connectors) el Centro de cumplimiento de Microsoft.
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>Creación de una consulta para buscar en todos los datos de terceros

Para buscar (o poner en espera) cualquier tipo de datos de terceros que haya importado a Office 365, puede usar el par de propiedades y valores del mensaje en el cuadro de palabra clave de una búsqueda de contenido o al crear una retención basada en `kind:externaldata` consultas. Por ejemplo, para buscar elementos importados desde cualquier origen de datos de terceros y contener la palabra "contoso" en la propiedad Subject del elemento importado, se usaría la siguiente consulta: 
  
```powershell
kind:externaldata AND subject:contoso
```

El ejemplo de consulta de palabra clave anterior incluye la propiedad subject. Para obtener una lista de otras propiedades para elementos de datos de terceros que pueden incluirse en una consulta de palabras clave, vea la sección "Más información" en Trabajar con un partner para archivar datos de terceros en [Office 365](work-with-partner-to-archive-third-party-data.md#more-information).
  
Al crear consultas para buscar y retener datos de terceros, también puede usar condiciones para restringir los resultados de la búsqueda. Para obtener más información acerca de cómo crear consultas de búsqueda de contenido, vea Consultas de palabras clave y condiciones [de búsqueda para búsqueda de contenido](keyword-queries-and-search-conditions.md).
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>Creación de una consulta para buscar tipos específicos de datos de terceros

En lugar de buscar en todos los tipos de datos de terceros, puede crear consultas que solo busquen un tipo especificado de datos de terceros mediante la siguiente propiedad *message: value* pair en el cuadro de palabras clave de una búsqueda de contenido:
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

Por ejemplo, para buscar datos de Facebook que contengan la palabra "contoso" en la propiedad Subject, use la siguiente consulta:
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

En la tabla siguiente se enumeran los tipos de datos de terceros que puede buscar y el valor que se usará para la propiedad message para buscar específicamente ese tipo de datos  `itemclass:` de terceros. La sintaxis de consulta no distingue mayúsculas de minúsculas. 
  
|**Tipo de datos de terceros**|**Valor de la  `itemclass:` propiedad**|
|:-----|:-----|
|AIM  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL con cliente Pivot  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Marcador de posición de ejes  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|Blackberry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|Registros de llamadas de BlackBerry  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry PIN  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Mensaje de Bloomberg  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|Mensajería de Bloomberg  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box  <br/> | `ipm.externaldata.Box*` <br/> |
|Cisco IM &amp; Presence Server  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud para Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Conexión directa  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google+  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM Connections  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|Chat ICE  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|Indii Messenger  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|Alineación de la mente  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|MSN  <br/> | `ipm.externaldata.MSN*` <br/> |
|MySpace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|Documento principal  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|Skype Empresarial  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|Squawker  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS Chat  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
