---
title: Usar Microsoft Teams reuniones con Canvas
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
description: Integrar Microsoft Teams reuniones con Canvas
ms.openlocfilehash: dfa9bf10400900f879c806d6ea44bdb9b4b67a9c
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212467"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Usar Microsoft Teams reuniones con Canvas

Microsoft Teams reuniones es una aplicación de interoperabilidad de Learning Tools (LTI) que ayuda a los formadores y alumnos a navegar fácilmente entre su sistema de administración de Learning (LMS) y Teams. Los usuarios pueden acceder a sus equipos de clase asociados con su curso directamente desde su LMS.

## <a name="prerequisites-before-deployment"></a>Requisitos previos antes de la implementación

> [!NOTE]
> El LTI Teams meetings actual solo admite la sincronización de usuarios de Canvas con Microsoft Azure Active Directory (AAD) en un ámbito limitado. 
> - El inquilino debe tener una licencia de Microsoft Education.
> - Solo se puede usar un único espacio empresarial de Microsoft para asignar usuarios entre Canvas y Microsoft.
> - Tendrá que desactivar School Data Sync (SDS) antes de usar la clase Teams LTI para evitar la duplicación de grupos.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Administrador

Antes de administrar la integración de Microsoft Teams en Instructure Canvas, es importante que la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas sea aprobada por el administrador de Microsoft Office 365 de la institución en el inquilino de Microsoft Azure antes de completar la configuración de administración de Canvas.

1. Inicie sesión en Canvas.

2. Seleccione el **vínculo** Administrador en la navegación global y, a continuación, seleccione su cuenta.

3. En la navegación de administración, seleccione el **vínculo Configuración** y, a continuación, la **pestaña Integraciones.**

![Canvas Teams Sync Updated png.](https://user-images.githubusercontent.com/87142492/128552407-78cb28e9-47cf-4026-954d-12dc3553af6f.png)

4. Escriba el nombre del inquilino de Microsoft, el atributo de inicio de sesión, el sufijo de dominio y el atributo de búsqueda de AAD. Estos campos se usarán para hacer coincidir usuarios en Canvas con usuarios de Microsoft Azure Active Directory. 
   * El atributo Login es el atributo de usuario Canvas que se usa para la coincidencia.
   * El campo Sufijo es opcional y le permite especificar un dominio cuando no hay una asignación exacta entre los atributos canvas y los campos de Microsoft AAD. Por ejemplo, si el correo electrónico de Canvas es "name@example.edu" mientras el UPN de Microsoft AAD es "nombre", puede hacer coincidir a los usuarios si escribe "example.edu" en el campo sufijo.
   * El atributo de búsqueda de Active Directory es el campo del lado microsoft con el que coinciden los atributos canvas. Seleccione entre UPN, dirección de correo electrónico principal o el alias de correo electrónico.

5. Seleccione **Actualizar Configuración** una vez que haya terminado.

6. Para aprobar el acceso a la aplicación azure de **Microsoft-Teams-Sync-for-Canvas** de Canvas de Canvas, seleccione el vínculo Conceder acceso **al** espacio empresarial. Se le redirigirá al punto de conexión de consentimiento de administrador de la plataforma de identidad de Microsoft.

   ![permisos.](media/permissions.png)

7. Seleccione **Aceptar**. 

> [!NOTE]
> La sincronización es una funcionalidad administrada por el partner de LMS y se usa para sincronizar la pertenencia en un nivel de curso al equipo de Teams mediante las API de Microsoft graph. Esta es principalmente una funcionalidad que un profesor activa como true en un nivel de curso. Posteriormente, cualquier cambio de pertenencia realizado en el lado LMS para la adición o eliminación de los miembros se refleja mediante la sincronización implementada por el partner de LMS. Incluso antes de habilitar este proceso para un educador, el administrador del instituto educativo M365 permite a sus profesores acceder a la sincronización mediante el modal de permisos de sincronización que se encuentra a continuación. Estos permisos se conceden al partner de LMS para permitir a los profesores sincronizar la pertenencia entre el curso lms y Teams de clase.

8. Habilite la Microsoft Teams sincronización activando la alternancia.

   ![teams-sync.](media/teams-sync.png)

## <a name="canvas-admin"></a>Administrador de Canvas

Configure la integración Microsoft Teams LTI 1.3.

Como administrador de Canvas, tendrás que agregar la aplicación LTI Microsoft Teams reuniones en tu entorno. Anote el id. de cliente de LTI para la aplicación.

 - Microsoft Teams reuniones: 170000000000703

1. Access **Admin settings**  >  **Apps**.

2. Selecciona **+ Aplicación** para agregar las Teams LTI.

   ![external-apps.](media/external-apps.png)

3. Seleccione **Por identificador de cliente** para el tipo de configuración.

   ![agregar aplicación.](media/add-app.png)

4. Escriba el id. de cliente proporcionado y, a continuación, **seleccione Enviar**.

   Verás el nombre de la aplicación LTI Microsoft Teams reuniones para el identificador de cliente para confirmación.

5. Haga clic en **Instalar**.

   La Microsoft Teams LTI de reuniones de reuniones se agregará a la lista de aplicaciones externas.

6. Para habilitar la aplicación, vaya a las claves de desarrollador de la cuenta de administrador de Canvas, seleccione heredado y active la opción "activar" para Microsoft Teams reuniones.
   
## <a name="enable-for-canvas-courses"></a>Habilitar cursos de Canvas

Para poder usar el LTI dentro de un curso, un instructor del curso canvas debe habilitar la sincronización de integraciones. Cada curso debe estar habilitado por un instructor para que se cree Teams correspondiente; no hay ningún mecanismo global para la Teams creación. Esto está diseñado por precaución para evitar que se cree Teams no deseados.

Consulte a los instructores la documentación [del](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) profesor para habilitar el LTI para cada curso y finalizar la configuración de integración.
