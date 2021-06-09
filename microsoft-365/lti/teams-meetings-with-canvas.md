---
title: Usar Microsoft Teams reuniones con Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrar Microsoft Teams reuniones con Canvas
ms.openlocfilehash: 8ccf1c1d45d38fa4a92b556146744a2c17cd5105
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821924"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Usar Microsoft Teams reuniones con Canvas

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Microsoft Teams reuniones es una aplicación de interoperabilidad de herramientas de aprendizaje (LTI) que ayuda a los formadores y alumnos a navegar fácilmente entre su Sistema de administración de aprendizaje (LMS) y Teams. Los usuarios pueden acceder a sus equipos de clase asociados con su curso directamente desde su LMS.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Administrador

Antes de administrar la integración de Microsoft Teams en Instructure Canvas, es importante que la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas sea aprobada por el administrador de Microsoft Office 365 de la institución en el inquilino de Microsoft Azure antes de completar la configuración de administración de Canvas.

1. Inicie sesión en Canvas.
 
2. Seleccione el **vínculo** Administrador en la navegación global y, a continuación, seleccione su cuenta.

3. En la navegación de administración, seleccione el **vínculo Configuración** y, a continuación, la **pestaña Integraciones.** 

4. Escriba el nombre del inquilino de Microsoft y el atributo de inicio de sesión. 

   El atributo login se usará para asociar el usuario canvas con un Azure Active Directory usuario. 

5. Seleccione **Actualizar Configuración** una vez que haya terminado.

6. Para aprobar el acceso a la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas, seleccione el vínculo Conceder acceso **al** espacio empresarial. Se le redirigirá al punto de conexión de consentimiento de administrador de la plataforma de identidad de Microsoft.

   ![permisos](media/permissions.png)

7. Seleccione **Aceptar**.
 
8. Habilite la Microsoft Teams sincronización activando la alternancia.

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a>Administrador de Canvas

Configure la integración Microsoft Teams LTI 1.3.

Como administrador de Canvas, tendrás que agregar la aplicación LTI Microsoft Teams reuniones en tu entorno. Anote el id. de cliente de LTI para la aplicación.

 - Microsoft Teams - 170000000000703

1. Access **Admin settings**  >  **Apps**.

2. Selecciona **+ Aplicación** para agregar las Teams LTI. 
 
   ![external-apps](media/external-apps.png)

3. Seleccione **Por identificador de cliente** para el tipo de configuración.

   ![agregar aplicación](media/add-app.png)

4. Escriba el id. de cliente proporcionado y, a continuación, **seleccione Enviar**.
   
   Verás el nombre de la aplicación LTI Microsoft Teams reuniones para el identificador de cliente para confirmación. 

5. Seleccione **Instalar**.

   La Microsoft Teams LTI de reuniones de reuniones se agregará a la lista de aplicaciones externas.
