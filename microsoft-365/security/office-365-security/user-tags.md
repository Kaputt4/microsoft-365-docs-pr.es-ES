---
title: Etiquetas de usuario en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a identificar grupos específicos de usuarios con etiquetas de usuario en Microsoft Defender para Office 365 Plan 2. El filtrado de etiquetas está disponible en alertas, informes e investigaciones en Microsoft Defender para Office 365 identificar rápidamente a los usuarios etiquetados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3ac53891e0eb106ab3681251cc4cb8c969b51f8a
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083121"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Etiquetas de usuario en Microsoft Defender para Office 365

> [!NOTE]
> La característica de etiquetas de usuario está en Versión preliminar, no está disponible para todos y está sujeta a cambios. Para obtener información acerca de la programación de lanzamiento, consulte el [mapa Microsoft 365 ruta de trabajo](https://www.microsoft.com/microsoft-365/roadmap).

Las etiquetas de usuario son identificadores de grupos específicos de usuarios en [Microsoft Defender para Office 365](defender-for-office-365.md). Hay dos tipos de etiquetas de usuario:

- **Etiquetas del** sistema: Actualmente, [las cuentas de prioridad](../../admin/setup/priority-accounts.md) son el único tipo de etiqueta del sistema.
- **Etiquetas personalizadas:** puede crear estas etiquetas de usuario usted mismo.

Si su organización tiene Defender para Office 365 Plan 2 (incluido en la suscripción o como complemento), puede crear etiquetas de usuario personalizadas además de usar la etiqueta cuentas de prioridad.

> [!NOTE]
> Actualmente, solo puede aplicar etiquetas de usuario a los usuarios de buzones.

Después de aplicar etiquetas del sistema o etiquetas personalizadas a los usuarios, puede usar esas etiquetas como filtros en alertas, informes e investigaciones:

- [Alertas](alerts.md)
- [Directivas de alerta personalizadas](../../compliance/alert-policies.md#viewing-alerts)
- [Explorador de amenazas y detecciones en tiempo real](threat-explorer.md)
- [Página de la entidad de correo electrónico](mdo-email-entity-page.md#other-innovations)
- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
- [Vistas de campañas](campaigns.md)
- Para las cuentas de prioridad, puede usar el [informe](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) Problemas de correo electrónico para cuentas de prioridad en el Centro Exchange administración (EAC).

En este artículo se explica cómo configurar etiquetas de usuario en el portal Microsoft 365 Defender usuario. No hay cmdlets en Microsoft 365 Defender portal para administrar etiquetas de usuario.

Para ver cómo las etiquetas de usuario forman parte de la estrategia para ayudar a proteger las cuentas de usuario de alto impacto, vea Recomendaciones de seguridad para cuentas [de prioridad en Microsoft 365](security-recommendations-for-priority-accounts.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com/>. Para ir directamente a la **página Etiquetas de** usuario, abra <https://security.microsoft.com/securitysettings/userTags> .

- Debe tener asignados permisos en el portal de Microsoft 365 Defender para poder realizar los procedimientos descritos en este artículo:
  - Para crear, modificar y eliminar etiquetas de usuario, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.
  - Para agregar y quitar miembros de etiquetas de usuario existentes, debe ser miembro de los grupos de roles Administración de la **organización,** Administrador de seguridad **o** Operador de seguridad 
  - Para obtener acceso de solo lectura a las etiquetas de usuario, debe ser miembro de los grupos de roles **Lector global** o **Lector de** seguridad.

  Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

  > [!NOTE]
  >
  > - Agregar usuarios al rol Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el _portal_ de Microsoft 365 Defender y permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - La administración de etiquetas de usuario está controlada por los roles **Lector de** etiquetas y **Administrador de etiquetas.**

- También puede administrar y supervisar cuentas de prioridad en el Centro de administración de Microsoft 365. Para obtener instrucciones, vea [Administrar y supervisar cuentas de prioridad](../../admin/setup/priority-accounts.md).

- Para obtener información sobre cómo proteger _cuentas con privilegios_ (cuentas de administrador), vea [este tema](/azure/architecture/framework/security/critical-impact-accounts).

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a>Usar el portal Microsoft 365 Defender para crear etiquetas de usuario

1. En el portal Microsoft 365 Defender, vaya **a** Configuración \> **Correo electrónico & etiquetas de usuario de** \> **colaboración.**

2. En la **página Etiquetas de** usuario, haga clic ![ en Crear icono de etiqueta Crear ](../../media/m365-cc-sc-create-icon.png) **etiqueta**.

3. El **Asistente para crear** etiquetas se abre en un nuevo menú desplegable. En la **página Definir etiqueta,** configure las siguientes opciones:
   - **Nombre:** escriba un nombre descriptivo único para la etiqueta. Este es el valor que verá y usará. Tenga en cuenta que no puede cambiar el nombre de una etiqueta después de crearla.
   - **Descripción:** escriba una descripción opcional para la etiqueta.

   Cuando termine, haga clic en **Siguiente**.

4. En la página Asignar **miembros,** realice uno de los pasos siguientes:
   - Haga ![ clic en Agregar miembros icono Agregar ](../../media/m365-cc-sc-create-icon.png) **miembros**. En el menú desplegable que aparece, siga uno de los pasos siguientes para agregar usuarios o grupos individuales:
     - Haga clic en el cuadro y desplácese por la lista para seleccionar un usuario o grupo.
     - Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario o grupo.
     - Para agregar valores adicionales, haga clic en un área vacía del cuadro.
     - Para quitar entradas individuales, haga clic en ![Quitar icono de entrada](../../media/m365-cc-sc-remove-selection-icon.png) junto a la entrada del cuadro.
     - Para quitar todas las entradas, haga clic en Quitar icono de entrada en el elemento Usuarios nn seleccionados y ![ ](../../media/m365-cc-sc-remove-selection-icon.png) **nn grupos** situado debajo del cuadro.

     Cuando haya terminado, haga clic en **Agregar**.

     Back on the **Assign members** page, you can also remove entries by clicking Delete icon next to ![ the ](../../media/m365-cc-sc-delete-icon.png) entry.

   - Haga **clic en** Importar para seleccionar un archivo de texto que contenga las direcciones de correo electrónico de los usuarios o grupos. Asegúrese de que el archivo de texto contiene una entrada por línea.

   Cuando termine, haga clic en **Siguiente**.

5. En la **página Revisar etiqueta** que aparece, revisa la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar** y, a continuación, haga clic **en Listo.**

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a>Usar el portal Microsoft 365 Defender para ver etiquetas de usuario

1. En el portal Microsoft 365 Defender, vaya **a** Configuración \> **Correo electrónico & etiquetas de usuario de** \> **colaboración.**

2. En la **página Etiquetas de** usuario, se muestran las siguientes propiedades en la lista de etiquetas de usuario:

   - **Tag:** el nombre de la etiqueta de usuario. Tenga en cuenta que esto incluye la etiqueta del sistema de cuentas **de prioridad** integrada.
   - **Se aplica a**: El número de miembros
   - **Última modificación**
   - **Fecha de creación**

3. Al seleccionar una etiqueta de usuario haciendo clic en el nombre, los detalles se muestran en un control desplegable.

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a>Usar el portal Microsoft 365 Defender para modificar etiquetas de usuario

1. En el portal Microsoft 365 Defender, vaya **a** Configuración \> **Correo electrónico & etiquetas de usuario de** \> **colaboración.**

2. En la **página Etiquetas de** usuario, seleccione la etiqueta de usuario de la lista y, a continuación, haga clic en Editar icono ![ de etiqueta Editar ](../../media/m365-cc-sc-edit-icon.png) **etiqueta**.

3. En el control desplegable de detalles que aparece, el mismo asistente y la misma configuración están disponibles como se describe en la sección Usar el [portal de Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-user-tags) para crear etiquetas de usuario anteriormente en este artículo.

   **Notas**:

   - La **página Definir etiqueta** no está  disponible para la etiqueta del sistema de cuentas de prioridad integrada, por lo que no puede cambiar el nombre de esta etiqueta ni cambiar la descripción.
   - No puede cambiar el nombre de una etiqueta personalizada, pero puede cambiar la descripción.

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a>Usar el portal Microsoft 365 Defender para quitar etiquetas de usuario

> [!NOTE]
> No puede quitar la etiqueta del sistema de cuenta de **prioridad** integrada.

1. En el portal Microsoft 365 Defender, vaya **a** Configuración \> **Correo electrónico & etiquetas de usuario de** \> **colaboración.**

2. En la **página Etiquetas de** usuario, seleccione la etiqueta de usuario de la lista y, a continuación, haga clic en Eliminar icono ![ de etiqueta Eliminar ](../../media/m365-cc-sc-delete-icon.png) **etiqueta**.

3. Lea la advertencia en el cuadro de diálogo de confirmación que aparece y, a continuación, haga clic **en Sí, quite**.
