---
title: RGPD
description: 'Guía técnica de Microsoft: CONJUNTO DE HERRAMIENTAS DE MIGRACIONES DE FASTTRACK PARA ENVIAR SOLICITUDES DE ELIMINACIÓN'
keywords: Migración de FastTrack, Microsoft 365 Educación, documentación de Microsoft 365, RGPD
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: mohitku
author: MohitKumar
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 89ddb00045e2a17821ef2e841ad9a9b4c38d2219
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596467"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a>Conjunto de herramientas de migración de FastTrack para cursar solicitudes de eliminación

## <a name="toolset-purpose"></a>Finalidad del conjunto de herramientas

Si es un cliente que actualmente está realizando una migración de FastTrack, eliminar la cuenta de usuario de Office 365 no hará que se elimine la copia de datos que el equipo de FastTrack de Microsoft conserva, cosa que hace con el único propósito de completar la migración. Si quiere que el equipo de Microsoft FastTrack elimine también esa copia de datos durante la migración, curse una solicitud a través de este conjunto de herramientas. En el transcurso habitual de las actividades, Microsoft FastTrack eliminará todas las copias de datos cuando la migración finalice.

### <a name="supported-platforms"></a>Plataformas compatibles
Microsoft admite la versión inicial de este conjunto de herramientas en la plataforma de Windows y en la consola de PowerShell. Este conjunto de herramientas admite las siguientes plataformas conocidas:
 
***Tabla 1: plataformas admitidas por este conjunto de herramientas***
 
<!--start table here HEADER -->
 
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
| |**Windows 7**|**Windows 8**|**Windows 10**|**Windows Server 2012**|**Windows Server 2016**|
|PS 5.0|No<br/>Compatible.|Compatible.|Compatible.|Compatible.|Compatible.|
|PS 5.1|No<br/>Compatible.|Compatible.|Compatible.|Compatible.|Compatible.|
|||
 
<!-- end of table -->

### <a name="obtaining-the-toolset"></a>Obtener el conjunto de herramientas

Este conjunto de herramientas está disponible en la Galería de PowerShell de la aplicación de consola de PowerShell. Para encontrar y cargar este módulo de cmdlet, abra primero PowerShell en el modo de administrador para, así, contar con los permisos adecuados para instalar el módulo. Si no ha usado PowerShell anteriormente, vaya a la barra de tareas de Windows y, en el cuadro de búsqueda, escriba "PowerShell". Seleccione la aplicación de consola haciendo clic con el botón derecho, elija **Ejecutar como administrador** y haga clic en **Sí** para ejecutar Windows PowerShell.

![PowerShell: ejecutar como administrador](media/fasttrack-powershell_image.png)

![PowerShell: permitir que la aplicación haga cambios](media/fasttrack-run-powershell_image.png)

Con la consola ya abierta, hay que configurar los permisos que permitan ejecutar scripts. Para ello, escriba el siguiente comando: "Set-ExecutionPolicy – ExecutionPolicy: Bypass – Scope: Process".

Se le pedirá que confirme esta acción, dado que el administrador puede cambiar el ámbito a su conveniencia.

***Definir la directiva de ejecución***

![Cambio de establecimiento de la directiva de ejecución en PowerShell](media/powershell-set-execution-policy_image.png)

Ahora que la consola está configurada para permitir la ejecución de scripts, ejecute el siguiente comando para instalar el módulo:

>`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery `
>        
>               -WarningAction: SilentlyContinue `
>               -Force’

### <a name="prerequisites-for-module"></a>Requisitos previos del módulo
Para ejecutar correctamente este módulo, puede que sea necesario instalar módulos dependientes para usarlos si aún no están instalados. Posiblemente deba reiniciar PowerShell.  

Para enviar una solicitud de interesado, antes tiene que iniciar sesión con sus credenciales de Office 365; cuando especifique las credenciales apropiadas, se validará el estado de su cuenta de administrador global y se recopilará información del inquilino. 

**Login-FastTrackAccount -ApiKey: \<Clave de API proporcionada por FastTrack MVM\>**

Tras haber iniciado sesión correctamente, la clave y las credenciales se almacenarán para su uso con módulos FastTrack durante lo que quede de la sesión actual de PowerShell.

Si necesita conectarse a un entorno de nube que no sea comercial, deberá agregar *-Environment* al comando *Login* con uno de los siguientes entornos válidos:
- AzureCloud
- AzureChinaCloud
- AzureGermanCloud
- AzureUSGovernmentCloud

**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <entorno de nube\>**

Para enviar una solicitud de interesado, ejecute el siguiente comando: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com

Si el cmdlet se ejecuta correctamente, devolverá un objeto de identificador de transacción. Guárdelo.


#### <a name="checking-the-status-of-a-request-transaction"></a>Comprobar el estado de una transacción de solicitud

Ejecutar la siguiente función usando el identificador de transacción obtenido anteriormente: Get-FastTrackGdprDsrRequest -TransactionID: "identificadorDeTransacción"

#### <a name="transaction-status-codes"></a>Códigos de estado de la transacción
<!--start table here no header -->

|||
|:-----|:-----|:-----|
|**Transacción** |**Estado**|
|**Created** |La solicitud se ha creado.|
|**Failed**|La solicitud no se ha podido crear. Vuelva a enviarla o póngase en contacto con el equipo de soporte técnico.|
|**Completed**|La solicitud se ha completado y saneado.|
|||

<!-- end of table -->

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->


## <a name="learn-more"></a>Más información
[Centro de confianza de Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)