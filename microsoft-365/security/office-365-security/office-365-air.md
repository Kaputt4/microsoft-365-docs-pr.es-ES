---
title: Investigar y responder automáticamente ante amenazas en Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Empiece a usar la investigación automatizada y las capacidades de respuesta en Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: d45141ce671a4615cb4fd550e36bc7215cd38d51
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088319"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a>Investigar y responder automáticamente ante amenazas en Office 365

## <a name="overview"></a>Información general

Según su suscripción, la [protección contra amenazas avanzada de Office 365](office-365-atp.md) puede incluir capacidades de investigación y respuesta automáticas (Air) que pueden ahorrar tiempo y esfuerzo en el equipo de operaciones de seguridad para tratar las alertas y las amenazas.

- Para empezar a usar las capacidades de investigación y respuesta automatizadas en Office 365, use este artículo. 
- Para obtener información general sobre cómo funciona, consulte la [investigación y la respuesta automatizadas en Office 365](automated-investigation-response-office.md).

> [!TIP]
> ¿Tiene Microsoft 365 E5 o Microsoft 365 E3 junto con la protección de la identidad y contra amenazas? Considere la posibilidad de probar la [investigación y respuesta automatizadas (Air) en la protección contra amenazas de Microsoft](../mtp/mtp-autoir.md).

Con las capacidades de investigación y respuesta automatizadas, cuando se desencadenan determinadas alertas, se inician una o más guías de seguridad y se inicia el proceso de investigación automatizada. Durante y después de un proceso de investigación automatizado, su equipo de seguridad puede hacer lo siguiente:

- [Ver los detalles de una investigación](#view-details-of-an-investigation)
- [Revisión y aprobación de acciones como resultado de una investigación](#review-and-approve-actions) 
- [Ver los detalles de una alerta relacionada con una investigación](#view-details-about-an-alert-related-to-an-investigation)

> [!IMPORTANT]
> Para llevar a cabo las tareas descritas en este artículo, debe tener asignados los permisos adecuados. Consulte [permisos necesarios para usar la funcionalidad de Air](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities).

## <a name="view-details-of-an-investigation"></a>Ver los detalles de una investigación

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión. Esto le llevará al centro de seguridad & cumplimiento.

2. Realice una de las acciones siguientes:

    - Vaya al **** > **Panel**de administración de amenazas. Esto le llevará al [Panel de seguridad](security-dashboard.md). Los widgets de AIR aparecen en la parte superior del [Panel de seguridad](security-dashboard.md). Seleccione un widget, como un **Resumen de investigaciones**.

    - Vaya a **** > **investigaciones**de administración de amenazas. 

    Cualquiera de estos métodos le lleva a una lista de investigaciones.

    ![Página principal de investigación para AIR](../../media/air-maininvestigationpage.png) 

3. En la lista de investigaciones, seleccione un elemento en la columna **ID** . Se abrirá la página Detalles de la investigación, empezando por el gráfico de investigación en la vista.

    ![Página de gráfico de investigación de aire](../../media/air-investigationgraphpage.png)

4. Use las distintas pestañas para obtener más información sobre la investigación.

## <a name="review-and-approve-actions"></a>Revisión y aprobación de acciones

En Office 365, las investigaciones automatizadas suelen dar como resultado una o varias acciones recomendadas. Sin embargo, no se lleva a cabo ninguna acción hasta que la aprueba el equipo de operaciones de seguridad. Use el siguiente procedimiento para revisar y aprobar acciones.

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión. 

2. Vaya a **** > **investigaciones**de administración de amenazas.

3. En la lista de investigaciones, seleccione un elemento en la columna **ID** . 

3. En la vista detalles de la investigación, seleccione la ficha **acciones** . Aquí se enumeran las acciones pendientes de aprobación.

4. Seleccione un elemento de la lista.

5. Seleccione **aprobar** para realizar la acción recomendada (o **rechazar** para cerrar la investigación sin emprender ninguna acción).

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Ver los detalles de una alerta relacionada con una investigación

Ciertos tipos de alertas desencadenan la investigación automática en Office 365. Para obtener más información, vea [alertas](automated-investigation-response-office.md#alerts). Use el siguiente procedimiento para ver los detalles de una alerta asociada a una investigación automatizada.

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión. Esto le llevará al centro de seguridad & cumplimiento.

2. Vaya a **** > **investigaciones**de administración de amenazas.

3. En la lista de investigaciones, seleccione un elemento en la columna **ID** . 

4. Con los detalles de una investigación abierta, seleccione la pestaña **alertas** . Aquí se enumeran las alertas que desencadenaron la investigación.

5. Seleccione un elemento de la lista. Se abre un control flotante, con detalles sobre la alerta y vínculos a acciones e información adicionales.

6. Revise la información en el control flotante y, en función de la alerta en particular, realice una acción, como **resolver**, **suprimir**o **notificar a los usuarios**. 

    - **Resolve** equivale a cerrar una alerta
    
    - **Suprimir** hace que una directiva no desencadene alertas durante un período de tiempo especificado
    
    - **Notify users** inicia un correo electrónico con las direcciones de correo electrónico de los usuarios que ya se han especificado y permite que el equipo de operaciones de seguridad escriba un mensaje para esos usuarios. (Es similar a enviar un mensaje a los destinatarios mediante el [Explorador de amenazas](threat-explorer.md)).  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Usar la API de actividad de administración de Office 365 para soluciones de informes personalizadas o de terceros

Si su organización usa una solución de informes personalizada o de terceros, puede ver información sobre las investigaciones automatizadas en esa solución mediante la API de actividad de administración 365 de Office.

Use los siguientes recursos para configurar esto:

|Resource  |Descripción  |
|---------|---------|
|[Información general de las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Office 365 y Azure Active Directory.         |
|[Introducción a las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |La API de administración 365 de Office usa Azure AD para proporcionar servicios de autenticación para que la aplicación tenga acceso a los datos de Office 365. Siga los pasos de este artículo para configurarlo.          |
|[Referencia de las API de Actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |Puede usar la API de actividad de administración de Office 365 para recuperar información sobre las acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Office 365 y Azure AD. Lea este artículo para obtener más información sobre cómo funciona.        |
|[Esquema de la API de Actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |Obtenga información general sobre el [esquema común](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) y el [esquema de investigación y respuesta de ATP y la investigación de amenazas de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para obtener información sobre los tipos de datos específicos disponibles a través de la API de actividad de administración de Office 365.         |

## <a name="next-steps"></a>Pasos siguientes

- [Descubra cómo obtener acceso a AIR y ver los permisos necesarios](automated-investigation-response-office.md#how-to-get-air)
- [Más información acerca de las alertas](../../compliance/alert-policies.md)
- [Buscar y investigar manualmente el correo electrónico malintencionado que se entregó en Office 365](investigate-malicious-email-that-was-delivered.md)
- [Obtener información sobre AIR en ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Visite el plan de desarrollo de Microsoft 365 para ver lo que estará próximamente y que se implementará](https://www.microsoft.com/microsoft-365/roadmap?filters=)
