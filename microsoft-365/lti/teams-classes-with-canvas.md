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
ms.openlocfilehash: 8091d84e1d0f26c820979450001a1e0c9ad1cdec775ac9e34317f69c24bd2df6
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53898712"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Usar Microsoft Teams clases con Canvas

Microsoft Teams clases es una aplicación Learning Tools Interoperability (LTI) que ayuda a los profesores y alumnos a navegar fácilmente entre su sistema de administración de Learning (LMS) y Teams. Los usuarios pueden acceder a sus equipos de clase asociados con su curso directamente desde su LMS.

## <a name="prerequisites-before-deployment"></a>Requisitos previos antes de la implementación

> [!NOTE]
> La clase actual Teams LTI solo admite la sincronización de usuarios de Canvas con Microsoft Azure Active Directory (AAD) en un ámbito limitado. 
> - El inquilino debe tener una coincidencia exacta entre un campo canvas (correo electrónico, id. de usuario o id. de SIS) y el UPN en Microsoft AAD. Estamos trabajando para ampliar la flexibilidad a la funcionalidad de sincronización, pero mientras tanto, los usuarios de Canvas que no coincidan con un UPN en AAD no se agregarán a la clase Teams sincronizada con Canvas. 
> - Solo se puede usar un único espacio empresarial de Microsoft para asignar usuarios entre Canvas y Microsoft.
> - Tendrá que desactivar SDS antes de usar la clase Teams LTI para evitar la duplicación de grupos.

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

Como administrador de Canvas, tendrás que agregar la aplicación LTI de Microsoft Teams clases en tu entorno. Accede a la descripción de la clave de desarrollador en la cuenta principal, cambia a las claves heredadas y habilita la Teams LTI. Anote el id. de cliente de LTI para la aplicación.

 - Microsoft Teams clases de 170000000000570

1. Access **Admin settings**  >  **Apps**.

2. Selecciona **+ Aplicación** para agregar las Teams LTI.

   ![external-apps](media/external-apps.png)

3. Seleccione **Por identificador de cliente** para el tipo de configuración.

   ![agregar aplicación](media/add-app.png)

4. Escriba el id. de cliente proporcionado y, a continuación, **seleccione Enviar**.

   Observarás el nombre de la aplicación Microsoft Teams clases LTI para el identificador de cliente para confirmación.

5. Seleccione **Instalar**.

   La Microsoft Teams clases de aplicación LTI se agregará a la lista de aplicaciones externas.
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a>Habilitar la aplicación LTI para cursos de Canvas

Para usar la aplicación LTI dentro de un curso, un instructor del curso canvas debe habilitar la sincronización de integraciones. Cada curso debe estar habilitado por un instructor para que se cree un equipo correspondiente; no hay ningún mecanismo global para la creación de equipos. Esto está diseñado como una medida de precaución para evitar que se creen equipos no deseados.

Consulte la documentación [](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) del profesor para habilitar la aplicación LTI para cada curso y completar la configuración de integración.
