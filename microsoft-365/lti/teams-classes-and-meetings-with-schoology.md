---
title: Integración de reuniones de Microsoft Teams con Schoology LMS
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: microsoft-365-business
ms.collection:
- M365-modern-desktop
- m365initiative-edu
ms.localizationpriority: medium
description: Cree y administre reuniones de Teams con Microsoft Learning Tools Interoperability (LTI) para Schoology LMS.
ms.openlocfilehash: 9a2aaf2780bfa79324b7292e0383e595cec2e0f1
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68471868"
---
# <a name="integrate-microsoft-teams-meetings-with-schoology-lms"></a>Integración de reuniones de Microsoft Teams con Schoology LMS

En esta guía se proporcionan los pasos del administrador de TI para registrar la aplicación LTI de reuniones de Teams en Schoology.

Para obtener información general sobre Microsoft LTI, consulte [Integración de productos de Microsoft con el sistema de administración de aprendizaje (LMS).](index.md)

> [!NOTE]
> La persona que realiza esta integración debe ser administrador de Schoology. Sin embargo, los usuarios de Schoology con acceso al **Centro de aplicaciones** de Schoology también pueden instalar la aplicación LTI de reuniones de Microsoft Teams.

## <a name="deploy-the-teams-meetings-lti-app-in-schoology"></a>Implementación de la aplicación LTI de reuniones de Teams en Schoology

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
