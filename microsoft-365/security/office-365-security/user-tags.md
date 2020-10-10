---
title: Etiquetas de usuario en la ATP de Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a identificar grupos específicos de usuarios con etiquetas de usuario en Office 365 ATP plan 2. El filtrado de etiquetas está disponible a través de alertas, informes e investigaciones en Office 365 ATP para identificar rápidamente los usuarios etiquetados.
ms.openlocfilehash: 475bf976a71fb688df8db9ac25f3b397c078d79a
ms.sourcegitcommit: 260c69fa31a898428d51cfdbd762c5f0213c403c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "48417276"
---
# <a name="user-tags-in-office-365-atp"></a>Etiquetas de usuario en la ATP de Office 365

> [!NOTE]
> La característica de etiquetas de usuario está en versión preliminar, no está disponible para todos los usuarios y está sujeta a cambios. Para obtener información sobre la programación de versiones, consulte el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

Las etiquetas de usuario son identificadores para grupos de usuarios específicos en [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md). Hay dos tipos de etiquetas de usuario:

- **Etiquetas del sistema**: Actualmente, [cuentas prioritarias](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) es el único tipo de etiqueta de sistema.
- **Etiquetas personalizadas**: usted mismo crea estas etiquetas de usuario.

Si su organización tiene Office 365 ATP plan 2 (incluido en su suscripción o como complemento), puede crear etiquetas de usuario personalizadas además de usar la etiqueta accounts Priority.

Después de aplicar etiquetas del sistema o etiquetas personalizadas a los usuarios, puede usar esas etiquetas como filtros en alertas, informes e investigaciones:

- [Alertas del centro de seguridad & cumplimiento](alerts.md)
- [Explorador de amenazas y detecciones en tiempo real](threat-explorer.md)
- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
- [Vistas de campañas](campaigns.md)

En este artículo se explica cómo configurar etiquetas de usuario en el centro de seguridad & cumplimiento. No hay cmdlets en el centro de seguridad & cumplimiento para administrar las etiquetas de usuario.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **etiquetas de usuario** , Abra <https://protection.office.com/userTags> .

- Para crear, modificar o quitar **etiquetas de usuario personalizadas**, debe ser miembro de los grupos de funciones **Administración** de la organización o **Administrador de seguridad** en el centro de seguridad & cumplimiento. Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

- Para configurar las cuentas prioritarias (etiquetas del sistema), debe ser [administrador global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o [Administrador de Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).

  También puede administrar y supervisar cuentas prioritarias en el centro de administración de Microsoft 365. Para obtener instrucciones, consulte [Manage and monitor Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).

## <a name="use-the-security-center-to-create-user-tags"></a>Usar el centro de seguridad para crear etiquetas de usuario

1. En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.

2. En la página **etiquetas de usuario** que se abre, haga clic en **crear etiqueta**.

3. El Asistente para **crear etiquetas** se abre en una nueva volar hacia fuera. En la página **definir etiqueta** , configure las siguientes opciones:

   - **Name**: escriba un nombre único y descriptivo para la etiqueta. Este es el valor que verás y usarás.

   - **Descripción**: escriba una descripción opcional para la etiqueta.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **asignar buzones** , siga uno de estos pasos:

   - Haga clic en **Agregar buzones**. En la volar hacia fuera que aparece, realice uno de los siguientes pasos para agregar grupos o usuarios individuales:

     - Haga clic en el cuadro y desplácese por la lista para seleccionar un usuario o grupo.
     - Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario o grupo.
     - Para agregar más valores, haga clic en un área vacía del cuadro.
     - Para quitar entradas individuales del cuadro, haga clic en **quitar** ![ icono de eliminación ](../../media/scc-remove-icon.png) en el usuario o grupo en el cuadro.
     - Para quitar las entradas existentes de la lista situada debajo del cuadro, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación de la entrada.

     Cuando haya terminado, haga clic en **Agregar**.

   - Haga clic en **importar** para seleccionar un archivo de texto que contenga las direcciones de correo electrónico de los usuarios o grupos. Asegúrese de que el archivo de texto contenga una entrada por línea.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **revisar etiqueta** , revise la configuración. Puede hacer clic en **Editar** en la sección específica para realizar cambios.

   Cuando haya terminado, haga clic en **Enviar**.

## <a name="use-the-security-center-to-view-user-tags"></a>Usar el centro de seguridad para ver las etiquetas de usuario

1. En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.

2. En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver (no haga clic en la casilla de verificación).

3. En los detalles de solo lectura que aparecen, revise la configuración.

   Cuando haya terminado, haga clic en **Cerrar**.

## <a name="use-the-security-center-to-modify-user-tags"></a>Usar el centro de seguridad para modificar las etiquetas de usuario

1. En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.

2. En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver y, a continuación, haga clic en **Editar etiqueta**.

3. El Asistente para directivas se abre en una **etiqueta de edición** hacia fuera. Haga clic en **siguiente** para revisar y modificar la configuración.

   Cuando haya terminado, haga clic en **Enviar**.

## <a name="use-the-security-center-to-remove-user-tags"></a>Usar el centro de seguridad para quitar etiquetas de usuario

**Nota**: no se puede quitar la etiqueta de **cuenta** integrada con prioridad.

1. En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.

2. En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea quitar, haga clic en **Eliminar etiqueta**y, a continuación, seleccione **sí, quitar** en la advertencia que aparece.
