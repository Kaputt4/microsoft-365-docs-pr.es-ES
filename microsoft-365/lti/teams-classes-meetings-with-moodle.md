---
title: Integración Microsoft Teams clases y reuniones con Moodle
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Cree y administre Teams clases y reuniones con Microsoft OneDrive Learning Tools Interoperability for Moodle.
ms.openlocfilehash: 0eacbd846d4582312f8936e57c4f630836d9264c
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2022
ms.locfileid: "64747532"
---
# <a name="integrate-microsoft-teams-classes-and-meetings-within-moodle"></a>Integración de Microsoft Teams clases y reuniones en Moodle

En esta guía se proporcionan los pasos del administrador de TI para registrar las aplicaciones LTI de Teams y Teams reuniones en Moodle.

Para obtener más información sobre cómo administrar todas las herramientas de OneLTI para cualquier LMS, consulte [Administración de Microsoft OneLTI para cualquier LMS](manage-microsoft-one-lti.md).

## <a name="prerequisites-before-set-up"></a>Requisitos previos antes de configurar

Para que la integración entre Moodle y Teams funcione correctamente, Moodle y Teams deben configurarse para comunicarse entre sí.

Siga las [instrucciones para instalar y configurar el complemento Moodle](moodle-plugin-configuration.md).

## <a name="register-microsoft-onelti-tools-for-use-in-moodle"></a>Registro de herramientas de Microsoft OneLTI para su uso en Moodle

> [!IMPORTANT]
> La persona que realiza esta integración debe ser un administrador de Moodle y un administrador de inquilinos Microsoft 365.

1. Visite [El portal de Microsoft LTI](https://lti.microsoft.com/) y seleccione **Ir al portal de registro**.

2. Inicie sesión con una cuenta de administrador de Microsoft 365.

3. Después de iniciar sesión, seleccione **Agregar nuevo registro**.

4. Seleccione **Teams LTI de reuniones** o **Teams Clases LTI** para registrarse y, a continuación, seleccione **Siguiente**.

5. Escriba un nombre **de registro** fácilmente identificable y seleccione **Moodle** como plataforma LMS. Seleccione **Siguiente**.

6. Se le dará una lista de claves que deben agregarse a su sitio de Moodle.

7. Abra Moodle en otra pestaña. No cierre la pestaña del portal de Microsoft LTI.

8. En Moodle, vaya a **Administración** >  del **sitioAdministración de sitiosAdministramientos** >  de **actividadHerramientas** >  **externasAdministración** >  de herramientas.

9. En la página **Administrar herramientas** , seleccione **Configurar una herramienta manualmente**.

10. En **Configuración de la herramienta**, escriba un **nombre de herramienta** como **clases Microsoft Teams**. En **Versión LTI**, seleccione **LTI 1.3**. En **Tipo de clave pública**, seleccione **Dirección URL del conjunto de claves**.

11. A continuación, copie las claves de **las claves LTI de Microsoft** en las entradas de herramientas correspondientes.
    1. La clave de **dirección URL del vínculo de destino** de Microsoft entra en el campo **Url de la herramienta** de Moodle.
    1. La clave de **dirección URL de conexión de Open ID** de Microsoft entra en el campo **Iniciar dirección URL de inicio de sesión** de Moodle.
    1. La clave de **dirección URL de redireccionamiento** de Microsoft entra en el campo **URI de redireccionamiento de** Moodle.

12. Seleccione **Guardar cambios**.

13. La nueva herramienta debería aparecer ahora en la sección **Herramientas** de la página **Administrar herramientas** de Moodle. Seleccione el icono de lista para ver **los detalles de configuración de la herramienta**.

14. Volver a la pestaña portal de Microsoft LTI. Seleccione **Siguiente** para ir al paso Claves de **registro proporcionadas por LMS**.

15. Copie y pegue los valores de **los detalles de configuración** de la herramienta de Moodle en el paso **de claves de registro proporcionadas por LMS** de Microsoft.

  Pegue los valores como se indica a continuación:

  | En Moodle | En el portal de registro de Microsoft LTI |
  | --------- | ------------------------------------ |
  | Id. de plataforma | Dirección URL del identificador de emisor |
  | Id. de cliente | Id. de cliente |
  | Identificador de implementación | Identificador de implementación |
  | Dirección URL del conjunto de claves público | Dirección URL del conjunto de claves |
  | Dirección URL del token de acceso | Dirección URL del token de acceso |
  | Dirección URL de la solicitud de autenticación | Dirección URL de autenticación de plataforma |

  Seleccione **Siguiente**.

16. Revise la página **Revisar y agregar** . Si no hay errores, seleccione **Guardar y salir**. Debería ver un mensaje que indica que el registro se ha realizado correctamente.

Ha completado el registro de las clases de Teams o de la aplicación LTI de reuniones de Teams.

Si también desea agregar la otra aplicación, repita los pasos anteriores y seleccione la otra aplicación LTI Teams en el paso 4.

### <a name="add-teams-lti-tools-to-educators-moodle-courses"></a>Incorporación de herramientas de LTI Teams a los cursos de Moodle para educadores

Después de registrar Teams aplicaciones LTI, los educadores pueden agregar la aplicación clases de Teams y la aplicación reuniones de Teams a sus cursos de Moodle.

- [Instrucciones para educadores sobre cómo agregar la aplicación clases de Teams](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-ac6a1e34-32f7-45e6-b83e-094185a1e78a).
- [Instrucciones para educadores sobre cómo agregar la aplicación Teams Reuniones](https://support.microsoft.com/topic/use-microsoft-teams-meetings-in-your-lms-11b6095d-f90b-42b9-ab77-4dcff2bb3b76).
