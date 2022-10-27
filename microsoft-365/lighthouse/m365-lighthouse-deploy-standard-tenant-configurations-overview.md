---
title: Información general sobre el uso de líneas base de Microsoft 365 Lighthouse para implementar configuraciones de inquilino estándar
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms.reviewer: shcallaw, kywirpel
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre el uso de líneas base para implementar configuraciones de inquilino estándar.
ms.openlocfilehash: 089a1cc932e13c12786337d0a1fa636f0ef4e138
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68729927"
---
# <a name="overview-of-using-microsoft-365-lighthouse-baselines-to-deploy-standard-tenant-configurations"></a>Información general sobre el uso de líneas base de Microsoft 365 Lighthouse para implementar configuraciones de inquilino estándar 

Microsoft 365 Lighthouse líneas base proporcionan una manera repetible y escalable de administrar la configuración de seguridad de Microsoft 365 en varios inquilinos de clientes. Las líneas base proporcionan configuraciones de inquilino estándar que implementan directivas de seguridad básicas y estándares de cumplimiento que mantienen a los usuarios, dispositivos y datos de los inquilinos seguros.

Puede ver la línea base predeterminada y sus pasos de implementación desde Lighthouse. Para aplicar una línea base a un inquilino, seleccione **Inquilinos** en el panel de navegación izquierdo y, a continuación, seleccione un inquilino. A continuación, vaya a la pestaña **Plan de implementación** para comenzar la implementación.

## <a name="lighthouse-baseline"></a>Línea base de Lighthouse

Las configuraciones de línea base de Lighthouse están diseñadas para asegurarse de que todos los inquilinos administrados son seguros y compatibles. Seleccione **Líneas base** en el panel de navegación izquierdo para ver la línea base predeterminada que se aplica a todos los inquilinos. Para ver los pasos de implementación incluidos en la línea base predeterminada, seleccione **Ver línea base** para abrir la página **Línea base predeterminada** . Seleccione cualquiera de los pasos de implementación para ver los detalles de la implementación y el impacto del usuario.

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Captura de pantalla de la página Línea base predeterminada.":::

### <a name="default-lighthouse-configurations"></a>Configuraciones predeterminadas de Lighthouse

| Configuración de línea base | Descripción |
|--|--|
| Requerir MFA para administradores | Directiva de acceso condicional que requiere autenticación multifactor para todos los administradores. Es necesario para todas las aplicaciones en la nube. Para obtener más información sobre esta línea base, vea [Acceso condicional: Requerir MFA para todos los administradores](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa).|
| Requerir MFA para los usuarios finales | Directiva de acceso condicional que requiere autenticación multifactor para todos los usuarios.  Es necesario para todas las aplicaciones en la nube. Para obtener más información sobre esta línea base, vea [Acceso condicional: Requerir MFA para todos los usuarios](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa). |
| Bloquear la autenticación heredada | Una directiva de acceso condicional para bloquear la autenticación de cliente heredada. Para obtener más información sobre esta línea base, consulte [Bloquear la autenticación heredada en Azure AD con acceso condicional](/azure/active-directory/conditional-access/block-legacy-authentication).|
| Configuración de la inscripción de dispositivos | La inscripción de dispositivos permite que los dispositivos de inquilino se inscriban en Microsoft Endpoint Manager y proporcionen visibilidad de Endpoint Analytics a los dispositivos a través de la supervisión del estado del dispositivo. Esta configuración se realiza mediante la configuración de la inscripción automática entre Azure Active Directory y Microsoft Endpoint Manager. Para obtener más información acerca de esta línea base, consulte [Configuración de la inscripción para dispositivos Windows](/mem/intune/enrollment/windows-enroll). |
| Configuración de la directiva de protección de aplicaciones | Un conjunto de directivas de protección que le permiten administrar y proteger los datos de la organización de un inquilino administrado dentro de una aplicación, independientemente de cualquier solución de administración de dispositivos móviles (MDM). Los datos de la organización se protegerán con o sin inscribir dispositivos en una solución MDM. |
| Configuración de Microsoft Defender para Empresas | Aprovisiona el inquilino para Microsoft Defender para Empresas e incorpora los dispositivos ya inscritos en Microsoft Endpoint Manager para Microsoft Defender para Empresas. Para obtener más información, consulte [¿Qué es Microsoft Defender para Empresas?](../security/defender-business/mdb-overview.md) |
| Configurar Exchange Online Protection y Microsoft Defender para Office 365 | Directiva para aplicar directivas recomendadas contra correo no deseado, antimalware, anti phishing, vínculos seguros y directivas de datos adjuntos seguros a los inquilinos Exchange Online buzones. |
| Configuración de Microsoft Defender Antivirus para Windows 10 y versiones posteriores | Un perfil de configuración de dispositivo para dispositivos Windows con la configuración preconfigurada Microsoft Defender Antivirus. Para obtener más información sobre esta línea base, vea [Configurar Microsoft Defender para punto de conexión en Intune](/mem/intune/protect/advanced-threat-protection-configure).|
| Configuración de Microsoft Defender Firewall para Windows 10 y versiones posteriores | Una directiva de firewall para ayudar a proteger los dispositivos mediante la prevención del tráfico de red no deseado y no autorizado. Para obtener más información sobre esta línea base, consulte [Procedimientos recomendados para configurar Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/best-practices-configuring).  |
| Configuración de una directiva de cumplimiento de dispositivos para Windows 10 y versiones posteriores | Una directiva de dispositivo Windows con la configuración preconfigurada para cumplir los requisitos básicos de cumplimiento. Para obtener más información sobre esta línea base, consulte [Acceso condicional: Requerir dispositivo unido a Azure AD híbrido o compatible](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device). |
| Configurar Microsoft Edge  | Una directiva de explorador de Microsoft Edge para Windows 10 o posterior con la configuración preconfigurada para mantenerse protegida frente a estafas de suplantación de identidad (phishing) y software malintencionado. Esta directiva también permite a Microsoft Edge guardar y supervisar contraseñas de forma segura y sugerir contraseñas seguras cuando sea necesario. |

## <a name="deployment-plans"></a>Planes de implementación

Cada inquilino activo tiene un plan de implementación que incluye los pasos de implementación de la línea base Microsoft 365 Lighthouse. Para acceder al plan de implementación de un inquilino, seleccione un inquilino activo en la lista de la página **Inquilinos** y, a continuación, seleccione la pestaña **Plan de implementación** .

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/deployment-plan-tab.png" alt-text="Captura de pantalla de la pestaña Plan de implementación.":::

La pestaña Plan de implementación incluye la siguiente información:


|Columna  |Descripción  |
|---------|---------|
|Paso de implementación     |  Descripción del paso de implementación.       |
|Estado     |Estado del paso de implementación.         |
|Línea base     |Línea base desde la que se deriva el paso de implementación.         |
|Categoría     | Si el paso de implementación está asociado a la administración de dispositivos, identidades o datos.        |
|Actualizado por última vez    | Fecha en la que se actualizó por última vez el paso de implementación.        |


La pestaña Plan de implementación también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar los datos del paso de implementación a un archivo de valores separados por comas (.csv) de Excel.
- **Actualizar:** Seleccione esta opción para recuperar los datos del paso de implementación más actuales.
- **Búsqueda:** Escriba palabras clave para localizar rápidamente un paso de implementación específico en la lista.

## <a name="deployment-steps-and-processes"></a>Pasos y procesos de implementación

El plan de implementación de cada inquilino incluye los pasos de implementación de la línea base de Microsoft 365 Lighthouse. Cada paso de implementación incluye uno o varios procesos que deben completarse. Cuando un nuevo inquilino se activa, debe completar las actividades de implementación asociadas a los pasos y procesos de implementación.

Para cada paso de implementación, puede realizar las siguientes acciones:

|Acción  |Descripción  |
|---------|---------|
| Compartir    |  Permite que el contenido del paso de implementación se comparta a través de un vínculo o por correo electrónico.    |
| Revisión e implementación    |  Permite al usuario: <ul><li>Cuando se admita, compare los valores de configuración del paso de implementación con los valores de las directivas existentes sin implementar la configuración en el inquilino.<br>Los siguientes pasos de implementación admiten la comparación:</br><ul><li>Configuración de una directiva de cumplimiento de dispositivos para Windows 10 y versiones posteriores</li><li>Requerir MFA para los usuarios finales</li><li>Requerir MFA para administradores</li><li>Bloquear la autenticación heredada</li></ul></li> <li>Implemente la configuración en el inquilino.</li></ul>**Nota:** Los pasos que no admiten la capacidad de comparar sin implementar la configuración en el inquilino le permitirán revisar los valores de configuración e implementarlos.|
| Actualización del estado del plan de acción    |  Permite al usuario notificar el estado de su plan de acción para el paso de implementación.      |

## <a name="related-content"></a>Contenido relacionado

[Implementar líneas base Microsoft 365 Lighthouse](m365-lighthouse-deploy-baselines.md) (artículo)\
[Directivas de acceso condicional comunes](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) (artículo)\
[Preguntas más frecuentes sobre Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (artículo)
