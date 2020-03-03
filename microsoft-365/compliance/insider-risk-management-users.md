---
title: Usuarios de administración de riesgos de Insider
description: Obtenga información sobre los usuarios de administración de riesgos de Insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos de Insider, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: f499cacd0ec63f9a192e2773b3604473d2153545
ms.sourcegitcommit: 9d6f9fd271e83c00e92a5e0247fcc51fc2070c3c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42370499"
---
# <a name="insider-risk-management-users"></a>Usuarios de administración de riesgos de Insider

Los usuarios de administración de riesgos de Insider son empleados de su organización que están incluidos en una o varias directivas de administración de riesgos de Insider. Use el **Panel usuarios** para revisar rápidamente la información de riesgos de los empleados y agregar un empleado a una directiva de administración de riesgos de Insider existente. Cada usuario incluido en una directiva de administración de riesgos de Insider tiene la siguiente información que se muestra en el **Panel de usuarios**:

- **Users**: el nombre de usuario de un usuario.
- **Nivel de riesgo**: el nivel de riesgo calculado actual del usuario. Esta puntuación se calcula cada 24 horas y usa los resultados de riesgo de alertas de todas las alertas activas asociadas al usuario.
- **Alertas activas**: el número de alertas activas para todas las directivas.
- **Infracciones confirmadas**: el número de casos resueltos como *infracción de la Directiva confirmada* para el usuario.
- **Caso**: el caso activo actual para el usuario.

![Panel de usuarios de administración de riesgos de Insider](../media/insider-risk-users-dashboard.png)

>[!NOTE]
>El número de usuarios que se muestran en el panel de usuario puede verse limitado en algunos casos, según el volumen de las alertas activas y las directivas coincidentes. Los usuarios con alertas activas se muestran cuando se generan las alertas, y es posible que haya casos raros de que se alcance el número máximo de usuarios mostrados. Si esto ocurre, los usuarios con alertas activas que no se muestran se agregarán al panel de usuario, ya que las alertas de usuario existentes se evaluarán.

## <a name="view-user-details"></a>Ver detalles del usuario

Para ver más detalles sobre la actividad de riesgos para un usuario, abra el panel de detalles del usuario haciendo doble clic en un usuario en el **Panel de usuarios**. En el panel de detalles, puede ver la siguiente información:

- Ficha **Perfil de usuario**
    - **Nombre y título**: el nombre y el título de la posición del usuario.
    - **Correo electrónico del usuario**: la dirección de correo electrónico del usuario.
    - **Alias**: el alias de red del usuario.
    - **Organización o departamento**: la organización o el Departamento del usuario.

- Ficha **actividad del usuario**
    - **Historial de la actividad reciente de los usuarios**: enumera los eventos de desencadenamiento de directivas y los indicadores de riesgos para las actividades de usuario. Un evento desencadenante puede ser la aceptación de una fecha de retirada o la fecha del último trabajo programado para el empleado. Los indicadores de riesgo son actividades que se determinan para tener un elemento de riesgo y que coinciden con las directivas en las que el usuario está incluido. Los eventos y las actividades de riesgo se muestran con el elemento más reciente enumerado primero.

## <a name="add-a-user-to-a-policy"></a>Agregar un usuario a una directiva

Para agregar un usuario a una directiva de administración de riesgos de Insider, use el Asistente para nueva Directiva o la pestaña **usuarios** de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365.

Complete los siguientes pasos para agregar un usuario a una directiva de riesgos de Insider existente:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **usuarios** .
2. Seleccione **Agregar un usuario a una directiva** en la barra de herramientas.
3. En el cuadro de diálogo **Agregar un nuevo usuario** , empiece a escribir un nombre de usuario en el campo **usuario** . Seleccione el usuario que desea agregar a una directiva.
4. Seleccione la flecha desplegable del campo de **Directiva** para mostrar las directivas de administración de riesgos de Insider configuradas. Seleccione la Directiva a la que desea agregar el usuario.
5. Use el control deslizante de la **ventana de activación** para definir el tiempo que la Directiva está activa para este usuario y se desencadena cuando el usuario realiza la primera actividad que coincide con la Directiva. El intervalo para la ventana de supervisión es de 5 a 30 días.
6. Seleccione **Agregar** y **confirme** para agregar el usuario a la Directiva.
