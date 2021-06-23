---
title: Usar Microsoft Teams clases con Blackboard
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
description: Integrar Microsoft Teams clases en el sistema Learning administración
ms.openlocfilehash: 940c5c695d602ddce6ea49b1f914f2345fbeb7e5
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083248"
---
# <a name="use-microsoft-teams-classes-with-blackboard"></a>Usar Microsoft Teams clases con Blackboard

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Microsoft Teams clases es una aplicación Learning Tools Interoperability (LTI) que ayuda a los profesores y alumnos a navegar fácilmente entre su sistema de administración de Learning (LMS) y Teams. Los usuarios pueden acceder a sus equipos de clase asociados con su curso directamente desde su LMS.

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a>Aprobar la aplicación en el Microsoft Azure inquilino

El administrador de Microsoft Office 365 y el administrador de Blackboard Learn Ultra completan las siguientes tareas.

Antes de administrar la integración en Blackboard Learn Ultra, el administrador de Microsoft Office 365 debe aprobar el Teams de **MSFT** de Blackboard para la aplicación Learn Ultra Azure para el inquilino Microsoft Azure la entidad.

1. Busque su id. de inquilino de Microsoft. Vea [cómo encontrar el espacio empresarial](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).

2. Redirija el extremo de consentimiento de administrador de la plataforma de identidad de Microsoft según el siguiente ejemplo:

   `https://login.microsoftonline.com/{tenant}/adminconsent?client_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > Reemplace {tenant} por el identificador de inquilino de Microsoft de su organización.

## <a name="register-the-integration-apps"></a>Registrar las aplicaciones de integración

Como administrador de Blackboard Learn Ultra, deberá registrar 2 aplicaciones de integración de LTI 1.3 en su entorno de prueba:

- La clase De Aprendizaje de Blackboard Teams integración para admitir la sincronización de listas

- La Microsoft Teams LTI de grupo de clase

1. Anote los siguientes IDs de cliente LTI para ambas aplicaciones:

    - Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41

    - Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89

2. Accede al Panel de administración y, en **Integraciones,** busca los proveedores de herramientas de LTI.

   ![este es el cuadro de diálogo Proveedor de herramientas de LTI que muestra una lista de proveedores](../media/lti-media/lti-tool-providers.png)

3. Seleccione **Registrar LTI1.3/Advantage Tool**.

4. Escriba el primero de los IDs de cliente proporcionados (Ya sea Blackboard o Microsoft) y seleccione **Enviar**.

5. Revise la configuración rellenada previamente y asegúrese de que el estado de la herramienta esté marcado como aprobado.

6. Desplácese hasta la parte inferior y, a continuación, **seleccione Enviar**.

7. Repita los pasos anteriores para registrar la segunda de las aplicaciones de LTI en su entorno.

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a>Configurar la aplicación REST y el uso compartido de recursos entre orígenes

El administrador de Blackboard Learn Ultra también tendrá que configurar la aplicación REST y la configuración de uso compartido de recursos entre orígenes.

Complete lo siguiente para configurar la aplicación REST

1. Obtenga acceso a Herramientas de administración de Learn y, a continuación, seleccione **Integraciones de API de REST** en la sección **Integraciones.**

2. Seleccione **Crear integraciones** y escriba el mismo id. de aplicación/cliente que escribió para la herramienta LTI de Teams clase de Aprendizaje de Blackboard.

3. Escriba el usuario de Learn (podría ser su propio nombre de usuario de administrador de Learn) o **seleccione Examinar** para buscar.

4. Seleccione **Sí para** acceso de usuario **final**.

5. Seleccione **Sí** para **Autorizado para actuar como usuario**

6. Seleccione **Enviar una** vez completada.

## <a name="set-up-cross-origin-resource-sharing"></a>Configurar el uso compartido de recursos entre orígenes

1. Obtenga acceso a herramientas de administración de Learn y seleccione **Uso** compartido de recursos entre orígenes en la **sección Integraciones.**

2. Seleccione **Crear configuración**.

3. Escriba `https://bb-ms-teams-ultra-ext.api.blackboard.com` en el origen.

4. Agregue la palabra **Autorización en** los **encabezados permitidos**.

5. Establezca **Disponible** en **Sí**.

6. Seleccione **Enviar una** vez completada.

## <a name="enable-class-teams-in-blackboard-learn"></a>Habilitar la clase Teams en Blackboard Learn

Una vez habilitadas las herramientas de LTI, el siguiente paso será configurar la integración de Microsoft Class Teams desde su propio Microsoft Office 365 inquilino. Para ello, siga estos pasos como administrador de Blackboard Learn Ultra.

1. En **Learn Admin** Tools and  >  **Utilities**, seleccione Microsoft Teams Integration **Admin**.

   ![el cuadro de diálogo herramientas y utilidades con una lista de herramientas disponibles](../media/lti-media/tools-utilities.png)

2. Active la casilla de verificación **Habilitar Microsoft Teams**.

3. Escriba su identificador de inquilino como se hace referencia en la sección de Administración de Microsoft O365

 > [!NOTE]
 > No podrás guardar la configuración hasta que la aplicación haya sido aprobada por el administrador de O365. Consulta [Aprobar la aplicación en Microsoft Azure inquilino](#approve-the-app-in-the-microsoft-azure-tenant).

4. Cuando el administrador global de O365 haya aprobado la aplicación Teams Desempresa de Blackboard en su inquilino de Microsoft, seleccione **Enviar**.
