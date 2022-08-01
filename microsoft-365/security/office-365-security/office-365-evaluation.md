---
title: Evaluar Microsoft Defender para Office 365
description: Defender para Office 365 en modo de evaluación crea Defender para Office 365 directivas de correo electrónico que registran veredictos, como malware, pero no actúan en los mensajes.
keywords: evaluar Office 365, Microsoft Defender para Office 365, evaluación de office 365, probar office 365, Microsoft Defender, Microsoft Defender para punto de conexión
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0f5d82e9baaca7209f8a91a7f1984aa38e3102e6
ms.sourcegitcommit: 74518b920b4166adccc10ea1581a62c44bb14edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2022
ms.locfileid: "66997835"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Evaluar Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Microsoft Defender para Office 365 evaluación está en versión preliminar pública. Esta versión preliminar se proporciona sin un contrato de nivel de servicio. Es posible que algunas características no se admitan o que tengan funcionalidades restringidas.

La realización de una evaluación exhaustiva de productos de seguridad puede ayudarle a tomar decisiones informadas sobre las actualizaciones y las compras. Ayuda a probar las funcionalidades del producto de seguridad para evaluar cómo puede ayudar al equipo de operaciones de seguridad en sus tareas diarias.

La experiencia [de evaluación de Microsoft Defender para Office 365](defender-for-office-365.md) está diseñada para eliminar las complejidades de la configuración de dispositivos y entornos para que pueda centrarse en evaluar las funcionalidades de Microsoft Defender para Office 365. Con el modo de evaluación, todos los mensajes enviados a Exchange Online buzones se pueden evaluar sin apuntar registros MX a Microsoft. La característica solo se aplica a la protección de correo electrónico y no a clientes de Office como Word, SharePoint o Teams.

Si aún no tiene una licencia que admita Microsoft Defender para Office 365, puede iniciar una [evaluación gratuita de 30 días](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) y probar las funcionalidades en el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Disfrutará de la configuración rápida y podrá desactivarla fácilmente si es necesario.

> [!NOTE]
> Si está en el portal de Microsoft 365 Defender en <https://security.microsoft.com>, puede iniciar una evaluación de Defender para Office 365 aquí: Email & Directivas de **colaboración** \> & **Modo de evaluación** de **directivas** \> de amenazas **de reglas** \> en la sección **Otros**. O bien, para ir directamente a la página **Modo de evaluación** , use <https://security.microsoft.com/atpEvaluation>.

## <a name="how-the-evaluation-works"></a>Funcionamiento de la evaluación

Defender para Office 365 en modo de evaluación crea Defender para Office 365 directivas de correo electrónico que registran veredictos, como malware, pero no actúan en los mensajes. No es necesario cambiar la configuración del registro MX.

Con el modo de evaluación, [los datos adjuntos seguros](safe-attachments.md), [los vínculos seguros](safe-links.md) y la [inteligencia de buzones de correo en las directivas anti-pishing](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) se configuran en su nombre. Todas las directivas de Defender para Office 365 se crean en modo no de cumplimiento en segundo plano y no son visibles para usted.

Como parte de la configuración, el modo de evaluación también configura el [filtrado mejorado para conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) (también conocido como _lista de omitir_). Esta configuración mejora la precisión del filtrado conservando la información del remitente y la dirección IP, que de lo contrario se pierden cuando el correo pasa a través de una puerta de enlace de seguridad de correo electrónico (ESG) delante de Defender para Office 365. El filtrado mejorado para conectores también mejora la precisión de filtrado de las directivas existentes de Exchange Online Protection (EOP) contra correo no deseado y contra phishing.

El filtrado mejorado para conectores mejora la precisión del filtrado, pero puede modificar la entrega de determinados mensajes si tiene un ESG delante de Defender para Office 365 y actualmente no omite el filtrado EOP. El impacto se limita a las directivas de EOP; Defender para Office 365 directivas configuradas como parte de la evaluación se crean en modo no conforme. Para minimizar el posible impacto en la producción, puede omitir la mayoría del filtrado de EOP mediante la creación de una regla de flujo de correo (también conocida como regla de transporte) para establecer el nivel de confianza de correo no deseado (SCL) de los mensajes en -1. Consulte [Uso de reglas de flujo de correo para establecer el nivel de confianza de correo no deseado (SCL) en los mensajes de Exchange Online](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl) para obtener más información.

Cuando se configura el modo de evaluación, tendrá un informe diario con hasta 90 días de datos que cuantifican los mensajes que se habrían bloqueado si se implementaran las directivas (por ejemplo, eliminar, enviar a correo no deseado o poner en cuarentena). Los informes se generan para todas las detecciones Defender para Office 365 y EOP. Los informes se agregan por tecnología de detección (por ejemplo, suplantación) y se pueden filtrar por intervalo de tiempo. Además, los informes de mensajes se pueden crear a petición para crear dinámicas personalizadas o para profundizar en los mensajes mediante el Explorador.

Con la experiencia de configuración simplificada, puede centrarse en:

- Ejecución de la evaluación
- Obtención de un informe detallado
- Análisis del informe para la acción
- Presentación del resultado de la evaluación

## <a name="before-you-begin"></a>Antes de empezar

### <a name="licensing"></a>Licencias

Para acceder a la evaluación, deberá cumplir los requisitos de licencia. Cualquiera de las siguientes licencias funcionará:

- Plan 1 de Microsoft Defender para Office 365
- Plan 2 de Microsoft Defender para Office 365
- Microsoft 365 E5, Seguridad de Microsoft 365 E5
- Office 365 E5

Si no tiene una de esas licencias, tendrá que obtener una licencia de prueba.

#### <a name="trial"></a>Prueba

Para obtener una licencia de prueba para Microsoft Defender para Office 365, debe tener el **rol administrador de facturación** o el **rol administrador global**. Solicite permiso a alguien que tenga el rol de administrador global. [Más información sobre las suscripciones y licencias](../../commerce/licenses/subscriptions-and-licenses.md)

Una vez que tenga el rol adecuado, la ruta de acceso recomendada es obtener una licencia de prueba para Microsoft Defender para Office 365 (Plan 2) en el Centro de administración de Microsoft 365 en <https://admin.microsoft.com> y, a continuación, ir a **Servicios de compra** de **facturación** \> y, a continuación, buscar y seleccionar el Microsoft Defender para Office 365 (plan 2) de prueba. O bien, para ir directamente a la página de evaluación, use <https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)> La evaluación incluye una evaluación gratuita de 30 días para 25 licencias.

Tendrá una ventana de 30 días con la evaluación para supervisar e informar sobre amenazas avanzadas. También tendrá la opción de comprar una suscripción de pago si desea tener todas las capacidades de Defender para Office 365.

### <a name="roles"></a>Funciones

**Exchange Online roles** son necesarios para configurar Defender para Office 365 en modo de evaluación. La asignación de un rol de administrador de seguridad o cumplimiento de Microsoft 365 no funcionará.

- [Obtenga información sobre los permisos en Exchange Online](/exchange/permissions-exo/permissions-exo)
- [Más información sobre la asignación de roles de administrador](../../admin/add-users/assign-admin-roles.md)

Se necesitan los siguientes roles:

|Tarea|Rol (en Exchange Online)|
|---|---|
|Obtener una evaluación gratuita o comprar Microsoft Defender para Office 365 (Plan 2)|Rol de administrador de facturación O rol de administrador global|
|Creación de una directiva de evaluación|Rol Dominios remotos y aceptados; Rol de administrador de seguridad|
|Editar directiva de evaluación|Rol Dominios remotos y aceptados; Rol de administrador de seguridad|
|Eliminar directiva de evaluación|Rol Dominios remotos y aceptados; Rol de administrador de seguridad |
|Ver informe de evaluación|Rol de administrador de seguridad O rol lector de seguridad|

### <a name="enhanced-filtering-for-connectors"></a>Filtrado avanzado para conectores

Las directivas de Exchange Online Protection, como la protección contra correo no deseado y masivo, seguirán siendo las mismas. Sin embargo, la evaluación activa el filtrado mejorado para conectores, lo que puede afectar al flujo de correo y a las directivas de Exchange Online Protection a menos que se omita.

El filtrado mejorado para conectores permite a los inquilinos usar la protección contra la suplantación de identidad. No se admite la protección contra la suplantación si usa una puerta de enlace de seguridad de correo electrónico (ESG) sin haber activado el filtrado mejorado para conectores.

### <a name="urls"></a>Direcciones URL

Las direcciones URL se detonarán durante el flujo de correo. Si no desea que se detone una dirección URL específica, administre la lista de direcciones URL permitidas correctamente. Consulte [Administrar la lista de permitidos o bloqueados](tenant-allow-block-list.md) de inquilinos para obtener más información.

Los vínculos URL de los cuerpos de mensajes de correo electrónico no se encapsulan para reducir el impacto del cliente.

### <a name="email-routing"></a>enrutamiento de Email

Prepare los detalles correspondientes que necesitará para configurar cómo se enruta actualmente el correo electrónico, incluido el nombre del conector de entrada que enruta el correo. Si solo usa Exchange Online Protection, no tendrá un conector. [Más información sobre el flujo de correo y el enrutamiento de correo electrónico](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Entre los escenarios de enrutamiento de correo electrónico admitidos se incluyen:

- **Proveedor de servicios local o asociado de terceros**: el conector de entrada que desea evaluar usa un proveedor de terceros o usa una solución para la seguridad de correo electrónico local.
- **solo protección de Microsoft Exchange Online**: el inquilino que desea evaluar usa Office 365 para la seguridad del correo electrónico y el registro de Intercambio de correo (MX) apunta a Microsoft.

### <a name="email-security-gateway"></a>Email puerta de enlace de seguridad

Si usa una puerta de enlace de seguridad de correo electrónico (ESG) de terceros, deberá conocer el nombre del proveedor. Si usa un ESG local o proveedores no compatibles, deberá conocer las direcciones IP públicas de los dispositivos.

Entre los asociados de terceros admitidos se incluyen:

- Barracuda
- Ironport
- Mimecast
- Punto de prueba
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Ámbito

Podrá limitar la evaluación a un conector de entrada. Si no hay ningún conector configurado, el ámbito de evaluación permitirá a los administradores recopilar datos de cualquier usuario del inquilino para evaluar Defender para Office 365.

## <a name="get-started-with-the-evaluation"></a>Introducción a la evaluación

Busque la tarjeta de configuración de evaluación Microsoft Defender para Office 365 en el portal de Microsoft 365 Defender desde los siguientes puntos de acceso:

- **Extremos** \> **Administración de vulnerabilidades** \> **Panel** (<https://security.microsoft.com/tvm_dashboard>)
- **Email &** directivas de colaboración \> **& reglas directivas** \> **de amenazas** (<https://security.microsoft.com/threatpolicy>)
- **Informes** \> **Email & informes de colaboración**  \> Email & colaboración (<https://security.microsoft.com/emailandcollabreport>)

## <a name="setting-up-the-evaluation"></a>Configuración de la evaluación

Una vez que inicie el flujo de configuración para la evaluación, se le darán dos opciones de enrutamiento. En función de las necesidades de evaluación y configuración de enrutamiento de correo de su organización, puede seleccionar si usa un proveedor de servicios local o de terceros o solo Microsoft Exchange Online.

- Si usa un asociado de terceros o un proveedor de servicios local, deberá seleccionar el nombre del proveedor en el menú desplegable. Proporcione los otros detalles relacionados con el conector.

- Seleccione **Microsoft Exchange Online** si el registro MX apunta a Microsoft y tiene un buzón de Exchange Online.

Revise la configuración y edítelas si es necesario. A continuación, seleccione **Crear evaluación**. Debería recibir un mensaje de confirmación para indicar que la configuración ha finalizado.

El informe de evaluación de Microsoft Defender para Office 365 se genera una vez al día. Los datos pueden tardar hasta 24 horas en rellenarse.

### <a name="exchange-mail-flow-rules-optional"></a>Reglas de flujo de correo de Exchange (opcional)

Si tiene una puerta de enlace existente, la habilitación del modo de evaluación activará el filtrado mejorado para conectores. Esta característica mejora la precisión del filtrado modificando la dirección IP del remitente entrante. Esta característica puede cambiar los veredictos de filtro y, si no omite Exchange Online Protection, esto puede alterar la entrega de determinados mensajes. En este caso, es posible que quiera omitir temporalmente el filtrado para analizar el impacto. Para omitir el filtrado, cree una regla de flujo de correo (también conocida como regla de transporte) en el Centro de administración de Exchange (EAC) en <https://admin.exchange.microsoft.com/#/transportrules> que establezca la SCL de los mensajes en -1 (si aún no tiene una). Para obtener instrucciones, consulte [Uso de reglas de flujo de correo para establecer el nivel de confianza de correo no deseado (SCL) en los mensajes de Exchange Online](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

## <a name="evaluate-capabilities"></a>Funcionalidades de evaluación

Una vez generado el informe de evaluación, vea cuántos vínculos de amenazas avanzadas, datos adjuntos de amenazas avanzados y posibles suplantaciones se identificaron en los correos electrónicos y áreas de trabajo de colaboración de su organización.

Una vez que la prueba haya expirado, puede seguir accediendo al informe durante 90 días. Sin embargo, no recopilará más información. Si desea seguir usando Microsoft Defender para Office 365 una vez que haya expirado la prueba, asegúrese de [comprar una suscripción de pago para Microsoft Defender para Office 365 (plan 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Puede ir a **Configuración** para actualizar el enrutamiento o desactivar la evaluación en cualquier momento. Sin embargo, debe volver a pasar por el mismo proceso de configuración si decide continuar con la evaluación después de haberla desactivado.

## <a name="provide-feedback"></a>Enviar comentarios

Sus comentarios nos ayudan a mejorar la protección de su entorno frente a ataques avanzados. Comparta su experiencia e impresiones de las funcionalidades del producto y los resultados de evaluación.

Seleccione **Dar comentarios** para que sepamos lo que piensa.
