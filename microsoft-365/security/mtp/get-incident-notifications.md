---
title: Obtener notificaciones de incidentes en Microsoft 365 defender
description: Aprenda a crear reglas para obtener notificaciones de correo electrónico para incidentes en Microsoft 365 defender
keywords: incidente, correo electrónico, correo electrónico notfications, configuración, usuarios, buzón, correo electrónico, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 3af1dcfec165c88a18cbc0d8cbf6866bb6398adc
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668362"
---
# <a name="get-incident-notifications-by-email"></a>Obtener notificaciones de incidentes por correo electrónico

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!IMPORTANT]
> La característica de notificaciones de correo electrónico para incidentes se encuentra actualmente en versión preliminar pública. Parte de la información sobre esta característica puede cambiar antes de la disponibilidad comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

**Se aplica a:**
- Microsoft 365 Defender

Puede configurar Microsoft 365 defender para que le envíe una notificación por correo electrónico cada vez que haya nuevos incidentes o actualizaciones nuevas a los incidentes existentes. 

Puede elegir obtener notificaciones en función de la gravedad del incidente o del grupo de dispositivos. También puede optar por obtener una notificación solo en la primera actualización por incidente.

Puede Agregar o quitar destinatarios en las notificaciones de correo electrónico. Los destinatarios recién agregados reciben una notificación sobre los incidentes después de que se hayan agregado. 

La notificación de correo electrónico contiene detalles importantes sobre el incidente como el nombre del incidente, la gravedad y las categorías, entre otros. También puede ir directamente a incidentes para que pueda iniciar la investigación inmediatamente. Para obtener más información sobre la investigación de incidentes, consulte [investigar incidentes en Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).

>[!NOTE]
>Necesita los permisos de administración de la configuración de seguridad para configurar las notificaciones de correo electrónico. Si ha elegido usar la administración básica de permisos, los usuarios con roles de administrador de seguridad o de administrador global pueden configurar las notificaciones de correo electrónico. <br> <br>
Del mismo modo, si su organización usa el control de acceso basado en roles (RBAC), solo puede crear, editar, eliminar y recibir notificaciones en función de los grupos de dispositivos que se le permita administrar.

## <a name="create-rules-for-incident-notifications"></a>Crear reglas para notificaciones de incidentes

Para configurar su primera notificación de incidentes, cree una nueva regla y personalice la configuración de las notificaciones de correo electrónico.

1. En el panel de navegación, seleccione  >  **notificaciones por correo electrónico de incidente** de configuración.
2. Seleccione **Agregar elemento**.
3. Asigne un nombre a la regla en **nombre** y proporcione una **Descripción**.

    ![Ventana crear regla para notifs de correo electrónico de incidentes](../../media/incidentemailnotif1.png) 
4. Seleccione **siguiente** para ir a **configuración de notificaciones**. Aquí puede especificar:
    - **Gravedad de alerta** : elija la gravedad de la alerta que desencadenará una notificación de incidente. Por ejemplo, si solo desea recibir información sobre los incidentes de gravedad alta, seleccione alta.
    - **Ámbito de grupo de dispositivos** : este cuadro desplegable muestra todos los grupos de dispositivos a los que el usuario puede tener acceso. Seleccione los grupos de dispositivos para los que va a crear las reglas de notificación de incidentes.
    - **Notificar solo en la primera aparición por incidente** : al seleccionar esta opción, se enviará una notificación por correo electrónico sólo en la primera alerta que coincida con las otras selecciones. Las actualizaciones o alertas posteriores relacionadas con el incidente no desencadenarán una notificación.
    - **Incluir nombre** de la organización: indica si el nombre del cliente aparece en la notificación por correo electrónico o no.
    - **Incluir vínculo de portal específico del inquilino** : agrega un vínculo con el identificador de inquilino para permitir el acceso a un inquilino específico.
    
    ![Ventana Configuración de la Notif para el correo electrónico de incidentes notifs](../../media/incidentemailnotif2.png)
5. Seleccione **siguiente** para ir a la sección **destinatarios** . Aquí puede especificar las direcciones de correo electrónico que recibirán las notificaciones por correo electrónico de incidentes. Seleccione **Agregar un destinatario después de** escribir cada dirección de correo electrónico.

    ![Ventana agregar destinatarios para el correo electrónico de incidentes notifs](../../media/incidentemailnotif3.png) 

6. Por último, seleccione **siguiente** para ir a **revisar regla** para que pueda ver toda la configuración asociada a la nueva regla. Los destinatarios empezarán a recibir notificaciones de incidentes a través del correo electrónico en función de la configuración.

## <a name="see-also"></a>Vea también
- [Información general sobre los incidentes en Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [Priorizar incidentes en Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [Investigar incidentes en Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

