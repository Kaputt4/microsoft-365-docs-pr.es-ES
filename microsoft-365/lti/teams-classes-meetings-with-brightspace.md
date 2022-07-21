---
title: Integración de clases y reuniones de Aplicaciones LTI de Microsoft Teams con Desire2Learn Brightspace LMS
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-modern-desktop
- m365initiative-edu
ms.localizationpriority: medium
description: Cree y administre clases y reuniones de Teams con Microsoft Learning Tools Interoperability (LTI) para Desire2Learn (D2L) Brightspace LMS.
ms.openlocfilehash: c3d551fcdc866c08437564addb1cd3cb9b144a75
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66951255"
---
# <a name="integrate-microsoft-teams-classes-and-meetings-lti-apps-within-desire2learn-brightspace-lms"></a>Integración de clases y reuniones de Aplicaciones LTI de Microsoft Teams en Desire2Learn Brightspace LMS

En esta guía se proporcionan los pasos del administrador de TI para registrar las aplicaciones LTI de las clases de Teams y reuniones de Teams para Desire2Learn (D2L) Brightspace LMS.

Para obtener más información sobre cómo administrar todas las aplicaciones LTI para cualquier LMS, consulte [Administración de La puerta de enlace de Microsoft LMS para cualquier LMS](manage-microsoft-one-lti.md).

Los pasos básicos para integrar las aplicaciones LTI de Teams y Brightspace son:

1. [Requisitos previos antes de la integración](#prerequisites-before-integration).
1. [Registre Microsoft LTI para usarlo en Brightspace](#register-microsoft-teams-lti-for-use-in-brightspace).
1. [Implemente las aplicaciones de Microsoft LTI en Brightspace](#deploy-the-microsoft-lti-apps-to-brightspace).
1. [Agregue vínculos de aplicaciones LTI de Teams a Brightspace de educadores](#add-teams-lti-app-links-to-educators-brightspace).

## <a name="prerequisites-before-integration"></a>Requisitos previos antes de la integración

Para que la integración entre D2L Brightspace y Teams funcione correctamente, Brightspace y Teams deben estar configurados para comunicarse entre sí.

1. Para que las clases de Teams funcionen, debe tener **brightspace Course Connector** instalado y configurado correctamente. Siga [estos pasos para instalar el conector en su cuenta de Brightspace](https://community.brightspace.com/s/article/Getting-started-with-Brightspace-Course-Connector-for-Microsoft-Teams).

   > [!NOTE]
   > Seleccione **Equipo de clase** para **Tipo de integración** al configurar el conector para garantizar la compatibilidad con las herramientas LTI de Teams.

2. Las reuniones de Teams funcionarán sin el conector del curso. Sin embargo, algunas características, como **Agregar clase completa** , no estarán disponibles. Se recomienda instalar **Brightspace Course Connector** para la aplicación Teams Meetings LTI.

## <a name="register-microsoft-teams-lti-for-use-in-brightspace"></a>Registro de LTI de Microsoft Teams para su uso en Brightspace

1. Visite [La puerta de enlace de Microsoft LMS](https://lti.microsoft.com/) y seleccione el botón **Ir al portal de registro** .

2. Inicie sesión con una *cuenta de administrador de Microsoft 365*.

3. Después de iniciar sesión, seleccione **Agregar nuevo registro**.

4. Seleccione **LTI de reuniones de Teams** o **LTI de clases de Teams** para registrarse y, a continuación, seleccione **Siguiente**.

5. Escriba un nombre **de registro** fácilmente identificable y seleccione **D2L Brightspace** como plataforma LMS. Seleccione **Siguiente**.

6. Se le dará una lista de claves que deben agregarse al sitio de Brightspace LMS.

7. Abra el sitio de Brightspace en otra pestaña. No cierre la pestaña Puerta de enlace de Microsoft LMS.

8. En el sitio de Brightspace, vaya a **Administración** >  **Administrar extensibilidad** y seleccione **Ventaja de LTI** y, a continuación, **Registrar herramienta**.

9. Seleccione **Registro estándar** y copie las claves de **las claves LTI de Microsoft** en las entradas de herramientas correspondientes.
    1. La clave de **dirección URL del vínculo de destino** de Microsoft entra en el campo **URI de vínculo de destino** de Brightspace.
    1. La clave de **dirección URL de conexión de Open ID** de Microsoft entra en el campo **OpenID Connect Login URL (Dirección URL de inicio de sesión de OpenID Connect)** de Brightspace.
    1. La clave de **dirección URL de redireccionamiento** de Microsoft entra en el campo **Direcciones URL de redireccionamiento** de Brightspace.

10. En el campo **Dominio** , escriba `https://teams.microsoft.com`.

11. Seleccione el botón **Registrar**.

12. Un modal mostrará los detalles del registro de Brightspace. Estos valores deben agregarse en la puerta de enlace de Microsoft LMS.

13. En la pestaña **Puerta de enlace de Microsoft LMS** , seleccione **LMS provided registration keys (Claves de registro proporcionadas por LMS**).

14. Copie y pegue los valores de los detalles de configuración de Brightspace en el paso **de claves de registro proporcionadas por LMS** de Microsoft.

    Pegue los valores como se indica a continuación:

    | En Brightspace                         | En el portal de registro de Microsoft LTI |
    | -------------------------------------- | ------------------------------------ |
    | Emisor                                 | Dirección URL del identificador de emisor                        |
    | Id. de cliente                              | Id. de cliente                            |
    | Dirección URL del conjunto de claves de Brightspace                 | Dirección URL del conjunto de claves                           |
    | Punto de conexión de autenticación de OpenID Connect | Dirección URL de autenticación de plataforma          |

    Seleccione **Siguiente**.

15. Revise la página **Revisar y agregar** . Si no hay errores, seleccione **Guardar y salir**. Debería ver un mensaje que indica que el registro se ha realizado correctamente.

Ha completado el registro de la aplicación Teams Classes o Teams Meetings LTI.

Si también desea agregar la otra aplicación, repita los pasos anteriores y seleccione la otra aplicación LTI de Teams en el paso 4.

## <a name="deploy-the-microsoft-lti-apps-to-brightspace"></a>Implementación de las aplicaciones de Microsoft LTI en Brightspace

Después de registrar las aplicaciones de Microsoft LTI, debe implementar las aplicaciones en el sitio de Brightspace.

Este es el procedimiento para crear una nueva implementación:

1. En el sitio de Brightspace, seleccione la herramienta que ha creado.
2. Escriba un nombre de implementación.
3. Seleccione toda la configuración de seguridad excepto **Classlist** y **Anonymous**.
4. No establezca los valores de configuración.
5. Seleccione **Crear implementación**.

Elija las **unidades de organización** que desea usar la nueva aplicación LTI. Seleccione la **organización raíz** o seleccione elementos secundarios de la unidad organizativa individual.

## <a name="add-teams-lti-app-links-to-educators-brightspace"></a>Incorporación de vínculos de aplicaciones LTI de Teams a Brightspace de educadores

Después de crear una implementación, creará un nuevo vínculo. Este vínculo agregará la aplicación LTI de Microsoft a la experiencia de Brightspace de los educadores.

1. En el sitio de Brightspace, seleccione la implementación que ha creado.
2. Desplácese hacia abajo y seleccione **Ver vínculos**.
3. Seleccione **Nuevo vínculo**.
4. Rellene estos detalles necesarios:
    1. Pegue la **dirección URL de redireccionamiento** de la *puerta de enlace de Microsoft LMS* en el campo **URL** . Para acceder a esta dirección URL, vea el registro en la puerta de enlace.
    1. Establezca el tipo en **Inicio básico**.
5. Seleccione **Guardar y cerrar**.

El formador ahora puede agregar la aplicación LTI de Microsoft seleccionándola en la lista desplegable **Contenido existente** de Brightspace.
