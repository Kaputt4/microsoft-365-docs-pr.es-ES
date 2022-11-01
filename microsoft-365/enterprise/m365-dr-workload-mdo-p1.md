---
title: Data Residency para Microsoft Defender para Office P1
description: Más información sobre Data Residency para Microsoft Defender para Office P1
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
ms.openlocfilehash: 4e4c002ca4748b2d125c0b8043e6198ac962115f
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806207"
---
# <a name="data-residency-for-microsoft-defender-for-office-p1"></a>Data Residency para Microsoft Defender para Office P1

## <a name="overview"></a>Información general

Documentación del servicio: [seguridad de Office 365, incluidos Microsoft Defender para Office 365 y Exchange Online Protection](/microsoft-365/security/office-365-security/defender-for-office-365)

Resumen de funcionalidad: protege el correo electrónico y la colaboración frente a malware, phish y compromiso de correo electrónico empresarial de día cero.  MDO P1 se basa en Exchange Online Protection (EOP).  

## <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

### <a name="advanced-data-residency-add-on"></a>Complemento de Data Residency avanzado

Condiciones necesarias:

1. _El inquilino_ tiene un país de registro incluido en _Geografía de la región local_ o _Geografía de región local expandida_.
1. _El inquilino_ tiene una suscripción de Data Residency avanzada válida para todos los usuarios del _inquilino_.
1. Los datos del cliente de la suscripción de MDO P1 se aprovisionan en _Geografía de región local_ o _Geografía de región local expandida_.

**Compromiso:**

Consulte la [página Compromiso de ADR](m365-dr-commitments.md#microsoft-defender-for-office-p1) para ver los datos específicos del cliente en reposo para Microsoft Defender para Office P1.

Otra información

Además, el procesamiento de datos necesarios para analizar amenazas e inspeccionar correos electrónicos, documentos, mensajes y vínculos sospechosos se realiza en un entorno de espacio aislado y se realiza dentro de la geografía de la _región local_ o _la región local expandida_.

## <a name="exchange-online-protection"></a>Exchange Online Protection

### <a name="overview"></a>Información general

Documentación del servicio: [introducción a Exchange Online Protection (EOP)](/microsoft-365/security/office-365-security/exchange-online-protection-overview)

Resumen de funcionalidad: Exchange Online Protection (EOP) es el servicio de filtrado basado en la nube que protege a su organización contra el correo no deseado, el malware y otras amenazas de correo electrónico.

### <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

#### <a name="advanced-data-residency-add-on"></a>Complemento de Data Residency avanzado

Condiciones necesarias:

1. _El inquilino_ tiene un país de registro incluido en _Geografía de la región local_ o _Geografía de región local expandida_.
1. _El inquilino_ tiene una suscripción de Data Residency avanzada válida para todos los usuarios del _inquilino_.
1. Los datos del cliente de la suscripción de EOP se aprovisionan en _Geografía de región local_ o _Geografía de región local expandida_

**Compromiso:**

Consulte la página [Compromiso avanzado de Data Residency](m365-dr-commitments.md) para obtener los datos específicos del cliente en reposo para Exchange Online Protection.

## <a name="migration"></a>Migración

Los datos del cliente de EOP se migran durante la migración Exchange Online. MDO P1 no tiene datos de cliente para migrar.

## <a name="how-can-i-determine-customer-data-location"></a>¿Cómo puedo determinar la ubicación de los datos del cliente?

Estamos en proceso de actualizar la ubicación de datos real en el Centro de Administración de _inquilinos_. Una vez completado este cambio, podrá ver la ubicación de datos real, para las cargas de trabajo confirmadas, navegando a Administración| Configuración| Configuración de la organización| Perfil de la organización| Ubicación de datos. Hasta que ese cambio sea visible, puede ver la información de ubicación de datos Exchange Online para comprender dónde se almacenan los datos del cliente en el ámbito de este servicio.
