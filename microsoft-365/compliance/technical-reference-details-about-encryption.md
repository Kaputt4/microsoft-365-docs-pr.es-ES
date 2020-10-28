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
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Obtenga información sobre los distintos certificados, tecnologías y conjuntos de cifrado TLS que se usan para el cifrado en Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb45f325095143e6f66d9cd2bfa6f3875fb03043
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769180"
---
# <a name="technical-reference-details-about-encryption"></a>Detalles de referencia técnica sobre el cifrado

Consulte este artículo para obtener información sobre certificados, tecnologías y conjuntos de cifrado TLS usados para el [cifrado en Office 365](encryption.md). En este artículo también se proporcionan detalles sobre las despreciaciones planeadas.

- Si está buscando información general, vea [cifrado en Office 365](encryption.md).
- Si está buscando información de configuración, consulte [configurar el cifrado en Office 365 Enterprise](set-up-encryption.md).
- Para obtener información acerca de los conjuntos de cifrado compatibles con versiones específicas de Windows, consulte [conjuntos de cifrado en TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Propiedad y administración de certificados de Microsoft Office 365

No es necesario comprar ni mantener certificados para Office 365 porque Microsoft usa sus propios certificados.

## <a name="current-encryption-standards-and-planned-deprecations"></a>Estándares de cifrado actuales y despreciaciones planeadas

Para seguir proporcionando el mejor cifrado de su clase para Office 365, Microsoft revisa regularmente los estándares de cifrado compatibles. A veces, es necesario dejar de usar los estándares anteriores, ya que se han quedado obsoletos y, por lo tanto, son menos seguros. En este tema se describen los conjuntos de cifrado admitidos actualmente y otros estándares, así como detalles sobre las despreciaciones planeadas.

## <a name="fips-compliance-for-office-365"></a>Cumplimiento de FIPS para Office 365

Todos los conjuntos de programas de cifrado compatibles con Office 365 usan algoritmos aceptables en FIPS 140-2. Office 365 hereda las validaciones FIPS de Windows (a través de Schannel). Para obtener información sobre Schannel, consulte [conjuntos de cifrado en TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).

## <a name="versions-of-tls-supported-by-office-365"></a>Versiones de TLS admitidas por Office 365

TLS (Seguridad de la capa de transporte) y SSL (antecesor de TLS) son protocolos criptográficos que protegen la comunicación por red con certificados de seguridad que cifran una conexión entre equipos. Office 365 admite TLS versión 1,2 (TLS 1,2).

La versión 1,3 de TLS (TLS 1,3) no es compatible actualmente.

## <a name="support-for-tls-10-and-11-deprecation-and-what-this-means-for-you"></a>Compatibilidad con el desuso de TLS 1,0 y 1,1 y lo que esto significa para usted

Desde el 31 de octubre de 2018, Office 365 ya no admite TLS 1,0 y 1,1. Esto significa que Microsoft no corregirá los nuevos problemas que se encuentren en los clientes, dispositivos o servicios que se conecten a Office 365 mediante TLS 1.0 y 1.1. El desuso oficial para los entornos altos y DoD de GCC empezó el 15 de enero de 2020. El desuso de TLS 1,0 y 1,1 para los entornos de todo el mundo y GCC comienza el 15 de octubre de 2020.

Debe asegurarse de que todas las combinaciones cliente-servidor y explorador-servidor usen los conjuntos de cifrado TLS 1,2 y modernos para mantener una conexión segura con los servicios de Office 365 y Microsoft 365. Es posible que tenga que actualizar ciertas combinaciones cliente-servidor y navegador-servidor. Para obtener más información acerca de cómo esto afecta, vea [preparación del uso obligatorio de TLS 1,2 en Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

## <a name="deprecating-support-for-3des"></a>Desuso de la compatibilidad con 3DES

Desde el 31 de octubre de 2018, Office 365 ya no admite el uso de conjuntos de cifrado 3DES para comunicarse con Office 365. Más concretamente, Office 365 ya no es compatible con el conjunto de cifrado de TLS_RSA_WITH_3DES_EDE_CBC_SHA. Desde el 28 de febrero de 2019, este conjunto de cifrado se ha deshabilitado en Office 365. Clientes y servidores que se comunican con Office 365 una vez que esta fecha debe ser compatible con al menos uno de los cifrados más seguros que se enumeran en este tema (vea [conjuntos de cifrado de TLS compatibles con Office 365](#tls-cipher-suites-supported-by-office-365)).

## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Desuso de la compatibilidad con certificados SHA-1 en Office 365

A partir del 2016 de junio de Office 365 ya no acepta un certificado SHA-1 para las conexiones salientes o entrantes. Si actualmente usa un certificado con SHA-1 en la cadena de certificados, tendrá que actualizar la cadena para usar SHA-2 (algoritmo de hash seguro 2) o un algoritmo hash más seguro.

## <a name="tls-cipher-suites-supported-by-office-365"></a>Conjuntos de cifrado de TLS compatibles con Office 365

Un conjunto de cifrado es una colección de algoritmos de cifrado que TLS emplea para establecer conexiones seguras. Los conjuntos de cifrado compatibles con Office 365 se enumeran en la siguiente tabla por orden de seguridad, con el conjunto de cifrado más seguro en primer lugar. Cuando Office 365 recibe una solicitud de conexión, Office 365 primero intenta conectarse mediante el conjunto de cifrado superior. A continuación, si no lo consigue, Office 365 prueba el segundo conjunto de cifrado de la lista y así sucesivamente en la lista. Cuando Office 365 envía una solicitud de conexión a otro servidor o a un cliente, el servidor o el cliente receptor elige el conjunto de cifrado o si se va a usar TLS.

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

Estos son los siguientes conjuntos de cifrado que seguirán siendo compatibles con los protocolos TLS 1,0 y 1,1 hasta la fecha de desuso. Para los entornos de GCC altos y DoD, la fecha de degradación fue 15 de enero de 2020, y para entornos de todo el mundo y GCC, esa fecha es el 15 de octubre de 2020.

| Protocolos | Nombre del conjunto de cifrado | Algoritmo/fuerza de intercambio de claves | Compatibilidad con confidencialidad directa perfecta | Algoritmo de autenticación/seguridad | Cifrado o seguridad |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Sí  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Sí  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |No  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |No  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |No   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |No   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-topics"></a>Temas relacionados
[Conjuntos de cifrado TLS en Windows 10 V1903](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Cifrado en Office 365](encryption.md)

[Configurar el cifrado en Office 365 Enterprise](set-up-encryption.md)

[Riesgos y protección de cifrado](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-risks-and-protections?view=o365-worldwide)

[Implementación de Schannel TLS 1,0 en la actualización de estado de seguridad de Windows: 24 de noviembre de 2015](https://support.microsoft.com/kb/3117336)

[Mejoras de cifrado de TLS/SSL (centro de TI de Windows)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)

[Preparación para TLS 1.2 en Office 365 y Office 365 GCC](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
