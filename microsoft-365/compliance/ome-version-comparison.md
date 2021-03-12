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
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Este artículo ayuda a explicar las diferencias entre las diferentes versiones del cifrado de mensajes de Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a587e27460d949811f9f30af0244cf325aaadac6
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741341"
---
# <a name="compare-versions-of-ome"></a>Comparar versiones de OME

> [!IMPORTANT]
> El 28 de febrero de 2021, Microsoft dejará de admitir AD RMS en Exchange Online. Si ha implementado un entorno híbrido donde los buzones de Exchange están en línea y está usando IRM con RMS de Active Directory local, tendrá que migrar a Azure. Las organizaciones que se han implementado en el entorno moderado de GCC también se ven afectadas. Vea "Overview of AD RMS deprecation in Exchange Online" en este artículo para obtener información.

El resto de este artículo compara el cifrado de mensajes (OME) de Office 365 heredado con las nuevas funcionalidades de OME y el cifrado de mensajes avanzado de Office 365. Las nuevas funcionalidades son una fusión y una versión más reciente de OME y Information Rights Management (IRM). También se describen las características únicas de implementación en GCC High. Los dos pueden coexistir en la organización. Para obtener información sobre cómo funcionan las nuevas funcionalidades, vea Cifrado de mensajes [de Office 365 (OME).](ome.md)

Este artículo forma parte de una serie más grande de artículos sobre cifrado de mensajes de Office 365. Este artículo está dirigido a administradores e ITPros. Si solo está buscando información sobre el envío o recepción de un mensaje cifrado, consulte la lista de artículos en Cifrado de mensajes [(OME) de Office 365](ome.md) y busque el artículo que mejor se adapte a sus necesidades.

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Información general sobre la desuso de AD RMS en Exchange Online

Exchange Online incluye funcionalidad de Information Rights Management (IRM) que proporciona protección en línea y sin conexión de mensajes de correo electrónico y datos adjuntos. De forma predeterminada, Exchange Online usa Azure Azure Information Protection. Sin embargo, es posible que su organización haya configurado Exchange Online IRM para usar el Servicio de administración de derechos de Active Directory (AD RMS) local. La compatibilidad con AD RMS en Exchange Online se está retirando. En su lugar, Azure Information Protection reemplazará a AD RMS por completo.

Antes de comenzar, revise y evalúe el impacto de su organización. Si su organización ya usa Azure Information Protection para cifrar el correo electrónico en Exchange Online, no hay nada que hacer. Si cifra el correo electrónico con reglas de flujo de correo de Exchange, por ejemplo, mediante cifrado de mensajes de Office 365, no tendrá que cambiar el correo electrónico seguro. De lo contrario, deberá prepararse para la desuso de AD RMS cambiando a Azure Information Protection.

### <a name="prepare-for-ad-rms-deprecation"></a>Prepararse para la desuso de AD RMS

Si ya ha configurado Azure Information Protection pero no lo está usando, habilite el servicio con Exchange Online PowerShell. En el equipo local, con una cuenta laboral o educativa que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) en una ventana Windows PowerShell usuario.

Para habilitar Azure Information Protection, use Set-IrmConfiguration cmdlet escribiendo el siguiente comando.

```powershell
Set-IrmConfiguration -AzureRMSLicensingEnabled $true
```

Si su organización aún no ha configurado Azure Information Protection, deberá migrar de AD RMS a Azure Information Protection. Para obtener instrucciones, [consulte Migración de AD RMS a Azure Information Protection](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms).

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>Comparación en paralelo de características y funcionalidades

|           **Situación**           | **OME heredado**    | **IRM en AD RMS**        | **Nuevas funcionalidades de OME** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*Enviar un correo cifrado*        |A través de reglas de flujo de correo de Exchange|Usuario final iniciado desde el escritorio de Outlook o Outlook en la Web; o a través de reglas de flujo de correo de Exchange|Usuario final iniciado desde el escritorio de Outlook, Outlook para Mac o Outlook en la Web; a través de reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) y prevención de pérdida de datos (DLP)|
|*Plantilla de administración de derechos*       |   N/D      |Opción No reenviar y plantillas personalizadas|Opción No reenviar, opción de solo cifrado y plantillas personalizadas|
|*Tipo de destinatario*                   |Destinatarios internos y externos|Solo destinatarios internos         |Destinatarios internos y externos|
|*Experiencia para destinatarios internos*|Los destinatarios reciben un mensaje HTML, que descargan y abren en un explorador web o una aplicación móvil|Experiencia en línea nativa en clientes de Outlook|Experiencia en línea nativa para destinatarios de la misma organización que usan clientes de Outlook.  Los destinatarios pueden leer mensajes desde el portal de OME con clientes distintos de Outlook (no se requiere ninguna descarga o aplicación).|
|*Experiencia para destinatarios externos*|Los destinatarios reciben un mensaje HTML, que descargan y abren en un explorador web o una aplicación móvil|N/D|Experiencia en línea nativa para destinatarios de Microsoft 365. Todos los demás destinatarios pueden leer mensajes desde el portal de OME (no se requiere descarga ni aplicación).|
|*Permisos de datos adjuntos*           |Sin restricciones en los datos adjuntos|Los datos adjuntos están protegidos|Los datos adjuntos están protegidos para la opción No reenviar y las plantillas personalizadas. Los administradores pueden elegir si los datos adjuntos de la opción de solo cifrado están protegidos o no.|
|*Traer su propia clave (BYOK) soporte técnico*|Ninguno                |Ninguno               |BYOK compatible          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>Ventajas de las nuevas funcionalidades de OME sobre OME heredada

Las nuevas funcionalidades proporcionan las siguientes ventajas:

- Posibilidad de usar la opción de solo cifrado (que habilita la colaboración segura), la opción No reenviar y las restricciones personalizadas.
- Los remitentes pueden enviar correo cifrado con las nuevas funcionalidades manualmente desde Outlook Desktop, Outlook para Mac y Outlook en los clientes web.
- Los destinatarios de Microsoft 365 pueden usar una experiencia en línea en clientes de Outlook compatibles. Como alternativa, los administradores pueden elegir mostrar a los destinatarios de Microsoft 365 una experiencia de marca.
- Las cuentas fuera de Microsoft 365, como las cuentas de Gmail, Yahoo y Microsoft, están federadas con el portal de OME, que proporciona una mejor experiencia de usuario para estos destinatarios. Todas las demás identidades usan un código de paso único para obtener acceso a mensajes cifrados.
- Los administradores pueden personalizar la personalización de marca y crear varias plantillas de personalización de marca.
- Los administradores pueden revocar los correos electrónicos cifrados con las nuevas funcionalidades.
- Las nuevas funcionalidades proporcionan informes de uso detallados a través del Centro de &amp; cumplimiento de seguridad.

## <a name="office-365-advanced-message-encryption-capabilities"></a>Funcionalidades de cifrado de mensajes avanzado de Office 365

El cifrado de mensajes avanzado de Office 365 ofrece capacidades adicionales además de las nuevas funcionalidades de OME. Debe tener las nuevas capacidades de cifrado de mensajes de Office 365 configuradas en su organización para poder usar las funciones de cifrado de mensajes avanzado. Además, para poder usar estas funcionalidades, los destinatarios deben ver y responder para proteger el correo a través del Portal de OME. Las funcionalidades avanzadas incluyen:

- Revocación de mensajes

- Expiración de mensajes

- Varias plantillas de personal de marca

El cifrado de mensajes avanzado de Office 365 no se admite en GCC High.

Para obtener información sobre el uso del cifrado de mensajes avanzado, vea Cifrado de mensajes avanzado de [Office 365](ome-advanced-message-encryption.md).

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>Características únicas del cifrado de mensajes de Office 365 en una implementación de GCC High

Si planea usar el cifrado de mensajes de Office 365 en un entorno GCC High, hay algunas características únicas con respecto a la experiencia del destinatario.

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>Correo electrónico cifrado entre destinatarios GCC High y GCC High

Los remitentes pueden cifrar manualmente los correos electrónicos en Outlook para PC y Mac y Outlook en la web, o bien las organizaciones pueden configurar una directiva para cifrar correos electrónicos mediante reglas de flujo de correo de Exchange.

Los destinatarios de GCC High reciben la misma experiencia de lectura en línea en Outlook para PC y Mac y Outlook en la web que el resto de usuarios.

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>Correo electrónico cifrado entre destinatarios GCC High y Non-GCC High

Los remitentes de GCC High pueden enviar correo electrónico cifrado fuera del límite de GCC High y viceversa.

Todos los destinatarios externos a GCC High, incluidos los usuarios comerciales de Microsoft 365, los usuarios de Outlook.com y otros usuarios de otros proveedores de correo electrónico como Gmail y Yahoo, reciben un correo contenedor. Este correo contenedor redirige al destinatario al Portal de OME, donde el destinatario puede leer y responder al mensaje. Esto también es así para los remitentes externos a GCC High que envían correo cifrado de OME a GCC High.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Coexistencia de OME heredada y las nuevas funcionalidades en el mismo inquilino

Puede usar OME heredada y las nuevas funcionalidades en el mismo espacio empresarial. Como administrador, debe elegir qué versión de OME desea usar al crear las reglas de flujo de correo.

- Para especificar la versión heredada de OME, use la acción Regla de flujo de correo de Exchange **Aplicar la versión anterior de OME**.

- Para especificar las nuevas funcionalidades, use la acción De regla de flujo de correo de Exchange Aplicar cifrado de mensajes de **Office 365 y protección de derechos**.

Los usuarios pueden enviar manualmente correo cifrado con las nuevas funcionalidades de Outlook Desktop, Outlook para Mac y Outlook en la web.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>Migrar de la OME heredada a las nuevas funcionalidades

Aunque ambas versiones de OME pueden coexistir, se recomienda encarecidamente editar las reglas de flujo de correo antiguas que usan la acción de regla Aplicar la versión anterior de **OME** para usar las nuevas funcionalidades. Actualice estas reglas para usar la acción de regla de flujo de correo Aplicar cifrado de mensajes de **Office 365 y protección de derechos**. Para obtener instrucciones, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-ome"></a>Introducción a OME

Normalmente, las nuevas funcionalidades de OME se habilitan automáticamente para la organización. Para obtener más información acerca de las nuevas funcionalidades de OME dentro de la organización, vea [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).

La versión heredada de OME se habilita automáticamente para su organización si ha habilitado Azure Information Protection. En el pasado, la OME heredada funcionaba incluso si Azure Information Protection no estaba habilitada. Ya no es así.

Para empezar a usar OME heredada, si ha habilitado Azure Information Protection, configure las reglas de flujo de correo que usan la acción de regla Aplicar la **versión anterior de OME**. Para obtener instrucciones, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico.](define-mail-flow-rules-to-encrypt-email.md)
