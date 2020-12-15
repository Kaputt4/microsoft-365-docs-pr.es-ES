---
title: Evalúe Microsoft defender para Office 365
description: Defender para Office 365 en modo de evaluación crea directivas de correo de defender para Office 365 que registran los veredictos, como el malware, pero no actúan en los mensajes.
keywords: evaluar Office 365, Microsoft defender para Office 365, evaluación de Office 365, probar Office 365, Microsoft defender, ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 54acf9d21e3dd935f8b87c6ee4a13ab30e7bc59e
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668078"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Evalúe Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Evalúe Microsoft defender para Office 365 estará pronto en versión preliminar pública. Esta versión preliminar se proporciona sin un contrato de nivel de servicio. Es posible que algunas características no se admitan o que tengan capacidades restringidas.

Realizar una evaluación exhaustiva de un producto de seguridad puede ayudarle a tomar decisiones informadas sobre las actualizaciones y las compras. Ayuda a probar las capacidades del producto de seguridad para evaluar cómo puede ayudar a su equipo de operaciones de seguridad en sus tareas cotidianas.

La experiencia de evaluación de [Microsoft defender para Office 365](office-365-atp.md) está diseñada para eliminar las complejidades de la configuración de dispositivos y entornos, de modo que pueda centrarse en la evaluación de las capacidades de la solución de seguridad. Solo se aplica a la protección de correo electrónico y no a SharePoint, clientes de Office o equipos.

Si aún no tiene una licencia que admita Microsoft defender para Office 365, puede iniciar una [evaluación gratuita de 30 días](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) y probar las capacidades del centro de seguridad & cumplimiento de Office 365 ( https://protection.office.com/homepage) . Disfrutará de la rápida configuración y podrá desactivarla fácilmente si es necesario.

## <a name="how-the-evaluation-works"></a>Funcionamiento de la evaluación

Defender para Office 365 en modo de evaluación crea directivas de correo de defender para Office 365 que registran los veredictos, como el malware, pero no actúan en los mensajes. No es necesario cambiar la configuración del registro MX.

Con el modo de evaluación, los [datos adjuntos seguros](atp-safe-attachments.md), [vínculos seguros](atp-safe-links.md)y [las directivas de suplantación contra suplantación de identidad](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) se configuran en su nombre. Todas las directivas de defender para Office 365 se crean en segundo plano en el modo de no aplicación y no son visibles para usted.

Como parte de la configuración, el modo de evaluación también configura el [filtrado mejorado para los conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors). Mejora la precisión del filtrado conservando la dirección IP y el remitente, que se pierden en caso de que el correo pase por una puerta de enlace de seguridad de correo electrónico (ESG) delante de defender para Office 365. Esto también mejora la precisión de filtrado de las directivas contra correo electrónico no deseado y antiphishing de Exchange Online Protection (EOP).

Para minimizar el impacto potencial de producción en algunos escenarios no admitidos, puede omitir todo el filtrado de EOP mediante la creación de una regla de transporte para establecer el nivel de confianza contra correo no deseado (SCL) en-1. Consulte [usar el EAC para crear una regla de flujo de correo que establezca el SCL de un mensaje](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)   para obtener más información.

Cuando se configura el modo de evaluación, tendrá un informe actualizado diariamente con hasta 90 días de datos cuantificando los mensajes que se habrían bloqueado si se hubieran creado e implementado las directivas (por ejemplo, eliminar, enviar a correo no deseado, poner en cuarentena). Los informes se generan para todas las detecciones de defender para Office 365 y EOP. Se agregan por tecnología de detección (por ejemplo, suplantación) y se pueden filtrar por intervalo de tiempo. Además, los informes de mensajes se pueden crear a petición para crear tablas dinámicas personalizadas o para profundizar en los mensajes mediante el explorador de amenazas.

Con la experiencia de configuración simplificada, puede centrarse en:

- Ejecución de la evaluación
- Obtención de un informe detallado
- Analizar el informe de acción
- Presentar el resultado de la evaluación

## <a name="before-you-begin"></a>Antes de empezar

### <a name="licensing"></a>Licencias

Para obtener acceso a la evaluación, deberá cumplir con los requisitos de licencia. Funcionará cualquiera de las siguientes licencias:

- Plan 1 de Microsoft Defender para Office 365
- Plan 2 de Microsoft Defender para Office 365
- Microsoft 365 E5, Microsoft 365 E5 Security
- Office 365 E5

Si no tiene una de esas licencias, deberá obtener una licencia de prueba.

#### <a name="trial"></a>Prueba

Para obtener una licencia de prueba de Microsoft defender para Office 365, debe tener el rol de **Administrador de facturación** o el rol de **administrador global**. Solicitar permiso a un usuario que tenga el rol de administrador global. [Obtener información sobre las suscripciones y licencias](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

Una vez que tenga el rol adecuado, la ruta de acceso recomendada es obtener una licencia de prueba para Microsoft defender para Office 365 (plan 2) en el centro de administración de Microsoft 365 yendo a Billing > Purchase Services. La versión de prueba incluye una prueba gratuita de 30 días para 25 licencias. [Obtenga una versión de prueba de Microsoft defender para Office 365 (plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).

Tendrá un período de 30 días con la evaluación para supervisar y crear informes sobre amenazas avanzadas. También tendrá la opción de comprar una suscripción de pago si desea el total de capacidades de defender para Office 365.

### <a name="roles"></a>Roles

Las funciones de Exchange online son necesarias para configurar defender para Office 365 en modo de evaluación. Se necesitan los siguientes roles:

|Task|Función|
|---|---|
|Obtenga una prueba gratuita o compre Microsoft defender para Office 365 (plan 2)|Rol de administrador de facturación o rol de administrador global|
|Crear una directiva de evaluación|Rol dominios remotos y aceptados; Rol de administrador de seguridad|
|Editar Directiva de evaluación|Rol dominios remotos y aceptados; Rol de administrador de seguridad|
|Eliminar Directiva de evaluación|Rol dominios remotos y aceptados; Rol de administrador de seguridad |
|Ver informe de evaluación|Rol de administrador de seguridad o rol de lector de seguridad|
|

### <a name="enhanced-filtering"></a>Filtrado mejorado

Las directivas de protección en línea de Exchange, como la protección masiva y contra correo no deseado, seguirán siendo las mismas. La entrega de mensajes también seguirá siendo la misma. Sin embargo, la evaluación activa el filtrado mejorado para los conectores, lo que afectará a las directivas de Exchange Online Protection, a menos que se omitan.

El filtrado mejorado de los conectores permitirá a los inquilinos usar la protección contra la suplantación de identidad. No se admite la suplantación de identidad (phishing) si usa una puerta de enlace de seguridad de correo electrónico (ESG) sin activar el filtrado mejorado para los conectores.

### <a name="urls"></a>Direcciones URL

Las direcciones URL se detonarán durante el flujo de correo. Si no quiere detonaciones de direcciones URL específicas, administre la lista de URL permitidas de forma adecuada. Consulte [administrar direcciones URL en la lista de permitidos/bloqueados de inquilino](tenant-allow-block-list.md) para obtener más información.

Los vínculos URL en los cuerpos de los mensajes de correo electrónico no se ajustan para reducir el impacto del cliente.

### <a name="email-routing"></a>Enrutamiento de correo electrónico

Debe preparar los detalles correspondientes que necesitará para configurar la forma en que el correo electrónico se enruta actualmente, incluido el nombre del conector de entrada que enruta el correo. Si solo usa Exchange Online Protection, no tendrá un conector.  [Obtenga información sobre el flujo de correo y el enrutamiento de correo electrónico](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Los escenarios de enrutamiento de correo electrónico admitidos son:

- **Proveedor de servicios locales o asociados de terceros**: el conector de entrada que desea evaluar usa un proveedor de terceros y/o está usando una solución para la seguridad de correo electrónico local.
- **Solo Microsoft Exchange Online Protection**: el inquilino que desea evaluar usa Office 365 para la seguridad del correo electrónico y el registro de intercambio de correo (mx) apunta a Microsoft.

### <a name="email-security-gateway"></a>Puerta de enlace de seguridad de correo electrónico

Si está usando una puerta de enlace de seguridad de correo electrónico de terceros (ESG), necesitará conocer el nombre del proveedor. Si está usando un proveedor de ESG local o no admitido, necesitará conocer las direcciones IP públicas para los dispositivos de.

Entre los asociados de terceros admitidos se incluyen:

- Barracuda Spam
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Ámbito

Podrá definir el ámbito de la evaluación en un conector de entrada. Si no hay ningún conector configurado, el ámbito de evaluación permitirá a los administradores recopilar datos de cualquier usuario del inquilino para evaluar defender para Office 365.

## <a name="get-started-with-the-evaluation"></a>Introducción a la evaluación

Busque la tarjeta de configuración de evaluación de Microsoft defender para Office 365 en el centro de seguridad & cumplimiento de Office 365 ( https://protection.office.com/homepage) desde tres puntos de acceso:

- Panel de > de administración de amenazas
- Directiva de > de administración de amenazas
- Informes > panel

## <a name="setting-up-the-evaluation"></a>Configuración de la evaluación

Una vez que inicie el flujo de configuración para la evaluación, se le ofrecerán dos opciones de enrutamiento. Según la configuración de enrutamiento de correo y las necesidades de evaluación de su organización, puede seleccionar si está usando un proveedor de servicios local o de terceros o solo Microsoft Exchange Online.

- Si está usando un proveedor de servicios locales o de socio de terceros, tendrá que seleccionar el nombre del proveedor en el menú desplegable de de. Proporcione los otros detalles relacionados con el conector.

- Seleccione Microsoft Exchange Online si el registro MX apunta a Microsoft y tiene un buzón de correo de Exchange Online.

Revise la configuración y edítela si es necesario. A continuación, seleccione **crear evaluación**. Debe obtener un mensaje de confirmación para indicar que su configuración ha finalizado.

El informe de evaluación de Microsoft defender para Office 365 se genera una vez al día. El rellenado de datos puede tardar hasta 24 horas en completarse.

### <a name="exchange-rules-optional"></a>Reglas de Exchange (opcional)

Si tiene una puerta de enlace existente, es posible que desee omitir el filtrado, ya que activará el filtrado mejorado para los conectores y modificará la dirección IP del remitente entrante. Para omitir, vaya al centro de administración de Exchange y cree una directiva de SCL-1 (si todavía no tiene una). Para obtener más información sobre los componentes de la regla y cómo funcionan, consulte mail Flow Rules (Transport Rules) in Exchange Online.

## <a name="evaluate-capabilities"></a>Funcionalidades de evaluación

Una vez generado el informe de evaluación, vea cuántos vínculos avanzados de amenazas, datos adjuntos de amenazas avanzados y potenciales suplantaciones se identificaron en las áreas de trabajo de correo electrónico y colaboración de la organización.

Una vez que la versión de prueba ha expirado, puede seguir teniendo acceso al informe durante 90 días. Sin embargo, no recopilará más información. Si desea seguir usando Microsoft defender para Office 365 una vez que haya expirado el período de prueba, asegúrese de [comprar una suscripción de pago para Microsoft defender para office 365 (plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).

Puede ir a **configuración** para actualizar el enrutamiento o para desactivar la evaluación en cualquier momento. Sin embargo, debe volver a realizar el mismo proceso de configuración si decide continuar la evaluación después de haber desactivado.

## <a name="provide-feedback"></a>Enviar comentarios

Sus comentarios nos ayudan a mejorar la protección del entorno contra ataques avanzados. Comparta su experiencia y impresiones de las capacidades del producto y los resultados de la evaluación.

Seleccione **Enviar comentarios** para hacerle saber lo que piensa.
