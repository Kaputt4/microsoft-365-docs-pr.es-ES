---
title: Cómo protegerse contra ataques de suplantación de identidad
ms.reviewer: ''
description: Obtenga información sobre cómo funciona la suplantación de identidad (phishing), entregar malware para sus dispositivos y qué puede hacer para protegerse
keywords: seguridad, malware, phishing, información, estafa, ingeniería social, cebo, señuelo, protección, tendencias, ataque dirigido
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 39b998b69b62a8c927ff26c1325d8a88812e0be6
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683607"
---
# <a name="how-to-protect-against-phishing-attacks"></a>Cómo protegerse contra ataques de suplantación de identidad

Los ataques de suplantación de identidad intentan robar información confidencial a través de correos electrónicos, sitios web, mensajes de texto u otras formas de comunicación electrónica. Intentan parecer comunicación oficial de empresas o personas legítimas.

Los cibercriminales suelen intentar robar nombres de usuario, contraseñas, detalles de tarjetas de crédito, información de cuentas bancarias u otras credenciales. Usan información robada con fines malintencionados, como piratería, robo de identidad o robo de dinero directamente de cuentas bancarias y tarjetas de crédito. La información también se puede vender en mercados clandestinos cibercriminales.

Los ataques de ingeniería social están diseñados para aprovechar el posible lapso de toma de decisiones de un usuario. Tenga en cuenta y nunca proporcione información confidencial o personal a través de correo electrónico o sitios web desconocidos, o por teléfono. Recuerde que los correos electrónicos de suplantación de identidad están diseñados para que parezcan legítimos.

## <a name="learn-the-signs-of-a-phishing-scam"></a>Obtenga información sobre los signos de una estafa de suplantación de identidad (phishing)

La mejor protección es la sensibilización y la educación. No abra archivos adjuntos o vínculos en correos electrónicos no solicitados, incluso si los correos electrónicos provenían de un origen reconocido. Si el correo electrónico es inesperado, tenga cuidado con abrir los datos adjuntos y compruebe la dirección URL.

Las empresas deben educar y formar a sus empleados para que sean caulosos ante cualquier comunicación que solicite información personal o financiera. También deben indicar a los empleados que informen inmediatamente de la amenaza al equipo de operaciones de seguridad de la compañía.

Estos son varios signos revelados de una estafa de suplantación de identidad:

* Los vínculos o direcciones URL proporcionados en  los correos electrónicos no apuntan a la ubicación correcta o apuntan a un sitio de terceros que no está asociado con el remitente del correo electrónico. Por ejemplo, en la imagen debajo de la dirección URL proporcionada no coincide con la dirección URL a la que se le va a llevar.

    ![ejemplo de mantener el mouse sobre una dirección URL.](../../media/security-intelligence-images/url-hover.png)

* Hay una solicitud de **información personal** , como números de seguridad social o información bancaria o financiera. Por lo general, las comunicaciones oficiales no le solicitarán información personal en forma de correo electrónico.

* **Los elementos de la dirección de correo electrónico** se cambiarán para que sea lo suficientemente similar a una dirección de correo electrónico legítima, pero haya agregado números o letras modificadas.

* El mensaje es **inesperado y no solicitado**. Si de repente recibe un correo electrónico de una entidad o de una persona con la que rara vez trata, considere este correo electrónico como sospechoso.

* El mensaje o los datos adjuntos le piden que habilite **macros, ajuste la configuración de seguridad o instale aplicaciones**. Los correos electrónicos normales no le pedirán que lo haga.

* El mensaje contiene **errores**. Es menos probable que los mensajes corporativos legítimos tengan errores tipográficos o gramaticales o que contengan información incorrecta.

* La **dirección del remitente no coincide con la firma** del mensaje en sí. Por ejemplo, se pretende que un correo electrónico sea de María de Contoso Corp, pero la dirección del remitente es john<span></span>@example.com.

* Hay varios **destinatarios en el** campo "Para" y parecen ser direcciones aleatorias. Normalmente, los mensajes corporativos se envían directamente a destinatarios individuales.

* El saludo en el mensaje **en sí no le direcciona personalmente**. Aparte de los mensajes que se direccionan por error a una persona diferente, los saludos que usan mal su nombre o sacan su nombre directamente de su dirección de correo electrónico tienden a ser malintencionados.

* El sitio web es familiar, pero **hay incoherencias o cosas que no son del todo correctas**. Los signos de advertencia incluyen logotipos obsoletos, errores or ask users to give additional information that is not asked by legitimate sign-in websites.

* La página que se abre **no es una página** en directo, sino una imagen diseñada para parecer al sitio con el que estás familiarizado. Puede que aparezca una ventana emergente que solicite credenciales.

En caso de duda, póngase en contacto con la empresa por canales conocidos para comprobar si algún correo electrónico sospechoso es en realidad legítimo.

## <a name="software-solutions-for-organizations"></a>Soluciones de software para organizaciones

* [Microsoft Edge](/microsoft-edge/deploy/index) y [Protección de aplicaciones de Windows Defender](/windows/security/microsoft-defender-application-guard/md-app-guard-overview.md) ofrecen protección contra la amenaza creciente de ataques dirigidos con la tecnología de virtualización de Hyper-V líder del sector de Microsoft. Si se considera que un sitio web explorado no es de confianza, el contenedor de Hyper-V aislará ese dispositivo del resto de la red, lo que impedirá el acceso a los datos de la empresa.

* [Microsoft Exchange Online Protection (EOP)](https://products.office.com/exchange/exchange-email-security-spam-protection) ofrece confiabilidad de clase empresarial y protección contra correo no deseado y malware, al tiempo que mantiene el acceso al correo electrónico durante y después de las emergencias.  Con varias capas de filtrado, EOP puede proporcionar diferentes controles para el filtrado de correo no deseado, como controles de correo masivo y correo no deseado internacional, que mejorarán aún más los servicios de protección.

* Usa [Microsoft Defender para Office 365](https://products.office.com/exchange/online-email-threat-protection?ocid=cx-blog-mmpc) para proteger el correo electrónico, los archivos y el almacenamiento en línea contra malware. Ofrece protección holística en Microsoft Teams, Word, Excel, PowerPoint, Visio, SharePoint Online y OneDrive para la Empresa. Al proteger contra datos adjuntos no seguros y ampliar la protección contra vínculos malintencionados, complementa las características de seguridad de Exchange Online Protection para proporcionar una mejor protección de día cero.

## <a name="what-to-do-if-youve-been-a-victim-of-a-phishing-scam"></a>Qué hacer si has sido víctima de una estafa de suplantación de identidad (phishing)

Si crees que has sido víctima de un ataque de suplantación de identidad:

1. Póngase en contacto con el administrador de TI si está en un equipo de trabajo
2. Cambiar inmediatamente todas las contraseñas asociadas a las cuentas
3. Notificar cualquier actividad fraudulenta a su banco y a la compañía de tarjetas de crédito

### <a name="reporting-spam"></a>Notificar correo no deseado

- **Outlook.com**: si recibe un mensaje de correo electrónico sospechoso que solicita información personal, active la casilla situada junto al mensaje en la bandeja de entrada Outlook correo electrónico. Seleccione la flecha situada junto a **Correo** no deseado y, a continuación, **suplantación de identidad**.

- **Microsoft Office Outlook**: mientras se encuentra en el mensaje sospechoso, seleccione **Informar del mensaje** de la cinta de opciones y, a continuación, seleccione **Suplantación de identidad**.

- **Microsoft 365**: use el [portal de envíos de Microsoft 365 Defender](/microsoft-365/security/office-365-security/report-junk-email-messages-to-microsoft) para enviar la muestra de correo no deseado o suplantación de identidad (phishing) a Microsoft para su análisis. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](/microsoft-365/security/office-365-security/report-junk-email-messages-to-microsoft).

- **Grupo de trabajo contra la suplantación de** identidad: phishing-report@us-cert.gov. El grupo usa informes generados a partir de correos electrónicos enviados para combatir las estafas de suplantación de identidad (phishing) y los hackers. Participan isp, proveedores de seguridad, instituciones financieras y organismos de aplicación de la ley.

### <a name="if-youre-on-a-suspicious-website"></a>Si estás en un sitio web sospechoso

- **Microsoft Edge**: mientras se encuentra en un sitio sospechoso, seleccione el sitio **Más (...) iconHelp** >  **y feedbackReport** >  **Unsafe**. Siga las instrucciones de la página web que se muestra para informar del sitio web.

- **Internet Explorer**: mientras se encuentra en un sitio sospechoso, seleccione el icono de engranaje, elija Seguridad **y, a** continuación, seleccione **Informar de sitio web no seguro**. Siga las instrucciones de la página web que se muestra para informar del sitio web.

## <a name="more-information-about-phishing-attacks"></a>Más información sobre los ataques de suplantación de identidad

- [Protegerse de la suplantación de identidad (phishing)](https://support.microsoft.com/help/4033787/windows-protect-yourself-from-phishing)
- [Tendencias de phishing](phishing-trends.md)
