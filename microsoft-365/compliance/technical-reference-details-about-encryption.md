---
title: Detalles de referencia técnica sobre el cifrado
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 06/15/2020
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
description: Obtenga información sobre los distintos certificados, tecnologías y conjuntos de cifrado de seguridad de la capa de transporte (TLS) que se usan para el cifrado en Office 365 y Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 244d7a6cef6d77322475245435dafb6c89ab5353
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663433"
---
# <a name="technical-reference-details-about-encryption"></a>Detalles de referencia técnica sobre el cifrado

Consulte este artículo para obtener información sobre certificados, tecnologías y conjuntos de cifrado TLS usados para el [cifrado en Office 365](encryption.md). En este artículo también se proporcionan detalles sobre las despreciaciones planeadas.
  
- Si está buscando información general, vea [cifrado en Office 365](encryption.md).
- Si está buscando información de configuración, consulte [configurar el cifrado en Office 365 Enterprise](set-up-encryption.md).
- Para obtener información acerca de los conjuntos de cifrado compatibles con versiones específicas de Windows, consulte [conjuntos de cifrado en TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Propiedad y administración de certificados de Microsoft Office 365

No es necesario comprar ni mantener certificados para Office 365. En su lugar, Office 365 usa sus propios certificados.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Estándares de cifrado actuales y despreciaciones planeadas

Para proporcionar el mejor cifrado de su clase, Office 365 revisa con regularidad los estándares de cifrado compatibles. A veces, los estándares antiguos están en desuso porque están obsoletos y están menos protegidos. En este artículo se describen los conjuntos de cifrado admitidos actualmente y otros estándares y detalles sobre las despreciaciones planeadas.

## <a name="fips-compliance-for-office-365"></a>Cumplimiento de FIPS para Office 365

Todos los conjuntos de programas de cifrado compatibles con Office 365 usan algoritmos aceptables en FIPS 140-2. Office 365 hereda las validaciones FIPS de Windows (a través de Schannel). Para obtener información sobre Schannel, consulte [conjuntos de cifrado en TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versiones de TLS admitidas por Office 365

TLS, y SSL que se incluían antes de TLS, son protocolos criptográficos que protegen la comunicación a través de una red mediante certificados de seguridad para cifrar una conexión entre equipos. Office 365 admite TLS versión 1,2 (TLS 1,2).

La versión 1,3 de TLS (TLS 1,3) no es compatible actualmente.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Compatibilidad con el desuso de TLS 1,0 y 1,1

Office 365 ha dejado de admitir TLS 1,0 y 1,1 el 31 de octubre de 2018. Los nuevos problemas encontrados en los clientes, dispositivos o servicios que se conectan a Office 365 sobre TLS 1,0 y 1,1 no se solucionarán. El desuso oficial para los entornos altos y DoD de GCC empezó el 15 de enero de 2020. El desuso de TLS 1,0 y 1,1 para entornos en todo el mundo y GCC comenzó el 15 de octubre de 2020.

Para mantener una conexión segura con los servicios de Office 365 y Microsoft 365, todas las combinaciones cliente-servidor y explorador-servidor usan los conjuntos de cifrado TLS 1,2 y modernos. Es posible que tenga que actualizar ciertas combinaciones cliente-servidor y navegador-servidor. Para obtener información sobre cómo afecta este cambio, consulte [preparación del uso obligatorio de TLS 1,2 en Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Desuso de la compatibilidad con 3DES

Desde el 31 de octubre de 2018, Office 365 ya no admite el uso de conjuntos de cifrado 3DES para comunicarse con Office 365. Más concretamente, Office 365 ya no es compatible con el conjunto de cifrado de TLS_RSA_WITH_3DES_EDE_CBC_SHA. Desde el 28 de febrero de 2019, este conjunto de cifrado se ha deshabilitado en Office 365. Los clientes y servidores que se comunican con Office 365 deben admitir uno o varios de los cifrados admitidos. Para obtener una lista de los cifrados admitidos, consulte [conjuntos de cifrado de TLS compatibles con Office 365](#tls-cipher-suites-supported-by-office-365).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Desuso de la compatibilidad con certificados SHA-1 en Office 365

Desde junio de 2016, Office 365 ya no acepta un certificado SHA-1 para las conexiones salientes o entrantes. Use SHA-2 (algoritmo de hash seguro 2) o un algoritmo hash más seguro en la cadena de certificados.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Conjuntos de cifrado de TLS compatibles con Office 365

TLS utiliza *conjuntos de cifrado*, colecciones de algoritmos de cifrado, para establecer conexiones seguras. Office 365 admite los conjuntos de cifrado que se enumeran en la tabla siguiente. En la tabla se enumeran los conjuntos de cifrado en orden de rigor, con el conjunto de cifrado más seguro que aparece en primer lugar.

Office 365 responde a una solicitud de conexión en primer lugar al intentar conectarse con el conjunto de cifrado más seguro. Si la conexión no funciona, Office 365 probará con el segundo conjunto de cifrado más seguro de la lista, y así sucesivamente. El servicio continuará hacia abajo en la lista hasta que se acepte la conexión. Del mismo modo, cuando Office 365 solicita una conexión, el servicio receptor elige si se utilizará TLS y el conjunto de cifrado que se va a usar.

> [!IMPORTANT]
> Tenga en cuenta que las versiones de TLS están en desuso y que *no deben usarse* versiones obsoletas cuando hay versiones más recientes disponibles. TLS 1,3 no se admite actualmente. Si los servicios heredados no requieren TLS 1,0 o 1,1, debe deshabilitarlos.

| Conjunto de cifrado | Algoritmo/fuerza de intercambio de claves | Confidencialidad directa perfecta | Cifrado o seguridad | Algoritmo de autenticación |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|Sí <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|Sí <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|Sí <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|Sí <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|Sí <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|Sí <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |No <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |No <br/> |AES/256 <br/>|RSA/112 <br/> |

Estos conjuntos de cifrado admiten los protocolos TLS 1,0 y 1,1 hasta la fecha de desuso. Para los entornos de GCC altos y DoD, la fecha de degradación fue 15 de enero de 2020, y para los entornos de todo el mundo y GCC, la fecha fue el 15 de octubre de 2020.

| Protocolos | Nombre del conjunto de cifrado | Algoritmo/fuerza de intercambio de claves | Compatibilidad con confidencialidad directa perfecta | Algoritmo de autenticación/seguridad | Cifrado o seguridad |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Sí  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Sí  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |No  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |No  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |No   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |No   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>Artículos relacionados

[Conjuntos de cifrado TLS en Windows 10 V1903](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Cifrado en Office 365](encryption.md)
  
[Configurar el cifrado en Office 365 Enterprise](set-up-encryption.md)
  
[Implementación de Schannel TLS 1,0 en la actualización de estado de seguridad de Windows: 24 de noviembre de 2015](https://support.microsoft.com/kb/3117336)
  
[Mejoras de cifrado de TLS/SSL (centro de TI de Windows)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
[Preparación para TLS 1.2 en Office 365 y Office 365 GCC](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
