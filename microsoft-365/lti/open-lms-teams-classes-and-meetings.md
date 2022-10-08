---
title: Integración de clases y reuniones de Microsoft Teams con Open LMS
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: microsoft-365-business
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Cree y administre clases y reuniones de Teams con interoperabilidad de Microsoft Learning Tools para Open LMS.
ms.openlocfilehash: 034aa9924798b7e284665713e6d8fe2809c1e70f
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68203824"
---
# <a name="integrate-microsoft-teams-classes-and-meetings-within-open-lms"></a>Integración de clases y reuniones de Microsoft Teams en Open LMS

En esta guía se proporcionan los pasos del administrador de TI para registrar tanto las clases de Teams como las aplicaciones LTI de reuniones de Teams en Open LMS.

Para obtener más información sobre cómo administrar todas las aplicaciones LTI para cualquier LMS, consulte [Administración de La puerta de enlace de Microsoft LMS para cualquier LMS](manage-microsoft-one-lti.md).

## <a name="prerequisites-before-set-up"></a>Requisitos previos antes de configurar

Para que la integración entre Open LMS y Teams funcione correctamente, Open LMS y Teams deben configurarse para comunicarse entre sí.

Siga las [instrucciones para instalar y configurar los complementos de Moodle LMS](open-lms-plugin-configuration.md).

## <a name="register-microsoft-teams-lti-for-use-in-open-lms"></a>Registro de LTI de Microsoft Teams para su uso en Open LMS

> [!IMPORTANT]
> La persona que realiza esta integración debe ser un administrador de Open LMS y un administrador de inquilinos de Microsoft 365.

1. Visite [Puerta de enlace de Microsoft LMS](https://lti.microsoft.com/) y seleccione el botón **Ir al portal de registro** .

2. Inicie sesión con una cuenta de administrador de Microsoft 365.

3. Después de iniciar sesión, seleccione **Agregar nuevo registro**.

4. Seleccione **LTI de reuniones de Teams** o **LTI de clases de Teams** para registrarse y, a continuación, seleccione **Siguiente**.

5. Escriba un nombre **de registro** fácilmente identificable y seleccione **Open LMS** como plataforma LMS. Seleccione **Siguiente**.

6. Se le dará una lista de claves que deben agregarse al sitio de Open LMS.

7. Abra Open LMS en otra pestaña. No cierre la pestaña Puerta de enlace de Microsoft LMS.

8. En Open LMS, vaya a Módulos de actividad **de complementos** >  de **administración** >  del sitio **Herramientas** > **externas** > **Administrar herramientas**.

9. En la página **Administrar herramientas** , seleccione **Configurar una herramienta manualmente**.

10. En **Configuración de herramientas**, escriba un **nombre de herramienta** como **Clases de Microsoft Teams**. En **Versión LTI**, seleccione **LTI 1.3**. En **Tipo de clave pública**, seleccione **Dirección URL del conjunto de claves**.

11. A continuación, copie las claves de **las claves LTI de Microsoft** en las entradas de la herramienta correspondientes.
    1. La clave de **dirección URL del vínculo de destino** de Microsoft entra en el campo **Url de la herramienta** de Open LMS.
    1. La clave de **dirección URL de conexión de Open ID** de Microsoft entra en el campo **Iniciar dirección URL de inicio de sesión** de Open LMS.
    1. La clave de **dirección URL de redireccionamiento** de Microsoft entra en el campo **URI de redireccionamiento de** Open LMS.

12. Seleccione **Guardar cambios**.

13. La nueva herramienta debería aparecer ahora en la sección **Herramientas** de la página **Administrar herramientas** de Open LMS. Seleccione el icono de lista para ver **los detalles de configuración de la herramienta**.

14. Volver a la pestaña Puerta de enlace de Microsoft LMS. Seleccione **Siguiente** para ir al paso **Claves de registro proporcionadas por LMS**.

15. Copie y pegue los valores de **los detalles de configuración** de la herramienta Open LMS en el paso **de claves de registro proporcionadas por LMS** de Microsoft.

    Pegue los valores como se indica a continuación:

    | En Open LMS | En el portal de registro de Microsoft LTI |
    | --------- | ------------------------------------ |
    | Id. de plataforma | Dirección URL del identificador de emisor |
    | Id. de cliente | Id. de cliente |
    | Identificador de implementación | Identificador de implementación |
    | Dirección URL del conjunto de claves público | Dirección URL del conjunto de claves |
    | Dirección URL del token de acceso | Dirección URL del token de acceso |
    | Dirección URL de la solicitud de autenticación | Dirección URL de autenticación de plataforma |

    Seleccione **Siguiente**.

16. Revise la página **Revisar y agregar** . Si no hay errores, seleccione **Guardar y salir**. Debería ver un mensaje que indica que el registro se ha realizado correctamente.

Ha completado el registro de la aplicación Teams Classes o Teams Meetings LTI.

Si también desea agregar la otra aplicación, repita los pasos anteriores y seleccione la otra aplicación LTI de Teams en el paso 4.

### <a name="add-teams-lti-apps-to-educators-open-lms-courses"></a>Incorporación de aplicaciones LTI de Teams a los cursos de Open LMS de los formadores

Después de registrar aplicaciones LTI de Teams, los educadores pueden agregar la aplicación Clases de Teams y la aplicación Reuniones de Teams a sus cursos de Open LMS.

- [Instrucciones para educadores sobre cómo agregar la aplicación Clases de Teams](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-ac6a1e34-32f7-45e6-b83e-094185a1e78a).
- [Instrucciones para educadores sobre cómo agregar la aplicación Reuniones de Teams](https://support.microsoft.com/topic/use-microsoft-teams-meetings-in-your-lms-11b6095d-f90b-42b9-ab77-4dcff2bb3b76).

## <a name="technical-requirements-to-launch-teams-lti-apps"></a>Requisitos técnicos para iniciar aplicaciones LTI de Teams

Para iniciar las aplicaciones de LTI de Teams en Open LMS, es necesario cumplir algunos requisitos técnicos.

> [!NOTE]
> Los administradores y educadores de TI pueden registrar aplicaciones LTI en el portal de registro de aplicaciones de LTI.

### <a name="it-admin-technical-requirements"></a>Requisitos técnicos del administrador de TI

- Use Moodle versión 3.10 o posterior.
- Descargue el complemento de Microsoft O365 más reciente para Moodle versión 3.10 o posterior.
- Acceda al portal de registro de aplicaciones LTI para registrar las aplicaciones LTI.
  - El registro debe estar completado en un dispositivo de escritorio.
- Descargue la versión más reciente de Microsoft Edge, Google Chrome, Safari o Mozilla Firefox.

### <a name="educator-technical-requirements"></a>Requisitos técnicos del educador

- Acceda al portal de registro de aplicaciones LTI para registrar las aplicaciones LTI, si el administrador de TI no ha registrado las aplicaciones.
  - El registro debe estar completado en un dispositivo de escritorio.
- Descargue la versión más reciente de Microsoft Edge, Google Chrome, Safari o Mozilla Firefox.
- [Aplicaciones de LTI de Teams para clases y reuniones en Open LMS](#add-teams-lti-apps-to-educators-open-lms-courses).

### <a name="student-technical-requirements"></a>Requisitos técnicos de los alumnos

- Aplicaciones de LTI de Teams para clases y reuniones en Open LMS.
  - Los alumnos no necesitan realizar ninguna acción para agregar las aplicaciones de LTI de clases o reuniones de Teams.
