---
title: Administrar permite y bloquea en la lista de permitidos o bloqueados de inquilinos
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
ms.date: 08/11/2022
search.appverid:
- MET150
ms.collection:
- m365-security
ms.custom: ''
description: Obtenga información sobre cómo administrar los bloques y los permitidos en la lista de permitidos o bloqueados de inquilinos en el portal de seguridad.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 20dc3a8a9b69da2df684d5f0f35f8b552f3b1f4f
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68622164"
---
# <a name="manage-your-allows-and-blocks-in-the-tenant-allowblock-list"></a>Administrar los bloques y los permitidos en la lista de permitidos o bloqueados de inquilinos

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones de correo en organizaciones Exchange Online o independientes de Exchange Online Protection (EOP) sin Exchange Online buzones, es posible que no esté de acuerdo con el veredicto de filtrado de EOP. Por ejemplo, un buen mensaje podría marcarse como incorrecto (un falso positivo) o un mensaje incorrecto podría permitirse a través de (un falso negativo).

La lista de permitidos o bloqueados de inquilinos del portal de Microsoft 365 Defender proporciona una manera de invalidar manualmente los veredictos de filtrado de Microsoft 365. La lista de permitidos o bloqueados de inquilinos se usa durante el flujo de correo para los mensajes entrantes de remitentes externos (no se aplica a los mensajes dentro de la organización) y en el momento de hacer clic en el usuario.

La lista Permitir o bloquear inquilinos está disponible en el portal de Microsoft 365 Defender en <https://security.microsoft.com> \> **Directivas & reglas** \> **Directivas** \> de amenazas Listas de **inquilinos permitidos o bloqueados** en la sección **Reglas**. Para ir directamente a la página **Permitir o bloquear listas de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

Para obtener instrucciones de configuración y creación de entradas, consulte los temas siguientes:

- **Dominios y direcciones de correo electrónico** y **remitentes suplantados**: [permitir o bloquear correos electrónicos mediante la lista de permitidos o bloqueados de](allow-block-email-spoof.md) inquilinos
- **Archivos**: [permitir o bloquear archivos mediante la lista de inquilinos permitidos o bloqueados](allow-block-files.md)
- **Direcciones URL**: [permitir o bloquear direcciones URL mediante la lista de permitidos o bloqueados de inquilinos](allow-block-urls.md).

Estos artículos contienen procedimientos en el portal de Microsoft 365 Defender y en PowerShell.

## <a name="block-entries-in-the-tenant-allowblock-list"></a>Bloquear entradas en la lista de permitidos o bloqueados de inquilinos

Use el portal envíos (también conocido como *envío de administrador*) en <https://security.microsoft.com/reportsubmission> para crear entradas de bloque para los siguientes tipos de elementos a medida que los informe como falsos positivos a Microsoft:

- **Dominios y direcciones de correo electrónico**:
  - Email mensajes de estos remitentes se marcan como *spam de alta confianza* (SCL = 9). Lo que sucede con los mensajes viene determinado por la [directiva antispam](configure-your-spam-filter-policies.md) que detectó el mensaje para el destinatario. En la directiva de antispam predeterminada y en las nuevas directivas personalizadas, los mensajes marcados como correo no deseado de alta confianza se entregan de forma predeterminada a la carpeta Junk Email. En las [directivas de seguridad preestablecidas](preset-security-policies.md) Estándar y Estricta, los mensajes de spam de alta confianza se ponen en cuarentena.
  - Los usuarios de la organización no pueden enviar correo electrónico a estos dominios y direcciones bloqueados. Recibirán el siguiente informe de no entrega (también conocido como NDR o mensaje de devolución): `5.7.1  Your message can't be delivered because one or more recipients are blocked by your organization's tenant allow/block list policy.` todo el mensaje se bloquea a todos los destinatarios si el correo electrónico se envía a cualquiera de las entradas de la lista.

- **Archivos**: Email mensajes que contienen estos archivos bloqueados se bloquean como *malware*.

- **Direcciones URL**: Email mensajes que contienen estas direcciones URL bloqueadas se bloquean como *suplantación de identidad de alta confianza*. Los mensajes que contienen las direcciones URL bloqueadas se ponen en cuarentena.

En la Lista de permitidos o bloqueados de inquilinos, también puede crear directamente entradas de bloque para los siguientes tipos de elementos:

- **Dominios y direcciones de correo electrónico**, **archivos** y **direcciones URL**.

- **Remitentes suplantados**: si invalida manualmente un veredicto de permitido existente a partir de la [inteligencia de suplantación](learn-about-spoof-intelligence.md) de identidad, el remitente suplantado bloqueado se convierte en una entrada de bloque manual que aparece solo en la pestaña **Remitentes suplantados de la Lista de permitidos o bloqueados de inquilinos** .

De forma predeterminada, las entradas de bloque para **dominios y direcciones de correo electrónico**, **archivos** y **direcciones URL** expiran después de 30 días, pero puede configurarlas para que expiren hasta 90 días o para que nunca expiren. Las entradas de bloque para **remitentes suplantados** nunca expiran.

## <a name="allow-entries-in-the-tenant-allowblock-list"></a>Permitir entradas en la lista de permitidos o bloqueados de inquilinos

En la mayoría de los casos, no puede crear directamente entradas permitidas en la lista de permitidos o bloqueados de inquilinos:

- **Dominios y direcciones de correo electrónico**, **archivos** y **direcciones URL**: no se pueden crear entradas permitidas directamente en la lista de permitidos o bloqueados de inquilinos. En su lugar, usa el portal Envíos en <https://security.microsoft.com/reportsubmission> para informar del **correo electrónico**, **los datos adjuntos de correo electrónico** o la **dirección URL** a Microsoft, ya **que no se debería haber bloqueado (falso positivo).**

- **Remitentes suplantados**:
  - Si la inteligencia de suplantación de identidad ya ha bloqueado el mensaje como suplantación de identidad, use el portal Envíos en <https://security.microsoft.com/reportsubmission> para informar del **correo electrónico** a Microsoft, ya **que no debería haberse bloqueado (Falso positivo).**
  - Puede crear de forma proactiva una entrada de permiso para un remitente suplantado en la pestaña **Remitente suplantado** de la lista de permitidos o bloqueados de inquilinos antes de que la [inteligencia de suplantación](learn-about-spoof-intelligence.md) identifique y bloquee el mensaje como suplantación de identidad.

En la lista siguiente se describe lo que sucede en la lista de permitidos o bloqueados de inquilinos cuando se notifica algo a Microsoft como falso positivo en el portal envíos:

- **Email datos adjuntos** y **direcciones URL**: se crea una entrada allow y aparece en la pestaña **Archivos** o **direcciones URL** de la Lista de permitidos o bloqueados de inquilinos.

- **Email**: Si la pila de filtrado de Microsoft 365 bloqueó un mensaje, es posible que se cree una entrada allow en la lista de permitidos o bloqueados de inquilinos:

  - Si la [inteligencia de suplantación](learn-about-spoof-intelligence.md) de identidad bloqueó el mensaje, se crea una entrada de permiso para el remitente y aparece en la pestaña **Remitentes suplantados** de la lista de permitidos de inquilinos.

  - Si la [protección de suplantación de usuario o dominio](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) bloqueó el mensaje en Defender para Office 365, no se crea una entrada de permitido en la lista de permitidos o bloqueados de inquilinos. En su lugar, el dominio o el remitente se agrega a la **sección Remitentes y dominios de confianza** de la [directiva anti-phishing](configure-mdo-anti-phishing-policies.md#use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies) que detectó el mensaje.

  - Si el mensaje se bloqueó por otros motivos, se crea una entrada de permiso para el remitente y aparece en la pestaña **Dominios & direcciones** de la Lista de bloqueos permitidos de inquilinos.

  - Si el mensaje no se bloqueó y no se creó una entrada de permiso para el remitente, no se creará en la pestaña **Remitentes suplantados** ni en la pestaña **Dominios & direcciones** .

De forma predeterminada, permitir entradas para **dominios y direcciones de correo electrónico**, **archivos** y **direcciones URL** expiran después de 30 días, que también es el máximo. Permitir entradas para **remitentes suplantados** nunca expira.

> [!NOTE]
> Microsoft no le permite crear entradas permitidas directamente, ya que conduce a la creación de permites que no son necesarios, por lo que expone el inquilino del cliente a correos electrónicos malintencionados que, de lo contrario, podrían haber sido filtrados por el sistema.
>
> Microsoft administra el proceso de creación de permitir desde envío mediante la creación de permite las entidades (dominios o direcciones de correo electrónico, remitentes suplantados, direcciones URL, archivos) que se determinaron como malintencionadas por los filtros durante el flujo de correo. Por ejemplo, si se ha determinado que el remitente y una dirección URL del mensaje son incorrectos, se crea una entrada allow para el remitente y se crea una entrada allow para la dirección URL.
>
> Cuando se vuelve a encontrar esa entidad (dirección de dominio o correo electrónico, dirección URL, archivo), se omiten todos los filtros asociados a esa entidad.
>
> Durante el flujo de correo, si los mensajes del dominio o la dirección de correo electrónico pasan otras comprobaciones en la pila de filtrado, se entregarán los mensajes. Por ejemplo, si se supera la [autenticación por correo electrónico](email-validation-and-authentication.md) , se entregará un mensaje de un remitente en la entrada allow.

## <a name="what-to-expect-after-you-add-an-allow-or-block-entry"></a>Qué esperar después de agregar una entrada de permitir o bloquear

Después de agregar una entrada de permiso a través del portal envíos o una entrada de bloque en la lista de permitidos o bloqueados de inquilinos, la entrada debería empezar a funcionar inmediatamente el 99,999 % del tiempo. Para el resto, podría tardar hasta 24 horas.

Se recomienda permitir que las entradas expiren automáticamente después de 30 días para ver si el sistema ha obtenido información sobre el permiso o el bloque. Si no es así, debe realizar otra entrada para dar al sistema otros 30 días para aprender.

Con **permitir la administración de expiración** (actualmente en versión preliminar privada), si Microsoft no ha aprendido de la entrada de permitir, Microsoft ampliará automáticamente el tiempo de expiración de las entradas permitidas que pronto expirarán en otros 30 días. Esta extensión ayuda a evitar que el correo electrónico legítimo vuelva a ir a correo no deseado o a cuarentena. Si Microsoft no aprende en un plazo de 90 días naturales a partir de la fecha de creación original de la entrada permitida, Microsoft quitará la entrada permitida.

Si Microsoft ha aprendido de la entrada allow, se quitará la entrada y obtendrá una alerta que le informará sobre ella.
