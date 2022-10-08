---
title: Etiquetas de usuario en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/17/2021
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- m365-security
ms.custom: ''
description: Los administradores pueden aprender a identificar grupos específicos de usuarios con etiquetas de usuario en Microsoft Defender para Office 365 Plan 2. El filtrado de etiquetas está disponible en alertas, informes e investigaciones en Microsoft Defender para Office 365 para identificar rápidamente a los usuarios etiquetados.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 28e1df8bd94cb9829bc8c68e6f13e376cf54126c
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68066352"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Etiquetas de usuario en Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a:**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Las etiquetas de usuario son identificadores de grupos específicos de usuarios en [Microsoft Defender para Office 365](defender-for-office-365.md). Hay dos tipos de etiquetas de usuario:

- **Etiquetas del sistema**: actualmente, [las cuentas de prioridad](../../admin/setup/priority-accounts.md) son el único tipo de etiqueta del sistema.
- **Etiquetas personalizadas**: cree estas etiquetas de usuario usted mismo.

Si su organización tiene Defender para Office 365 plan 2 (incluido en la suscripción o como complemento), puede crear etiquetas de usuario personalizadas además de usar la etiqueta de cuentas de prioridad.

> [!NOTE]
> Actualmente, solo puede aplicar etiquetas de usuario a los usuarios del buzón.

Después de aplicar etiquetas del sistema o etiquetas personalizadas a los usuarios, puede usar esas etiquetas como filtros en alertas, informes e investigaciones:

- [Alertas](alerts.md)
- [Directivas de alertas personalizadas](../../compliance/alert-policies.md#view-alerts)
- [Explorador de amenazas y detecciones en tiempo real](threat-explorer.md)
- [Informe de usuario en peligro](view-email-security-reports.md#compromised-users-report)
- [Página de la entidad de correo electrónico](mdo-email-entity-page.md#other-innovations)
- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
- [Informe de remitentes y destinatarios principales](view-email-security-reports.md#top-senders-and-recipients-report)
- [Simulación de ataque](attack-simulation-training.md#target-users)
- [Vistas de campañas](campaigns.md)
- [Administración y envíos de usuarios](admin-submission.md)
- [Cuarentena](quarantine.md)
- En el caso de las cuentas de prioridad, puede usar los [problemas de Email para el informe de cuentas de prioridad](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) en el Centro de administración de Exchange (EAC).

En este artículo se explica cómo configurar etiquetas de usuario en el portal de Microsoft 365 Defender. No hay cmdlets en Microsoft 365 Defender portal para administrar las etiquetas de usuario.

Para ver cómo las etiquetas de usuario forman parte de la estrategia para ayudar a proteger las cuentas de usuario de alto impacto, consulte [Recomendaciones de seguridad para cuentas de prioridad en Microsoft 365](security-recommendations-for-priority-accounts.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Etiquetas de usuario** , use <https://security.microsoft.com/securitysettings/userTags>.

- Debe tener permisos asignados en el portal de Microsoft 365 Defender para poder realizar los procedimientos de este artículo:
  - Para crear, modificar y eliminar etiquetas de usuario personalizadas, debe ser miembro de los grupos de roles Administración de la **organización** o **Administrador de seguridad** .
  - Para agregar y quitar miembros de la etiqueta de sistema de cuenta de prioridad, debe ser miembro de los grupos de roles **Administrador de seguridad** y **Exchange Administración**.
  - Para agregar y quitar miembros de etiquetas de usuario personalizadas existentes, debe ser miembro de los grupos de roles Administración de la **organización** o **Administrador de seguridad** .
  - Para el acceso de solo lectura a las etiquetas de usuario, debe ser miembro de los grupos de roles **Lector global**, **Operador de seguridad** o **Lector de seguridad** .

  Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

  > [!NOTE]
  >
  > - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el portal de Microsoft 365 Defender _y_ permisos para otras características de Microsoft 365. Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - La administración de etiquetas de usuario se controla mediante los roles **Lector de etiquetas** y **Administrador de etiquetas** .

- También puede administrar y supervisar las cuentas de prioridad en el Centro de administración de Microsoft 365. Para obtener instrucciones, consulte [Administración y supervisión de cuentas de prioridad](../../admin/setup/priority-accounts.md).

- Para obtener información sobre cómo proteger _cuentas con privilegios_ (cuentas de administrador), consulte [este tema](/security/compass/critical-impact-accounts).

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a>Uso del portal de Microsoft 365 Defender para crear etiquetas de usuario

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Configuración** \> Email & **etiquetas de usuario** de **colaboración**\>. Para ir directamente a la página **Etiquetas de usuario** , use <https://security.microsoft.com/securitysettings/userTags>.

2. En la página **Etiquetas de usuario** , haga clic en el ![icono Crear etiqueta.](../../media/m365-cc-sc-create-icon.png) **Crear etiqueta**.

3. El Asistente **para crear etiquetas** se abre en un nuevo control flotante. En la página **Definir etiqueta** , configure los siguientes valores:
   - **Nombre**: escriba un nombre descriptivo único para la etiqueta. Este es el valor que verá y usará. Tenga en cuenta que no puede cambiar el nombre de una etiqueta después de crearla.
   - **Descripción**: escriba una descripción opcional para la etiqueta.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **Asignar miembros** , realice uno de los pasos siguientes:
   - Haga clic en ![el icono Agregar miembros.](../../media/m365-cc-sc-create-icon.png) **Agregar miembros**. En el control flotante que aparece, realice cualquiera de los pasos siguientes para agregar usuarios o grupos individuales:
     - Haga clic en el cuadro y desplácese por la lista para seleccionar un usuario o grupo.
     - Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario o grupo.
     - Para agregar valores adicionales, haga clic en un área vacía del cuadro.
     - Para quitar entradas individuales, haga clic en ![Icono Quitar entrada.](../../media/m365-cc-sc-remove-selection-icon.png) junto a la entrada del cuadro.
     - Para quitar todas las entradas, haga clic en ![el icono Quitar entrada.](../../media/m365-cc-sc-remove-selection-icon.png) en el elemento **Usuarios nn seleccionados y grupos nn** debajo del cuadro.

     Cuando haya terminado, haga clic en **Agregar**.

     De nuevo en la página **Asignar miembros** , también puede quitar entradas haciendo clic en ![el icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) junto a la entrada.

   - Haga clic en **Importar** para seleccionar un archivo de texto que contenga las direcciones de correo electrónico de los usuarios o grupos. Asegúrese de que el archivo de texto contiene una entrada por línea.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **Revisar etiqueta** que aparece, revise la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviary**, a continuación, haga clic en **Listo**.

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a>Uso del portal de Microsoft 365 Defender para ver las etiquetas de usuario

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Configuración** \> Email & **etiquetas de usuario** de **colaboración**\>. Para ir directamente a la página **Etiquetas de usuario** , use <https://security.microsoft.com/securitysettings/userTags>.

2. En la página **Etiquetas de usuario** , se muestran las siguientes propiedades en la lista de etiquetas de usuario:

   - **Etiqueta**: nombre de la etiqueta de usuario. Tenga en cuenta que esto incluye la etiqueta de sistema de **cuenta priority** integrada.
   - **Aplicado a**: número de miembros
   - **Última modificación**
   - **Fecha de creación**

3. Al seleccionar una etiqueta de usuario haciendo clic en el nombre, los detalles se muestran en un control flotante.

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a>Uso del portal de Microsoft 365 Defender para modificar las etiquetas de usuario

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Configuración** \> Email & **etiquetas de usuario** de **colaboración**\>. Para ir directamente a la página **Etiquetas de usuario** , use <https://security.microsoft.com/securitysettings/userTags>.

2. En la página **Etiquetas** de usuario, seleccione la etiqueta de usuario de la lista y, a continuación, haga clic en ![el icono Editar etiqueta.](../../media/m365-cc-sc-edit-icon.png) **Editar etiqueta**.

3. En el control flotante de detalles que aparece, el mismo asistente y la misma configuración están disponibles como se describe en [la sección Uso del portal de Microsoft 365 Defender para crear etiquetas de usuario](#use-the-microsoft-365-defender-portal-to-create-user-tags) anteriormente en este artículo.

   **Notas**:

   - La página **Definir etiqueta** no está disponible para la etiqueta de sistema de **cuenta** priority integrada, por lo que no puede cambiar el nombre de esta etiqueta ni cambiar la descripción.
   - No se puede cambiar el nombre de una etiqueta personalizada, pero puede cambiar la descripción.

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a>Uso del portal de Microsoft 365 Defender para quitar etiquetas de usuario

> [!NOTE]
> No se puede quitar la etiqueta de sistema de **cuenta** priority integrada.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Configuración** \> Email & **etiquetas de usuario** de **colaboración**\>. Para ir directamente a la página **Etiquetas de usuario** , use <https://security.microsoft.com/securitysettings/userTags>.

2. En la página **Etiquetas** de usuario, seleccione la etiqueta de usuario de la lista y, a continuación, haga clic en ![el icono Eliminar etiqueta.](../../media/m365-cc-sc-delete-icon.png) **Eliminar etiqueta**.

3. Lea la advertencia en el cuadro de diálogo de confirmación que aparece y, a continuación, haga clic en **Sí, quitar**.

## <a name="more-information"></a>Más información

[Configuración y revisión de cuentas de prioridad en Microsoft Defender para Office 365](configure-review-priority-account.md)
