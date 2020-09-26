---
title: Puntuación de productividad de Microsoft-privacidad
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Cómo se protege la privacidad con la puntuación de productividad.
ms.openlocfilehash: 799d532ca1f0abd5fa6234052d4875a79d629601
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48287331"
---
# <a name="privacy-controls-for-productivity-score"></a>Controles de privacidad para la puntuación de productividad

La puntuación de productividad ayuda a las organizaciones a transformar cómo se realiza el trabajo con información sobre cómo los usuarios usan Microsoft 365 y las experiencias tecnológicas que los admiten. La puntuación refleja el rendimiento de su organización&#39;s con las medidas de experiencia de empleado y tecnología, y compara su puntuación con organizaciones como la suya. Para obtener más información, consulte el tema de [información general sobre la puntuación de productividad](productivity-score.md) .

Su privacidad es importante para nosotros y puede ver [aquí](https://privacy.microsoft.com/privacystatement)la declaración de privacidad de Microsoft. En la puntuación de productividad, hay información vital que proporcionamos sobre cómo funcionan las personas de su organización. Por lo tanto, también estamos orientados a proporcionar controles para asegurarse de que la información sea accionable de una forma significativa sin poner en peligro la confianza que se pone en la misma.

Proporcionamos los siguientes controles para permitir un tratamiento más seguro de los datos:

- Roles de administrador flexibles para controlar quién puede ver la información en la puntuación de productividad.
- Anonymization de métricas de nivel de usuario.
- Capacidad para dejar de participar en la experiencia de los empleados.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Roles de administrador flexibles para controlar quién puede ver la información en la puntuación de productividad

Para ver toda la experiencia de puntuación de productividad con un rol de administrador, incluidos los detalles de nivel de inquilino y los detalles de nivel de usuario, su rol debe ser uno de los siguientes:

- Administrador global
- Administradores de Exchange
- Administrador de SharePoint
- Administrador de Skype Empresarial
- Administrador de Teams
- Lector global
- Lector de informes

Para invitar a personas responsables de la administración y adopción de cambios, pero que no son administradores de TI en la experiencia, a la vez que les dan acceso a la experiencia completa, incluidos los detalles de nivel de inquilino y los detalles de nivel de usuario, puede darles el rol lector de informes.

Dentro de la experiencia de los empleados, proporcionamos detalles de actividad por nivel de usuario en formato de cuadrícula para cada página de detalles de categoría. Como este nivel de detalle no es adecuado para todos los posibles visitantes de la puntuación de productividad, hemos creado un rol personalizado dentro de Azure AD – función lector de informes de Resumen de uso, para permitir el acceso a un conjunto más amplio de visitantes dentro de su organización solo para las métricas agregadas y no detalles por nivel dentro de la experiencia.

:::image type="content" source="../../media/communicationspage.jpg" alt-text="Página comunicaciones en los informes de productividad.":::

## <a name="anonymization-of-user-level-metrics"></a>Anonymization de métricas de nivel de usuario

Para hacer anónimos los datos que se recopilan para todos los informes, debe ser un administrador global. Esto ocultará la información identificable como nombres de usuario, grupo y sitio en todos los informes, incluida la puntuación de productividad y el uso de 365 de Microsoft.

1. En el centro de administración, vaya a configuración **de la**   >   **organización** y, en la ficha **servicios** , elija **informes**.
2. Seleccione  **informes** y, a continuación, elija  **Mostrar identificadores anónimos para los nombres de usuario, grupo y sitio en informes de uso y puntuación de productividad**. Esta configuración se aplica tanto a los informes de uso como a la aplicación de plantilla.
3. Seleccione  **Guardar cambios**.

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="Hacer que la información de usuario sea anónima para los informes.":::

## <a name="capability-to-opt-out-of-employee-experience"></a>Capacidad para dejar de participar en la experiencia de los empleados

También proporcionaremos la capacidad de dejar de participar en el área de experiencia de los empleados sobre la puntuación de productividad en general Availability. Al activar esta opción, los usuarios de la Organización podrán ver estas métricas y quitar la organización de los cálculos relacionados con las categorías de comunicación, las reuniones, el trabajo en equipo, la colaboración y la movilidad del contenido.

1. En el centro de administración, vaya a configuración **de la**   >   **organización** y, en la ficha **servicios** , elija **informes**.
2. Seleccione  **informes** y, a continuación, desactive la casilla que dice  **compartir los datos de su organización&#39;s con puntuación de productividad**información sobre la experiencia de los empleados. Para comprender cómo modificar la configuración de uso compartido de datos para el análisis de extremos en Intune Configuration Manager, haga clic en **más información**.
3. Seleccione  **Guardar cambios**.

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="Página de configuración de la organización en la que puede rechazar la experiencia de los empleados.":::