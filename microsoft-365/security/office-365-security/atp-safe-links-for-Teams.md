---
title: Vínculos seguros de ATP para equipos, safelinks, vínculos seguros, bloquear vínculos malintencionados, Office 365 ATP, equipos vínculos seguros, impedir que los usuarios haga clic en vínculos no válidos, vínculos malintencionados
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Los equipos ahora tendrán acceso a vínculos seguros en el momento de hacer clic. Si usa chats 1-en-1 chats, entre grupos o en canales y pestañas, si tiene una suscripción a Office 365 ATP, tendrá la posibilidad de habilitar y usar esta característica de seguridad.
ms.openlocfilehash: 07f20f0adf503e4592d2bd3f3bc9857d08a1e433
ms.sourcegitcommit: 481fb95d8b80cf2102a9c73b21e7effa79e594e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "43808996"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a>Vínculos seguros en Teams

> [!IMPORTANT]
> Esta característica se encuentra en **versión preliminar pública** para los clientes del programa de adopción de tecnología de Microsoft Teams (TAP) a partir del 28 de febrero de 2020. Esta nota se quitará del artículo cuando vínculos seguros para Teams esté más disponible.

Microsoft Teams, una aplicación basada en la nube de Microsoft para administrar el trabajo, ya usa datos adjuntos seguros (para Office 365), pero ahora tendrá acceso a vínculos seguros en el momento de hacer clic. Independientemente de si usa chats, chats de grupo, canales o pestañas, si tiene una suscripción a Office 365 ATP, tendrá la posibilidad de habilitar y usar esta medida de seguridad. Para obtener más información sobre los requisitos de licencias, consulte [Instrucciones de licencias de Microsoft 365 del nivel de espacio empresarial](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

Aquí se muestra cómo funciona: 

1. Cuando inicie la aplicación Teams, Microsoft 365 se asegurará de que el usuario pertenece a una organización con ATP de Office 365 y que el usuario forma parte de una directiva de vínculos seguros activa con la protección habilitada para Microsoft Teams.

2. Si las opciones anteriores son verdaderas, las direcciones URL se validarán en el momento de hacer clic en chats, chats de grupo, canales y en las pestañas para ese usuario.
 
## <a name="what-will-users-experience"></a>¿Qué van a experimentar los usuarios? 

Todos los usuarios protegidos tendrán esta experiencia con direcciones URL peligrosas: 

- Si se hizo clic en el vínculo desde una conversación de Microsoft Teams, un chat de grupo o desde canales, una página se representará en el explorador predeterminado. Si se hizo clic en el vínculo desde una pestaña anclada, la página aparecerá en la interfaz gráfica de usuario de Microsoft Teams dentro de esa pestaña y la opción para abrirla en el explorador se deshabilitará por motivos de seguridad.

- Este usuario se bloqueará para continuar con el sitio de la dirección URL.

Si el usuario que envió el vínculo no está protegido por Office 365 ATP, es libre de hacer clic en la dirección URL de su equipo y resolver el problema. Esto hace que sea doblemente importante para que los administradores sepan quiénes son y deben ser los usuarios protegidos.

![Una página vínculos seguros para equipos que informa de un vínculo malintencionado y bloquea el tránsito a la página.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

Si hace clic en el botón *volver atrás* de esta página en Microsoft Teams, se cerrará (o puede dar como resultado una página en blanco que los usuarios pueden cerrar). Sin embargo, si vuelve a hacer clic en el vínculo, tendrá que volver a evaluar la reputación del sitio para que vuelva a aparecer esta página.

> [!NOTE]
> Algunos administradores de Microsoft 365 habilitarán el mensaje **continuar de todas formas** en la página de bloqueo. Sin embargo, si vínculos seguros mide la reputación de un sitio y descubre que carece de él, no se debe emprender ningún otro clic. No se recomienda que los usuarios omitan las medidas de seguridad. Valore esto en sus consideraciones antes de habilitar la continuación de todas formas. 
