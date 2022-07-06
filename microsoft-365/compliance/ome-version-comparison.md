---
title: Comparación de versiones de cifrado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: En este artículo se explican las diferencias entre las distintas versiones del cifrado de mensajes.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64a67ac9423463e4fcf1b5a3ff6c2262801933b0
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629341"
---
# <a name="compare-versions-of-message-encryption"></a>Comparar versiones del cifrado de mensajes

> [!IMPORTANT]
> El 28 de febrero de 2021, Microsoft desusó la compatibilidad con AD RMS en Exchange Online. Si ha implementado un entorno híbrido en el que los buzones de Exchange están en línea y usa IRM con Active Directory RMS local, tendrá que migrar a Azure. Las organizaciones que se han implementado en el entorno moderado de GCC también se ven afectadas. Consulte "Información general sobre el desuso de AD RMS en Exchange Online" en este artículo para obtener información.

El resto de este artículo compara el cifrado de mensajes (OME) Office 365 heredado con Cifrado de mensajes de Microsoft Purview y el cifrado avanzado de mensajes de Microsoft Purview. Cifrado de mensajes de Microsoft Purview es la fusión y la versión más reciente de OME y Information Rights Management (IRM). También se describen las características únicas de la implementación en GCC High. Los dos pueden coexistir en su organización. Para obtener información sobre cómo funcionan las nuevas funcionalidades, vea [Office 365 Cifrado de mensajes (OME).](ome.md)

Este artículo forma parte de una serie más amplia de artículos sobre el cifrado de mensajes. Este artículo está pensado para administradores y profesionales de TI. Si solo busca información sobre cómo enviar o recibir un mensaje cifrado, consulte la lista de artículos de [Cifrado](ome.md) de mensajes y busque el artículo que mejor se adapte a sus necesidades.

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Introducción al desuso de AD RMS en Exchange Online

Exchange Online incluye funcionalidad de Information Rights Management (IRM) que proporciona protección en línea y sin conexión de mensajes de correo electrónico y datos adjuntos. De forma predeterminada, Exchange Online usa Azure Information Protection. Sin embargo, es posible que su organización haya configurado Exchange Online IRM para usar Active Directory local Rights Management Service (AD RMS). La compatibilidad con AD RMS en Exchange Online se está retirando. En su lugar, Azure Information Protection reemplazará por completo AD RMS.

Para evaluar si este desuso afecta a su organización, consulte [Migración de AD RMS a Azure RMS en Exchange Online](/exchange/troubleshoot/administration/migrate-ad-rms-to-azure). En este artículo se proporcionan recomendaciones sobre las opciones de migración.

## <a name="side-by-side-comparison-of-message-encryption-features-and-capabilities"></a>Comparación en paralelo de características y funcionalidades de cifrado de mensajes

|           **Situación**           | **OME heredado**    | **IRM en AD RMS**        | **Cifrado de mensajes de Microsoft Purview** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*Envío de un correo cifrado*        |A través de reglas de flujo de correo de Exchange|El usuario final iniciado desde el escritorio de Outlook o Outlook en la Web; o mediante reglas de flujo de correo de Exchange|Usuario final iniciado desde el escritorio de Outlook, Outlook para Mac o Outlook en la Web; a través de reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) y prevención de pérdida de datos (DLP)|
|*Plantilla de administración de derechos*       |   N/D      |Opción No reenviar y plantillas personalizadas|Opción No reenviar, opción de solo cifrado y plantillas personalizadas|
|*Tipo de destinatario*                   |Destinatarios internos y externos|Solo destinatarios internos         |Destinatarios internos y externos|
|*Experiencia para el destinatario interno*|Los destinatarios reciben un mensaje HTML que descargan y abren en un explorador web o una aplicación móvil|Experiencia en línea nativa en clientes de Outlook|Experiencia insertada nativa para destinatarios de la misma organización con clientes de Outlook.  Los destinatarios pueden leer el mensaje desde el portal de OME mediante clientes distintos de Outlook (no se requiere ninguna descarga o aplicación).|
|*Experiencia para el destinatario externo*|Los destinatarios reciben un mensaje HTML que descargan y abren en un explorador web o una aplicación móvil|N/D|Experiencia en línea nativa para destinatarios de Microsoft 365. Todos los demás destinatarios pueden leer el mensaje desde el portal de OME (no se requiere descarga ni aplicación).|
|*Permisos de datos adjuntos*           |No hay restricciones en los datos adjuntos|Los datos adjuntos están protegidos|Los datos adjuntos están protegidos para la opción No reenviar y las plantillas personalizadas. Los administradores pueden elegir si los datos adjuntos de la opción de solo cifrado están protegidos o no.|
|*Compatibilidad con Bring your own key (BYOK)*|Ninguno                |Ninguno               |Compatible con BYOK          |
||

## <a name="advantages-of-microsoft-purview-message-encryption-over-legacy-ome"></a>Ventajas de Cifrado de mensajes de Microsoft Purview sobre OME heredado

Las nuevas funcionalidades proporcionan las siguientes ventajas:

- Capacidad de usar la opción de solo cifrado (que permite la colaboración segura), la opción No reenviar y las restricciones personalizadas.
- Los remitentes pueden enviar correo cifrado con las nuevas funcionalidades manualmente desde Outlook Desktop, Outlook para Mac y Outlook en la Web clientes.
- Los destinatarios de Microsoft 365 pueden usar una experiencia insertada en clientes de Outlook compatibles. Como alternativa, los administradores pueden elegir mostrar a los destinatarios de Microsoft 365 una experiencia de marca.
- Las cuentas fuera de Microsoft 365, como gmail, yahoo y cuentas de Microsoft, están federadas con el portal de OME, lo que proporciona una mejor experiencia de usuario para estos destinatarios. Todas las demás identidades usan un código de paso único para acceder a los mensajes cifrados.
- Los administradores pueden personalizar la personalización de marca y crear varias plantillas de personalización de marca.
- Los administradores pueden revocar los correos electrónicos cifrados con las nuevas funcionalidades.
- Las nuevas funcionalidades proporcionan informes de uso detallados a través del Centro de cumplimiento de seguridad &amp; .

## <a name="microsoft-purview-advanced-message-encryption-capabilities"></a>Funcionalidades avanzadas de cifrado de mensajes de Microsoft Purview

El cifrado avanzado de mensajes de Microsoft Purview ofrece funcionalidades adicionales además de Cifrado de mensajes de Microsoft Purview. Debe tener Cifrado de mensajes de Microsoft Purview configurado en su organización para poder usar el cifrado avanzado de mensajes. Además, para poder usar estas funcionalidades, los destinatarios deben ver y responder para proteger el correo a través de Cifrado de mensajes de Microsoft Purview Portal. Las funcionalidades avanzadas incluyen:

- Revocación de mensajes

- Expiración del mensaje

- Varias plantillas de personalización de marca

El cifrado avanzado de mensajes no se admite en GCC High.

Para obtener información sobre el uso del cifrado avanzado de mensajes, consulte [Cifrado avanzado de mensajes de Microsoft Purview](ome-advanced-message-encryption.md).

## <a name="unique-characteristics-of-microsoft-purview-message-encryption-in-a-gcc-high-deployment"></a>Características únicas de Cifrado de mensajes de Microsoft Purview en una implementación de GCC High

Si tiene previsto usar Cifrado de mensajes de Microsoft Purview en un entorno de GCC High, hay algunas características únicas con respecto a la experiencia del destinatario.

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>Correo electrónico cifrado entre destinatarios de GCC High y GCC High

Los remitentes pueden cifrar manualmente los correos electrónicos en Outlook para PC y Mac y Outlook en la Web, o bien las organizaciones pueden configurar una directiva para cifrar los correos electrónicos mediante reglas de flujo de correo de Exchange.

Los destinatarios dentro de GCC High reciben la misma experiencia de lectura en línea en Outlook para PC y Mac y Outlook en la Web que todos los demás usuarios.

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>Correo electrónico cifrado entre los destinatarios de GCC High y Non-GCC High

Los remitentes dentro de GCC High pueden enviar correo electrónico cifrado fuera del límite de GCC High y viceversa.

Todos los destinatarios fuera de GCC High, incluidos los usuarios comerciales de Microsoft 365, Outlook.com usuarios y otros usuarios de otros proveedores de correo electrónico como Gmail y Yahoo, reciben un correo contenedor. Este correo contenedor redirige al destinatario al portal de Cifrado de mensajes de Microsoft Purview, donde el destinatario puede leer y responder al mensaje. Esto también es cierto para los remitentes fuera de GCC High que envían correo cifrado OME a GCC High.

## <a name="coexistence-of-legacy-ome-and-microsoft-purview-message-encryption-in-the-same-tenant"></a>Coexistencia de OME heredado y Cifrado de mensajes de Microsoft Purview en el mismo inquilino

Puede usar OME heredado y Cifrado de mensajes de Microsoft Purview en el mismo inquilino. Como administrador, para ello, elija qué versión del cifrado de mensajes desea usar al crear las reglas de flujo de correo.

- Para especificar la versión heredada de OME, use la acción Regla de flujo de correo de Exchange **Aplicar la versión anterior de OME**.

- Para especificar Cifrado de mensajes de Microsoft Purview, use la acción **De aplicación Office 365 cifrado de mensajes y protección de derechos** de la regla de flujo de correo de Exchange.

Los usuarios pueden enviar manualmente correo cifrado con Cifrado de mensajes de Microsoft Purview desde Outlook Desktop, Outlook para Mac y Outlook en la Web.

## <a name="migrate-from-legacy-ome-to-microsoft-purview-message-encryption"></a>Migración de OME heredada a Cifrado de mensajes de Microsoft Purview

Aunque ambas versiones pueden coexistir, se recomienda encarecidamente editar las reglas de flujo de correo antiguas que usan la acción **de regla Aplicar la versión anterior de OME** para usar Cifrado de mensajes de Microsoft Purview. Actualice estas reglas para usar la acción de regla de flujo de correo **Aplicar Office 365 cifrado de mensajes y protección de derechos**. Para obtener instrucciones, consulte [Definición de reglas de flujo de correo para cifrar los mensajes de correo electrónico](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-ome"></a>Introducción a OME

Normalmente, Cifrado de mensajes de Microsoft Purview se habilita automáticamente para su organización. Para obtener más información sobre Cifrado de mensajes de Microsoft Purview dentro de la organización, consulte [Configuración de Cifrado de mensajes de Microsoft Purview](set-up-new-message-encryption-capabilities.md).

La versión heredada de OME se habilita automáticamente para su organización si ha habilitado Azure Information Protection. En el pasado, OME heredado funcionaba incluso si Azure Information Protection no estaba habilitado. Ya no es así.

Para empezar a usar OME heredado, si ha habilitado Azure Information Protection, configure reglas de flujo de correo que usen la acción de regla **Aplicar la versión anterior de OME**. Para obtener instrucciones, consulte [Definición de reglas de flujo de correo para cifrar los mensajes de correo electrónico](define-mail-flow-rules-to-encrypt-email.md).
