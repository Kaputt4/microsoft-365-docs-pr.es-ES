---
title: Cambios en el certificado TLS de Office
description: Cómo prepararse para los próximos cambios en los certificados TLS de Office.
author: pshelton-skype
ms.author: pshelton
manager: toddbeckett
ms.topic: article
audience: Developer
ms.date: 3/7/2022
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.openlocfilehash: 65b0ffd5d605302dd62369471b65c1ac10aacd40
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66641776"
---
# <a name="office-tls-certificate-changes"></a>Cambios en el certificado TLS de Office

Microsoft 365 está actualizando los servicios que alimentan mensajería, reuniones, telefonía, voz y vídeo para usar certificados TLS de un conjunto diferente de entidades de certificación raíz (CA). Este cambio se está realizando porque la entidad de certificación raíz actual expirará en mayo de 2025.

Los productos afectados incluyen:
- Microsoft Teams
- Skype
- Skype Empresarial Online
- Microsoft Dynamics 365
- Groupme
- Kaizala
- Azure Communication Services

Los puntos de conexión afectados incluyen (pero no se limitan a):
- *.teams.microsoft.com
- *.skype.com
- *.skypeforbusiness.com
- *.groupme.com
- *.communication.azure.com
- *.operatorconnect.microsoft.com

Además, Los puntos de conexión de Teams y Skype Empresarial Online en las instancias de nube nacionales de Microsoft 365 del Gobierno de EE. UU. realizarán el mismo cambio, lo que afectará a puntos de conexión como:
- *.gcc.teams.microsoft.com
- *.dod.teams.microsoft.us
- *.gov.teams.microsoft.us
- *.online.dod.skypeforbusiness.us
- *.online.gov.skypeforbusiness.us
- *.um-dod.office365.us
- *.um.office365.us

Este cambio no afectará a los certificados, dominios o servicios utilizados en las instancias de nube nacionales de China o Alemania de Microsoft 365.

Toda la información de certificado de este artículo se proporcionó anteriormente en [las cadenas de cifrado de Microsoft 365](./encryption-office-365-certificate-chains.md) a más tardar en octubre de 2020.

## <a name="when-will-this-change-happen"></a>¿Cuándo se producirá este cambio?

Los servicios comenzaron la transición a las nuevas ENTIDADes de certificación raíz en enero de 2022 y continuarán hasta octubre de 2022.

## <a name="what-is-changing"></a>¿Qué está cambiando?

En la actualidad, la mayoría de los certificados TLS usados por los servicios de Microsoft 365 se encadenan hasta la siguiente CA raíz:

| Nombre común de la entidad de certificación | Huella digital (SHA1) |
|--|--|
| [Baltimore CyberTrust Root](https://cacerts.digicert.com/BaltimoreCyberTrustRoot.crt) | d4de20d05e66fc53fe1a50882c78db2852cae474 |

con una de las siguientes CA intermedias:

| Nombre común de la entidad de certificación | Huella digital (SHA1) |
|--|--|
| [Microsoft RSA TLS CA 01](https://www.microsoft.com/pki/mscorp/Microsoft%20RSA%20TLS%20CA%2001.crt) | 703d7a8f0ebf55aaa59f98eaf4a206004eb2516a |
| [Microsoft RSA TLS CA 02](https://www.microsoft.com/pki/mscorp/Microsoft%20RSA%20TLS%20CA%2002.crt) | b0c2d2d13cdd56cdaa6ab6e2c04440be4a429c75 |

Ahora, los nuevos certificados TLS usados por los servicios de Microsoft 365 encadenan hasta uno de los siguientes CA raíz:

| Nombre común de la entidad de certificación | Huella digital (SHA1) |
|--|--|
| [DigiCert Global Root G2](https://cacerts.digicert.com/DigiCertGlobalRootG2.crt) | df3c24f9bfd666761b268073fe06d1cc8d4f82a4 |
| [Entidad de certificación raíz rsa de Microsoft 2017](https://www.microsoft.com/pkiops/certs/Microsoft%20RSA%20Root%20Certificate%20Authority%202017.crt) | 73a5e64a3bff8316ff0edccc618a906e4eae4d74 | 
| [Entidad de certificación raíz de Microsoft ECC 2017](https://www.microsoft.com/pkiops/certs/Microsoft%20ECC%20Root%20Certificate%20Authority%202017.crt) | 999a64c37ff47d9fab95f14769891460eec4c3c5 |

con una de las siguientes CA intermedias:

| Nombre común de la entidad de certificación | Huella digital (SHA1) |
|--|--|
| [Microsoft Azure TLS Issuing CA 01](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2001%20-%20xsign.crt) | 2f2877c5d778c31e0f29c7e371df5471bd673173 |
| [Microsoft Azure TLS Issuing CA 02](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2002%20-%20xsign.crt) | e7eea674ca718e3befd90858e09f8372ad0ae2aa |
| [Microsoft Azure TLS Issuing CA 05](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2005%20-%20xsign.crt) | 6c3af02e7f269aa73afd0eff2a88a4a1f04ed1e5 |
| [Microsoft Azure TLS Issuing CA 06](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2006%20-%20xsign.crt) | 30e01761ab97e59a06b41ef20af6f2de7ef4f7b0 |

Por ejemplo, se trata de un certificado válido con una de las nuevas cadenas de certificados:

![Cadena de certificados TLS de Teams](../media/teams-tls-certificate-chain.png)

## <a name="will-this-change-affect-me"></a>¿Me afectará este cambio?

La ca raíz "DigiCert Global Root G2" es ampliamente confiable por sistemas operativos como Windows, macOS, Android e iOS y por exploradores como Microsoft Edge, Chrome, Safari y Firefox. Esperamos que **la mayoría de los clientes de Microsoft 365 no se vean afectados**. 

Sin embargo, **la aplicación puede verse afectada si especifica explícitamente una lista de CA aceptables**. Esta práctica se conoce como "anclaje de certificados". Los clientes que no tengan las nuevas CA raíz en su lista de CA aceptables recibirán errores de validación de certificados, que pueden afectar a la disponibilidad o función de la aplicación.

Estas son algunas maneras de detectar si la aplicación puede verse afectada:

- Busque en el código fuente la huella digital, el nombre común u otras propiedades de cualquiera de las ENTIDADes de certificación intermedias que se encuentran [aquí](https://www.microsoft.com/pki/mscorp/cps/default.htm). Si hay una coincidencia, la aplicación se verá afectada. Para resolver este problema, actualice el código fuente para agregar las propiedades de las nuevas CA. Como procedimiento recomendado, asegúrese de que las CA se pueden agregar o editar con breve antelación. Las regulaciones del sector requieren que los certificados de CA se reemplacen en un plazo de siete días en algunas circunstancias, por lo que las aplicaciones que implementan el anclaje de certificados deben reaccionar a estos cambios rápidamente.

- .NET expone las `System.Net.ServicePointManager.ServerCertificateValidationCallback` funciones de devolución de llamada y `System.Net.HttpWebRequest.ServerCertificateValidationCallback` , que permiten a los desarrolladores usar lógica personalizada para determinar si los certificados son válidos en lugar de depender del almacén de certificados estándar de Windows. Un desarrollador puede agregar lógica que compruebe un nombre común o huella digital específico o solo permite una entidad de certificación raíz específica, como "Baltimore CyberTrust Root". Si la aplicación usa estas funciones de devolución de llamada, debe asegurarse de que acepta las ENTIDADes de certificación raíz e intermedias antiguas y nuevas.

- Las aplicaciones nativas pueden usar `WINHTTP_CALLBACK_STATUS_SENDING_REQUEST`, lo que permite a las aplicaciones nativas implementar la lógica de validación de certificados personalizada. El uso de esta notificación es poco frecuente y requiere una cantidad significativa de código personalizado para implementar. De forma similar a lo anterior, asegúrese de que la aplicación acepta las CA raíz e intermedia antiguas y nuevas. 

- Si usa una aplicación que se integra con Microsoft Teams, Skype, Skype Empresarial Online o las API de Microsoft Dynamics y no está seguro de si usa el anclaje de certificados, consulte con el proveedor de la aplicación.

- Los diferentes sistemas operativos y entornos de ejecución de lenguaje que se comunican con los servicios de Azure pueden requerir otros pasos para compilar y validar correctamente las nuevas cadenas de certificados:
   - **Linux**: muchas distribuciones requieren que agregue CA a `/etc/ssl/certs`. Para obtener instrucciones específicas, consulte la documentación de la distribución.
   - **Java**: asegúrese de que el almacén de claves de Java contiene las CA enumeradas anteriormente.
   - **Windows que se ejecuta en entornos desconectados**: los sistemas que se ejecutan en entornos desconectados tendrán que agregar las nuevas ENTIDADes de certificación raíz a su `Trusted Root Certification Authorities` almacén y las nuevas CA intermedias agregadas a su `Intermediate Certification Authorities` almacén.
   - **Android**: compruebe la documentación del dispositivo y la versión de Android.
   - **IoT o dispositivos incrustados**: los dispositivos incrustados, como los equipos de tv, suelen enviarse con un conjunto limitado de certificados de entidad de certificación raíz y no tienen ninguna manera sencilla de actualizar el almacén de certificados. Si escribe código para o administra implementaciones de dispositivos integrados o de IoT personalizados, asegúrese de que los dispositivos confían en las nuevas CA raíz. Es posible que tenga que ponerse en contacto con el fabricante del dispositivo.

- Si tiene un entorno en el que las reglas de firewall solo permiten llamadas salientes a puntos de conexión específicos, permita las siguientes direcciones URL de lista de revocación de certificados (CRL) o protocolo de estado de certificado en línea (OCSP):
   - `http://crl3.digicert.com`
   - `http://crl4.digicert.com`
   - `http://ocsp.digicert.com`
   - `http://crl.microsoft.com`
   - `http://oneocsp.microsoft.com`
   - `http://ocsp.msocsp.com`
   - `http://www.microsoft.com/pkiops`

- Si se ve afectado por este cambio, es posible que vea mensajes de error que dependen del tipo de entorno en el que se ejecuta y del escenario en el que se ve afectado. Compruebe los registros de eventos de la aplicación Windows, los registros de eventos CAPI2 y los registros de aplicaciones personalizados para ver los mensajes que tienen el siguiente aspecto:
   ```output
   An operation failed because the following certificate has validation errors:
   
   Subject Name: CN=teams.microsoft.com
   Issuer Name: CN=Microsoft Azure TLS Issuing CA 01, O=Microsoft Corporation, C=US
   
   Errors:
   
   The root of the certificate chain is not a trusted root authority.
   ```

## <a name="when-can-i-retire-the-old-ca-information"></a>¿Cuándo puedo retirar la información de ca antigua?

No se revocarán los certificados raíz, intermedio y hoja actuales. Los nombres comunes de ca o las huellas digitales existentes serán necesarios hasta al menos octubre de 2023 en función de la duración de los certificados existentes.

## <a name="known-issues"></a>Problemas conocidos

En circunstancias muy poco frecuentes, los usuarios empresariales pueden ver errores de validación de certificados en los que la entidad de certificación raíz "DigiCert Global Root G2" aparece como revocada. Esto se debe a un error conocido de Windows en las dos condiciones siguientes:

- La entidad de certificación raíz está en el [almacén de certificados CurrentUser\Root](/windows/win32/seccrypto/system-store-locations#cert_system_store_current_user) y faltan las `NotBeforeFileTime` propiedades y `NotBeforeEKU` .
- La entidad de certificación raíz también está en el almacén de certificados [LocalMachine\AuthRoot](/windows/win32/seccrypto/system-store-locations#cert_system_store_local_machine) , pero tiene las `NotBeforeFileTime` propiedades y `NotBeforeEKU` .

Todos los certificados hoja emitidos desde esta entidad de certificación raíz después de que `NotBeforeFileTime` aparezcan revocados. 

Los administradores pueden identificar y solucionar el problema inspeccionando el registro CAPI2 para ver este error:

```text
Log Name:      Microsoft-Windows-CAPI2/Operational
Source:        Microsoft-Windows-CAPI2
Date:          6/23/2022 8:36:39 AM
Event ID:      11
Task Category: Build Chain
Level:         Error
[...]
        <ChainElement>
          <Certificate fileRef="DF3C24F9BFD666761B268073FE06D1CC8D4F82A4.cer" subjectName="DigiCert Global Root G2" />
          [...]
          <TrustStatus>
            <ErrorStatus value="4000024" CERT_TRUST_IS_REVOKED="true" CERT_TRUST_IS_UNTRUSTED_ROOT="true" CERT_TRUST_IS_EXPLICIT_DISTRUST="true" />
            <InfoStatus value="10C" CERT_TRUST_HAS_NAME_MATCH_ISSUER="true" CERT_TRUST_IS_SELF_SIGNED="true" CERT_TRUST_HAS_PREFERRED_ISSUER="true" />
          </TrustStatus>
          [...]
          <RevocationInfo freshnessTime="PT0S">
            <RevocationResult value="80092010">The certificate is revoked.</RevocationResult>
          </RevocationInfo>
        </ChainElement>
      </CertificateChain>
      <EventAuxInfo ProcessName="Teams.exe" />
      <Result value="80092010">The certificate is revoked.</Result>
```
Observe la presencia del `CERT_TRUST_IS_EXPLICIT_DISTRUST="true"` elemento . 

Puede confirmar que hay dos copias de la entidad de certificación raíz con propiedades diferentes `NotBeforeFileTime` ejecutando los siguientes `certutil` comandos y comparando la salida:

```
certutil -store -v authroot DF3C24F9BFD666761B268073FE06D1CC8D4F82A4
certutil -user -store -v root DF3C24F9BFD666761B268073FE06D1CC8D4F82A4
```

Un usuario puede resolver el problema mediante la eliminación de la copia de la entidad de certificación raíz en el almacén de `CurrentUser\Root` certificados:
```
certutil -user -delstore root DF3C24F9BFD666761B268073FE06D1CC8D4F82A4
```