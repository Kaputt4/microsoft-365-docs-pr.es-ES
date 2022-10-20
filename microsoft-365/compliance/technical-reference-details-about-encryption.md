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
ms.localizationpriority: medium
ms.collection:
- purview-compliance
- m365solution-mip
- m365initiative-compliance
- tier1
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Obtenga información sobre los distintos certificados, tecnologías y conjuntos de cifrado de seguridad de la capa de transporte (TLS) que se usan para el cifrado en Office 365 y Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a26d54a4532c7c6fe5c07f59368bd143a53b5285
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68644755"
---
# <a name="technical-reference-details-about-encryption"></a>Información de referencia técnica sobre el cifrado

Consulte este artículo para obtener información sobre los certificados, las tecnologías y los conjuntos de cifrado TLS usados para el [cifrado en Office 365](encryption.md). En este artículo también se proporcionan detalles sobre los desusos planeados.
  
- Si busca información general, consulte [Cifrado en Office 365](encryption.md).
- Si busca información de configuración, consulte [Configuración del cifrado en Office 365 Enterprise](set-up-encryption.md).
- Para obtener información sobre los conjuntos de cifrado compatibles con versiones específicas de Windows, consulte [Conjuntos de cifrado en TLS/SSL (Schannel SSP).](/windows/desktop/SecAuthN/cipher-suites-in-schannel)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Propiedad y administración de certificados de Microsoft Office 365

No es necesario comprar ni mantener certificados para Office 365. En su lugar, Office 365 usa sus propios certificados.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Estándares de cifrado actuales y desusos planeados

Para proporcionar el mejor cifrado de su clase, Office 365 revisa periódicamente los estándares de cifrado admitidos. A veces, los estándares antiguos están en desuso a medida que están obsoletos y son menos seguros. En este artículo se describen los conjuntos de cifrado admitidos actualmente y otros estándares y detalles sobre los desusos planeados.

## <a name="fips-compliance-for-office-365"></a>Cumplimiento de FIPS para Office 365

Todos los conjuntos de cifrado admitidos por Office 365 usan algoritmos aceptables en FIPS 140-2. Office 365 hereda las validaciones FIPS de Windows (a través de Schannel). Para obtener información sobre Schannel, consulte [Conjuntos de cifrado en TLS/SSL (Schannel SSP).](/windows/desktop/SecAuthN/cipher-suites-in-schannel)
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versiones de TLS admitidas por Office 365

TLS y SSL que precedieron a TLS son protocolos criptográficos que protegen la comunicación a través de una red mediante certificados de seguridad para cifrar una conexión entre equipos. Office 365 admite TLS versión 1.2 (TLS 1.2).

La versión 1.3 de TLS (TLS 1.3) es compatible con algunos de los servicios.

> [!IMPORTANT]
> Tenga en cuenta que las versiones de TLS están en desuso y que las versiones en desuso *no deben usarse* cuando estén disponibles las versiones más recientes. Si los servicios heredados no requieren TLS 1.0 o 1.1, debe deshabilitarlos.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Compatibilidad con TLS 1.0 y 1.1 en desuso

Office 365 dejó de admitir TLS 1.0 y 1.1 el 31 de octubre de 2018. Hemos completado la deshabilitación de TLS 1.0 y 1.1 en entornos GCC High y DoD. Comenzamos a deshabilitar TLS 1.0 y 1.1 para entornos globales y GCC a partir del 15 de octubre de 2020 y continuaremos con la implementación en las próximas semanas y meses.

Para mantener una conexión segura a los servicios Office 365 y Microsoft 365, todas las combinaciones cliente-servidor y explorador-servidor usan TLS 1.2 y conjuntos de cifrado modernos. Es posible que tenga que actualizar ciertas combinaciones cliente-servidor y navegador-servidor. Para obtener información sobre cómo afecta este cambio, consulte [Preparación para el uso obligatorio de TLS 1.2 en Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Compatibilidad en desuso para 3DES

Desde el 31 de octubre de 2018, Office 365 ya no admite el uso de conjuntos de cifrado 3DES para la comunicación con Office 365. Más concretamente, Office 365 ya no admite el conjunto de cifrado de TLS_RSA_WITH_3DES_EDE_CBC_SHA. Desde el 28 de febrero de 2019, este conjunto de cifrado se ha deshabilitado en Office 365. Los clientes y servidores que se comunican con Office 365 deben admitir uno o varios de los cifrados admitidos. Para obtener una lista de los cifrados admitidos, consulte [Conjuntos de cifrado TLS compatibles con Office 365](#tls-cipher-suites-supported-by-office-365).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Desuso de la compatibilidad con certificados SHA-1 en Office 365

Desde junio de 2016, Office 365 ya no acepta un certificado SHA-1 para las conexiones salientes o entrantes. Use SHA-2 (algoritmo hash seguro 2) o un algoritmo hash más seguro en la cadena de certificados.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Conjuntos de cifrado TLS admitidos por Office 365

TLS usa *conjuntos de cifrado*, colecciones de algoritmos de cifrado, para establecer conexiones seguras. Office 365 admite los conjuntos de cifrado enumerados en la tabla siguiente. En la tabla se enumeran los conjuntos de cifrado en orden de intensidad, con el conjunto de cifrado más seguro en primer lugar.

Office 365 responde a una solicitud de conexión al intentar conectarse primero con el conjunto de cifrado más seguro. Si la conexión no funciona, Office 365 intenta el segundo conjunto de cifrado más seguro de la lista, etc. El servicio continúa hacia abajo en la lista hasta que se acepta la conexión. Del mismo modo, cuando Office 365 solicita una conexión, el servicio receptor elige si se usará TLS y qué conjunto de cifrado se usará.

| Nombre del conjunto de cifrado | Fuerza/algoritmo de intercambio de claves | Secreto hacia delante | Cifrado/intensidad | Algoritmo/fuerza de autenticación |
|:-----|:-----|:-----|:-----|:-----|
| TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> | ECDH/192  <br/> | Yes  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> | ECDH/128  <br/> | Yes  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384  <br/> | ECDH/192  <br/> | Sí  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256  <br/> | ECDH/128  <br/> | Sí  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA     <br/> | ECDH/192  <br/> | Sí  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA     <br/> | ECDH/128  <br/> | Sí  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_RSA_WITH_AES_256_GCM_SHA384        <br/> | RSA/112   <br/> | No   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_RSA_WITH_AES_128_GCM_SHA256        <br/> | RSA/112   <br/> | No   <br/> | AES/256  <br/> | RSA/112  <br/> |

Los siguientes conjuntos de cifrado admitían protocolos TLS 1.0 y 1.1 hasta su fecha de desuso. En los entornos de GCC High y DoD, la fecha de desuso era el 15 de enero de 2020. En el caso de los entornos mundial y GCC, esa fecha era el 15 de octubre de 2020.

| Protocolos | Nombre del conjunto de cifrado | Fuerza/algoritmo de intercambio de claves | Secreto hacia delante | Cifrado/intensidad | Algoritmo/fuerza de autenticación | 
|:-----|:-----|:-----|:-----|:-----|:-----|
| TLS 1.0, 1.1, 1.2  <br/> | TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> | ECDH/192  <br/> | Yes  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> | ECDH/128  <br/> | Yes  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_256_CBC_SHA        <br/> | RSA/112   <br/> | No   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_128_CBC_SHA        <br/> | RSA/112   <br/> | No   <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> | RSA/112   <br/> | No   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> | RSA/112   <br/> | No   <br/> | AES/256  <br/> | RSA/112  <br/> |

Algunos productos de Office 365 (incluido Microsoft Teams) usan [Azure Front Door](/azure/frontdoor/front-door-overview) para finalizar las conexiones TLS y enrutar el tráfico de red de forma eficaz. Al menos uno de los [conjuntos de cifrado admitidos por Azure Front Door a través de TLS 1.2](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-) debe estar habilitado para conectarse correctamente a estos productos. Para Windows 10 y versiones posteriores, se recomienda habilitar uno o ambos conjuntos de cifrado ECDHE para mejorar la seguridad. Windows 7, 8 y 8.1 no son compatibles con los conjuntos de cifrado ECDHE de Azure Front Door y los conjuntos de cifrado DHE se han proporcionado para la compatibilidad con esos sistemas operativos.

## <a name="related-articles"></a>Artículos relacionados

[Conjuntos de cifrado TLS en Windows 10 v1903](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Cifrado en Office 365](encryption.md)
  
[Configurar el cifrado en Office 365 Enterprise](set-up-encryption.md)
  
[Implementación Schannel de TLS 1.0 en la actualización de estado de seguridad de Windows: 24 de noviembre de 2015](https://support.microsoft.com/kb/3117336)
  
[Mejoras criptográficas TLS/SSL (Centro de TI de Windows)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[Preparar TLS 1.2 en Office 365 y CCO de Office 365](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)

[¿Cuáles son los conjuntos de cifrado actuales admitidos por Azure Front Door?](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-)
