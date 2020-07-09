---
title: Crear y realizar un seguimiento de los vales de ServiceNow en el centro de seguridad de Microsoft 365
description: Obtenga información sobre cómo crear y realizar un seguimiento de vales en ServiceNow desde el centro de seguridad de Microsoft 365.
keywords: seguridad, Microsoft 365, M365, calificación segura, centro de seguridad, ServiceNow, billetes, tareas
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 48512cf2fff802509ebaa14ca69d3ca02908902e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45087938"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a>Crear y realizar un seguimiento de los vales de ServiceNow en el centro de seguridad de Microsoft 365

El [centro de seguridad de Microsoft 365](overview-security-center.md) se ha mejorado con la capacidad de crear y realizar un seguimiento de vales en ServiceNow de forma nativa. [Obtenga más información sobre ServiceNow](https://www.servicenow.com/)

En el centro de seguridad, los administradores de seguridad pueden enviar una acción de mejora de la [calificación segura de Microsoft](microsoft-secure-score.md) directamente a ServiceNow y crear un vale. Se pueden crear tíquets de administración de incidentes y de administración de cambios. A continuación, se puede realizar un seguimiento de ellos en la página de inicio del centro de seguridad y en ServiceNow.

- [**Información sobre los requisitos previos, el intercambio de datos y la solución de problemas**](tickets.md)
- **Administrar vales de ServiceNow en el centro de cumplimiento** (próximamente)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Conectar el centro de seguridad de Microsoft 365 a ServiceNow

Vaya a la página de inicio del centro de seguridad 365 de Microsoft para ver la tarjeta de conexión de ServiceNow.

![¿Usa ServiceNow?](../../media/do-you-use-servicenow-250.png)

Seleccione "conectarse a ServiceNow" para ir a la página de configuración de ServiceNow. Siga las instrucciones para autorizar la aplicación conector de 365 de Microsoft.

> [!NOTE]
> Antes de autorizar la conexión entre el centro de seguridad de Microsoft 365 y ServiceNow, asegúrese de usar el inicio de sesión de usuario y la contraseña de integración que creó en los pasos de instalación. No use sus credenciales personales.

Una vez que haya seguido las instrucciones y la autorización de la conexión, vea el estado de conexión en la página conexión del centro de seguridad 365 de Microsoft y en la experiencia de la aplicación conector de vales de Microsoft 365 de ServiceNow. Ahora ya está todo listo para empezar a crear tareas.

### <a name="troubleshooting"></a>Solución de problemas

Obtenga información sobre los errores comunes que puede encontrar en el proceso de conexión y cómo mitigarlos en la [sección de solución de problemas](tickets.md#troubleshooting).

## <a name="create-a-task-and-share-it-to-servicenow"></a>Crear una tarea y compartirla en ServiceNow

Una vez que la integración esté configurada, cree tareas de ServiceNow basadas en acciones específicas para la mejora de la calificación segura de Microsoft. Vaya a cualquier acción de mejora en puntuación segura en el portal del centro de seguridad 365 de Microsoft y seleccione el icono "compartir". Una de las opciones de lista desplegable es ServiceNow.

![Uso compartido de ServiceNow en calificación segura](../../media/servicenow-share.png)

Se genera una tarea en la que puede establecer la prioridad y editar el nombre, la descripción o la fecha de vencimiento. Una vez que se hayan rellenado todos los campos obligatorios, envíe la tarea a ServiceNow.

La tarea es visible en ServiceNow como una solicitud de cambio de configuración y seguridad de Microsoft 365.

## <a name="track-tickets"></a>Seguimiento de vales

Una vez que se han creado los vales de administración de cambios y la administración de cambios de ServiceNow, se muestran en las tarjetas de la página de inicio del centro de seguridad de Microsoft 365. Desde estas tarjetas, puede crear un vale, ver todos los vales o administrar la configuración de ServiceNow.

![Vales de administración de cambios de ServiceNow](../../media/change-management-375.png)  ![Vales de administración de incidentes de ServiceNow](../../media/incident-management-375.png)

Para volver a aprovisionar o administrar la integración de ServiceNow en el centro de seguridad de Microsoft 365, seleccione **administrar la configuración de servicenow** en una de las tarjetas. Desde allí, elimine la conexión de ServiceNow actual y personalice los nombres de los Estados de las incidencias.

Con los vales de ServiceNow visibles en el centro de seguridad de Microsoft 365, las tareas residen en un lugar en el que se puede realizar un seguimiento y actuar junto a otros elementos del panel de seguridad.

## <a name="resources"></a>Recursos

- [Información sobre los requisitos previos, el intercambio de datos y la solución de problemas](tickets.md)
- [Puntuación de seguridad de Microsoft](microsoft-secure-score.md)