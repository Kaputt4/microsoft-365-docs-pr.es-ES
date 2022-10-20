---
title: Protección contra ataques de suplantación de identidad (phishing)
ms.reviewer: ''
description: Obtenga información sobre cómo funciona la suplantación de identidad (phishing), entrega de malware a los dispositivos y lo que puede hacer para protegerse
keywords: seguridad, malware, phishing, información, estafa, ingeniería social, cebo, señuelo, protección, tendencias, ataque dirigido
ms.service: microsoft-365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
search.appverid: met150
ms.openlocfilehash: 2c93e2defdbffd9d676625c988d83e2bc1d6c559
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68633315"
---
# <a name="how-to-protect-against-phishing-attacks"></a>Protección contra ataques de suplantación de identidad (phishing)

Los ataques de suplantación de identidad (phishing) son aquellos que intentan robar información confidencial a través de correos electrónicos, sitios web, mensajes de texto u otras formas de comunicación electrónica. Intentan parecerse a la comunicación oficial de empresas o individuos legítimos.

Los cibercriminales suelen intentar robar nombres de usuario, contraseñas, detalles de tarjetas de crédito, información de la cuenta bancaria u otras credenciales. Usan información robada con fines malintencionados, como piratería, robo de identidad o robo de dinero directamente de cuentas bancarias y tarjetas de crédito. La información también se puede vender en los mercados subterráneos cibercriminales.

Los ataques de ingeniería social están diseñados para aprovechar la posible caída de un usuario en la toma de decisiones. Tenga en cuenta y nunca proporcione información confidencial o personal a través de correo electrónico o sitios web desconocidos, o por teléfono. Recuerde que los correos electrónicos de suplantación de identidad están diseñados para parecer legítimos.

## <a name="learn-the-signs-of-a-phishing-scam"></a>Obtenga información sobre los signos de una estafa de suplantación de identidad (phishing)

La mejor protección es la conciencia y la educación. No abra datos adjuntos o vínculos en correos electrónicos no solicitados, incluso si los correos electrónicos proceden de un origen reconocido. Si el correo electrónico es inesperado, tenga cuidado con la apertura de los datos adjuntos y compruebe la dirección URL.

Las empresas deben educar y entrenar a sus empleados para que sean cautelosos con cualquier comunicación que solicite información personal o financiera. También deben indicar a los empleados que informen de la amenaza al equipo de operaciones de seguridad de la empresa inmediatamente.

Estas son varias señales reveladoras de una estafa de phishing:

* Los vínculos o direcciones URL proporcionados en los correos electrónicos **no apuntan a la ubicación correcta** o apuntan a un sitio de terceros no afiliado al remitente del correo electrónico. Por ejemplo, en la imagen debajo de la dirección URL proporcionada no coincide con la dirección URL a la que se le llevará.

    ![ejemplo de mantener el puntero sobre una dirección URL.](../../media/security-intelligence-images/url-hover.png)

* Hay una **solicitud de información personal** , como números de seguro social o información bancaria o financiera. Por lo general, las comunicaciones oficiales no le solicitarán información personal en forma de correo electrónico.

* **Los elementos de la dirección de correo electrónico se cambiarán** para que sea lo suficientemente similar a una dirección de correo electrónico legítima, pero haya agregado números o letras modificadas.

* El mensaje es **inesperado y no solicitado**. Si de repente recibe un correo electrónico de una entidad o de una persona con la que raramente trata, considere este sospechoso de correo electrónico.

* El mensaje o los datos adjuntos le piden **que habilite macros, ajuste la configuración de seguridad o instale aplicaciones**. Los correos electrónicos normales no le pedirán que haga esto.

* El mensaje contiene **errores**. Es menos probable que los mensajes corporativos legítimos tengan errores tipográficos o gramaticales o contengan información incorrecta.

* La **dirección del remitente no coincide con la firma** del propio mensaje. Por ejemplo, se pretende que un correo electrónico sea de Mary of Contoso Corp, pero la dirección del remitente es john<span></span>@example.com.

* Hay **varios destinatarios** en el campo "Para" y parecen ser direcciones aleatorias. Normalmente, los mensajes corporativos se envían directamente a destinatarios individuales.

* El saludo en el mensaje en sí **no se dirige personalmente a usted**. Aparte de los mensajes que se dirigen por error a otra persona, los saludos que hacen mal uso de su nombre o extraen su nombre directamente de su dirección de correo electrónico tienden a ser malintencionados.

* El sitio web parece familiar, pero hay **incoherencias o cosas que no están del todo bien**. Los signos de advertencia incluyen logotipos obsoletos, errores tipográficos o piden a los usuarios que proporcionen información adicional que no se le pide a los sitios web de inicio de sesión legítimos.

* La página que se abre **no es una página activa**, sino una imagen diseñada para parecerse al sitio con el que está familiarizado. Puede aparecer un elemento emergente que solicita credenciales.

En caso de duda, póngase en contacto con la empresa por canales conocidos para comprobar si algún correo electrónico sospechoso es legítimo.

## <a name="software-solutions-for-organizations"></a>Soluciones de software para organizaciones

* [Microsoft Edge](/microsoft-edge/deploy/index) y [Windows डिफेन्डर Protección de aplicaciones](/windows/security/microsoft-defender-application-guard/md-app-guard-overview.md) ofrecen protección contra la amenaza creciente de ataques dirigidos mediante la tecnología de virtualización hyper-V líder del sector de Microsoft. Si se considera que un sitio web explorado no es de confianza, el contenedor de Hyper-V aislará ese dispositivo del resto de la red, lo que impedirá el acceso a los datos empresariales.

* [Microsoft Exchange Online Protection (EOP)](https://products.office.com/exchange/exchange-email-security-spam-protection) ofrece confiabilidad y protección de clase empresarial contra el correo no deseado y el malware, a la vez que mantiene el acceso al correo electrónico durante y después de las emergencias.  Mediante el uso de varias capas de filtrado, EOP puede proporcionar diferentes controles para el filtrado de correo no deseado, como controles de correo masivo y correo no deseado internacional, que mejorarán aún más sus servicios de protección.

* Use [Microsoft Defender para Office 365](https://products.office.com/exchange/online-email-threat-protection?ocid=cx-blog-mmpc) para ayudar a proteger el correo electrónico, los archivos y el almacenamiento en línea contra el malware. Ofrece protección holística en Microsoft Teams, Word, Excel, PowerPoint, Visio, SharePoint Online y OneDrive para la Empresa. Al protegerse frente a datos adjuntos no seguros y ampliar la protección contra vínculos malintencionados, complementa las características de seguridad de Exchange Online Protection para proporcionar una mejor protección de día cero.

## <a name="what-to-do-if-youve-been-a-victim-of-a-phishing-scam"></a>Qué hacer si ha sido víctima de una estafa de suplantación de identidad (phishing)

Si siente que ha sido víctima de un ataque de suplantación de identidad (phishing):

1. Póngase en contacto con el administrador de TI si está en un equipo de trabajo.
2. Cambiar inmediatamente todas las contraseñas asociadas a las cuentas
3. Informar de cualquier actividad fraudulenta a su banco y compañía de tarjetas de crédito

### <a name="reporting-spam"></a>Generación de informes de correo no deseado

- **Outlook.com**: si recibe un mensaje de correo electrónico sospechoso que solicita información personal, active la casilla situada junto al mensaje en la bandeja de entrada de Outlook. Seleccione la flecha situada junto a **Correo no deseado** y, después **, phishing.**

- **Microsoft Office Outlook**: mientras está en el mensaje sospechoso, seleccione **Mensaje** de informe en la cinta de opciones y, después **, phishing.**

- **Microsoft 365**: use el [portal envíos de Microsoft 365 Defender](/microsoft-365/security/office-365-security/report-junk-email-messages-to-microsoft) para enviar el ejemplo de correo no deseado o phishing a Microsoft para su análisis. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](/microsoft-365/security/office-365-security/report-junk-email-messages-to-microsoft).

- **Grupo de trabajo contra phishing**: phishing-report@us-cert.gov. El grupo usa informes generados a partir de correos electrónicos enviados para luchar contra estafas de phishing y hackers. Los ISP, los proveedores de seguridad, las instituciones financieras y las agencias de cumplimiento de la ley están involucrados.

### <a name="if-youre-on-a-suspicious-website"></a>Si está en un sitio web sospechoso

- **Microsoft Edge**: mientras se encuentra en un sitio sospechoso, seleccione el **icono** >  Más (...)**Ayuda y comentarios** > **Notificar sitio no seguro**. Siga las instrucciones de la página web que se muestra para informar del sitio web.

- **Internet Explorer**: mientras se encuentra en un sitio sospechoso, seleccione el icono de engranaje, seleccione **Seguridad** y, después, informe **sitio web no seguro**. Siga las instrucciones de la página web que se muestra para informar del sitio web.

## <a name="more-information-about-phishing-attacks"></a>Más información sobre los ataques de suplantación de identidad (phishing)

- [Protegerse contra suplantación de identidad (phishing)](https://support.microsoft.com/help/4033787/windows-protect-yourself-from-phishing)
- [Tendencias de suplantación de identidad](phishing-trends.md)
