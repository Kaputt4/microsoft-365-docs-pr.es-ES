---
title: Microsoft 365 Defender para clientes del Gobierno de los EE.UU.
description: Obtenga información sobre los Microsoft 365 Defender para las funcionalidades y los requisitos de los clientes del Gobierno de EE. UU. disponibles
keywords: government, gcc, high, requirements, capabilities, defender, Microsoft 365 Defender, xdr, dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: d1fa56bc797a3f651d79ab87f9ade0a9d753849d
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482150"
---
# <a name="microsoft-365-defender-for-us-government-customers"></a>Microsoft 365 Defender para clientes del Gobierno de los EE.UU.

**Se aplica a:**
- Microsoft 365 Defender

Microsoft 365 Defender para los clientes del Gobierno de EE. UU., integrado en el entorno de Azure US Government, usa las mismas tecnologías subyacentes que Microsoft 365 Defender en Azure Commercial.

Esta oferta está disponible para los clientes de GCC, GCC High y DoD y se basa en la misma prevención, detección, investigación y corrección que la versión comercial. Sin embargo, hay algunas diferencias en la disponibilidad de las funcionalidades de esta oferta.

> [!NOTE]
> Si es un cliente de GCC que usa Defender for Cloud Apps, Defender para punto de conexión o Defender for Identity en comercial, debe realizar la transición de esos servicios a sus versiones de GCC para que sean aptos para Microsoft 365 Defender GCC.

## <a name="licensing-requirements"></a>Requisitos de licencias

Microsoft 365 Defender para los clientes del Gobierno de EE. UU. requiere una de las siguientes ofertas de licencias por volumen de Microsoft:

### <a name="desktop-licensing"></a>Licencias de escritorio

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft 365 GCC G5|Microsoft 365 E5 para GCC High|Microsoft 365 G5 para DOD|
|GCC de seguridad de Microsoft 365 G5|Seguridad de Microsoft 365 G5 para GCC High|Seguridad de Microsoft 365 G5 para DOD|
|GCC Enterprise Mobility + Security G5|Enterprise Mobility + Security E5 para GCC High|Enterprise Mobility + Security E5 para DOD|
|GCC Office 365 G5|Office 365 E5 para GCC High|Office 365 E5 para DOD|
|Microsoft Defender for Cloud Apps GCC|Microsoft Defender for Cloud Apps para GCC High|Microsoft Defender for Cloud Apps para DOD|
|Microsoft Defender para punto de conexión - GCC|Microsoft Defender para punto de conexión para GCC High|Microsoft Defender para punto de conexión para DOD|
|Microsoft Defender for Identity - GCC|Microsoft Defender for Identity para GCC High|Microsoft Defender for Identity para DOD|
|Microsoft Defender para Office 365 (Plan 2) GCC|Microsoft Defender para Office 365 (Plan 2) para GCC High|Microsoft Defender para Office 365 (Plan 2) para DOD|
|Windows 10 Enterprise E5 GCC|Windows 10 Enterprise E5 para GCC High|Windows 10 Enterprise E5 para DOD|
|

### <a name="server-licensing"></a>Licencias de servidor

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|GCC de Microsoft Defender para punto de conexión Server|Microsoft Defender para punto de conexión Server para GCC High|Microsoft Defender para punto de conexión Server for DOD|
|Microsoft Defender para servidores|Microsoft Defender para servidores: Administración pública|Microsoft Defender para servidores: Administración pública|
|

## <a name="portal-urls"></a>Direcciones URL del portal

A continuación se muestran las direcciones URL del portal de Microsoft 365 Defender para los clientes del gobierno de EE. UU.:

<br />

****

|Tipo de cliente|Portal URL|
|---|---|
|GCC|<https://security.microsoft.com>|
|GCC High|Implementando|
|DoD|Implementando|
|
> [!NOTE]
> Si es cliente de GCC y está en proceso de pasar de Microsoft Defender para punto de conexión comercial a GCC, use https://transition.security.microsoft.com para acceder a sus datos comerciales Microsoft Defender para punto de conexión.

## <a name="api"></a>API

En lugar de los URI públicos que aparecen en la documentación de la [API](api-overview.md), deberá usar los siguientes URI:

<br />

****

|Tipo de punto de conexión|GCC|GCC High & DoD|
|---|---|---|
|Inicio de sesión|`https://login.microsoftonline.com`|`https://login.microsoftonline.us`|
|API de Microsoft 365 Defender|`https://api-gcc.security.microsoft.us`|`https://api-gov.security.microsoft.us`|
|

## <a name="feature-parity-with-commercial"></a>Paridad de características con comercial

Microsoft 365 Defender para clientes del Gobierno de EE. UU. no tiene una paridad completa con la oferta comercial. Aunque nuestro objetivo es ofrecer todas las características y funcionalidades comerciales a nuestros clientes del Gobierno de EE. UU., todavía no hay algunas funcionalidades disponibles que queremos resaltar.

Estas son las brechas conocidas:

<br />

****

|Nombre de la característica|GCC|GCC High|DoD|
|---|:---:|:---:|:---:|
|Integraciones: Microsoft Sentinel (incidentes & datos sin procesar)|![Yes](../defender-endpoint/images/svg/check-yes.svg) En versión preliminar pública|![Yes](../defender-endpoint/images/svg/check-yes.svg) En versión preliminar pública|![Yes](../defender-endpoint/images/svg/check-yes.svg) En versión preliminar pública|
|Expertos en amenazas de Microsoft|![No](../defender-endpoint/images/svg/check-no.svg) En el trabajo pendiente de ingeniería|![No](../defender-endpoint/images/svg/check-no.svg) En el trabajo pendiente de ingeniería|![No](../defender-endpoint/images/svg/check-no.svg) En el trabajo pendiente de ingeniería|

Para obtener una lista detallada de las tablas de Event Streaming API, consulte [Microsoft 365 Defender tipos de eventos de streaming admitidos en Event Streaming API](supported-event-types.md).

## <a name="more-details"></a>Más detalles

Para obtener más información, consulte las páginas de us gov de cargas de trabajo individuales:

- [Microsoft Defender for Cloud Apps](/enterprise-mobility-security/solutions/ems-cloud-app-security-govt-service-description).
- [Microsoft Defender for Identity](/enterprise-mobility-security/solutions/ems-mdi-govt-service-description).
- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/gov).
