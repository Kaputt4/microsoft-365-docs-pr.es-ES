---
title: Supervisión de Exchange Online para Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Usar supervisión de Exchange Online para obtener información sobre avisos o incidentes de correo electrónico en Microsoft 365.
ms.openlocfilehash: 4de4104f3112126b20d51fb6fcf0616cd413b884
ms.sourcegitcommit: f358e321f7e81eff425fe0f0db1be0f3348d2585
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2021
ms.locfileid: "58506447"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a>Supervisión de Exchange Online para Microsoft 365

Puede usar la supervisión de Exchange Online en el Centro de administración de Microsoft 365 para supervisar el estado del servicio de Exchange para la suscripción de Microsoft 365 de su organización. La supervisión de Exchange Online ofrece información sobre incidentes y avisos que se recopilan en estas categorías:

- **Infraestructura**: se detecta un problema en la infraestructura de Microsoft 365 que es propiedad de Microsoft para proporcionar actualizaciones periódicas y solucionar el problema. Por ejemplo, los usuarios no pueden acceder a Exchange Online debido a problemas con Exchange u otra infraestructura en la nube de Microsoft 365.
- **Infraestructura de terceros**: se detecta un problema en una infraestructura de terceros en la que la organización tiene una dependencia y necesita una acción de su organización para su resolución. Por ejemplo, las transacciones de autenticación de usuario se limitan con un proveedor de servicio de token de seguridad (STS) de terceros que impide que los usuarios se conecten a Exchange Online.
- **Infraestructura del cliente**: se detecta un problema en la infraestructura de la organización y requiere una acción de su organización para su resolución. Por ejemplo, los usuarios no pueden acceder a Exchange Online porque no pueden obtener un token de autenticación de un proveedor de STS hospedado por la organización debido a un certificado caducado.

Este es un ejemplo de la página **Estado del servicio** en el Centro de administración de Microsoft 365, disponible en Health > **Servicio > Estado del servicio** para escenarios de la organización.

**los problemas de la organización** se identificarán y usarán en la supervisión de nivel organizativo.

:::image type="content" source="../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png" alt-text="La página de Estado del servicio en el Centro de administración de Microsoft 365":::

El valor de la columna **Estado** en **Problemas de la organización** indica si la infraestructura de la organización o el software de terceros afectan a la experiencia de mantenimiento del servicio de los usuarios de la organización con Exchange Online. Los avisos o incidencias requieren *sus* acciones para resolverse.

El valor de la columna **Estado** en **Estado del servicio Microsoft** indica que el servicio está en buen estado o tiene avisos o incidentes basados en los servicios en la nube que mantiene Microsoft.

Este es un ejemplo de la página de supervisión de Exchange Online en el Centro de administración de Microsoft 365 que muestra el estado de los escenarios de nivel de organización, disponible en **Estado > Estado del servicio > Exchange Online**.

:::image type="content" source="../media/microsoft-365-exchange-monitoring/exchange-monitoring-example.png" alt-text="La página de supervisión de Exchange Online en el Centro de administración de Microsoft 365":::

Con la página de supervisión de **Exchange Online**, puede ver si el servicio de Exchange Online está en buen estado o no y si hay incidentes o avisos asociados. Con la supervisión de Exchange Online, puede observar el estado del servicio para escenarios de correo electrónico específicos y ver señales casi en tiempo real para determinar el impacto por escenario a nivel de organización.

## <a name="requirements"></a>Requisitos

Esta vista previa está habilitada para los clientes que cumplan estos requisitos: 

- Su organización necesita tener al menos 5000 licencias de uno o varios de estos productos: Office 365 E3, Microsoft 365 E3, Office 365 E5 o Microsoft 365 E5.

  Por ejemplo, su organización podría tener 3000 licencias de Office 365 E3 y 2500 de Microsoft 365 E5, con un total de 5500 licencias de productos aptos.

- Su organización necesita tener al menos 50 usuarios activos de Exchange Online mensuales.

- Cualquier rol con permisos de nivel de panel de Estado del servicio puede tener acceso a la supervisión de Exchange Online. Para más información, consulte [Cómo comprobar el estado del servicio de Microsoft 365](view-service-health.md).

## <a name="organization-level-scenarios"></a>Escenarios de nivel de organización

Con la supervisión de Exchange Online se admiten los siguientes escenarios:

- **Clientes de correo**: con la supervisión de Exchange, puede ver el estado de los siguientes clientes de correo electrónico basándose en la actividad de lectura de correo electrónico:

  - Versión de escritorio de Outlook
  - Outlook en la Web
  - Clientes de correo electrónico nativo de iOS y Android
  - Aplicación móvil de Outlook en iOS y Android
  - Cliente de Outlook para Mac
  - Abrir Outlook en la Web

   Para estos clientes, puede ver el número de usuarios activos en los últimos 30 minutos basándose en los usuarios que lean un correo electrónico, así como la cantidad de incidentes y avisos en el panel. Estos datos se comparan con el mismo intervalo de la semana anterior para ver si hay un problema.

   >[!Note]
   > El recuento de usuarios activos se mide por una única actividad, por ejemplo, cuando un usuario lee un correo electrónico. Solo se tienen en cuenta los últimos 30 minutos de actividad.

- **Conectividad de aplicaciones**: la conectividad estimada se basa en el porcentaje de conexiones sintéticas correctas entre los dispositivos de la organización y Exchange Online, y puede incluir problemas fuera del control de Microsoft. 

- **Autenticación básica y autenticación moderna**: número de usuarios validados correctamente en el servicio de Exchange Online.

- **Flujo de correo**: el número de mensajes entregados correctamente a un buzón sin retraso desde que el mensaje llegó a la red Microsoft 365.

  ![Un ejemplo de supervisión del estado de Exchange para la entrega de correo](../media/microsoft-365-exchange-monitoring/exchange-monitoring-scenario-example.png)

Para todos estos escenarios, los números clave son para los últimos 30 minutos en el panel principal. Las vistas detalladas de cada uno de estos escenarios muestran la tendencia en tiempo casi real durante siete días con un agregado de 30 minutos en comparación con la semana anterior.

## <a name="send-us-feedback"></a>Enviarnos comentarios

Hay dos formas de proporcionar comentarios:

- Usar la opción **Enviar comentarios** disponible en cada página del Centro de administración de Microsoft 365.

- Enviar comentarios usando el vínculo **¿Es útil esta publicación?** para un incidente o aviso específico.

![El vínculo "¿Es útil esta publicación?" para un incidente o aviso específico](../media/microsoft-365-exchange-monitoring/exchange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a>1. ¿Por qué no veo "Supervisión de Exchange Online" en Estado en el Centro de administración de Microsoft 365? 

En primer lugar, asegúrese de que ha habilitado el nuevo Centro de administración en la página **Inicio** del Centro de administración de Microsoft 365.

Después, asegúrese de que cumple los siguientes requisitos: 

- Su organización necesita tener al menos 5000 licencias de uno o varios de estos productos: Office 365 E3, Microsoft 365 E3, Office 365 E5 o Microsoft 365 E5. 

- Su organización necesita tener al menos 50 usuarios activos de Exchange Online mensuales.

Si el número de licencias de la organización es inferior a 5000 usuarios y los usuarios activos mensuales son menos de 50, no se habilitará la supervisión de Exchange Online hasta que se cumplan estos requisitos.

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a>2. El número de usuarios activos en el panel de control de cada cliente parece ser bajo. Tenemos muchas licencias activas asignadas a los usuarios. ¿Qué significa esto?

El recuento de usuarios activos que se muestra en la supervisión se basa en una ventana de 30 minutos donde los usuarios han realizado la actividad indicada en la característica. No debe confundirse con los números de uso. Para ver los números de uso, utilice los informes de actividad en el Centro de administración de Microsoft 365 (**Informes > Uso**).

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a>3. ¿Hay otros escenarios de supervisión para otros servicios, como Microsoft Teams y SharePoint?

Microsoft está integrando esta experiencia directamente en el panel de Estado del servicio en el Centro de administración de Microsoft 365. Esto ofrecerá oportunidades para que Microsoft extienda escenarios de supervisión a otros servicios, que se anunciarán cuando haya novedades para compartir.

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a>4. ¿Cuál es el plan para la disponibilidad general de esta experiencia?

Microsoft ha integrado la supervisión de Exchange Online directamente en el panel de **Estado del servicio** en el Centro de administración de Microsoft 365.

Con esta nueva experiencia integrada, el plan de Microsoft es recopilar sus comentarios y definir nuestro plan de disponibilidad general.

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a>5. ¿Es una característica gratuita (incluida) o de pago (extra)? 

Esta es una característica gratuita que está en versión preliminar y solo está disponible para los clientes que cumplen los requisitos de la pregunta 1. No hay una opción de pago para recibir este contenido.

#### <a name="6-how-do-i-provide-feedback"></a>6. ¿Cómo puedo proporcionar comentarios?

Para los comentarios generales, use el icono **Enviar comentarios** en la esquina inferior derecha de la página de supervisión de **Exchange Online**. 

Para los comentarios sobre incidentes o avisos use el vínculo **¿Es útil esta publicación?**.

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a>7. ¿Dónde están los datos instrumentados para los escenarios que muestran las tendencias de actividad?

Los datos se usan en el servicio de Exchange Online. Si se produce un error antes de que la solicitud llegue a Exchange Online o existe un error en Exchange Online, verá una caída en la señal de actividad.

#### <a name="8-are-there-any-privacy-concerns"></a>8. ¿Hay problemas de privacidad?

La supervisión se centra en los metadatos del servicio y no se supervisa el contenido del usuario.

## <a name="see-also"></a>Vea también

- [Cómo comprobar el estado del servicio de Microsoft 365](view-service-health.md) 
- [Límites de Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-storage-limits)
