---
title: Microsoft 365 Defender para clientes del Gobierno de ESTADOS UNIDOS
description: Obtenga información sobre las Microsoft 365 Defender y las capacidades disponibles para los clientes del Gobierno de Estados Unidos
keywords: government, gcc, high, requirements, capabilities, defender, Microsoft 365 Defender, xdr, dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 3e8f6e523a5483de99beb0af7d01ab96951b7a3e
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "61375339"
---
# <a name="microsoft-365-defender-for-us-government-customers"></a>Microsoft 365 Defender para clientes del Gobierno de ESTADOS UNIDOS

**Se aplica a:**
- Microsoft 365 Defender

Microsoft 365 Defender para clientes del gobierno de Estados Unidos, integrados en el entorno de Azure US Government, usa las mismas tecnologías subyacentes que Microsoft 365 Defender en Azure Commercial.

Esta oferta está disponible para clientes GCC, GCC High y DoD y se basa en la misma prevención, detección, investigación y corrección que la versión comercial. Sin embargo, hay algunas diferencias en la disponibilidad de capacidades para esta oferta.

> [!NOTE]
> Si es un cliente de GCC que usa Defender para aplicaciones en la nube, Defender para endpoint o Defender for Identity en Commercial, debe realizar la transición de esos servicios a sus versiones de GCC para que sean aptos para Microsoft 365 Defender GCC.

## <a name="licensing-requirements"></a>Requisitos de licencias

Microsoft 365 Defender para los clientes del Gobierno de Estados Unidos requiere una de las siguientes ofertas de licencias por volumen de Microsoft:

### <a name="desktop-licensing"></a>Licencias de escritorio

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft 365 GCC G5|Microsoft 365 E5 para GCC High|Microsoft 365 G5 para DOD|
|Microsoft 365 G5 Security GCC|Microsoft 365 G5 Security for GCC High|Microsoft 365 G5 Security for DOD|
|Enterprise Mobility + Security G5 GCC|Enterprise Mobility + Security E5 para GCC High|Enterprise Mobility + Security E5 para DOD|
|Office 365 G5 GCC|Office 365 E5 para GCC High|Office 365 E5 para DOD|
|Microsoft Defender para aplicaciones en la nube GCC|Microsoft Defender para aplicaciones en la nube para GCC high|Microsoft Defender para aplicaciones en la nube para DOD|
|Microsoft Defender para endpoint: GCC|Microsoft Defender para endpoint for GCC High|Microsoft Defender para endpoint para DOD|
|Microsoft Defender para la identidad: GCC|Microsoft Defender para identity for GCC High|Microsoft Defender para identidad para DOD|
|Microsoft Defender para Office 365 (Plan 2) GCC|Microsoft Defender para Office 365 (Plan 2) para GCC High|Microsoft Defender para Office 365 (Plan 2) para DOD|
|Windows 10 Enterprise E5 GCC|Windows 10 Enterprise E5 para GCC High|Windows 10 Enterprise E5 para DOD|
|

### <a name="server-licensing"></a>Licencias de servidor

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft Defender para endpoint server GCC|Microsoft Defender para Endpoint Server para GCC High|Microsoft Defender para Endpoint Server para DOD|
|Microsoft Defender para servidores|Microsoft Defender para servidores- Gobierno|Microsoft Defender para servidores- Gobierno|
|

## <a name="portal-urls"></a>Direcciones URL del portal

A continuación se de Microsoft 365 Defender direcciones URL del portal para clientes del Gobierno de ESTADOS UNIDOS:

<br />

****

|Tipo de cliente|Portal URL|
|---|---|
|GCC|<https://security.microsoft.com>|
|GCC High|Implementando|
|DoD|Implementando|
|
> [!NOTE]
> Si es un cliente GCC y en el proceso de pasar de Microsoft Defender para endpoint comercial a GCC, use para obtener acceso a los datos comerciales de https://transition.security.microsoft.com Microsoft Defender para endpoint.

## <a name="api"></a>API

En lugar de los URI públicos enumerados en nuestra [documentación de la API,](api-overview.md)deberá usar los siguientes URI:

<br />

****

|Tipo de extremo|GCC|GCC High & DoD|
|---|---|---|
|Inicio de sesión|`https://login.microsoftonline.com`|`https://login.microsoftonline.us`|
|Microsoft 365 Defender API|`https://api-gcc.security.microsoft.us`|`https://api-gov.security.microsoft.us`|
|

## <a name="feature-parity-with-commercial"></a>Paridad de características con comercial

Microsoft 365 Defender para los clientes del Gobierno de Estados Unidos no tiene una paridad completa con la oferta comercial. Aunque nuestro objetivo es ofrecer todas las funciones y características comerciales a nuestros clientes del Gobierno de Estados Unidos, aún no hay algunas funcionalidades disponibles que queremos destacar.

Estas son las diferencias conocidas:

<br />

****

|Nombre de la característica|GCC|GCC High|DoD|
|---|:---:|:---:|:---:|
|Integraciones: Microsoft Sentinel (incidentes & datos sin procesar)|![Sí](../defender-endpoint/images/svg/check-yes.svg)|![Sí](../defender-endpoint/images/svg/check-yes.svg) En versión preliminar privada|![Sí](../defender-endpoint/images/svg/check-yes.svg) En versión preliminar privada|
|Expertos en amenazas de Microsoft|![No](../defender-endpoint/images/svg/check-no.svg) En el trabajo pendiente de ingeniería|![No](../defender-endpoint/images/svg/check-no.svg) En el trabajo pendiente de ingeniería|![No](../defender-endpoint/images/svg/check-no.svg) En el trabajo pendiente de ingeniería|

## <a name="more-details"></a>Más detalles

Para obtener más información, vea las cargas de trabajo individuales de las páginas de Us Gov:
- [Microsoft Defender para aplicaciones en la nube](/enterprise-mobility-security/solutions/ems-cloud-app-security-govt-service-description).
- [Microsoft Defender para identity](/enterprise-mobility-security/solutions/ems-mdi-govt-service-description).
- [Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/gov).
