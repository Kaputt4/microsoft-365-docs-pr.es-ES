---
title: Data Residency para Viva Connections
description: Data Residency para Viva Connections
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
ms.openlocfilehash: ce1bb0dc936c57493c5fd16e4301adda9e214c8d
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806151"
---
# <a name="data-residency-for-viva-connections"></a>Data Residency para Viva Connections

## <a name="overview"></a>Información general

Documentación del servicio: [Información general: Viva Connections](/viva/connections/viva-connections-overview)

Resumen de funcionalidad: Microsoft Viva Connections es la puerta de enlace a una experiencia de empleado moderna diseñada para mantener a todos involucrados e informados. Conexiones Viva es una aplicación personalizable de Microsoft Teams que ofrece a todos los usuarios un destino personalizado para descubrir noticias, conversaciones y las herramientas pertinentes que necesitan para tener éxito.  El almacenamiento de datos está relacionado con los siguientes componentes de Viva Connections: panel y fuente.

## <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

### <a name="advanced-data-residency-add-on"></a>Complemento de Data Residency avanzado

Condiciones necesarias:

1. _El inquilino_ tiene un país de registro incluido en _Geografía de la región local_ o _Geografía de región local expandida_.
1. _El inquilino_ tiene una suscripción Data Residency avanzada válida para todos los usuarios del _inquilino_.
1. Los datos del cliente de Viva Connections suscripción se aprovisionan en _Geografía de la región local_ o _Geografía expandida de la región local_.

**Compromiso:**

Consulte la [página Compromiso de ADR](m365-dr-commitments.md#viva-connections) para ver los datos específicos del cliente en reposo para Viva Connections.

### <a name="migration"></a>Migración

Los datos se almacenan en Exchange Online, SharePoint Online y Microsoft Teams.  Los procesos de migración se controlan mediante las cargas de trabajo aplicables o pertinentes.

### <a name="how-can-i-determine-customer-data-location"></a>¿Cómo puedo determinar la ubicación de los datos del cliente?

Estamos en proceso de actualizar la ubicación de datos _real en el_ Centro de Administración inquilinos.  Una vez completado este cambio, podrá ver la ubicación de datos real, para los datos confirmados, navegando a Administración->Settings->Org Settings->Organization Profile->Data Location.  Hasta que ese cambio sea visible, puede ver la información de ubicación de datos de Exchange Online, SharePoint Online y Microsoft Teams para comprender dónde se almacenan los datos confirmados para este servicio.
