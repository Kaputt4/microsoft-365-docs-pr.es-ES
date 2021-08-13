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
ms.openlocfilehash: 7743e7064bf31d87513c8c274f0ef8d0f70e7e8b9f97f530a2ad2f1826dd0542
ms.sourcegitcommit: 9410944dab4a34c38ee420e66b14c58ca037f31c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2021
ms.locfileid: "57803625"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Usar Microsoft Teams clases con Canvas

Microsoft Teams clases es una aplicación Learning Tools Interoperability (LTI) que ayuda a los profesores y alumnos a navegar fácilmente entre su sistema de administración de Learning (LMS) y Teams. Los usuarios pueden acceder a sus equipos de clase asociados con su curso directamente desde su LMS.

## <a name="prerequisites-before-deployment"></a>Requisitos previos antes de la implementación

> [!NOTE]
> La clase actual Teams LTI solo admite la sincronización de usuarios de Canvas con Microsoft Azure Active Directory (AAD) en un ámbito limitado. 
> - El inquilino debe tener una licencia de Microsoft Education.
> - Solo se puede usar un único espacio empresarial de Microsoft para asignar usuarios entre Canvas y Microsoft.
> - Tendrá que desactivar SDS antes de usar la clase Teams LTI para evitar la duplicación de grupos.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Administrador

Antes de administrar la integración de Microsoft Teams en Instructure Canvas, es importante que la aplicación Azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas sea aprobada por el administrador de Microsoft Office 365 de la institución en el inquilino de Microsoft Azure antes de completar la configuración de administración de Canvas.

1. Inicie sesión en Canvas.

2. Seleccione el **vínculo** Administrador en la navegación global y, a continuación, seleccione su cuenta.

3. En la navegación de administración, seleccione el **vínculo Configuración** y, a continuación, la **pestaña Integraciones.**

4. Habilite Microsoft Teams sincronización activando la alternancia.
   
   ![Canvas Teams Sync Updated png](https://user-images.githubusercontent.com/87142492/128225881-abdfc52d-dc9e-48ad-aec5-f6617c6436f3.png)

5. Escriba el nombre del inquilino de Microsoft, el atributo de inicio de sesión, el sufijo de dominio y el atributo de búsqueda de AAD.

   Estos campos se usarán para hacer coincidir usuarios en Canvas con usuarios de Microsoft Azure Active Directory. 
   * El atributo Login es el atributo de usuario Canvas que se usa para la coincidencia.
   * El campo Sufijo es opcional y le permite especificar un dominio cuando no hay una asignación exacta entre los atributos canvas y los campos de Microsoft AAD. Por ejemplo, si el correo electrónico de Canvas es "name@example.edu" mientras el UPN de Microsoft AAD es "nombre", puede hacer coincidir a los usuarios si escribe "example.edu" en el campo sufijo.
   * El atributo de búsqueda de Active Directory es el campo del lado microsoft con el que coinciden los atributos canvas. Seleccione entre UPN, dirección de correo electrónico principal o el alias de correo electrónico.

6. Seleccione **Actualizar Configuración** una vez que haya terminado.

7. Para aprobar el acceso a la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas, seleccione el vínculo Conceder acceso **al** espacio empresarial. Se le redirigirá al punto de conexión de consentimiento de administrador de la plataforma de identidad de Microsoft.

   ![permissions](media/permissions.png)

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
