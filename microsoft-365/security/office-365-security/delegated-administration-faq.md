---
title: Preguntas más frecuentes sobre administración delegada
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: En este tema se proporcionan preguntas más frecuentes y respuestas para los partners y revendedores de Microsoft que quieren realizar tareas delegadas de administración de Microsoft 365.
ms.openlocfilehash: d1522973292b290fd9f66f534ca23aeaa55ee756
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209528"
---
# <a name="delegated-administration-faq"></a>Preguntas más frecuentes sobre administración delegada

En este tema se proporcionan preguntas frecuentes y respuestas a los partners y revendedores de Microsoft que quieren realizar tareas de administración delegada, incluida la capacidad de administrar Exchange Online Protection (EOP) para otros inquilinos (empresas).

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a>Soy un revendedor y necesito administrar los inquilinos de mis clientes; ¿Cómo funciona?

Si es un distribuidor o un partner de Microsoft y se ha registrado para ser un asesor de Microsoft, puede solicitar permiso para administrar su inquilino dentro del centro de administración. Esto se conoce como administración delegada y le permite administrar su inquilino de Microsoft 365 (incluida la configuración de EOP) como si fuera un administrador de su organización. Los pasos para llevar a cabo la administración delegada son los siguientes:

1. Regístrese para ser un [asesor de Microsoft Office 365](https://aka.ms/cloudbenefits).

2. Regístrese para obtener una administración delegada. Antes de que pueda comenzar a administrar la cuenta de un cliente, este debe autorizarlo como administrador delegado. Para obtener su aprobación, primero debe [enviarle una oferta de administración delegada](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). (También puede ofrecerle administración delegada a su cliente más adelante).

3. Cree la cuenta de administrador delegado mediante los pasos descritos en [Agregar, cambiar o eliminar un partner Asesor de suscripción](https://docs.microsoft.com/office365/admin/misc/add-partner).

Visite [Partners: cree su empresa y administre la suscripción de Partner](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) para obtener más información acerca de cómo configurar la administración delegada.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a>Soy un cliente, no un revendedor, ¿cómo puede configurar un administrador delegado para mis subinquilinos?

En este momento, la administración delegada solo está disponible para los distribuidores y socios. Sin embargo, hemos incluido un script de ejemplo de Windows PowerShell que le ayudará a aplicar directivas a sus subinquilinos (empresas). Para obtener más información, consulte [Script de ejemplo para aplicar la configuración de EOP a varios inquilinos](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a>¿Puedo evitar que mi administrador de subinquilinos modifique la directiva?

Microsoft 365 no tiene actualmente esta capacidad.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a>¿Puedo obtener informes consolidados en todos mis subinquilinos?

La generación de informes consolidados en las empresas que administra no está disponible para los informes del centro de administración de Microsoft 365 en este momento. Sin embargo, puede hacerlo con [Microsoft Graph](https://docs.microsoft.com/graph/overview).
