---
title: Obtener notificaciones de incidentes en Microsoft 365 Defender
description: Obtenga información sobre cómo crear reglas para obtener notificaciones por correo electrónico para incidentes en Microsoft 365 Defender
keywords: incidente, correo electrónico, notificaciones de correo electrónico, configurar, usuarios, buzón, correo electrónico, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9db025818fdd5eb2635a9a676e4a10e20f3036b6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930983"
---
# <a name="get-incident-notifications-by-email"></a>Obtener notificaciones de incidentes por correo electrónico

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Puede configurar Microsoft 365 Defender para que le notifique por correo electrónico cada vez que haya nuevos incidentes o nuevas actualizaciones de incidentes existentes. 

Puedes elegir obtener notificaciones según la gravedad del incidente o por grupo de dispositivos. También puedes elegir obtener una notificación solo en la primera actualización por incidente.

Puede agregar o quitar destinatarios en las notificaciones por correo electrónico. Los destinatarios recién agregados reciben una notificación sobre incidentes después de agregarse. 

La notificación por correo electrónico contiene detalles importantes sobre el incidente, como el nombre del incidente, la gravedad y las categorías, entre otros. También puede ir directamente a incidentes para que pueda iniciar la investigación inmediatamente. Para obtener más información sobre cómo investigar incidentes, consulte [Investigar incidentes en Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

>[!NOTE]
>Necesita permisos "Administrar la configuración de seguridad" para configurar las opciones de notificación por correo electrónico. Si ha elegido usar la administración de permisos básicos, los usuarios con roles de administrador de seguridad o administrador global pueden configurar las notificaciones por correo electrónico. <br> <br>
Del mismo modo, si su organización usa el control de acceso basado en roles (RBAC), solo puede crear, editar, eliminar y recibir notificaciones en función de los grupos de dispositivos que tenga permiso para administrar.

## <a name="create-rules-for-incident-notifications"></a>Crear reglas para notificaciones de incidentes

Para configurar la primera notificación por correo electrónico para incidentes, cree una nueva regla y personalice la configuración de notificación por correo electrónico.

1. En el panel de navegación, seleccione **Notificaciones de** correo electrónico de incidentes  >  **de configuración.**
2. Seleccione **Agregar elemento**.
3. Asigne a la regla un nombre **en Nombre** y proporcione una **descripción.**

    ![Crear ventana de regla para notificaciones de correo electrónico de incidentes](../../media/incidentemailnotif1.png) 
4. Seleccione **Siguiente para** ir a Configuración de **notificaciones.** Aquí puede especificar:
    - **Gravedad de alerta:** elige la gravedad de alerta que desencadenará una notificación de incidente. Por ejemplo, si solo desea que se le informe sobre incidentes de gravedad alta, seleccione Alta.
    - **Ámbito de grupo de** dispositivos: esta lista desplegable muestra todos los grupos de dispositivos a los que el usuario puede acceder. Selecciona para qué grupos de dispositivos vas a crear las reglas de notificación de incidentes.
    - **Notificar solo en la primera aparición por** incidente: al seleccionar esta opción, solo se enviará una notificación por correo electrónico en la primera alerta que coincida con las otras selecciones. Las actualizaciones o alertas posteriores relacionadas con el incidente no desencadenarán una notificación.
    - **Incluir el nombre de** la organización: indica si el nombre del cliente aparece en la notificación por correo electrónico o no.
    - **Incluir el vínculo del portal específico del inquilino:** agrega un vínculo con el id. de inquilino para permitir el acceso a un inquilino específico.
    
    ![Notif settings window for incident email notifs](../../media/incidentemailnotif2.png)
5. Seleccione **Siguiente** para ir a **la sección** Destinatarios. Aquí puede especificar direcciones de correo electrónico que recibirán las notificaciones por correo electrónico de incidentes. Seleccione **Agregar un destinatario después** de escribir cada dirección de correo electrónico.

    ![Ventana Agregar destinatarios para notificaciones de correo electrónico de incidentes](../../media/incidentemailnotif3.png) 

6. Por último, seleccione **Siguiente** para ir a Revisar **regla** para que pueda ver toda la configuración asociada a la nueva regla. Los destinatarios empezarán a recibir notificaciones de incidentes por correo electrónico en función de la configuración.

## <a name="see-also"></a>Consulte también
- [Información general sobre incidentes en Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [Priorizar incidentes en Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [Investigar incidentes en Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

