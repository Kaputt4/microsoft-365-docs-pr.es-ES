---
title: Etiquetas de usuario en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a identificar grupos específicos de usuarios con etiquetas de usuario en Microsoft Defender para Office 365 Plan 2. El filtrado de etiquetas está disponible en alertas, informes e investigaciones en Microsoft Defender para Office 365 para identificar rápidamente a los usuarios etiquetados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6f98dcfe3e8c44e852134e7a12def4ff78c1bcdd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207267"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Etiquetas de usuario en Microsoft Defender para Office 365

> [!NOTE]
> La característica de etiquetas de usuario está en Versión preliminar, no está disponible para todos y está sujeta a cambios. Para obtener información acerca de la programación de lanzamiento, consulte la guía [básica de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

Las etiquetas de usuario son identificadores para grupos específicos de usuarios en [Microsoft Defender para Office 365](defender-for-office-365.md). Hay dos tipos de etiquetas de usuario:

- **Etiquetas del** sistema: Actualmente, [las cuentas de prioridad](../../admin/setup/priority-accounts.md) son el único tipo de etiqueta del sistema.
- **Etiquetas personalizadas:** puede crear estas etiquetas de usuario usted mismo.

Si su organización tiene Defender para Office 365 Plan 2 (incluido en la suscripción o como complemento), puede crear etiquetas de usuario personalizadas además de usar la etiqueta de cuentas de prioridad.

Después de aplicar etiquetas del sistema o etiquetas personalizadas a los usuarios, puede usar esas etiquetas como filtros en alertas, informes e investigaciones:

- [Alertas en el Centro de seguridad & cumplimiento](alerts.md)
- [Explorador de amenazas y detecciones en tiempo real](threat-explorer.md)
- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
- [Vistas de campañas](campaigns.md)
- Para las cuentas de prioridad, puede usar el informe Problemas de correo electrónico [para cuentas de prioridad](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) en el Centro de administración de Exchange (EAC).

En este artículo se explica cómo configurar las etiquetas de usuario en el Centro de seguridad & cumplimiento. No hay cmdlets en el Centro de seguridad & cumplimiento para administrar etiquetas de usuario.

Para ver cómo las etiquetas de usuario forman parte de la estrategia para ayudar a proteger las cuentas de usuario de alto impacto, vea Recomendaciones de seguridad para cuentas de prioridad [en Microsoft 365](security-recommendations-for-priority-accounts.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la **página Etiquetas de** usuario, abra <https://protection.office.com/userTags> .

- Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:
  - Para crear, modificar y eliminar etiquetas de usuario, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.
  - Para agregar y quitar miembros de etiquetas de usuario existentes, debe ser miembro de los grupos de roles Administración de la **organización,** Administrador de seguridad **o** Operador de seguridad 
  - Para obtener acceso de solo lectura a las etiquetas de usuario, debe ser miembro de los grupos de roles **Lector global** o **Lector de** seguridad.

  Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  **Notas**:

  - Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - La administración de etiquetas de usuario está controlada por los roles **Lector de** etiquetas y **Administrador de etiquetas.**

- También puede administrar y supervisar cuentas de prioridad en el Centro de administración de Microsoft 365. Para obtener instrucciones, vea [Administrar y supervisar cuentas de prioridad](../../admin/setup/priority-accounts.md).

## <a name="use-the-security--compliance-center-to-create-user-tags"></a>Usar el Centro de seguridad & cumplimiento para crear etiquetas de usuario

1. En el Centro de seguridad & cumplimiento, vaya a **Administración de amenazas** \> **Etiquetas de usuario**.

2. En la **página Etiquetas de** usuario que se abre, haga clic **en Crear etiqueta**.

3. El **Asistente para crear** etiquetas se abre en un nuevo menú desplegable. En la **página Definir etiqueta,** configure las siguientes opciones:
   - **Nombre:** escriba un nombre descriptivo único para la etiqueta. Este es el valor que verá y usará.
   - **Descripción:** escriba una descripción opcional para la etiqueta.

   Cuando termine, haga clic en **Siguiente**.

4. En la página Asignar **usuarios,** siga uno de estos pasos:

   - Haga clic **en Agregar usuarios**. En el menú desplegable que aparece, siga uno de los pasos siguientes para agregar usuarios o grupos individuales:
     - Haga clic en el cuadro y desplácese por la lista para seleccionar un usuario o grupo.
     - Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario o grupo.
     - Para agregar valores adicionales, haga clic en un área vacía del cuadro.
     - Para quitar entradas individuales del cuadro, haga clic en **Quitar** icono Quitar del ![ usuario o grupo del ](../../media/scc-remove-icon.png) cuadro.
     - Para quitar las entradas existentes de la lista debajo del cuadro, haga clic **en Quitar** icono de ![ la ](../../media/scc-remove-icon.png) entrada.

     Cuando haya terminado, haga clic en **Agregar**.

   - Haga **clic en** Importar para seleccionar un archivo de texto que contenga las direcciones de correo electrónico de los usuarios o grupos. Asegúrese de que el archivo de texto contiene una entrada por línea.

   Cuando termine, haga clic en **Siguiente**.

5. En la **página Revisar etiqueta,** revisa la configuración. Puede hacer clic **en Editar** en la sección específica para realizar cambios.

   Cuando haya terminado, haga clic en **Enviar**.

## <a name="use-the-security--compliance-center-to-view-user-tags"></a>Usar el Centro de seguridad & cumplimiento para ver etiquetas de usuario

1. En el Centro de seguridad & cumplimiento, vaya a **Administración de amenazas** \> **Etiquetas de usuario**.

2. En la **página Etiquetas de** usuario que se abre, seleccione la etiqueta de usuario que desea ver (no haga clic en la casilla).

3. En los detalles de solo lectura que aparecen, revisa la configuración.

   Cuando haya terminado, haga clic en **Cerrar**.

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a>Usar el Centro de seguridad & cumplimiento para modificar las etiquetas de usuario

1. En el Centro de seguridad & cumplimiento, vaya a **Administración de amenazas** \> **Etiquetas de usuario**.

2. En la **página Etiquetas de** usuario que se abre, seleccione la etiqueta de usuario que desea ver y, a continuación, haga clic **en Editar etiqueta**.

3. El asistente para directivas se abre en un **control de salida de etiquetas** de edición. Haga **clic en** Siguiente para revisar y modificar la configuración.

   Cuando haya terminado, haga clic en **Enviar**.

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a>Usar el Centro de seguridad & cumplimiento para quitar etiquetas de usuario

**Nota:** No puede quitar la etiqueta de cuenta de **prioridad** integrada.

1. En el Centro de seguridad & cumplimiento, vaya a **Administración de amenazas** \> **Etiquetas de usuario**.

2. En la **página Etiquetas de** usuario que se abre, seleccione la etiqueta de usuario que desea quitar, haga clic en **Eliminar** etiqueta y, a continuación, seleccione **Sí,** quite en la advertencia que aparece.