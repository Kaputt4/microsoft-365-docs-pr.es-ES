---
title: Integración de reuniones de Microsoft Teams con Schoology LMS
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
description: Cree y administre reuniones de Teams con Microsoft Learning Tools Interoperability (LTI) para Schoology LMS.
ms.openlocfilehash: 41f389e7a936f91928ea084dddb9688f8703c7bf
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67694446"
---
# <a name="integrate-microsoft-teams-meetings-with-schoology-lms"></a>Integración de reuniones de Microsoft Teams con Schoology LMS

En esta guía se proporcionan los pasos del administrador de TI para registrar la aplicación LTI de reuniones de Teams en Schoology.

Para obtener información general sobre Microsoft LTI, consulte [Integración de productos de Microsoft con el sistema de administración de aprendizaje (LMS).](index.md)

> [!NOTE]
> La persona que realiza esta integración debe ser administrador de Schoology. Sin embargo, los usuarios de Schoology con acceso al **Centro de aplicaciones** de Schoology también pueden instalar la aplicación LTI de reuniones de Microsoft Teams.

## <a name="register-the-teams-meetings-lti-app-for-schoology"></a>Registro de la aplicación LTI de reuniones de Teams para Schoology

1. Inicie sesión en la instancia de Schoology como administrador con acceso para instalar y configurar aplicaciones.
1. Acceda a la aplicación **Reuniones de Microsoft Teams** en el [**Centro de aplicaciones**](https://app.schoology.com/apps) abriendo este vínculo directo Reuniones de [Microsoft Teams en Schoology](https://app.schoology.com/apps/profile/6017478062).
1. Seleccione el botón **Instalar aplicación LTI 1.3** para comenzar el proceso de instalación.
1. Seleccione el botón **Acepto** .
1. Se le preguntará si esta aplicación debe instalarse para toda la organización o solo para usted. Seleccione **Agregar a la organización** y se le redirigirá a la página **Aplicaciones** de la organización para completar la configuración.
1. En la [**lista Aplicaciones de la organización**](https://app.schoology.com/apps/school_apps), busque la aplicación **Reuniones de Microsoft Teams** y seleccione el botón **Configurar** .
    1. Copie el **identificador de implementación** asignado a la implementación de la aplicación.
        1. Este identificador se usará en el proceso de configuración **de la puerta de enlace de Microsoft LMS** .
1. En la [**lista Aplicaciones de la organización**](https://app.schoology.com/apps/school_apps), busque la aplicación **Reuniones de Microsoft Teams** y seleccione el botón **Instalar o quitar** .
    1. Para instalar la aplicación para todos los usuarios, elija la casilla **Todos los usuarios** .
        1. Seleccione solo los roles que tendrán acceso a Microsoft Teams en su organización, como profesores, alumnos o administradores del sistema.
    1. Para instalar la aplicación para todos los cursos, elija la casilla **Todos los cursos** .
        1. No active la opción **Solo administradores** del curso para asegurarse de que la aplicación está disponible para todos los miembros del curso.
    1. Para instalar la aplicación para todos los grupos, elija la casilla **Todos los grupos** .

> [!NOTE]
> Si decide no instalar la aplicación para todos los cursos, *los administradores de cursos* deben instalar la aplicación por sí mismos:
>
> 1. Vaya a la [lista Aplicaciones](https://app.schoology.com/apps/school_apps) de la organización, seleccione el botón **Instalar o quitar** y elija los cursos en los que instalar la aplicación.
> 1. O bien, pueden seleccionar el vínculo **Instalar las aplicaciones** en la parte inferior del menú de navegación del carril izquierdo del curso y, a continuación, seleccionar la aplicación **Reuniones de Microsoft Teams** que se va a instalar.

## <a name="configure-the-teams-meetings-lti-app-to-work-with-schoology"></a>Configuración de la aplicación LTI de reuniones de Teams para que funcione con Schoology

1. Visite [Puerta de enlace de Microsoft LMS](https://lti.microsoft.com/) y seleccione el botón **Ir al portal de registro** .
1. Inicie sesión con una cuenta de administrador de Microsoft 365.
1. Seleccione el botón **Administración Consentimiento** y acepte los permisos.
    1. Si no se realiza este paso, el siguiente paso le proporcionará un error y no podrá realizar este paso durante una hora una vez que haya recibido el error.
1. Seleccione el botón **Crear nuevo inquilino de LTI** .
1. En la página Registro de LTI, elija **Schoology** en la lista desplegable Plataforma de consumidores de LTI y, a continuación, seleccione el botón **Siguiente** .
1. Pegue el **identificador de implementación** que copió al registrar la herramienta en Schoology y seleccione **Siguiente**.
1. Revise y guarde los cambios. Se mostrará un mensaje al registrarse correctamente.
1. Los detalles del registro también se pueden revisar seleccionando el botón **Ver inquilinos LTI** en la página principal.

Después de completar estos pasos, los educadores podrán usar la aplicación LTI de reuniones de Teams.
