---
title: Prevención de la pérdida de datos
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo administrar la configuración de directivas de prevención de pérdida de datos.
ms.openlocfilehash: 93c06af0203a5eb590d22d86e597d7485d7af238
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702909"
---
# <a name="prevent-data-loss-with-dlp"></a>Evitar la pérdida de datos con DLP

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

Las directivas de prevención de pérdida de datos ayudan a identificar y proteger la información confidencial de la empresa, como los números de la seguridad social o los registros médicos. 

## <a name="try-it"></a>¿Se atreve?

1. Para empezar, vaya al centro de [Administración](https://admin.microsoft.com)y seleccione **configurar**.
1. Desplácese hacia abajo hasta **configurar la prevención de pérdida de datos** y, después, seleccione **Ver** y **administrar**.
1. Para editar una directiva, selecciónela, seleccione **Editar Directiva** y, a continuación, seleccione qué cambiar. Por ejemplo, seleccione **ubicaciones** para cambiar lo que se examina.
1. Para habilitar el análisis de contenido en Microsoft Teams, gire el conmutador de alternancia a la posición **activado** y, a continuación, seleccione **Guardar**.
1. Para editar la configuración de la Directiva, seleccione **Editar**.
1. Deberá establecer reglas independientes que se apliquen a pequeñas y grandes cantidades de contenido confidencial detectado. Expanda su regla de volumen bajo. Elija **Editar regla**.
1. Revise la configuración y ajústela según sea necesario. Por ejemplo, puede optar por **personalizar el texto del correo electrónico** y **personalizar el texto de la sugerencia de directiva**. Haga clic en **Guardar**.
1. Repita para la regla de volumen alto. Seleccione **Guardar** y, a continuación, **cerrar**.
1. Para crear una nueva Directiva, seleccione **crear una directiva**.
1. Puede crear una directiva personalizada o empezar con una plantilla. Por ejemplo, para crear una directiva de HIPAA, seleccione la plantilla **médica and Health** y, a continuación, seleccione **ley de seguros de salud estadounidense (HIPAA)**. Seleccione **Siguiente**.
1. Escriba un nombre y una descripción para la Directiva. Seleccione **Siguiente**.
1. Elija las ubicaciones que desea analizar. Seleccione **Siguiente**.
1. Elija el tipo de contenido que desea proteger. Seleccione **Siguiente**.
1. Elija qué desea que suceda si se detecta información confidencial. Seleccione **Siguiente**.
1. Personalizar los permisos de acceso y anulación. Seleccione **Siguiente**.
1. Elija Cuándo desea que se aplique la Directiva. Seleccione **Siguiente**.
1. Revise la configuración y seleccione **crear**. Una vez que la Directiva surta efecto, se bloqueará el correo electrónico que contenga la información confidencial descrita y el remitente que intentó enviar la información verá un mensaje de advertencia.