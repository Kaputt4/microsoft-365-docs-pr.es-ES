---
title: Usar Microsoft Teams clases con Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrar Microsoft Teams clases con Canvas
ms.openlocfilehash: 50e4e8ef912a8f19f379bba29b328a5a27358b5c
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256908"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Usar Microsoft Teams clases con Canvas

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Microsoft Teams clases es una aplicación Learning Tools Interoperability (LTI) que ayuda a los profesores y alumnos a navegar fácilmente entre su sistema de administración de Learning (LMS) y Teams. Los usuarios pueden acceder a sus equipos de clase asociados con su curso directamente desde su LMS.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Administrador

Antes de administrar la integración de Microsoft Teams en Instructure Canvas, es importante que la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas sea aprobada por el administrador de Microsoft Office 365 de la institución en el inquilino de Microsoft Azure antes de completar la configuración de administración de Canvas.

1. Inicie sesión en Canvas.

2. Seleccione el **vínculo** Administrador en la navegación global y, a continuación, seleccione su cuenta.

3. En la navegación de administración, seleccione el **vínculo Configuración** y, a continuación, la **pestaña Integraciones.**

4. Habilite Microsoft Teams sincronización activando la alternancia.

   ![teams-sync](media/teams-sync.png)

5. Escriba el nombre del inquilino de Microsoft y el atributo de inicio de sesión.

   El atributo login se usará para asociar el usuario canvas con un Azure Active Directory usuario.

6. Seleccione **Actualizar Configuración** una vez que haya terminado.

7. Para aprobar el acceso a la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas, seleccione el vínculo Conceder acceso **al** espacio empresarial. Se le redirigirá al punto de conexión de consentimiento de administrador de la plataforma de identidad de Microsoft.

   ![permisos](media/permissions.png)

8. Seleccione **Aceptar**.

## <a name="canvas-admin"></a>Administrador de Canvas

Configure la integración Microsoft Teams LTI 1.3.

Como administrador de Canvas, tendrás que agregar la aplicación LTI de Microsoft Teams clases en tu entorno. Anote el id. de cliente de LTI para la aplicación.

 - Microsoft Teams : 170000000000570

1. Access **Admin settings**  >  **Apps**.

2. Selecciona **+ Aplicación** para agregar las Teams LTI.

   ![external-apps](media/external-apps.png)

3. Seleccione **Por identificador de cliente** para el tipo de configuración.

   ![agregar aplicación](media/add-app.png)

4. Escriba el id. de cliente proporcionado y, a continuación, **seleccione Enviar**.

   Observarás el nombre de la aplicación Microsoft Teams clases LTI para el identificador de cliente para confirmación.

5. Seleccione **Instalar**.

   La Microsoft Teams clases de aplicación LTI se agregará a la lista de aplicaciones externas.
