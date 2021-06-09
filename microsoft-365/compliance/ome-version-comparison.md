---
title: Comparación de versiones de cifrado de mensajes (OME)
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Este artículo ayuda a explicar las diferencias entre las diferentes versiones de Cifrado de mensajes de Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 92beb3625c0b115fe77f1667a448bf0bf9589040
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760138"
---
# <a name="compare-versions-of-ome"></a>Comparar versiones de OME

> [!IMPORTANT]
> El 28 de febrero de 2021, Microsoft desusó la compatibilidad con AD RMS en Exchange Online. Si ha implementado un entorno híbrido donde los buzones de Exchange están en línea y está usando IRM con RMS de Active Directory local, tendrá que migrar a Azure. Las organizaciones que se han implementado en GCC entorno moderado también se ven afectadas. Vea "Overview of AD RMS deprecation in Exchange Online" en este artículo para obtener información.

El resto de este artículo compara los Cifrado de mensajes de Office 365 heredados (OME) con las nuevas funcionalidades de OME y Cifrado de mensajes avanzado de Office 365. Las nuevas funcionalidades son una fusión y una versión más reciente de OME y Information Rights Management (IRM). También se describen las características únicas de la implementación en GCC High. Los dos pueden coexistir en la organización. Para obtener información sobre cómo funcionan las nuevas [funcionalidades, vea Cifrado de mensajes de Office 365 (OME).](ome.md)

Este artículo forma parte de una serie más grande de artículos sobre Cifrado de mensajes de Office 365. Este artículo está dirigido a administradores e ITPros. Si solo está buscando información sobre cómo enviar o recibir un mensaje cifrado, consulte la lista de artículos de [Cifrado de mensajes de Office 365 (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades.

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Información general sobre la desuso de AD RMS en Exchange Online

Exchange Online incluye funcionalidad de Information Rights Management (IRM) que proporciona protección en línea y sin conexión de mensajes de correo electrónico y datos adjuntos. De forma predeterminada, Exchange Online Azure Information Protection. Sin embargo, es posible que la organización haya configurado Exchange Online IRM para usar el Servicio de administración de derechos de Active Directory (AD RMS) local. La compatibilidad con AD RMS Exchange Online se retira. En su lugar, Azure Information Protection reemplazará a AD RMS por completo.

Para evaluar si este desuso afecta a su organización, vea [How to migrate AD RMS to Azure RMS in Exchange Online](https://support.microsoft.com/help/5001237). En este artículo se proporcionan recomendaciones sobre las opciones de migración.

## <a name="side-by-side-comparison-of-ome-features-and-capabilities"></a>Comparación en paralelo de características y funcionalidades de OME

|           **Situación**           | **OME heredado**    | **IRM en AD RMS**        | **Nuevas funcionalidades de OME** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*Enviar un correo cifrado*        |A través Exchange de flujo de correo|Usuario final iniciado desde Outlook escritorio o Outlook en la Web; o a través Exchange de flujo de correo|El usuario final se inició Outlook escritorio, Outlook para Mac o Outlook en la Web; a Exchange de flujo de correo (también conocidas como reglas de transporte) y prevención de pérdida de datos (DLP)|
|*Plantilla de administración de derechos*       |   N/D      |Opción No reenviar y plantillas personalizadas|Opción No reenviar, opción de solo cifrado y plantillas personalizadas|
|*Tipo de destinatario*                   |Destinatarios internos y externos|Solo destinatarios internos         |Destinatarios internos y externos|
|*Experiencia para destinatarios internos*|Los destinatarios reciben un mensaje HTML, que descargan y abren en un explorador web o una aplicación móvil|Experiencia en línea nativa en Outlook clientes|Experiencia en línea nativa para destinatarios de la misma organización que usan Outlook clientes.  Los destinatarios pueden leer el mensaje desde el portal de OME con clientes que no Outlook (no se requiere ninguna descarga o aplicación).|
|*Experiencia para destinatarios externos*|Los destinatarios reciben un mensaje HTML, que descargan y abren en un explorador web o una aplicación móvil|N/D|Experiencia en línea nativa para Microsoft 365 destinatarios. Todos los demás destinatarios pueden leer mensajes desde el portal de OME (no se requiere descarga ni aplicación).|
|*Permisos de datos adjuntos*           |Sin restricciones en los datos adjuntos|Los datos adjuntos están protegidos|Los datos adjuntos están protegidos para la opción No reenviar y las plantillas personalizadas. Los administradores pueden elegir si los datos adjuntos de la opción de solo cifrado están protegidos o no.|
|*Traer su propia clave (BYOK) soporte técnico*|Ninguno                |Ninguno               |BYOK compatible          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>Ventajas de las nuevas funcionalidades de OME sobre OME heredada

Las nuevas funcionalidades proporcionan las siguientes ventajas:

- Posibilidad de usar la opción de solo cifrado (que habilita la colaboración segura), la opción No reenviar y las restricciones personalizadas.
- Los remitentes pueden enviar correo cifrado con las nuevas funcionalidades manualmente desde Outlook escritorio, Outlook para Mac y Outlook en los clientes web.
- Microsoft 365 los destinatarios pueden usar una experiencia en línea en clientes Outlook compatibles. Como alternativa, los administradores pueden elegir mostrar a los Microsoft 365 una experiencia de marca.
- Las cuentas fuera de Microsoft 365, como las cuentas de Gmail, Yahoo y Microsoft, están federadas con el portal de OME, que proporciona una mejor experiencia de usuario para estos destinatarios. Todas las demás identidades usan un código de paso único para obtener acceso a mensajes cifrados.
- Los administradores pueden personalizar la personalización de marca y crear varias plantillas de personalización de marca.
- Los administradores pueden revocar los correos electrónicos cifrados con las nuevas funcionalidades.
- Las nuevas funcionalidades proporcionan informes de uso detallados a través del Centro de &amp; cumplimiento de seguridad.

## <a name="office-365-advanced-message-encryption-capabilities"></a>Cifrado de mensajes avanzado de Office 365 funcionalidades

Cifrado de mensajes avanzado de Office 365 ofrece capacidades adicionales además de las nuevas funcionalidades de OME. Debe tener las nuevas funcionalidades Cifrado de mensajes de Office 365 de correo electrónico configuradas en la organización para poder usar las funciones de cifrado de mensajes avanzado. Además, para poder usar estas funcionalidades, los destinatarios deben ver y responder para proteger el correo a través del Portal de OME. Las funcionalidades avanzadas incluyen:

- Revocación de mensajes

- Expiración de mensajes

- Varias plantillas de personal de marca

Cifrado de mensajes avanzado de Office 365 no se admite en GCC High.

Para obtener información sobre el uso del cifrado de mensajes avanzado, [vea Cifrado de mensajes avanzado de Office 365](ome-advanced-message-encryption.md).

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>Características únicas de Cifrado de mensajes de Office 365 en una implementación GCC high

Si tiene previsto usar Cifrado de mensajes de Office 365 en un entorno GCC High, hay algunas características únicas con respecto a la experiencia del destinatario.

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>Correo electrónico cifrado entre GCC destinatarios high y GCC high

Los remitentes pueden cifrar manualmente los correos electrónicos en Outlook para PC y Mac y Outlook en la web, o bien las organizaciones pueden configurar una directiva para cifrar correos electrónicos mediante Exchange reglas de flujo de correo.

Los destinatarios de GCC High reciben la misma experiencia de lectura en línea en Outlook para PC y Mac y Outlook en la web que todos los demás usuarios.

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>Correo electrónico cifrado entre GCC destinatarios High y Non-GCC High

Los remitentes de GCC High pueden enviar correo electrónico cifrado fuera del GCC límite alto y viceversa.

Todos los destinatarios fuera de GCC High, incluidos los usuarios de Microsoft 365 comerciales, los usuarios de Outlook.com y otros usuarios de otros proveedores de correo electrónico como Gmail y Yahoo, reciben un correo contenedor. Este correo contenedor redirige al destinatario al Portal de OME, donde el destinatario puede leer y responder al mensaje. Esto también es así para los remitentes fuera de GCC High que envían correo cifrado de OME a GCC High.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Coexistencia de OME heredada y las nuevas funcionalidades en el mismo inquilino

Puede usar OME heredada y las nuevas funcionalidades en el mismo espacio empresarial. Como administrador, debe elegir qué versión de OME desea usar al crear las reglas de flujo de correo.

- Para especificar la versión heredada de OME, use la acción Exchange regla de flujo de correo Aplicar la **versión anterior de OME**.

- Para especificar las nuevas funcionalidades, use la acción Exchange regla de flujo de correo **Aplicar Cifrado de mensajes de Office 365 y protección de derechos**.

Los usuarios pueden enviar manualmente correo cifrado con las nuevas funcionalidades de Outlook escritorio, Outlook para Mac y Outlook en la web.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>Migrar de la OME heredada a las nuevas funcionalidades

Aunque ambas versiones de OME pueden coexistir, se recomienda encarecidamente editar las reglas de flujo de correo antiguas que usan la acción de regla Aplicar la versión anterior de **OME** para usar las nuevas funcionalidades. Actualice estas reglas para usar la acción de regla de flujo de correo **Aplicar Cifrado de mensajes de Office 365 y protección de derechos**. Para obtener instrucciones, vea [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-ome"></a>Introducción a OME

Normalmente, las nuevas funcionalidades de OME se habilitan automáticamente para la organización. Para obtener más información acerca de las nuevas funcionalidades de OME dentro de la organización, vea Configurar nuevas [Cifrado de mensajes de Office 365 funciones](set-up-new-message-encryption-capabilities.md).

La versión heredada de OME se habilita automáticamente para su organización si ha habilitado Azure Information Protection. En el pasado, la OME heredada funcionaba incluso si Azure Information Protection no estaba habilitada. Ya no es así.

Para empezar a usar OME heredada, si ha habilitado Azure Information Protection, configure las reglas de flujo de correo que usan la acción de regla Aplicar la **versión anterior de OME**. Para obtener instrucciones, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico.](define-mail-flow-rules-to-encrypt-email.md)