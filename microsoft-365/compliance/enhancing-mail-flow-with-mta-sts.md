---
title: 'Mejora del flujo de correo con MTA-STS '
f1.keywords:
- NOCSH
ms.author: v-bshilpa
author: Benny-54
manager: serdars
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: high
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: Obtenga información sobre cómo mejorar el flujo de correo con MTA-STS.
ms.openlocfilehash: 4bcbe8cd64d4a2e3610b68480a39f697326ea65b
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65131481"
---
# <a name="enhancing-mail-flow-with-mta-sts"></a>Mejora del flujo de correo con MTA-STS

Se agregó compatibilidad con el estándar [SMTP MTA Strict Transport Security](https://datatracker.ietf.org/doc/html/rfc8461) (MTA-STS) a Exchange Online. El estándar se desarrolló para garantizar que siempre se use TLS para las conexiones entre los servidores de correo electrónico. También proporciona una manera de enviar servidores para validar que el servidor receptor tenga un certificado de confianza. Si no se ofrece TLS o el certificado no es válido, el remitente se negará a enviar los mensajes. Estas nuevas comprobaciones mejoran la seguridad general de SMTP y protegen frente a los ataques de tipo "Man in the middle”.

MTA-STS se puede dividir en dos escenarios: protección entrante y saliente. La entrante cubre la protección de dominios hospedados en Exchange Online con MTA-STS y la saliente cubre las validaciones de MTA-STS realizadas por Exchange Online al enviar correos electrónicos a dominios protegidos por MTA-STS.

## <a name="outbound-protection"></a>Protección saliente

Todos los mensajes enviados desde Exchange Online a los destinatarios protegidos con MTA-STS se validan con estas comprobaciones de seguridad adicionales establecidas por el estándar MTA-STS. Los administradores no tienen que hacer nada para aplicarlas. Nuestra implementación saliente respeta los deseos de los propietarios del dominio del destinatario a través de su directiva MTA-STS. MTA-STS forma parte de la infraestructura de seguridad de Exchange Online y, por tanto, siempre está activado (así como otras características principales de SMTP).

## <a name="inbound-protection"></a>Protección de entrada

Los propietarios de dominios pueden tomar medidas para proteger los correos electrónicos enviados a sus dominios con MTA-STS si su registro MX apunta a Exchange Online. Si el registro MX apunta a un servicio de terceros intermediario, deberá comprobar que se cumplan los requisitos de MTA-STS y seguir sus instrucciones.

Una vez configurado MTA-STS para su dominio, todos los mensajes enviados desde remitentes que admitan MTA-STS realizarán las validaciones establecidas por el estándar para garantizar una conexión segura. Si recibe un correo electrónico de un remitente que no es compatible con MTA-STS, el correo electrónico se enviará de todas maneras, pero sin la protección adicional. Del mismo modo, no habrá ninguna interrupción en los mensajes si usted aún no está usando MTA-STS pero el remitente sí lo admite. El único escenario en el que los mensajes no se envían es cuando ambos lados usan la validación MTA-STS y MTA-STS produce un error.

## <a name="how-to-adopt-mta-sts"></a>Adopción de MTA-STS

MTA-STS permite a un dominio declarar la compatibilidad con TLS y comunicar el registro MX y el certificado de destino esperados. También indica lo que debe hacer el servidor de envío si hay algún problema. Esto se realiza mediante la combinación de un registro TXT de DNS y un archivo de directiva que se publica como una página web HTTPS. La directiva protegida con HTTPS introduce otra protección de seguridad que los atacantes deben superar.

El registro TXT MTA-STS de un dominio indica la compatibilidad con MTA-STS para un remitente, tras lo cual el remitente recupera la directiva MTA-STS basada en HTTPS del dominio. El siguiente registro TXT es un ejemplo que declara la compatibilidad con MTA-STS:

`_mta-sts.contoso.com. 3600 IN  TXT v=STSv1; id=20220101000000Z;`

La directiva MTA-STS de un dominio debe encontrarse en una dirección URL predefinida hospedada por la infraestructura web del dominio. La sintaxis de la dirección URL es `https://mta-sts.<domain name>/.well-known/mta-sts.txt`. Por ejemplo, la directiva de Microsoft.com se encuentra en: https://mta-sts.microsoft.com/.well-known/mta-sts.txt.

```
version: STSv1
mode: enforce
mx: *.mail.protection.outlook.com
max_age: 604800
```

Cualquier cliente cuyos registros MX apunten directamente a Exchange Online pueden especificar su propia directiva con los mismos valores que se muestran anteriormente en la directiva de microsoft.com. La información única necesaria de la directiva es el registro MX que apunta a Exchange Online (`*`.mail.protection.outlook.com) y todos los clientes de Exchange Online comparten el mismo certificado. Es posible publicar la directiva en modo de *prueba* para asegurarse de que sea válida antes de cambiarla al modo de *aplicación*. Hay herramientas de validación de terceros que pueden comprobar la configuración.

Estas directivas no son algo que Exchange Online pueda hospedar en nombre de los clientes y los clientes deben usar el servicio de hospedaje web que usen normalmente. La directiva debe protegerse mediante HTTPS con un certificado para el subdominio `mta-sts.<domain name>`. Hay alternativas al hospedaje de directivas, como [esta solución](https://github.com/jpawlowski/mta-sts.template), que usan GitHub Pages para hospedarlas.

Una vez que se crea el registro de dominio TXT de DNS y el archivo de directiva está disponible en la dirección URL HTTPS necesaria, el dominio estará protegido por MTA-STS. Los detalles acerca de MTA-STS están disponibles en  [RFC 8461](https://datatracker.ietf.org/doc/html/rfc8461).
