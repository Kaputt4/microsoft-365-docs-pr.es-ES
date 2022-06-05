---
title: Aumento de la protección contra amenazas para Microsoft 365 Empresa Premium
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- admindeeplinkMAC
- admindeeplinkEXCHANGE
- admindeeplinkSPO
search.appverid:
- BCS160
- MET150
description: Obtenga ayuda para aumentar el nivel de protección en Microsoft 365 Empresa Premium
ms.openlocfilehash: dfbde871e31bd4c8e47fb9365ad4da7a9a1f6226
ms.sourcegitcommit: c216ffa5da8f431e4380bb133a234ae7d94144c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2022
ms.locfileid: "65893193"
---
# <a name="increase-threat-protection-for-microsoft-365-business-premium"></a>Aumento de la protección contra amenazas para Microsoft 365 Empresa Premium

En este objetivo, aumentará la protección contra amenazas con Microsoft 365 Empresa Premium. Es fundamental proteger su negocio contra phishing, malware y otras amenazas. Este objetivo incluye información sobre:

- [Directivas de seguridad preestablecidas](#review-and-apply-preset-security-policies) que pueden ahorrar mucho tiempo en la instalación y configuración.
- [Directivas de seguridad personalizadas](#create-custom-security-policies) que puede definir para satisfacer sus necesidades empresariales
- Cómo [ajustar la configuración de uso compartido para archivos y carpetas de SharePoint y OneDrive](#set-sharing-settings-for-sharepoint-and-onedrive-files-and-folders).
- [Directivas de alerta](#review-your-alert-policies) que supervisan archivos específicos y cómo se usan.

## <a name="review-and-apply-preset-security-policies"></a>Revisión y aplicación de directivas de seguridad preestablecidas

La suscripción incluye [directivas de seguridad preestablecidas](../security/office-365-security/preset-security-policies.md) que usan la configuración recomendada para la protección contra correo no deseado, antimalware y contra phishing. De forma predeterminada, la protección integrada está habilitada; sin embargo, considere la posibilidad de aplicar protección estándar o estricta para aumentar la seguridad.

:::image type="content" source="media/m365bp-presetsecuritypolicies.png" alt-text="Captura de pantalla de las directivas de seguridad preestablecidas.":::

> [!NOTE]
> Las directivas de seguridad preestablecidas no son lo mismo que [los valores predeterminados de seguridad](m365bp-conditional-access.md#security-defaults). Normalmente, usará primero *o bien* los valores predeterminados de seguridad *o* [el acceso condicional](m365bp-conditional-access.md#conditional-access) y, a continuación, agregará las directivas de seguridad. [Las directivas de seguridad preestablecidas](#what-are-preset-security-policies) simplifican el proceso de agregar las directivas de seguridad. También puede [agregar sus propias directivas personalizadas](#create-custom-security-policies). 

### <a name="what-are-preset-security-policies"></a>¿Qué son las directivas de seguridad preestablecidas?

Las directivas de seguridad preestablecidas proporcionan protección para el contenido de sus correos electrónicos y colaboraciones. Estas directivas constan de:

- *Perfiles*, que determinan el nivel de protección
- *Directivas* (como antispam, antimalware, antiphishing, configuración de suplantación, suplantación, datos adjuntos seguros y vínculos seguros)
- *Configuración de directivas* (como grupos, usuarios o dominios para recibir las directivas y las excepciones)

En la tabla siguiente se resumen los niveles de protección y los tipos de directivas preestablecidos.

| Nivel de protección | Descripción |
|:---|:---|
| **Protección estándar** <br/>(*recomendado para la mayoría de las empresas*) | La protección estándar usa un perfil básico adecuado para la mayoría de los usuarios. La protección estándar incluye directivas antispam, antimalware, antiphishing, configuración de suplantación, vínculos seguras y directivas de datos adjuntos seguros.  |
| **Protección estricta**  | La protección estricta incluye los mismos tipos de directivas que la protección estándar, pero con una configuración más estricta. Si su empresa debe cumplir requisitos o regulaciones de seguridad adicionales, considere la posibilidad de aplicar una protección estricta a al menos los usuarios prioritarios o los objetivos de alto valor. |
| **Protección integrada** | Protege contra vínculos y datos adjuntos malintencionados en el correo electrónico. La protección integrada está habilitada y se aplica a todos los usuarios de forma predeterminada.  |

> [!TIP]
> Puede especificar los usuarios, grupos y dominios para recibir directivas preestablecidas. También puede definir determinadas excepciones, pero no puede cambiar las directivas preestablecidas. Si desea usar diferentes configuraciones para las directivas de seguridad, puede crear sus propias directivas personalizadas para satisfacer las necesidades de su empresa.

### <a name="policy-order-of-priority"></a>Orden de prioridad de la directiva

Si a los usuarios se les asignan varias directivas, se usa un orden de prioridad para aplicar las directivas. El orden de prioridad funciona de la siguiente manera:

1. **La protección estricta** recibe la prioridad más alta e invalida todas las demás directivas.

2. **Protección estándar** 

3. **Directivas de seguridad personalizadas**

4. **La protección integrada** recibe la prioridad más baja y se invalida por la protección estricta, la protección estándar y las directivas personalizadas.

La protección estricta invalida el resto de directivas y las demás directivas invalidan la protección integrada. 

Para obtener más información sobre las directivas de seguridad preestablecidas, consulte [De qué están hechas las directivas de seguridad preestablecidas](../security/office-365-security/preset-security-policies.md#what-preset-security-policies-are-made-of).

### <a name="how-do-i-assign-preset-security-policies-to-users"></a>¿Cómo asigno directivas de seguridad preestablecidas a los usuarios?

> [!IMPORTANT]
> Antes de empezar, asegúrese de que tiene uno de los siguientes roles asignados en Exchange Online (que se incluye en la suscripción):
> 
> - Administrador global
> - Administración de la organización
> - Administrador de seguridad
> 
> Para obtener más información, consulte [Permisos en Exchange Online](/exchange/permissions-exo/permissions-exo) y [Acerca de los roles de administrador](../admin/add-users/about-admin-roles.md).

Para asignar directivas de seguridad preestablecidas, siga estos pasos:

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Directivas de seguridad prestablecidas** en la sección **Directivas con plantilla**. (Para ir directamente a la página de **Directivas de seguridad preestablecidas**, use <https://security.microsoft.com/presetSecurityPolicies>.)

2. En la página **Directivas de seguridad preestablecidas**, en la sección **Protección estándar** o **Protección estricta**, cambie el botón de alternancia de **Deshabilitado** a **Habilitado** y, a continuación, seleccione **Administrar**.

3. El asistente **Aplicar protección estándar** o **Aplicar protección estricta** se inicia en un control flotante. En la página **Protecciones de EOP que se aplican a**, identifique los destinatarios internos a los que se aplican las directivas (condiciones de destinatario):
   - **Usuarios**
   - **Grupos**
   - **Dominios**

   Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en el icono **Quitar** junto al valor.

   Para los usuarios o grupos, puede utilizar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de la cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados. Para los usuarios, introduzca un asterisco (\*) por sí mismo para ver todos los valores disponibles.

   Para especificar una exclusión, active la casilla **Excluir estos usuarios, grupos y dominios** y, a continuación, especifique los usuarios, grupos o dominios que se van a excluir.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **Defender para Office 365 las protecciones se aplican a** para identificar los destinatarios internos a los que se aplican las directivas (condiciones de destinatario). Especifique usuarios, grupos y dominios igual que hizo en el paso anterior.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **Revisar y confirmar los cambios**, compruebe las selecciones y, a continuación, seleccione **Confirmar**.

> [!TIP]
> Para obtener más información sobre la asignación de directivas de seguridad preestablecidas, consulte los artículos siguientes:
> - [Asignación de directivas de seguridad preestablecidas a los usuarios](../security/office-365-security/preset-security-policies.md#assign-preset-security-policies-to-users)
> - [Configuración recomendada para el contenido de correo electrónico y colaboración](../security/office-365-security/recommended-settings-for-eop-and-office365.md) (Microsoft 365 Empresa Premium incluye Exchange Online Protection y Microsoft Defender para Office 365 Plan 1)

## <a name="create-custom-security-policies"></a>Creación de directivas de seguridad personalizadas

Las [directivas de seguridad preestablecidas](#what-are-preset-security-policies) descritas anteriormente en este artículo proporcionan una protección segura para la mayoría de las empresas. Sin embargo, no se limita solo al uso de directivas de seguridad preestablecidas. Puede definir sus propias directivas de seguridad personalizadas para satisfacer las necesidades de su empresa. 

Use nuestra guía de inicio rápido, [Protección contra amenazas](../security/office-365-security/protect-against-threats.md), para empezar a crear sus propias directivas personalizadas. La guía no solo le guía a través de cómo configurar sus propias directivas de seguridad, sino que también proporciona la configuración recomendada que se usará como punto de partida para:

- [Protección contra el malware](../security/office-365-security/protect-against-threats.md#part-1---anti-malware-protection-in-eop)
- [Protección avanzada contra el phishing](../security/office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
- [Protección contra correo no deseado](../security/office-365-security/protect-against-threats.md#part-3---anti-spam-protection-in-eop)
- [Habilitar vínculos seguros y datos adjuntos seguros](../security/office-365-security/protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)

## <a name="set-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>Establecer la configuración de uso compartido para archivos y carpetas de SharePoint y OneDrive

De forma predeterminada, los niveles de uso compartido se establecen en el nivel más permisivo para SharePoint y OneDrive. Se recomienda cambiar la configuración predeterminada para proteger mejor su empresa.

1. Vaya a <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Uso compartido** en el Centro de administración de SharePoint</a>, e inicie sesión con una cuenta que tenga [permisos de administrador](/sharepoint/sharepoint-admin-role) en su organización.
 
2. En **Uso compartido externo**, especifique el nivel de uso compartido. (Se recomienda usar **Menos permisivo** para evitar el uso compartido externo).

3. En **Vínculos de archivos y carpetas**, seleccione una opción (por ejemplo, **Personas específicas**). A continuación, elija si desea conceder permisos de Vista o Edición de forma predeterminada para los vínculos compartidos (por ejemplo, **Ver**).

4. En **Otras opciones**, seleccione las opciones que desea usar.

5. A continuación, elija **Guardar**.

> [!TIP]
> Para más información sobre esta configuración, consulte[Administrar configuración de uso compartido.](/sharepoint/turn-external-sharing-on-or-off).

## <a name="review-your-alert-policies"></a>Revisión de las directivas de alerta

Las directivas de alerta son útiles para realizar un seguimiento de las actividades de usuario y administrador, posibles amenazas de malware e incidentes de pérdida de datos en su empresa. La suscripción incluye un conjunto de directivas predeterminadas, pero también puede crear otras personalizadas. Por ejemplo, si almacena un archivo importante en SharePoint que no quiere que nadie comparta externamente, puede crear una notificación que le avise si alguien lo comparte.

En la imagen siguiente se muestran algunas de las directivas predeterminadas que se incluyen con Microsoft 365 Empresa Premium.

![Directivas de alerta predeterminadas incluidas con Microsoft 365.](../media/alertpolicies.png)

### <a name="view-your-alert-policies"></a>Visualización de las directivas de alerta

1. Vaya al portal de cumplimiento de Microsoft Purview en [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión.

2. En el panel de navegación, elija **Directivas** y, a continuación, elija **Directivas de alerta**.

3. Seleccione una directiva individual para ver más detalles o editarla. En la imagen siguiente se muestra una lista de directivas de alerta con una directiva seleccionada:

   :::image type="content" source="media/selected-alert-policy.png" lightbox="media/selected-alert-policy.png" alt-text="Captura de pantalla de una directiva de alerta seleccionada.":::

> [!TIP]
> Para obtener más información, consulte [Directivas de alerta](../compliance/alert-policies.md).

### <a name="how-to-view-alerts"></a>Cómo ver alertas

En función de la alerta específica, puede ver las alertas en el portal de Microsoft 365 Defender o en el portal de cumplimiento Microsoft Purview.

| Tipo de la alerta.  | Qué hacer  |
|---------|---------|
| Alerta de seguridad, como cuando un usuario hace clic en un vínculo malintencionado, se notifica un correo electrónico como malware o phish, o se detecta que un dispositivo contiene malware.     | Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a> y, en **Correo electrónico & colaboración**, seleccione **Directivas & reglas** > **Directiva de alertas**. Como alternativa, puede ir directamente a <https://security.microsoft.com/alertpolicies>. |
| Alerta de cumplimiento, como cuando un usuario comparte información delicada o confidencial (alerta de prevención de pérdida de datos) o hay un volumen inusual de uso compartido de archivos externos (alerta de gobernanza de la información)    | Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Portal de cumplimiento de Microsoft Purview</a> y, a continuación, seleccione **Directivas** > **Alerta** > **Directivas de alerta**.  |

Para obtener más información, vea [Ver alertas](../compliance/alert-policies.md#view-alerts).

## <a name="disable-or-manage-calendar-sharing"></a>Deshabilitar o administrar el uso compartido del calendario

Puede evitar que las personas de su organización compartan sus calendarios. También puede administrar qué nivel de detalle pueden compartir. Por ejemplo, puede restringir el uso compartido solo a horas de mucho o poco trabajo.

1. Vaya a [Configuración de la organización en el Centro de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2053743) e inicie sesión.

2. Elija **Calendario** y elija si las personas de su organización pueden compartir sus calendarios con personas de fuera que tengan Office 365 o Exchange, o con cualquier persona.

   Se recomienda borrar la opción de **Uso compartido externo**.

   Si elige la opción compartir con cualquier persona, puede decidir si se puede compartir la información de libre/ocupado.

3. Elija **Guardar cambios** en la parte inferior de la página.

   En la imagen siguiente se muestra que no se permite el uso compartido de calendarios.

   ![Captura de pantalla en la que se muestra el uso compartido del calendario externo como no permitido.](../media/nocalendarsharing.png)

   En la imagen siguiente se muestra la configuración cuando se permite el uso compartido de calendarios con un vínculo de correo electrónico con solo información de libre/ocupado.

   ![Captura de pantalla del uso compartido de libre/ocupado del calendario con cualquier usuario.](../media/sharefreebusy.png)

Si los usuarios pueden compartir sus calendarios, consulte [estas instrucciones](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) sobre cómo compartir desde Outlook en la Web.

## <a name="next-steps"></a>Siguientes pasos

Ahora vamos a [**configurar esos dispositivos BYOD no administrados**](m365bp-devices-overview.md).
