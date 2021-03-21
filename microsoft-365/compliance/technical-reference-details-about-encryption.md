---
title: Información de referencia técnica sobre el cifrado
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
- Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Obtenga información sobre los distintos certificados, tecnologías y conjuntos de cifrado de seguridad de la capa de transporte (TLS) usados para el cifrado en Office 365 y Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e7e50ea399cd694f512e0538de3f7e67c63ee0e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919356"
---
# <a name="technical-reference-details-about-encryption"></a>Información de referencia técnica sobre el cifrado

Consulte este artículo para obtener información sobre certificados, tecnologías y conjuntos de cifrado TLS usados para el cifrado [en Office 365](encryption.md). En este artículo también se proporcionan detalles sobre los desusos planeados.
  
- Si está buscando información general, vea [Cifrado en Office 365](encryption.md).
- Si está buscando información de configuración, vea [Configurar el cifrado en Office 365 Enterprise](set-up-encryption.md).
- Para obtener información sobre conjuntos de cifrado compatibles con versiones específicas de Windows, vea [Cipher Suites in TLS/SSL (Schannel SSP).](/windows/desktop/SecAuthN/cipher-suites-in-schannel)

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Propiedad y administración de certificados de Microsoft Office 365

No es necesario comprar ni mantener certificados para Office 365. En su lugar, Office 365 usa sus propios certificados.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Estándares de cifrado actuales y desusos planeados

Para proporcionar el mejor cifrado de su clase, Office 365 revisa periódicamente los estándares de cifrado admitidos. A veces, los estándares antiguos están en desuso a medida que se vuelven obsoletos y menos seguros. En este artículo se describen los conjuntos de cifrado admitidos actualmente y otros estándares y detalles sobre los desusos planeados.

## <a name="fips-compliance-for-office-365"></a>Cumplimiento de FIPS para Office 365

Todos los conjuntos de cifrado admitidos por Office 365 usan algoritmos aceptables en FIPS 140-2. Office 365 hereda las validaciones fips de Windows (a través de Schannel). Para obtener información acerca de Schannel, vea [Cipher Suites in TLS/SSL (Schannel SSP).](/windows/desktop/SecAuthN/cipher-suites-in-schannel)
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versiones de TLS admitidas por Office 365

TLS y SSL anteriores a TLS son protocolos criptográficos que protegen la comunicación a través de una red mediante certificados de seguridad para cifrar una conexión entre equipos. Office 365 admite TLS versión 1.2 (TLS 1.2).

Actualmente no se admite TLS versión 1.3 (TLS 1.3).
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Compatibilidad con la desuso de TLS 1.0 y 1.1

Office 365 dejó de admitir TLS 1.0 y 1.1 el 31 de octubre de 2018. Hemos completado la deshabilitación de TLS 1.0 y 1.1 en entornos GCC High y DoD. Comenzamos a deshabilitar TLS 1.0 y 1.1 para entornos de todo el mundo y GCC a partir del 15 de octubre de 2020 y continuaremos con la implementación en las próximas semanas y meses.

Para mantener una conexión segura con los servicios de Office 365 y Microsoft 365, todas las combinaciones cliente-servidor y explorador-servidor usan TLS 1.2 y conjuntos de cifrado modernos. Es posible que tenga que actualizar ciertas combinaciones cliente-servidor y navegador-servidor. Para obtener información sobre cómo le afecta este cambio, vea [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Desuso de compatibilidad con 3DES

Desde el 31 de octubre de 2018, Office 365 ya no admite el uso de conjuntos de cifrado 3DES para la comunicación con Office 365. Más específicamente, Office 365 ya no admite el conjunto TLS_RSA_WITH_3DES_EDE_CBC_SHA de cifrado. Desde el 28 de febrero de 2019, este conjunto de cifrado se ha deshabilitado en Office 365. Los clientes y servidores que se comunican con Office 365 deben admitir uno o varios de los cifrados compatibles. Para obtener una lista de cifrados admitidos, vea Conjuntos de cifrado [TLS admitidos por Office 365](#tls-cipher-suites-supported-by-office-365).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Desuso de la compatibilidad con certificados SHA-1 en Office 365

Desde junio de 2016, Office 365 ya no acepta un certificado SHA-1 para las conexiones salientes o entrantes. Use SHA-2 (Algoritmo hash seguro 2) o un algoritmo de hash más fuerte en la cadena de certificados.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Conjuntos de cifrado TLS compatibles con Office 365

TLS usa *conjuntos de cifrado,* colecciones de algoritmos de cifrado, para establecer conexiones seguras. Office 365 admite los conjuntos de cifrado enumerados en la tabla siguiente. En la tabla se enumeran los conjuntos de cifrado en orden de intensidad, con el conjunto de cifrado más fuerte enumerado primero.

Office 365 responde a una solicitud de conexión intentando conectarse primero con el conjunto de cifrado más seguro. Si la conexión no funciona, Office 365 intenta el segundo conjunto de cifrado más seguro de la lista, y así sucesivamente. El servicio continúa en la lista hasta que se acepta la conexión. Asimismo, cuando Office 365 solicita una conexión, el servicio de recepción elige si se usará TLS y qué conjunto de cifrado usar.

> [!IMPORTANT]
> Tenga en cuenta que las versiones TLS están en desuso y que las versiones en desuso no deben *usarse* cuando hay disponibles versiones más recientes. Tls 1.3 actualmente no es compatible. Si los servicios heredados no requieren TLS 1.0 o 1.1, debe deshabilitarlos.

| Conjunto de cifrado | Algoritmo/fuerza de intercambio de claves | Secreto de reenvío | Cifrado/resistencia | Algoritmo de autenticación |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|Sí <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|Sí <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|Sí <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|Sí <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|Sí <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|Sí <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |No <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |No <br/> |AES/256 <br/>|RSA/112 <br/> |

Estos conjuntos de cifrado admiten protocolos TLS 1.0 y 1.1 hasta su fecha de desuso. Para los entornos GCC High y DoD que la fecha de desuso era el 15 de enero de 2020, y para los entornos mundiales y GCC esa fecha era el 15 de octubre de 2020.

| Protocolos | Nombre del conjunto de cifrado | Algoritmo de intercambio de claves/Fuerza | Compatibilidad con el secreto de reenvío | Algoritmo de autenticación/Fuerza | Cifrado/Intensidad |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Sí  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Sí  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |No  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |No  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |No   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |No   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>Artículos relacionados

[Conjuntos de cifrado TLS en Windows 10 v1903](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Cifrado en Office 365](encryption.md)
  
[Configurar el cifrado en Office 365 Enterprise](set-up-encryption.md)
  
[Implementación de Schannel de TLS 1.0 en la actualización de estado de seguridad de Windows: 24 de noviembre de 2015](https://support.microsoft.com/kb/3117336)
  
[Mejoras criptográficas TLS/SSL (Centro de WINDOWS IT)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[Preparación para TLS 1.2 en Office 365 y Office 365 GCC](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)