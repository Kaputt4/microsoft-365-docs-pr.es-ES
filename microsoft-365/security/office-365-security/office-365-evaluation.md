---
title: Evaluar Microsoft Defender para Office 365
description: Defender para Office 365 en modo de evaluación crea directivas de correo electrónico de Defender para Office 365 que registra veredictos, como malware, pero no actúan en mensajes.
keywords: evaluar Office 365, Microsoft Defender para Office 365, evaluación de Office 365, probar office 365, Microsoft Defender, ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d16c0afc675ba759e392c9fe9a44c42b89dbad0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287658"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Evaluar Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> La evaluación de Microsoft Defender para Office 365 está en versión preliminar pública. Esta versión preliminar se proporciona sin un contrato de nivel de servicio. Es posible que algunas características no sean compatibles o que tengan funcionalidades restringidas.

Llevar a cabo una evaluación completa del producto de seguridad puede ayudarte a tomar decisiones fundamentadas sobre las actualizaciones y compras. Ayuda a probar las capacidades del producto de seguridad para evaluar cómo puede ayudar al equipo de operaciones de seguridad en sus tareas diarias.

La experiencia de evaluación de Microsoft Defender para [Office 365](office-365-atp.md) está diseñada para eliminar las complejidades de la configuración de dispositivos y entornos para que pueda centrarse en evaluar las capacidades de la solución de seguridad. Solo se aplica a la protección de correo electrónico y no a SharePoint, Clientes de Office o Teams.

Si aún no tiene una licencia compatible con Microsoft Defender para Office 365, puede iniciar una evaluación gratuita de [30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) días y probar las capacidades en el Centro de seguridad y cumplimiento de Office 365 & ( https://protection.office.com/homepage) . Podrá disfrutar de la configuración rápida y puede desactivarla fácilmente si es necesario.

## <a name="how-the-evaluation-works"></a>Cómo funciona la evaluación

Defender para Office 365 en modo de evaluación crea directivas de correo electrónico de Defender para Office 365 que registra veredictos, como malware, pero no actúan en mensajes. No es necesario cambiar la configuración del registro MX.

Con el modo de evaluación, [los datos](atp-safe-attachments.md)adjuntos seguros, [los](atp-safe-links.md)vínculos seguros y las directivas de suplantación contra [suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) de identidad se establecen en su nombre. Todas las directivas de Defender para Office 365 se crean en modo de no aplicación en segundo plano y no son visibles para usted.

Como parte de la configuración, el modo de evaluación también configura el [filtrado mejorado para conectores.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) Mejora la precisión del filtrado al conservar la dirección IP y la información del remitente, que de lo contrario se pierden cuando el correo pasa a través de una puerta de enlace de seguridad de correo electrónico (ESG) delante de Defender para Office 365. El filtrado mejorado también mejora la precisión de filtrado de las directivas contra correo electrónico no deseado y contra suplantación de identidad de Exchange Online Protection (EOP).

Para minimizar el posible impacto en la producción en algunos escenarios no admitidos, puede omitir todo el filtrado de EOP mediante la creación de una regla de transporte para establecer el nivel de confianza contra correo no deseado (SCL) en -1. Consulte [Usar el EAC para crear una regla de flujo de correo que establece el SCL de un mensaje para](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)obtener más   información.

Cuando se configura el modo de evaluación, tendrá un informe actualizado diariamente con hasta 90 días de datos cuantificando los mensajes que se habrían bloqueado si se hubieran implementado las directivas (por ejemplo, eliminar, enviar a correo no deseado, cuarentena). Se generan informes para todas las detecciones de Defender para Office 365 y EOP. Se agregan por tecnología de detección (por ejemplo, suplantación) y se pueden filtrar por intervalo de tiempo. Además, los informes de mensajes se pueden crear a petición para crear tablas dinámicas personalizadas o para profundizar en los mensajes mediante el Explorador de amenazas.

Con la experiencia de configuración simplificada, puede centrarse en:

- Ejecución de la evaluación
- Obtener un informe detallado
- Análisis del informe para la acción
- Presentación del resultado de la evaluación

## <a name="before-you-begin"></a>Antes de empezar

### <a name="licensing"></a>Licencias

Para obtener acceso a la evaluación, debe cumplir los requisitos de licencia. Cualquiera de las siguientes licencias funcionará:

- Plan 1 de Microsoft Defender para Office 365
- Plan 2 de Microsoft Defender para Office 365
- Microsoft 365 E5, Seguridad de Microsoft 365 E5
- Office 365 E5

Si no tiene una de estas licencias, necesitará obtener una licencia de prueba.

#### <a name="trial"></a>Prueba

Para obtener una licencia de prueba para Microsoft Defender para Office 365, necesita tener el rol de administrador de facturación **o** el rol de **administrador global.** Solicitar permiso a alguien que tenga el rol de administrador global. [Más información sobre suscripciones y licencias](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

Una vez que tenga el rol adecuado, la ruta recomendada es obtener una licencia de prueba para Microsoft Defender para Office 365 (Plan 2) en el Centro de administración de Microsoft 365 yendo a Facturación > Servicios de compra. La prueba incluye una prueba gratuita de 30 días para 25 licencias. [Obtenga una versión de prueba de Microsoft Defender para Office 365 (Plan 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Tendrá una ventana de 30 días con la evaluación para supervisar e informar sobre amenazas avanzadas. You'll also have the option to buy a paid subscription if you want the full Defender for Office 365 capabilities.

### <a name="roles"></a>Roles

Los roles de Exchange Online son necesarios para configurar Defender para Office 365 en modo de evaluación.

- [Más información sobre los permisos en Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
- [Más información sobre la asignación de roles de administrador](../../admin/add-users/assign-admin-roles.md)

Se necesitan los siguientes roles:

|Task|Función|
|---|---|
|Obtener una prueba gratuita o comprar Microsoft Defender para Office 365 (Plan 2)|Rol de administrador de facturación O rol de administrador global|
|Crear directiva de evaluación|Rol Dominios remotos y aceptados; Rol de administrador de seguridad|
|Editar directiva de evaluación|Rol Dominios remotos y aceptados; Rol de administrador de seguridad|
|Eliminar directiva de evaluación|Rol Dominios remotos y aceptados; Rol de administrador de seguridad |
|Ver informe de evaluación|Rol de administrador de seguridad O rol de lector de seguridad|
|


### <a name="enhanced-filtering"></a>Filtrado mejorado

Las directivas de Exchange Online Protection, como la protección masiva y contra correo no deseado, seguirán siendo las mismas. La entrega de mensajes también seguirá siendo la misma. Sin embargo, la evaluación activa el filtrado mejorado para los conectores, lo que afectará al flujo de correo y a las directivas de Exchange Online Protection a menos que se omitan.

El filtrado mejorado para los conectores permitirá a los inquilinos usar la protección contra la suplantación. No se admite la protección contra la suplantación si usa una puerta de enlace de seguridad de correo electrónico (ESG) sin haber activado el filtrado mejorado para conectores.

### <a name="urls"></a>Direcciones URL

Las direcciones URL se detonarán durante el flujo de correo. Si no desea que se detonan direcciones URL específicas, administre la lista de direcciones URL permitidas correctamente. Consulte [Administrar la lista de permitidos o bloqueados del espacio empresarial](tenant-allow-block-list.md) para obtener más información.

Los vínculos url de los cuerpos de mensajes de correo electrónico no se encapsulan para reducir el impacto del cliente.

### <a name="email-routing"></a>Enrutamiento de correo electrónico

Prepare los detalles correspondientes que necesitará para configurar cómo se enruta actualmente el correo electrónico, incluido el nombre del conector de entrada que enruta el correo. Si solo usa Exchange Online Protection, no tendrá un conector.  [Obtenga información sobre el flujo de correo y el enrutamiento de correo electrónico](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Entre los escenarios de enrutamiento de correo electrónico admitidos se incluyen:

- **Asociado** de terceros o proveedor de servicios local: el conector de entrada que desea evaluar usa un proveedor de terceros o está usando una solución para la seguridad de correo electrónico local.
- **Microsoft Exchange Online protección** de correo electrónico: el inquilino que desea evaluar usa Office 365 para la seguridad de correo electrónico y el registro de Exchange de correo (MX) apunta a Microsoft.

### <a name="email-security-gateway"></a>Puerta de enlace de seguridad de correo electrónico

Si usa una puerta de enlace de seguridad de correo electrónico (ESG) de terceros, necesitará saber el nombre del proveedor. Si usas un ESG local o proveedores no compatibles, debes conocer las direcciones IP públicas de los dispositivos.

Entre los asociados de terceros compatibles se incluyen:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Resalte
- Symantec
- Trend Micro

### <a name="scoping"></a>Ámbito

Podrá convertir la evaluación en un conector entrante. Si no hay ningún conector configurado, el ámbito de evaluación permitirá a los administradores recopilar datos de cualquier usuario de su espacio empresarial para evaluar Defender para Office 365.

## <a name="get-started-with-the-evaluation"></a>Introducción a la evaluación

Busque la tarjeta de configuración de evaluación de Microsoft Defender para Office 365 en el Centro de seguridad y & cumplimiento de Office 365 (desde tres puntos https://protection.office.com/homepage) de acceso:

- Panel de administración > amenazas
- Directiva de administración > amenazas
- Panel de > informes

## <a name="setting-up-the-evaluation"></a>Configuración de la evaluación

Una vez que inicie el flujo de configuración de la evaluación, se le ofrecerán dos opciones de enrutamiento. En función de las necesidades de configuración y evaluación de enrutamiento de correo de su organización, puede seleccionar si usa un proveedor de servicios de terceros o local o solo Microsoft Exchange Online.

- Si usa un asociado de terceros o un proveedor de servicios local, tendrá que seleccionar el nombre del proveedor en el menú desplegable. Proporcione los demás detalles relacionados con el conector.

- Seleccione Microsoft Exchange Online si el registro MX apunta a Microsoft y tiene un buzón de Exchange Online.

Revisa la configuración y edála si es necesario. A continuación, **seleccione Crear evaluación.** Debería recibir un mensaje de confirmación para indicar que la configuración se ha completado.

El informe de evaluación de Microsoft Defender para Office 365 se genera una vez al día. Los datos pueden tardar hasta 24 horas en rellenarse.

### <a name="exchange-rules-optional"></a>Reglas de Exchange (opcional)

Si tiene una puerta de enlace existente, al habilitar el modo de evaluación se activará el filtrado mejorado para los conectores. Esto mejora la precisión de filtrado modificando la dirección IP del remitente entrante. Esto puede cambiar los veredictos de filtro y si no omite Exchange Online Protection, esto puede alterar la entrega de determinados mensajes. En este caso, es posible que desee omitir temporalmente el filtrado para analizar el impacto. Para omitir, vaya al Centro de administración de Exchange y cree una directiva de SCL -1 (si aún no tiene una). Para obtener más información sobre los componentes de regla y cómo funcionan, consulte Reglas de flujo de correo (reglas de transporte) en Exchange Online.

## <a name="evaluate-capabilities"></a>Funcionalidades de evaluación

Una vez generado el informe de evaluación, vea cuántos vínculos de amenazas avanzados, datos adjuntos de amenazas avanzados y posibles suplantaciones se identificaron en los correos electrónicos y áreas de trabajo de colaboración de su organización.

Una vez que haya expirado la versión de prueba, puede seguir accediendo al informe durante 90 días. Sin embargo, no recopilará más información. Si desea seguir usando Microsoft Defender para Office 365 después de que haya expirado la versión de prueba, asegúrese de comprar una suscripción de pago para Microsoft Defender para [Office 365 (Plan 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Puede ir a Configuración **para** actualizar el enrutamiento o desactivar la evaluación en cualquier momento. Sin embargo, debe volver a pasar por el mismo proceso de configuración si decide continuar la evaluación después de desactivarla.

## <a name="provide-feedback"></a>Enviar comentarios

Sus comentarios nos ayudan a mejorar la protección de su entorno frente a ataques avanzados. Comparta su experiencia y impresiones de las capacidades del producto y los resultados de la evaluación.

Seleccione **Enviar comentarios** para que sepamos lo que piensa.
