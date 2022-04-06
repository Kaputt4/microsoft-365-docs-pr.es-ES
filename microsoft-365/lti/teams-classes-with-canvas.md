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
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: Integrar Microsoft Teams clases con Canvas
ms.openlocfilehash: 08edb2065cd91ccb0e0d52290dfe83f8a3e60392
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64569012"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Usar Microsoft Teams clases con Canvas

Microsoft Teams clases es una aplicación de interoperabilidad de Learning Tools (LTI) que ayuda a los profesores y alumnos a navegar fácilmente entre su sistema de administración de Learning (LMS) y Teams. Los usuarios pueden acceder a sus equipos de clase asociados con su curso directamente desde su LMS.

## <a name="prerequisites-before-deployment"></a>Requisitos previos antes de la implementación

> [!NOTE]
> La clase Teams actual LTI solo admite la sincronización de usuarios de Canvas con Microsoft Azure Active Directory (AAD) en un ámbito limitado.
>
> - El inquilino debe tener una licencia de Microsoft Education (A1 o posterior).
> - Solo se puede usar un único espacio empresarial de Microsoft para asignar usuarios entre Canvas y Microsoft.
> - El inquilino debe tener una coincidencia exacta entre un campo canvas (correo electrónico, id. de usuario único, id. de SIS o id. de integración) y un campo en AAD (nombre principal de usuario (UPN), dirección de correo electrónico principal (correo) o alias de correo electrónico (mailNickname)).
> - Si usa SDS para crear clases y grupos, se recomienda deshabilitar la opción de creación de equipo en SDS y realizar una [](/schooldatasync/group-cleanup) limpieza de grupo para evitar la duplicación de clases. SDS todavía se puede usar para sincronizar datos de usuario y organización.

## <a name="enable-the-microsoft-teams-app-in-canvas"></a>Habilitar la Microsoft Teams en Canvas

Para comenzar la integración, debes habilitar la aplicación en Canvas habilitando las claves de desarrollador, habilitando la sincronización de Microsoft Teams y aprobando la aplicación Microsoft-Teams-Sync-for-Canvas. Ten en cuenta que la aprobación de la aplicación solo la puede realizar un administrador de inquilinos de Microsoft que pueda aprobar aplicaciones.

**Para habilitar Microsoft Teams sincronización y aprobar el acceso a la aplicación**:

1. Inicie sesión en Canvas como administrador.

2. Seleccione el **vínculo** Administrador en la navegación global y, a continuación, seleccione su cuenta.
3. En la navegación de administración, seleccione el vínculo **Claves de** desarrollador y, a continuación, seleccione la **pestaña** Heredado.
4. Habilita las aplicaciones de LTI que vas a implementar seleccionando el estado **ON** para cada una de las aplicaciones adecuadas.

5. En la navegación de administración, seleccione **el vínculo Configuración** y, a continuación, la **pestaña Integraciones**.

6. Habilite Microsoft Teams sincronización activando la alternancia. Esta sincronización permite crear clases en Teams en función de la inscripción de un curso.

   ![Canvas Teams Sync Updated png.](https://user-images.githubusercontent.com/87142492/128225881-abdfc52d-dc9e-48ad-aec5-f6617c6436f3.png)

7. Rellene los siguientes campos con la información adecuada. Estos campos se usarán para hacer coincidir usuarios en Canvas con usuarios de AAD.
   - El **nombre del inquilino** es el nombre del inquilino de Microsoft.
   - El **atributo Login** es uno de los siguientes atributos de usuario de Canvas usados para la asignación:
      - **El** correo electrónico es la dirección de correo electrónico predeterminada del usuario de Canvas. Si los usuarios cambian su dirección de correo electrónico predeterminada en Canvas, su inscripción en un curso podría bloquearse para que no se sincronice a Teams.
      - **Id. de usuario único** es el identificador de inicio de sesión de Canvas del usuario.
      - **Sis Id. de** usuario es el valor de id. que se rellena desde el Sistema de información de estudiantes (SIS) y se puede ver en la página de perfil del usuario.
      - **El identificador de** integración solo se rellena a través de importaciones de SIS y se puede ver en la página de perfil del usuario. Normalmente, este identificador único lo proporciona la entidad y se usa en situaciones de confianza de cuentas o consorcios para identificar usuarios en varias cuentas.

   - El **campo Sufijo** es opcional y le permite especificar un dominio cuando no hay una asignación exacta entre los atributos canvas y los campos AAD Microsoft. Por ejemplo, si el correo electrónico de Canvas es "name@example.edu" mientras el UPN de Microsoft AAD es "nombre", puede hacer coincidir a los usuarios si escribe "@example.edu" en el campo sufijo. El dominio debe especificarse en este campo con el @anterior.
   - El atributo de búsqueda de Active Directory es el campo de AAD con el que coinciden los atributos canvas. Seleccione entre UPN, dirección de correo electrónico principal o el alias de correo electrónico.

8. Seleccione **Actualizar Configuración**.

9. Para aprobar el acceso a la aplicación azure de **Microsoft-Teams-Sync-for-Canvas de Canvas de Canvas**, seleccione el vínculo Conceder acceso **al** espacio empresarial. Se le redirigirá al punto de conexión de consentimiento de administrador de la plataforma de identidad de Microsoft.

   ![permisos.](media/permissions.png)

   > [!NOTE]
   > Este paso debe realizarlo un administrador de inquilinos de Microsoft que pueda aprobar aplicaciones.

10. Seleccione **Aceptar**.

## <a name="integrate-teams-classes-lti-in-canvas"></a>Integrar Teams clases LTI en Canvas

Después de habilitar la sincronización y aprobar la aplicación de Azure, el administrador de Canvas ahora puede agregar la aplicación LTI de clases de Teams al entorno canvas para que aparezca en la navegación de la interfaz de usuario de Canvas.

**Para agregar la aplicación Teams clases de usuario LTI al entorno canvas**:

1. En la **pestaña Aplicaciones** en **Configuración de administración**, selecciona **+ Aplicación** para agregar las Teams LTI.

   ![external-apps.](media/external-apps.png)

2. Para **Tipo de configuración**, seleccione **Por identificador de cliente**.

   ![agregar aplicación.](media/add-app.png)

3. Para **Id. de** cliente, **escriba 170000000000570** para las clases Microsoft Teams LTI y, a continuación, **seleccione Enviar**.

4. En la confirmación que aparece, comprueba el nombre de la aplicación (Microsoft Teams clases) y, a continuación, selecciona **Instalar**.

   La Microsoft Teams clases de aplicación LTI ahora se agrega a la lista de aplicaciones externas.

## <a name="enabling-the-lti-app-for-canvas-courses"></a>Habilitar la aplicación LTI para cursos de Canvas

Para usar la aplicación LTI dentro de un curso, un instructor del curso canvas debe habilitar la sincronización de integraciones. Cada curso debe estar habilitado por un instructor para que se cree un equipo correspondiente; no hay ningún mecanismo global para la creación de equipos. Esto está diseñado como una medida de precaución para evitar que se creen equipos no deseados.

Consulte la documentación del profesor para [](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) habilitar la aplicación LTI para cada curso y completar la configuración de integración.
