---
title: Integración de LTI de Microsoft OneDrive con Schoology Learning
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
description: Crear y calificar asignaciones, compilar y mantener contenido del curso, y colaborar en archivos en tiempo real con la nueva aplicación de interoperabilidad de herramientas de aprendizaje de Microsoft OneDrive para PowerSchool Unified Classroom® Schoology Learning.
ms.openlocfilehash: ab3c732127cc614d0540974591e8f2847fc0d26c
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804716"
---
# <a name="integrate-microsoft-onedrive-lti-with-schoology-learning"></a>Integración de LTI de Microsoft OneDrive con Schoology Learning

En esta guía se proporcionan los pasos de los administradores de TI para registrar la aplicación LTI de OneDrive para PowerSchool Unified Classroom® Schoology Learning.

Para obtener información general sobre Microsoft LTI, consulte [Integración de productos de Microsoft con el sistema de administración de aprendizaje (LMS).](index.md)

La persona que realiza esta integración debe ser administrador de Schoology Learning y administrador del inquilino de Microsoft 365.

## <a name="recommended-browser-settings"></a>Configuración recomendada del explorador

- Se deben permitir cookies para Microsoft OneDrive.
- No se deben bloquear los elementos emergentes para Microsoft OneDrive.

> [!NOTE]
> Las cookies no se permiten de forma predeterminada en el modo de incógnito del explorador Chrome y se deben permitir.
>
> Microsoft OneDrive LTI funciona en modo privado en el explorador Microsoft Edge. Asegúrese de que no ha bloqueado las cookies (que están permitidas de forma predeterminada).

## <a name="register-a-new-microsoft-onedrive-lti-app-for-your-microsoft-365-tenant"></a>Registro de una nueva aplicación LTI de Microsoft OneDrive para el inquilino de Microsoft 365

1. Inicie sesión en el [Portal de registro de LTI de Microsoft OneDrive](https://onedrivelti.microsoft.com/admin) mediante una credencial de Administración global de Office 365.
1. Seleccione el botón **Administración Consentimiento** y acepte los permisos.
    1. Si este paso no se completa correctamente, el siguiente paso le dará un error y es posible que no pueda realizar este paso durante una hora una vez que haya recibido el error. Si se produce un error en el consentimiento, asegúrese de que ha iniciado sesión como un Administración global y repita este paso.
1. Seleccione el botón **Crear nuevo inquilino de LTI** .
1. En la lista **Plataforma de consumidores de LTI** , seleccione **Schoology**.
1. En el campo **Dirección URL base de Schoology** , escriba la dirección URL base de Schoology Learning, como `https://testschool.schoology.com`.
1. Seleccione el botón **Siguiente**. Se cargará la página **Registrar aplicación LTI 1.3** .

## <a name="deploy-the-onedrive-lti-app-in-schoology-learning"></a>Implementación de la aplicación LTI de OneDrive en Schoology Learning

1. Inicie sesión en la instancia de Schoology Learning como administrador con acceso para instalar y configurar aplicaciones.
1. Acceda a la aplicación **Microsoft OneDrive** en el [**Centro de aplicaciones**](https://app.schoology.com/apps) abriendo este vínculo directo [Microsoft OneDrive en Schoology Learning](https://app.schoology.com/apps/profile/5910037138).
1. Seleccione el botón **Instalar aplicación LTI 1.3** para comenzar el proceso de instalación.
1. Seleccione el botón **Acepto** .
1. Se le pedirá que comparta la información necesaria con la aplicación y confirme el acceso a *los servicios de LTI Advantage*, como **vínculos profundos**, **nombres y roles**, y **asignaciones y calificaciones**. Seleccione el botón **Continuar** .
1. Se le preguntará si se debe instalar para toda la organización o solo para usted. Seleccione **Agregar a la organización** y se le redirigirá a la página **Aplicaciones** de la organización para completar la configuración.
1. En la [**lista Aplicaciones de la organización**](https://app.schoology.com/apps/school_apps), busque la aplicación **Microsoft OneDrive** y seleccione el botón **Configurar** .
    1. Copie el **identificador de implementación** asignado a la implementación de la aplicación.
        1. Este identificador se usará en el proceso **de configuración de la puerta de enlace de Microsoft LMS** .
1. En la [**lista Aplicaciones de la organización**](https://app.schoology.com/apps/school_apps), busque la aplicación **Microsoft OneDrive** y seleccione el botón **Instalar o quitar** .
    1. Para instalar la aplicación para todos los cursos, elija la casilla **Todos los cursos** .
        1. No active la opción **Solo administradores** del curso para asegurarse de que la aplicación está disponible para todos los miembros del curso.

> [!NOTE]
> Si decide no instalar la aplicación para todos los cursos, *los administradores de cursos* deben instalar la aplicación por sí mismos:
>
> 1. Vaya a la [lista Aplicaciones](https://app.schoology.com/apps/school_apps) de la organización, seleccione el botón **Instalar o quitar** y elija los cursos en los que instalar la aplicación.
> 1. O bien, pueden seleccionar el vínculo **Instalar las aplicaciones** en la parte inferior del menú de navegación del carril izquierdo del curso y, a continuación, seleccionar la aplicación **Microsoft OneDrive** que se va a instalar.
