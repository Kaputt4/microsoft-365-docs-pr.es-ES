---
title: Evaluar Microsoft Defender para Office 365
description: Defender para Office 365 en modo de evaluación crea directivas de correo electrónico de Defender para Office 365 que registra veredictos, como malware, pero no actúan en mensajes.
keywords: evaluar Office 365, Microsoft Defender para Office 365, evaluación de office 365, probar office 365, Microsoft Defender, ATP
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
ms.openlocfilehash: 2e97e510cbc3188f8cc6117c5d7bd1e1d23897eb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205899"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Evaluar Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> La evaluación de Microsoft Defender para Office 365 está en versión preliminar pública. Esta versión preliminar se proporciona sin un contrato de nivel de servicio. Es posible que algunas características no sean compatibles o que tengan capacidades limitadas.

La realización de una evaluación completa de productos de seguridad puede ayudarle a tomar decisiones fundamentadas sobre las actualizaciones y las compras. Ayuda a probar las capacidades del producto de seguridad para evaluar cómo puede ayudar al equipo de operaciones de seguridad en sus tareas diarias.

La experiencia de evaluación de Microsoft Defender para [Office 365](defender-for-office-365.md) está diseñada para eliminar las complejidades de la configuración de dispositivos y entornos para que pueda centrarse en evaluar las capacidades de Microsoft Defender para Office 365. Con el modo de evaluación, todos los mensajes enviados a buzones de Exchange Online se pueden evaluar sin apuntar registros MX a Microsoft. La característica solo se aplica a la protección de correo electrónico y no a clientes de Office como Word, SharePoint o Teams.

Si aún no tiene una licencia compatible con Microsoft Defender para Office 365, puede iniciar una evaluación gratuita de [30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) días y probar las capacidades en el Centro de seguridad y cumplimiento de Office 365 & ( https://protection.office.com/homepage) . Podrás disfrutar de la configuración rápida y puedes desactivarla fácilmente si es necesario.

## <a name="how-the-evaluation-works"></a>Cómo funciona la evaluación

Defender para Office 365 en modo de evaluación crea directivas de correo electrónico de Defender para Office 365 que registra veredictos, como malware, pero no actúan en mensajes. No es necesario cambiar la configuración del registro MX.

Con el modo de evaluación, [se establecen en](safe-attachments.md)su nombre datos adjuntos seguros, vínculos seguros y directivas de [suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) basadas en inteligencia de buzones. [](safe-links.md) Todas las directivas de Defender para Office 365 se crean en modo no de aplicación en segundo plano y no son visibles para usted.

Como parte de la configuración, el modo de evaluación también configura el filtrado [mejorado para conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors). Mejora la precisión de filtrado conservando la información de remitente y dirección IP, que de lo contrario se pierde cuando el correo pasa a través de una puerta de enlace de seguridad de correo electrónico (ESG) delante de Defender para Office 365. El filtrado mejorado para conectores también mejora la precisión de filtrado de las directivas contra correo no deseado y contra suplantación de identidad (EOP) existentes de Exchange Online Protection (EOP).

El filtrado mejorado habilitado para conectores mejora la precisión del filtrado, pero puede alterar la entrega de determinados mensajes si tiene un ESG delante de Defender para Office 365 y actualmente no omite el filtrado de EOP. El impacto se limita a las directivas de EOP; La configuración de directivas de MDO como parte de la evaluación se crea en modo no de aplicación. Para minimizar el posible impacto en la producción, puede omitir todo el filtrado de EOP mediante la creación de una regla de transporte para establecer el nivel de confianza de correo no deseado (SCL) en -1. Vea Usar el EAC para crear una regla de [flujo de correo que establece el SCL de un mensaje para obtener](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)más   información.

Cuando se configura el modo de evaluación, tendrá un informe actualizado diariamente con hasta 90 días de datos que cuantifican los mensajes que se habrían bloqueado si se hubieran implementado las directivas (por ejemplo, eliminar, enviar a correo no deseado, cuarentena). Se generan informes para todas las detecciones de Defender para Office 365 y EOP. Se agregan por tecnología de detección (por ejemplo, suplantación) y se pueden filtrar por intervalo de tiempo. Además, los informes de mensajes se pueden crear a petición para crear pivotes personalizados o para profundizar en los mensajes mediante el Explorador de amenazas.

Con la experiencia de configuración simplificada, puede centrarse en:

- Ejecución de la evaluación
- Obtener un informe detallado
- Análisis del informe para la acción
- Presentación del resultado de la evaluación

## <a name="before-you-begin"></a>Antes de empezar

### <a name="licensing"></a>Licencias

Para obtener acceso a la evaluación, deberá cumplir los requisitos de licencia. Cualquiera de las siguientes licencias funcionará:

- Plan 1 de Microsoft Defender para Office 365
- Plan 2 de Microsoft Defender para Office 365
- Microsoft 365 E5, Microsoft 365 E5 Security
- Office 365 E5

Si no tiene una de esas licencias, tendrá que obtener una licencia de prueba.

#### <a name="trial"></a>Prueba

Para obtener una licencia de prueba para Microsoft Defender para Office 365, debe tener el rol de administrador de facturación **o** el rol de **administrador global**. Solicitar permiso a alguien que tenga el rol de administrador global. [Información sobre suscripciones y licencias](../../commerce/licenses/subscriptions-and-licenses.md)

Una vez que tenga el rol adecuado, la ruta recomendada es obtener una licencia de prueba para Microsoft Defender para Office 365 (Plan 2) en el Centro de administración de Microsoft 365 yendo a Facturación > Servicios de compra. La prueba incluye una prueba gratuita de 30 días para 25 licencias. [Obtenga una versión de prueba de Microsoft Defender para Office 365 (Plan 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Tendrás una ventana de 30 días con la evaluación para supervisar e informar sobre amenazas avanzadas. También tendrá la opción de comprar una suscripción de pago si desea las funcionalidades completas de Defender para Office 365.

### <a name="roles"></a>Roles

**Los roles de Exchange Online son necesarios** para configurar Defender para Office 365 en modo de evaluación. La asignación de un rol de administrador de seguridad o cumplimiento de Microsoft 365 no funcionará.

- [Información sobre los permisos en Exchange Online](/exchange/permissions-exo/permissions-exo)
- [Obtenga información sobre cómo asignar roles de administrador](../../admin/add-users/assign-admin-roles.md)

Se necesitan los siguientes roles:

|Tarea|Rol (en Exchange Online)|
|---|---|
|Obtener una prueba gratuita o comprar Microsoft Defender para Office 365 (Plan 2)|Rol de administrador de facturación O rol de administrador global|
|Crear directiva de evaluación|Rol Dominios remotos y aceptados; Rol de administrador de seguridad|
|Editar directiva de evaluación|Rol Dominios remotos y aceptados; Rol de administrador de seguridad|
|Eliminar directiva de evaluación|Rol Dominios remotos y aceptados; Rol de administrador de seguridad |
|Ver informe de evaluación|Rol de administrador de seguridad O Rol de lector de seguridad|
|

### <a name="enhanced-filtering"></a>Filtrado mejorado

Las directivas de Exchange Online Protection, como la protección masiva y contra correo no deseado, seguirán siendo las mismas. Sin embargo, la evaluación activa el filtrado mejorado de conectores, lo que puede afectar al flujo de correo y a las directivas de Exchange Online Protection a menos que se omita.

El filtrado mejorado para conectores permite a los inquilinos usar protección contra la suplantación. No se admite la suplantación de seguridad si usa una puerta de enlace de seguridad de correo electrónico (ESG) sin haber activado el filtrado mejorado para conectores.

### <a name="urls"></a>Direcciones URL

Las direcciones URL se detonarán durante el flujo de correo. Si no desea que se detonan direcciones URL específicas, administre la lista de direcciones URL permitidas correctamente. Consulta [Administrar la lista de inquilinos permitidos o bloqueados](tenant-allow-block-list.md) para obtener más información.

Los vínculos url de los cuerpos de mensajes de correo electrónico no se ajustarán para disminuir el impacto del cliente.

### <a name="email-routing"></a>Enrutamiento de correo electrónico

Prepare los detalles correspondientes que necesitará para configurar cómo se enruta actualmente el correo electrónico, incluido el nombre del conector de entrada que enruta el correo. Si solo usa Exchange Online Protection, no tendrá un conector.  [Información sobre el flujo de correo y el enrutamiento de correo electrónico](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Entre los escenarios de enrutamiento de correo electrónico admitidos se incluyen:

- **Partner** de terceros o proveedor de servicios local: el conector de entrada que desea evaluar usa un proveedor de terceros o está usando una solución para la seguridad del correo electrónico local.
- **Microsoft Exchange Online protección** de correo electrónico: el inquilino que desea evaluar usa Office 365 para la seguridad del correo electrónico y el registro de Mail Exchange (MX) apunta a Microsoft.

### <a name="email-security-gateway"></a>Puerta de enlace de seguridad de correo electrónico

Si usa una puerta de enlace de seguridad de correo electrónico (ESG) de terceros, deberá conocer el nombre del proveedor. Si usas un ESG local o proveedores no compatibles, tendrás que conocer las direcciones IP públicas de los dispositivos.

Entre los asociados de terceros compatibles se incluyen:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Ámbito

Podrá tener el ámbito de la evaluación en un conector de entrada. Si no hay ningún conector configurado, el ámbito de evaluación permitirá a los administradores recopilar datos de cualquier usuario del inquilino para evaluar Defender para Office 365.

## <a name="get-started-with-the-evaluation"></a>Introducción a la evaluación

Busque la tarjeta de configuración de evaluación de Microsoft Defender para Office 365 en el Centro de seguridad y cumplimiento de Office 36 & 5 ( desde tres puntos https://protection.office.com/homepage) de acceso:

- Panel de administración > amenazas
- Directiva de administración > amenazas
- Panel > informes

## <a name="setting-up-the-evaluation"></a>Configuración de la evaluación

Una vez que inicie el flujo de configuración de la evaluación, se le darán dos opciones de enrutamiento. Según las necesidades de configuración y evaluación de enrutamiento de correo de su organización, puede seleccionar si usa un proveedor de servicios local o de terceros o solo Microsoft Exchange Online.

- Si usa un partner de terceros o un proveedor de servicios local, deberá seleccionar el nombre del proveedor en el menú desplegable. Proporcione los otros detalles relacionados con el conector.

- Seleccione Microsoft Exchange Online si el registro MX apunta a Microsoft y tiene un buzón de Exchange Online.

Revisa la configuración y edála si es necesario. A continuación, **seleccione Crear evaluación**. Debe obtener un mensaje de confirmación para indicar que la configuración se ha completado.

El informe de evaluación de Microsoft Defender para Office 365 se genera una vez al día. Los datos pueden tardar hasta 24 horas en rellenarse.

### <a name="exchange-rules-optional"></a>Reglas de Exchange (opcional)

Si tiene una puerta de enlace existente, al habilitar el modo de evaluación se activará el filtrado mejorado para los conectores. Esto mejora la precisión de filtrado modificando la dirección IP del remitente entrante. Esto puede cambiar los veredictos de filtro y, si no se omite Exchange Online Protection, esto puede alterar la entrega de determinados mensajes. En este caso, es posible que desee omitir temporalmente el filtrado para analizar el impacto. Para omitir, vaya al Centro de administración de Exchange y cree una directiva de SCL -1 (si aún no la tiene). Para obtener información detallada sobre los componentes de regla y cómo funcionan, vea Reglas de flujo de correo (reglas de transporte) en Exchange Online.

## <a name="evaluate-capabilities"></a>Funcionalidades de evaluación

Una vez generado el informe de evaluación, vea cuántos vínculos de amenazas avanzados, datos adjuntos avanzados de amenazas y posibles suplantaciones se identificaron en los correos electrónicos y áreas de trabajo de colaboración de su organización.

Una vez expirada la prueba, puede seguir teniendo acceso al informe durante 90 días. Sin embargo, no recopilará más información. Si desea seguir usando Microsoft Defender para Office 365 después de que haya expirado la prueba, asegúrese de comprar una suscripción de pago para [Microsoft Defender para Office 365 (Plan 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Puedes ir a **Configuración para** actualizar el enrutamiento o desactivar la evaluación en cualquier momento. Sin embargo, debe volver a realizar el mismo proceso de configuración si decide continuar la evaluación después de desactivarla.

## <a name="provide-feedback"></a>Enviar comentarios

Sus comentarios nos ayudan a mejorar la protección del entorno frente a ataques avanzados. Comparta su experiencia e impresiones de las capacidades del producto y los resultados de evaluación.

Seleccione **Enviar comentarios** para que sepamos lo que piensa.