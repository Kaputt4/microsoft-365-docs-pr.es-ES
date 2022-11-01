---
title: Data Residency para Office para La Web
description: Data Residency para Office para La Web
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
ms.openlocfilehash: ed0c8f67eedf666c7a20d2169d64bc2fad41f576
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806114"
---
# <a name="data-residency-for-office-for-the-web"></a>Data Residency para Office para La Web

## <a name="overview"></a>Información general

Documentación del [servicio: Office para la Web descripción del servicio: Descripciones del servicio](/office365/servicedescriptions/office-online-service-description/office-online-service-description)

Resumen de funcionalidad: Office para la Web (anteriormente Office Web Apps) abre documentos de Word, Excel y PowerPoint en el explorador web. Office para la Web facilita el trabajo y el uso compartido de archivos de Office desde cualquier lugar con una conexión a Internet, desde casi cualquier dispositivo. Los clientes de Microsoft 365 con Word, Excel o PowerPoint pueden ver, crear y editar archivos en cualquier lugar.

## <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

### <a name="advanced-data-residency-add-on"></a>Complemento de Data Residency avanzado

Condiciones necesarias:

1. _El inquilino_ tiene un país de registro incluido en _Geografía de la región local_ o _Geografía de región local expandida_.
1. _El inquilino_ tiene una suscripción _Data Residency avanzada_ válida para todos los usuarios del _inquilino_.
1. Los datos del cliente de la suscripción de Office para web se aprovisionan en _Geografía de la región local_ o _Geografía expandida de la región local_.

**Compromiso:**

Consulte la [página Compromiso de ADR](m365-dr-commitments.md#office-for-the-web) para conocer los datos específicos del cliente en reposo para Office for the Web.

### <a name="migration"></a>Migración

La caché de documentos no se migra a la nueva _geografía_ y se restablecerá a medida que los usuarios trabajen en documentos.

### <a name="how-can-i-determine-customer-data-location"></a>¿Cómo puedo determinar la ubicación de los datos del cliente?

Estamos en proceso de actualizar la ubicación de datos _real en el_ Centro de Administración inquilinos. Cuando se complete este cambio, el inquilino podrá ver la ubicación de datos real, para en los datos de ámbito, navegando a Administración| Configuración| Configuración de la organización| Perfil de la organización| Ubicación de datos. Hasta que ese cambio sea visible, puede ver los datos de Exchange Online o la información de ubicación de SharePoint Online para comprender dónde se almacenan los datos de ámbito de este servicio.
