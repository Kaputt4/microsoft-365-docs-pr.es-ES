---
title: Uso de clases de Microsoft Teams con Canvas
ms.author: danismith
author: cichur
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
description: Integración de clases de Microsoft Teams con Canvas
ms.openlocfilehash: 10024e124ce50ab542e6e68a5c237a47e1f7af83
ms.sourcegitcommit: 8a0de6240facfe26ee391a14076b7fe534ee6598
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2022
ms.locfileid: "65923027"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Uso de clases de Microsoft Teams con Canvas

Las clases de Microsoft Teams son una aplicación de interoperabilidad de herramientas de aprendizaje (LTI) que ayuda a los educadores y alumnos a navegar fácilmente entre su sistema de administración de aprendizaje (LMS) y Teams. Los usuarios pueden acceder a sus equipos de clase asociados a su curso directamente desde su LMS.

## <a name="prerequisites-before-deployment"></a>Requisitos previos antes de la implementación

> [!NOTE]
> Las clases actuales de Teams LTI solo admiten la sincronización de usuarios de Canvas con Microsoft Azure Active Directory (AAD) en un ámbito limitado.
>
> - El inquilino debe tener una licencia de Microsoft Education (A1 o superior).
> - Solo se puede usar un único inquilino de Microsoft para asignar usuarios entre Canvas y Microsoft.
> - El inquilino debe tener una coincidencia exacta entre un campo canvas (correo electrónico, identificador de usuario único, identificador de SIS o id. de integración) y un campo en AAD (nombre principal de usuario (UPN), dirección de correo electrónico principal (correo) o alias de correo electrónico (mailNickname)).
> - Si usa SDS para crear clases y grupos, se recomienda deshabilitar la opción de creación de equipos en SDS y realizar una [limpieza de grupo](/schooldatasync/group-cleanup) para evitar la duplicación de clases. SDS todavía se puede usar para sincronizar los datos de la organización y del usuario.

## <a name="enable-the-microsoft-teams-app-in-canvas"></a>Habilitación de la aplicación Microsoft Teams en Canvas

Para comenzar la integración, debe habilitar la aplicación en Canvas habilitando las claves para desarrolladores, habilitando la sincronización de Microsoft Teams y aprobando la aplicación Microsoft-Teams-Sync-for-Canvas. Tenga en cuenta que la aprobación de la aplicación solo la puede realizar un administrador de inquilinos de Microsoft que pueda aprobar aplicaciones.

**Para habilitar la sincronización de Microsoft Teams y aprobar el acceso para la aplicación**:

1. Inicie sesión en Canvas como administrador.

2. Seleccione el vínculo **Administrador** en la navegación global y, a continuación, seleccione su cuenta.
3. En la navegación del administrador, seleccione el vínculo **Claves de desarrollador** y, a continuación, seleccione la pestaña **Heredado** .
4. Habilite las aplicaciones LTI que va a implementar seleccionando el estado **ON** para cada una de las aplicaciones adecuadas.

5. En la navegación del administrador, seleccione el vínculo **Configuración** y, a continuación, la pestaña **Integraciones** .

6. Habilite La sincronización de Microsoft Teams activando el botón de alternancia. Esta sincronización permite crear clases en Teams en función de la inscripción de un curso.

   ![Canvas Teams Sync Png actualizado.](https://user-images.githubusercontent.com/87142492/128225881-abdfc52d-dc9e-48ad-aec5-f6617c6436f3.png)

7. Rellene los campos siguientes con la información adecuada. Estos campos se usarán para buscar coincidencias entre los usuarios de Canvas y los usuarios de AAD.
   - El **nombre del inquilino** es el nombre del inquilino de Microsoft.
   - El **atributo Login** es uno de los siguientes atributos de usuario de Canvas que se usan para la asignación:
      - **El correo electrónico** es la dirección de correo electrónico predeterminada del usuario de Canvas. Si los usuarios cambian su dirección de correo electrónico predeterminada en Canvas, se podría impedir que su inscripción en un curso se sincronice con Teams.
      - **Id. de usuario único** es el identificador de inicio de sesión de Canvas del usuario.
      - **SIS User ID (Id. de usuario de SIS** ) es el valor de id. que se rellena desde el Sistema de información de estudiantes (SIS) y se puede ver en la página de perfil del usuario.
      - **El identificador de integración** solo se rellena a través de importaciones de SIS y se puede ver en la página de perfil del usuario. Normalmente, la institución proporciona este identificador único y se usa en las situaciones de confianza de cuenta o consorcios para identificar usuarios en varias cuentas.

   - El campo **Sufijo** es opcional y le permite especificar un dominio cuando no hay una asignación exacta entre los atributos de Canvas y los campos de Microsoft AAD. Por ejemplo, si el correo electrónico de Canvas es "name@example.edu" mientras el UPN de Microsoft AAD es "name", puede hacer coincidir a los usuarios escribiendo "@example.edu" en el campo sufijo. El dominio debe escribirse en este campo con el @anterior.
   - El atributo de búsqueda de Active Directory es el campo de AAD con el que coinciden los atributos de Canvas. Seleccione entre UPN, dirección de correo electrónico principal o el alias de correo electrónico.

8. Seleccione **Actualizar configuración**.

9. Para aprobar el acceso a la aplicación de Azure **Microsoft-Teams-Sync-for-Canvas de** Canvas, seleccione el vínculo **Conceder acceso al inquilino** . Se le redirigirá al punto de conexión de consentimiento del administrador de Microsoft Identity Platform.

   ![Permisos.](media/permissions.png)

   > [!NOTE]
   > Este paso lo debe realizar un administrador de inquilinos de Microsoft que pueda aprobar aplicaciones.

10. Seleccione **Aceptar**.

## <a name="integrate-teams-classes-lti-in-canvas"></a>Integración de las clases de Teams LTI en Canvas

Después de habilitar la sincronización y aprobar la aplicación de Azure, el administrador de Canvas ahora puede agregar la aplicación de LTI de clases de Teams al entorno de Canvas para que aparezca en la navegación de la interfaz de usuario de Canvas.

**Para agregar la aplicación de LTI de clases de Teams al entorno de Canvas**:

1. En la pestaña **Aplicaciones** de **Configuración de administración**, seleccione **+ Aplicación** para agregar las aplicaciones LTI de Teams.

   ![external-apps.](media/external-apps.png)

2. En **Tipo de configuración**, seleccione **Por identificador de cliente**.

   ![agregar aplicación.](media/add-app.png)

3. En **Id. de cliente**, escriba **170000000000570** para las clases LTI de Microsoft Teams y, a continuación, seleccione **Enviar**.

4. En la confirmación que aparece, compruebe el nombre de la aplicación (clases de Microsoft Teams) y, a continuación, seleccione **Instalar**.

   La aplicación LTI de clases de Microsoft Teams ahora se agrega a la lista de aplicaciones externas.

## <a name="enabling-the-lti-app-for-canvas-courses"></a>Habilitación de la aplicación LTI para los cursos de Canvas

Para usar la aplicación LTI dentro de un curso, un instructor del curso de Canvas debe habilitar la sincronización de integraciones. Cada curso debe ser habilitado por un instructor para que se cree un equipo correspondiente; no hay ningún mecanismo global para la creación de equipos. Esto está diseñado como una medida de precaución para evitar la creación de equipos no deseados.

Consulte a los instructores la [documentación del educador](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) para habilitar la aplicación LTI para cada curso y completar la configuración de integración.
