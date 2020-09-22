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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden ver las preguntas más frecuentes y sus respuestas sobre las tareas de administración delegada en Microsoft 365 para partners y revendedores de Microsoft.
ms.openlocfilehash: 6729f276e6afea83568ca59d3bf48c08fcd837d2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203148"
---
# <a name="delegated-administration-faq"></a>Preguntas más frecuentes sobre administración delegada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En este artículo se proporcionan preguntas frecuentes y respuestas a las tareas de administración delegada en Microsoft 365 para partners y revendedores de Microsoft. La administración delegada incluye la capacidad de administrar la configuración de Exchange Online Protection (EOP) para otros inquilinos (empresas).

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>Soy un revendedor y necesito administrar mis inquilinos de cliente. ¿Cómo funciona?

Si es un distribuidor o un partner de Microsoft y se ha suscrito a un asesor de Microsoft, puede solicitar funcionalidades de _administración delegada_ en la organización de Microsoft 365 del cliente.

La administración delegada le permite administrar Microsoft 365 (incluida la configuración de EOP) como si fuera un administrador de esa organización. En la lista siguiente se describen los pasos para configurar la administración delegada:

1. Regístrese para ser un [asesor de Microsoft Office 365](https://aka.ms/cloudbenefits).

2. Regístrese para obtener una administración delegada. Antes de que pueda empezar a administrar el espacio empresarial de un cliente, debe autorizarlo como administrador delegado. Para obtener su aprobación, primero debe [enviarle una oferta de administración delegada](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). También puede ofrecer administración delegada a su cliente en un momento posterior.

3. Cree la cuenta de administrador delegado mediante los pasos descritos en [Agregar, cambiar o eliminar un partner Asesor de suscripción](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).

Visite [Partners: cree su empresa y administre la suscripción de Partner](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) para obtener más información acerca de cómo configurar la administración delegada.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>Soy un cliente, no un revendedor. ¿Cómo puede configurar el administrador delegado para mis inquilinos?

La administración delegada solo está disponible para revendedores y socios. Sin embargo, hay un script de PowerShell de ejemplo que le ayudará a aplicar directivas a sus subinquilinos (empresas). Para obtener más información, consulte [Script de ejemplo para aplicar la configuración de EOP a varios inquilinos](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>¿Puedo evitar que mi administrador de subinquilino modifique mi directiva?

No. Microsoft 365 no tiene actualmente esta capacidad.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>¿Puedo obtener informes consolidados en todos mis mis inquilinos?

Los informes consolidados en las empresas que administra no están disponibles en los informes del centro de administración de Microsoft 365. Sin embargo, puede obtener informes con [Microsoft Graph](https://docs.microsoft.com/graph/overview).
