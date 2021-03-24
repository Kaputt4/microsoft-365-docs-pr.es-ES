---
title: Preguntas más frecuentes sobre administración delegada
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden ver preguntas y respuestas más frecuentes sobre las tareas de administración delegadas en Microsoft 365 para partners y revendedores de Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 82fa70a8025f67610032ba59368bc74789b60f84
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073328"
---
# <a name="delegated-administration-faq"></a>Preguntas más frecuentes sobre administración delegada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En este artículo se proporcionan preguntas y respuestas más frecuentes sobre las tareas de administración delegadas en Microsoft 365 para partners y revendedores de Microsoft. La administración delegada incluye la capacidad de administrar la configuración de Exchange Online Protection (EOP) para otros inquilinos (empresas).

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>Soy revendedor y tengo que administrar los inquilinos de mis clientes. ¿Cómo funciona esto?

Si es un partner o revendedor de Microsoft y se ha registrado para  ser asesor de Microsoft, puede solicitar capacidades de administración delegadas en la organización de Microsoft 365 de su cliente.

La administración delegada le permite administrar Microsoft 365 (incluida la configuración de EOP) como si fuera un administrador dentro de esa organización. Los pasos para configurar la administración delegada se describen en la siguiente lista:

1. Regístrese para ser un [asesor de Microsoft Office 365](https://partner.microsoft.com/?cloudbenefits).

2. Registrarse para la administración delegada. Antes de empezar a administrar el inquilino de un cliente, debe autorizarlo como administrador delegado. Para obtener su aprobación, primero debe [enviarle una oferta de administración delegada](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). También puede ofrecer administración delegada a su cliente más adelante.

3. Cree la cuenta de administrador delegada con los pasos descritos [en Agregar, cambiar o eliminar un partner asesor de suscripción.](../../admin/misc/add-partner.md)

Visitar [partners: cree su empresa y administre la](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) suscripción de partner para obtener más información sobre cómo configurar la administración delegada.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>Soy un cliente, no un revendedor. ¿Cómo se puede configurar el administrador delegado para mis subterfugios?

La administración delegada solo está disponible para revendedores y partners. Sin embargo, hay un script de PowerShell de ejemplo que le ayudará a aplicar directivas a sus subterfugios (empresas). Para obtener más información, consulte [Script de ejemplo para aplicar la configuración de EOP a varios inquilinos](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>¿Puedo impedir que mi administrador subteniente modifique mi directiva?

No. Microsoft 365 no tiene actualmente esta funcionalidad.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>¿Puedo obtener informes consolidados en todos mis subterfugios?

Los informes consolidados en todas las empresas que administra no están disponibles en los informes del Centro de administración de Microsoft 365. Sin embargo, puede obtener informes mediante [Microsoft Graph](/graph/overview).