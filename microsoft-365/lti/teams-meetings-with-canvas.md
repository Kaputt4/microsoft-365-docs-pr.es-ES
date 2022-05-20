---
title: Uso de reuniones Microsoft Teams con Canvas
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: Integración de reuniones Microsoft Teams con Canvas
ms.openlocfilehash: a81b8c7da014ba4ded9e4a2e3cfd6b38509ae2db
ms.sourcegitcommit: b5529afa84f7dde0a89b1e08aeaf6a3a15cd7679
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2022
ms.locfileid: "65599621"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Uso de reuniones Microsoft Teams con Canvas

Microsoft Teams reuniones es una aplicación de interoperabilidad de herramientas de Learning (LTI) que ayuda a educadores y alumnos a navegar fácilmente entre su sistema de administración de Learning (LMS) y Teams. Los usuarios pueden acceder a sus equipos de clase asociados a su curso directamente desde su LMS.

## <a name="prerequisites-before-deployment"></a>Requisitos previos antes de la implementación

> [!NOTE]
> El LTI de reuniones de Teams actual solo admite la sincronización de usuarios de Canvas con Microsoft Azure Active Directory (AAD) en un ámbito limitado.
>
> - El inquilino debe tener una licencia de Microsoft Education.
> - Solo se puede usar un único inquilino de Microsoft para asignar usuarios entre Canvas y Microsoft.
> - Tendrá que desactivar School Data Sync (SDS) antes de usar la clase Teams LTI para evitar la duplicación de grupos.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Admin

Antes de administrar la integración de Microsoft Teams en Instructure Canvas, es importante que la aplicación de Azure **Microsoft-Teams-Sync-for-Canvas** de Canvas sea aprobada por el administrador de Microsoft Office 365 de la institución en el inquilino de Microsoft Azure antes de completar la configuración del administrador de Canvas.

1. Inicie sesión en Canvas.

2. Seleccione el vínculo **Admin** en la navegación global y, a continuación, seleccione su cuenta.

3. En la navegación del administrador, seleccione el vínculo **Configuración** y, a continuación, la pestaña **Integraciones**.

   ![Canvas Teams Sync Png actualizado.](https://user-images.githubusercontent.com/87142492/128552407-78cb28e9-47cf-4026-954d-12dc3553af6f.png)

4. Escriba el nombre del inquilino de Microsoft, el atributo de inicio de sesión, el sufijo de dominio y el atributo de búsqueda de AAD. Estos campos se usarán para buscar coincidencias entre los usuarios de Canvas con los usuarios de Microsoft Azure Active Directory.
   - El atributo Login es el atributo de usuario de Canvas utilizado para la coincidencia.
   - El campo Sufijo es opcional y le permite especificar un dominio cuando no hay una asignación exacta entre los atributos de Canvas y los campos de Microsoft AAD. Por ejemplo, si el correo electrónico de Canvas es "name@example.edu" mientras el UPN de Microsoft AAD es "name", puede hacer coincidir a los usuarios escribiendo "example.edu" en el campo sufijo.
   - El atributo de búsqueda de Active Directory es el campo del lado de Microsoft con el que coinciden los atributos de Canvas. Seleccione entre UPN, dirección de correo electrónico principal o el alias de correo electrónico.

5. Seleccione **Actualizar Configuración** una vez que haya terminado.

6. Para aprobar el acceso a la aplicación de Azure **Microsoft-Teams-Sync-for-Canvas de** Canvas, seleccione el vínculo **Conceder acceso al inquilino**. Se le redirigirá al punto de conexión de consentimiento de Microsoft Identity Platform Admin.

   ![Permisos.](media/permissions.png)

7. Seleccione **Aceptar**.

   > [!NOTE]
   > La sincronización es una funcionalidad administrada por el asociado de LMS y se usa para sincronizar la pertenencia en un nivel de curso al equipo de Teams mediante las API de Microsoft Graph. Se trata principalmente de una funcionalidad que un educador activa como verdadera en un nivel de curso. Posteriormente, cualquier cambio de pertenencia realizado en LMS para la adición o eliminación de los miembros se refleja mediante la sincronización implementada por el asociado de LMS. Incluso antes de habilitar este proceso para un educador, el administrador del instituto de educación M365 permite a sus educadores acceder a la sincronización mediante el modal de permisos de sincronización que se encuentra a continuación. Estos permisos se conceden al asociado de LMS para permitir que los formadores sincronicen la pertenencia entre el curso LMS y los equipos de clase Teams.

8. Habilite la sincronización de Microsoft Teams activando el botón de alternancia.

   ![teams-sync.](media/teams-sync.png)

## <a name="canvas-admin"></a>Admin de lienzo

Configure la integración Microsoft Teams LTI 1.3.

Como Admin canvas, deberá agregar la aplicación LTI de reuniones de Microsoft Teams dentro de su entorno. Anote el identificador de cliente LTI de la aplicación.

 - reuniones de Microsoft Teams: 170000000000703

1. Acceso **a la configuración de** >  Admin **Apps**.

2. Seleccione **+ Aplicación** para agregar las aplicaciones de LTI Teams.

   ![external-apps.](media/external-apps.png)

3. Seleccione **By Client ID (Por id. de cliente** ) para el tipo de configuración.

   ![agregar aplicación.](media/add-app.png)

4. Escriba el identificador de cliente proporcionado y, a continuación, seleccione **Enviar**.

   Observará el nombre de la aplicación LTI de reuniones de Microsoft Teams para el identificador de cliente para su confirmación.

5. Haga clic en **Instalar**.

   La aplicación LTI de reuniones Microsoft Teams se agregará a la lista de aplicaciones externas.

6. Habilite la aplicación; para ello, vaya a las claves de desarrollador de la cuenta de administrador de Canvas, seleccione Heredado y active el botón de alternancia "activado" para Microsoft Teams Reuniones.

## <a name="enable-for-canvas-courses"></a>Habilitar para cursos de Canvas

Para usar el LTI dentro de un curso, un instructor del curso de Canvas debe habilitar la sincronización de integraciones. Cada curso debe ser habilitado por un instructor para que se cree un Teams correspondiente; no hay ningún mecanismo global para Teams creación. Esto está diseñado por precaución para evitar que se creen Teams no deseados.

Consulte a los instructores la [documentación del educador](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) para habilitar el LTI para cada curso y finalizar la configuración de integración.
