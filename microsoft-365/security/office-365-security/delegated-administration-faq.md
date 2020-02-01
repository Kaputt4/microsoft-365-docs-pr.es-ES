---
title: Preguntas más frecuentes sobre administración delegada
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: En este tema se proporcionan las preguntas más frecuentes y sus respuestas para los socios y distribuidores de Microsoft que desean realizar tareas de administración delegada de Office 365, incluida la capacidad de administrar Exchange Online Protection (EOP) para otros inquilinos (empresas).
ms.openlocfilehash: 2a237da685ae3c3d81c5a0912e15b5e7370e2118
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599487"
---
# <a name="delegated-administration-faq"></a>Preguntas más frecuentes sobre administración delegada

En este tema se proporcionan las preguntas más frecuentes y sus respuestas para los socios y distribuidores de Microsoft que desean realizar tareas de administración delegada de Office 365, incluida la capacidad de administrar Exchange Online Protection (EOP) para otros inquilinos (empresas).

**P. Soy distribuidor y necesito administrar los inquilinos de mis clientes. ¿Cómo funciona?**

A. Si es un distribuidor o un partner de Microsoft y se ha registrado para ser un asesor de Microsoft, puede solicitar permiso para administrar su inquilino dentro del centro de administración. Esto se conoce como administración delegada y le permite administrar su inquilino de Office 365 (incluida la configuración de EOP) como si usted fuera un administrador de la organización. Los pasos para llevar a cabo la administración delegada son los siguientes:

1. Regístrese para ser un [asesor de Microsoft Office 365](https://aka.ms/cloudbenefits).

2. Regístrese para llevar a cabo la administración delegada de Office 365. Antes de que pueda comenzar a administrar la cuenta de un cliente, este debe autorizarlo como administrador delegado. Para obtener su aprobación, primero debe [enviarle una oferta de administración delegada](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e). (También puede ofrecerle administración delegada a su cliente más adelante).

3. Cree la cuenta de administrador delegado mediante los pasos descritos en [Agregar, cambiar o eliminar un partner Asesor de suscripción](https://docs.microsoft.com/office365/admin/misc/add-partner).

Visite [Partners: cree su empresa y administre su suscripción a office 365 Partner](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) para obtener más información acerca de cómo configurar la administración delegada de Office 365.

**P. Soy un cliente, no un distribuidor, ¿cómo puedo configurar un administrador delegado para mis inquilinos?**

R. En este momento, la administración delegada solo está disponible para los distribuidores y socios. Sin embargo, hemos incluido un script de ejemplo de Windows PowerShell que le ayudará a aplicar directivas a sus subinquilinos (empresas). Para obtener más información, consulte [Script de ejemplo para aplicar la configuración de EOP a varios inquilinos](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

**P. ¿Puedo evitar que mi administrador de subinquilinos modifique la directiva?**

R. Office 365 actualmente no tiene esta capacidad.

**P. ¿Puedo obtener informes consolidados en todos mis subinquilinos?**

R. La generación de informes consolidados en las empresas que administra no está disponible para los informes del centro de administración de Microsoft 365 en este momento. Sin embargo, puede hacerlo con [Microsoft Graph](https://docs.microsoft.com/graph/overview).
