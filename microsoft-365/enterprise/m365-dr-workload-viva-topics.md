---
title: Data Residency para Viva Topics
description: Data Residency para Viva Topics
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.reviewer: dmwmsft
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 416e6dccca24e4c79c0853cbed886b2d4e977c31
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806146"
---
# <a name="data-residency-for-viva-topics"></a>Data Residency para Viva Topics

## <a name="summary"></a>Resumen

Documentación del servicio: [introducción a Microsoft Viva Topics](/viva/topics/topic-experiences-overview)

Resumen de funcionalidad: Viva Topics usa la tecnología de Inteligencia artificial de Microsoft, Microsoft 365, Microsoft Graph, Search y otros componentes y servicios para aportar conocimiento a los usuarios en las aplicaciones de Microsoft 365 que usan todos los días, empezando por las páginas modernas de SharePoint, Outlook, Microsoft Search y Search en Word, PowerPoint y Excel.

## <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

### <a name="advanced-data-residency-add-on"></a>Complemento de Data Residency avanzado

Condiciones necesarias:

1. _El inquilino_ tiene un país de registro incluido en _Geografía de la región local_ o _Geografía de región local expandida_.
1. _El inquilino_ tiene una suscripción Data Residency avanzada válida para todos los usuarios del _inquilino_.
1. Los datos del cliente de Viva Topics suscripción se aprovisionan en _Geografía de región local_ o _Geografía de región local expandida_.

**Compromiso:**

Consulte la [página Compromiso de ADR](m365-dr-commitments.md#viva-topics) para conocer los datos específicos del cliente en reposo para Viva Topics.

## <a name="migration"></a>Migración

Los datos se almacenan en Exchange Online, SharePoint Online y Microsoft Teams.  Los procesos de migración se controlan mediante las cargas de trabajo aplicables o pertinentes.

## <a name="how-can-i-determine-customer-data-location"></a>¿Cómo puedo determinar la ubicación de los datos del cliente?

Estamos en proceso de actualizar la ubicación de datos _real en el_ Centro de Administración inquilinos.  Una vez completado este cambio, podrá ver la ubicación de datos real, para los datos confirmados, navegando a Administración->Settings->Org Settings->Organization Profile->Data Location.  Hasta que ese cambio sea visible, puede ver la información de ubicación de datos Exchange Online para comprender dónde se almacenan los datos confirmados para este servicio.
