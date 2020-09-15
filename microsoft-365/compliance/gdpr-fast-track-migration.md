---
title: RGPD
description: 'Guía técnica de Microsoft: CONJUNTO DE HERRAMIENTAS DE MIGRACIONES DE FASTTRACK PARA ENVIAR SOLICITUDES DE ELIMINACIÓN'
keywords: Migración de FastTrack, Microsoft 365 Educación, documentación de Microsoft 365, RGPD
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 10a983297640ac4b65aaf181ef35ac19918e74fe
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547397"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a>Conjunto de herramientas de migración de FastTrack para cursar solicitudes de eliminación

## <a name="toolset-purpose"></a>Finalidad del conjunto de herramientas

Si es un cliente que actualmente está realizando una migración de FastTrack, eliminar la cuenta de usuario no hará que se elimine la copia de datos que el equipo de FastTrack de Microsoft conserva, cosa que hace con el único propósito de completar la migración. Si quiere que el equipo de Microsoft FastTrack elimine también esa copia de datos durante la migración, curse una solicitud a través de este conjunto de herramientas. En el transcurso habitual de las actividades, Microsoft FastTrack eliminará todas las copias de datos cuando la migración finalice.

### <a name="supported-platforms"></a>Plataformas compatibles

Microsoft admite la versión inicial de este conjunto de herramientas en la plataforma de Windows y en la consola de PowerShell. Este conjunto de herramientas admite las siguientes plataformas conocidas:

***Tabla 1: plataformas admitidas por este conjunto de herramientas***

****

|Versión de PowerShell|Windows 7|Windows 8|Windows 10|Windows Server 2012|Windows Server 2016|
|:---:|:---:|:---:|:---:|:---:|:---:|
|5.0|No compatible|Compatible|Compatible.|Compatible.|Compatible|
|5.1|No compatible|Compatible|Compatible.|Compatible.|Compatible.|
|

### <a name="obtaining-the-toolset"></a>Obtener el conjunto de herramientas

Este conjunto de herramientas está disponible en la Galería de PowerShell de la aplicación de consola de PowerShell. Para encontrar y cargar este módulo de cmdlet, abra primero PowerShell en el modo de administrador para, así, contar con los permisos adecuados para instalar el módulo. Si no ha usado PowerShell anteriormente, vaya a la barra de tareas de Windows y, en el cuadro de búsqueda, escriba "PowerShell". Seleccione la aplicación de consola haciendo clic con el botón derecho, elija **Ejecutar como administrador** y haga clic en **Sí** para ejecutar Windows PowerShell.

![PowerShell: ejecutar como administrador](../media/fasttrack-powershell_image.png)

![PowerShell: permitir que la aplicación haga cambios](../media/fasttrack-run-powershell_image.png)

Ahora que la consola está abierta, debe establecer permisos para ejecutar la secuencia de comandos. Escriba el siguiente comando para permitir que se ejecuten los scripts:

```powershell
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process
```

Se le pedirá que confirme esta acción, dado que el administrador puede cambiar el ámbito a su conveniencia.

***Definir la directiva de ejecución***

![Cambio de establecimiento de la directiva de ejecución en PowerShell](../media/powershell-set-execution-policy_image.png)

Ahora que la consola está configurada para permitir la ejecución de scripts, ejecute el siguiente comando para instalar el módulo:

```powershell
Install-Module -Name Microsoft.FastTrack -Repository PSGallery -WarningAction SilentlyContinue -Force
```

### <a name="prerequisites-for-module"></a>Requisitos previos del módulo

Para ejecutar correctamente este módulo, puede que sea necesario instalar módulos dependientes para usarlos si aún no están instalados. Posiblemente deba reiniciar PowerShell.

Para poder enviar una DSR, primero debe iniciar sesión con sus credenciales de Office 365. Al escribir las credenciales correctas, se validará el estado de administrador global y se recopilará la información de espacio empresarial.

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM>
```

Tras haber iniciado sesión correctamente, la clave y las credenciales se almacenarán para su uso con módulos FastTrack durante lo que quede de la sesión actual de PowerShell.

Si necesita conectarse a un entorno de nube que no sea comercial, deberá agregar *-Environment* al comando *Login* con uno de los siguientes entornos válidos:

- AzureCloud
- AzureChinaCloud
- AzureGermanCloud
- AzureUSGovernmentCloud

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM> -Environment <cloud environment>
```

Para enviar una solicitud DSR, ejecute el siguiente comando:

```powershell
Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail SubjectUserEmail@mycompany.com
```

Si se ejecuta correctamente, el cmdlet devolverá un objeto de Id. de la transacción. Guarde el Id. de la transacción.

#### <a name="checking-the-status-of-a-request-transaction"></a>Comprobar el estado de una transacción de solicitud

Ejecute la siguiente función con el Id. de la transacción que consiguió previamente:

```powershell
Get-FastTrackGdprDsrRequest -TransactionID "YourTransactionID"
```

#### <a name="transaction-status-codes"></a>Códigos de estado de la transacción

|Transacción|Estado|
|---|---|
|**Created**|La solicitud se ha creado.|
|**Failed**|La solicitud no se ha podido crear. Vuelva a enviarla o póngase en contacto con el equipo de soporte técnico.|
|**Completed**|La solicitud se ha completado y saneado.|
|

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->

## <a name="learn-more"></a>Obtén más información

[Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
