---
title: Cambios en el certificado TLS de Office
description: Cómo prepararse para los próximos cambios en Office certificados TLS.
author: pshelton-skype
ms.author: pshelton
manager: toddbeckett
ms.topic: article
audience: Developer
ms.date: 3/7/2022
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.openlocfilehash: 075fb8f4c27401a4622f4ce639c897f2e98bb3e9
ms.sourcegitcommit: 2697938d2d4fec523b501c5e7b0b8ec8f34e59b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2022
ms.locfileid: "63450381"
---
# <a name="office-tls-certificate-changes"></a>Cambios en el certificado TLS de Office

Microsoft 365 actualiza servicios que powering messaging, meetings, telephony, voice, and video para usar certificados TLS de un conjunto diferente de autoridades de certificación raíz (CA). Este cambio se realiza porque la ca raíz actual expirará en mayo de 2025.

Entre los productos afectados se incluyen:
- Microsoft Teams
- Skype
- Skype Empresarial Online
- Microsoft Dynamics 365
- GroupMe
- Kaizala
- Servicios de comunicación de Azure

Los puntos de conexión afectados incluyen (pero no están limitados a):
- *.teams.microsoft.com
- *.skype.com
- *.skypeforbusiness.com
- *.groupme.com
- *.communication.azure.com
- *.operatorconnect.microsoft.com

Además, Teams y Skype Empresarial en línea en las instancias de nube nacionales del Gobierno de ESTADOS UNIDOS de Microsoft 365 realizarán el mismo cambio, lo que afectará a puntos de conexión como:
- *.gcc.teams.microsoft.com
- *.dod.teams.microsoft.us
- *.gov.teams.microsoft.us
- *.online.dod.skypeforbusiness.us
- *.online.gov.skypeforbusiness.us
- *.um-dod.office365.us
- *.um.office365.us

Este cambio no afectará a los certificados, dominios o servicios usados en las instancias de nube nacionales de China o Alemania de Microsoft 365.

Toda la información de certificado de este artículo se proporcionó anteriormente Microsoft 365 [cadenas de](./encryption-office-365-certificate-chains.md) cifrado a más tardar en octubre de 2020.

## <a name="when-will-this-change-happen"></a>¿Cuándo se realizará este cambio?

Los servicios empezaron la transición a las nuevas CA raíz en enero de 2022 y continuarán hasta octubre de 2022.

## <a name="what-is-changing"></a>¿Qué está cambiando?

En la actualidad, la mayoría de los certificados TLS usados por Microsoft 365 servicios se encadena hasta la siguiente CA raíz:

| Nombre común de la CA | Huella digital (SHA1) |
|--|--|
| [Baltimore CyberTrust Root](https://cacerts.digicert.com/BaltimoreCyberTrustRoot.crt) | d4de20d05e66fc53fe1a50882c78db2852cae474 |

con una de las siguientes CA intermedias:

| Nombre común de la CA | Huella digital (SHA1) |
|--|--|
| [Microsoft RSA TLS CA 01](https://www.microsoft.com/pki/mscorp/Microsoft%20RSA%20TLS%20CA%2001.crt) | 703d7a8f0ebf55aaa59f98eaf4a206004eb2516a |
| [Microsoft RSA TLS CA 02](https://www.microsoft.com/pki/mscorp/Microsoft%20RSA%20TLS%20CA%2002.crt) | b0c2d2d13cdd56cdaa6ab6e2c04440be4a429c75 |

Los nuevos certificados TLS usados por Microsoft 365 servicios ahora encadenarán hasta una de las siguientes CA raíz:

| Nombre común de la CA | Huella digital (SHA1) |
|--|--|
| [DigiCert Global Root G2](https://cacerts.digicert.com/DigiCertGlobalRootG2.crt) | df3c24f9bfd666761b268073fe06d1cc8d4f82a4 |
| [Microsoft RSA Root Certificate Authority 2017](https://www.microsoft.com/pkiops/certs/Microsoft%20RSA%20Root%20Certificate%20Authority%202017.crt) | 73a5e64a3bff8316ff0edccc618a906e4eae4d74 | 
| [Entidad de certificación raíz de Microsoft ECC 2017](https://www.microsoft.com/pkiops/certs/Microsoft%20ECC%20Root%20Certificate%20Authority%202017.crt) | 999a64c37ff47d9fab95f14769891460eec4c3c5 |

con una de las siguientes CA intermedias:

| Nombre común de la CA | Huella digital (SHA1) |
|--|--|
| [Microsoft Azure TLS Emisor CA 01](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2001%20-%20xsign.crt) | 2f2877c5d778c31e0f29c7e371df5471bd673173 |
| [Microsoft Azure TLS Emisor CA 02](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2002%20-%20xsign.crt) | e7eea674ca718e3befd90858e09f8372ad0ae2aa |
| [Microsoft Azure TLS Emisor CA 05](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2005%20-%20xsign.crt) | 6c3af02e7f269aa73afd0eff2a88a4a1f04ed1e5 |
| [Microsoft Azure TLS Emisor CA 06](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2006%20-%20xsign.crt) | 30e01761ab97e59a06b41ef20af6f2de7ef4f7b0 |

Por ejemplo, se trata de un certificado válido con una de las nuevas cadenas de certificados:

![Teams de certificados TLS](../media/teams-tls-certificate-chain.png)

## <a name="will-this-change-affect-me"></a>¿Me afectará este cambio?

La CA raíz "DigiCert Global Root G2" es ampliamente de confianza para los sistemas operativos, incluidos Windows, macOS, Android e iOS y por exploradores como Microsoft Edge, Chrome, Safari y Firefox. Esperamos que la **mayoría Microsoft 365 clientes no se verán afectados**. 

Sin embargo, **la aplicación puede resultar afectada si especifica explícitamente una lista de CA aceptables**. Esta práctica se conoce como "anclado de certificado". Los clientes que no tengan las nuevas CA raíz en su lista de CA aceptables recibirán errores de validación de certificados, lo que puede afectar a la disponibilidad o función de la aplicación.

Estas son algunas maneras de detectar si la aplicación puede estar afectada:

- Busque en el código fuente la huella digital, el nombre común u otras propiedades de cualquiera de las CA intermedias que se encuentran [aquí](https://www.microsoft.com/pki/mscorp/cps/default.htm). Si hay una coincidencia, la aplicación se verá afectada. Para resolver este problema, actualice el código fuente para agregar las propiedades de las nuevas CA. Como práctica recomendada, asegúrese de que las CA se pueden agregar o editar con un breve aviso. Las normativas del sector requieren que los certificados de ca se reemplacen en un plazo de siete días en algunas circunstancias, por lo que las aplicaciones que implementan la fijación de certificados deben reaccionar rápidamente a estos cambios.

- .NET expone las `System.Net.ServicePointManager.ServerCertificateValidationCallback` `System.Net.HttpWebRequest.ServerCertificateValidationCallback` funciones y las funciones de devolución de llamada, que permiten a los programadores usar lógica personalizada para determinar si los certificados son válidos en lugar de depender del almacén de certificados Windows estándar. Un desarrollador puede agregar lógica que busca un nombre común específico o huella digital o solo permite una CA raíz específica como "Raíz de CyberTrust de Baltimore". Si la aplicación usa estas funciones de devolución de llamada, debe asegurarse de que acepta tanto las CA raíz y intermedias antiguas como las nuevas.

- Las aplicaciones nativas pueden usar `WINHTTP_CALLBACK_STATUS_SENDING_REQUEST`, lo que permite a las aplicaciones nativas implementar lógica de validación de certificados personalizada. El uso de esta notificación es poco común y requiere una cantidad significativa de código personalizado para implementar. De forma similar a lo anterior, asegúrese de que la aplicación acepta tanto las ca raíz antiguas como las nuevas y las intermedias. 

- Si usa una aplicación que se integra con las API de Microsoft Teams, Skype, Skype Empresarial Online o Microsoft Dynamics y no está seguro de si usa la fijación de certificados, consulte con el proveedor de aplicaciones.

- Los diferentes sistemas operativos y tiempos de ejecución de idioma que se comunican con los servicios de Azure pueden requerir otros pasos para crear y validar correctamente las nuevas cadenas de certificados:
   - **Linux**: muchas distribuciones requieren que agregue CA a `/etc/ssl/certs`. Para obtener instrucciones específicas, consulte la documentación de la distribución.
   - **Java**: asegúrese de que el almacén Java de claves contiene las CA enumeradas anteriormente.
   - **Windows en entornos desconectados**: los sistemas que se ejecutan en entornos desconectados tendrán que agregar las nuevas CA raíz a su almacén y las nuevas CA intermedias `Trusted Root Certification Authorities` `Intermediate Certification Authorities` a su almacén.
   - **Android**: comprueba la documentación del dispositivo y la versión de Android.
   - **IoT o dispositivos** incrustados: los dispositivos incrustados, como los cuadros superiores de los televisores, suelen enviarse con un conjunto limitado de certificados de entidad raíz y no tienen una forma fácil de actualizar el almacén de certificados. Si escribe código para o administra implementaciones de dispositivos personalizados incrustados o ioT, asegúrese de que los dispositivos confían en las nuevas CA raíz. Es posible que deba ponerse en contacto con el fabricante del dispositivo.

- Si tiene un entorno donde las reglas de firewall permiten llamadas salientes solo a puntos de conexión específicos, permita las siguientes direcciones URL de lista de revocación de certificados (CRL) o protocolo de estado de certificado en línea (OCSP):
   - `http://crl3.digicert.com`
   - `http://crl4.digicert.com`
   - `http://ocsp.digicert.com`
   - `http://crl.microsoft.com`
   - `http://oneocsp.microsoft.com`
   - `http://ocsp.msocsp.com`
   - `http://www.microsoft.com/pkiops`

- Si se ve afectado por este cambio, es posible que vea mensajes de error que dependen del tipo de entorno en el que se está ejecutando y del escenario en el que se ve afectado. Compruebe Windows de eventos de aplicación, registros de eventos CAPI2 y registros de aplicaciones personalizados para obtener mensajes que parezcan:
   ```output
   An operation failed because the following certificate has validation errors:
   
   Subject Name: CN=teams.microsoft.com
   Issuer Name: CN=Microsoft Azure TLS Issuing CA 01, O=Microsoft Corporation, C=US
   
   Errors:
   
   The root of the certificate chain is not a trusted root authority.
   ```

## <a name="when-can-i-retire-the-old-ca-information"></a>¿Cuándo puedo retirar la información de ca antigua?

No se revocarán la CA raíz, la CA intermedia y los certificados hoja actuales. Los nombres comunes de ca existentes o las huellas digitales se requieren al menos hasta octubre de 2023 en función de la duración de los certificados existentes.
