---
title: Características de cifrado administradas por el cliente
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: En este artículo, aprenderá sobre las tecnologías de cifrado que puede administrar y configurar en Microsoft 365.
ms.openlocfilehash: 6a693c512100c59eef47414fdd6eab4a2924e835
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926238"
---
# <a name="customer-managed-encryption-features"></a>Características de cifrado administradas por el cliente

Junto con las tecnologías de cifrado Microsoft 365 administradas por Microsoft, Microsoft 365 también funciona con tecnologías de cifrado adicionales que puede administrar y configurar, como:

- [Azure Rights Management](/azure/information-protection/what-is-azure-rms)

- [Extensión de correo de Internet multipropósito segura](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Cifrado de mensajes de Office 365](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [Flujo de correo seguro con una organización asociada](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

Para obtener información adicional acerca de estas [tecnologías, vea Microsoft 365 descripciones del servicio](/office365/servicedescriptions/office-365-service-descriptions-technet-library).

## <a name="azure-rights-management"></a>Azure Rights Management

[Azure Rights Management](/azure/information-protection/what-is-azure-rms) (Azure RMS) es la tecnología de protección usada por [Azure Information Protection](/information-protection/understand-explore/what-is-information-protection). Usa directivas de cifrado, identidad y autorización para ayudar a proteger los archivos y el correo electrónico en varias plataformas y dispositivos: teléfonos, tabletas y equipos. La información se puede proteger tanto dentro como fuera de la organización porque la protección permanece con los datos. Azure RMS proporciona protección persistente de todos los tipos de archivos, protege archivos en cualquier lugar, admite colaboración entre empresas y una amplia variedad de dispositivos Windows y no Windows. La protección de Azure RMS también puede aumentar las directivas de prevención de pérdida de [datos (DLP).](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) Para obtener más información acerca de qué aplicaciones y servicios pueden usar el servicio Azure Rights Management de Azure Information Protection, vea [How applications support the Azure Rights Management service](/information-protection/understand-explore/applications-support).

Azure RMS se integra con Microsoft 365 y está disponible para todos los clientes. Para configurar Microsoft 365 para usar Azure RMS, vea [Configure IRM to use Azure Rights Management y Set up Information Rights Management (IRM) in SharePoint admin center](../enterprise/activate-rms-in-microsoft-365.md). Si opera el servidor RMS de Active Directory (AD) local, también puede configurar IRM para que use un servidor [de AD RMS](/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)local, pero le recomendamos encarecidamente que migre a [Azure RMS](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) para usar nuevas características como la colaboración segura con otras organizaciones.

Al proteger los datos de clientes con Azure RMS, Azure RMS usa una clave asimétrica RSA de 2048 bits con algoritmo hash SHA-256 para la integridad para cifrar los datos. La clave simétrica para Office documentos y correo electrónico es AES de 128 bits. Para cada documento o correo electrónico protegido por Azure RMS, Azure RMS crea una sola clave AES (la "clave de contenido") y esa clave está incrustada en el documento y persiste a través de ediciones del documento. La clave de contenido está protegida con la clave RSA de la organización (la "clave de inquilino de Azure Information Protection") como parte de la directiva del documento, y la directiva también la firma el autor del documento. Esta clave de inquilino es común a todos los documentos y correos electrónicos protegidos por Azure RMS para la organización y solo puede cambiarla un administrador de Azure Information Protection si la organización usa una clave de inquilino administrada por el cliente. Para obtener más información acerca de los controles criptográficos usados por Azure RMS, vea [¿Cómo funciona Azure RMS? Debajo del capó](/information-protection/understand-explore/how-does-it-work).

En una implementación predeterminada de Azure RMS, Microsoft genera y administra la clave raíz que es única para cada inquilino. Los clientes pueden administrar el ciclo de vida de su clave raíz en Azure RMS con Azure Key Vault Services mediante un método de administración de claves denominado [Bring Your Own Key (BYOK)](/azure/information-protection/plan-implement-tenant-key) que permite generar la clave en HSM locales (módulos de seguridad de hardware) y mantener el control de esta clave después de transferirla a los HSM validados por FIPS 140-2 de Nivel 2 de Microsoft. El acceso a la clave raíz no se da a ningún personal, ya que las claves no se pueden exportar ni extraer de los HSM que las protegen. Además, puede tener acceso a un registro casi en tiempo real que muestra todo el acceso a la clave raíz en cualquier momento. Para obtener más información, vea [Logging and Analyzing Azure Rights Management Usage](/azure/information-protection/log-analyze-usage).

Azure Rights Management ayuda a mitigar amenazas como el cableado, los ataques man-in-the-middle, el robo de datos y las infracciones involuntarias de las directivas de uso compartido de la organización. Al mismo tiempo, cualquier acceso injustificado de datos de clientes en tránsito o en reposo por parte de un usuario no autorizado que no tenga los permisos adecuados se impide a través de directivas que siguen a estos datos, lo que reduce el riesgo de que estos datos caigan en manos equivocadas, ya sea a sabiendas o sin conocimiento, y proporcionando funciones de prevención de pérdida de datos. Si se usa como parte de Azure Information Protection, Azure RMS también proporciona capacidades de clasificación y etiquetado de datos, marcado de contenido, seguimiento de acceso a documentos y capacidades de revocación de acceso. Para obtener más información sobre estas funcionalidades, vea [What is Azure Information Protection](/information-protection/understand-explore/what-is-information-protection), Azure Information Protection deployment [roadmap](/information-protection/plan-design/deployment-roadmap)y Quick Start tutorial for Azure [Information Protection](/information-protection/get-started/infoprotect-quick-start-tutorial).

## <a name="secure-multipurpose-internet-mail-extension"></a>Extensión de correo de Internet multipropósito segura

Secure/Multipurpose Internet Mail Extensions (S/MIME) es un estándar para el cifrado de claves públicas y la firma digital de datos MIME. S/MIME se define en RFC 3369, 3370, 3850, 3851 y otros. Permite a un usuario cifrar un correo electrónico y firmar digitalmente un correo electrónico. Un correo electrónico cifrado mediante S/MIME solo puede descifrarlo el destinatario del correo electrónico mediante su clave privada, que solo está disponible para ese destinatario. Por lo tanto, los correos electrónicos no pueden ser descifrados por nadie que no sea el destinatario del correo electrónico.

[Microsoft admite S/MIME](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx). Los certificados públicos se distribuyen en Active Directory local del cliente y se almacenan en atributos que se pueden replicar en un espacio empresarial Microsoft 365 cliente. Las claves privadas que corresponden a las claves públicas permanecen localmente y nunca se transmiten a Office 365. Los usuarios pueden redactar, cifrar, descifrar, leer y firmar digitalmente correos electrónicos entre dos usuarios de una organización mediante Outlook, Outlook en la web y Exchange ActiveSync clientes. Para obtener más información, vea [Cifrado S/MIME ahora en Office 365](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/).

## <a name="office-365-message-encryption"></a>Cifrado de mensajes de Office 365

[Cifrado de mensajes de Office 365](https://products.office.com/exchange/office-365-message-encryption) (OME) integrado en [Azure Information Protection](/information-protection/understand-explore/what-is-information-protection) (AIP) le permite enviar correo cifrado y protegido con derechos a cualquier persona. OME mitiga las amenazas, como los ataques de cable y man-in-the-middle, y otras amenazas, como el acceso injustificado de datos por parte de un usuario no autorizado que no tiene los permisos adecuados. Hemos realizado inversiones que le proporcionan una experiencia de correo electrónico más sencilla, intuitiva y segura que se basa en Azure Information Protection. Puede proteger los mensajes enviados Microsoft 365 a cualquier persona dentro o fuera de su organización. Estos mensajes se pueden ver en un conjunto diverso de clientes de correo con cualquier identidad, incluidos Azure Active Directory, cuenta de Microsoft e id. de Google. Para obtener más información sobre cómo su organización puede usar mensajes cifrados, [vea Cifrado de mensajes de Office 365](./ome.md).

## <a name="transport-layer-security"></a>Seguridad de la capa de transporte

Si desea garantizar una comunicación segura con un partner, puede usar conectores entrantes y salientes para proporcionar seguridad e integridad de mensajes. Puede configurar TLS de entrada y salida forzadas en cada conector mediante un certificado. El uso de un canal SMTP cifrado puede evitar que se roben datos a través de un ataque de tipo man-in-the-middle. Para obtener más información, vea [How Exchange Online uses TLS to secure email connections](./exchange-online-uses-tls-to-secure-email-connections.md).

## <a name="domain-keys-identified-mail"></a>Correo identificado con claves de dominio

Exchange Online Protection (EOP) y Exchange Online admiten la validación de entrada de mensajes de Correo identificado con claves de dominio (DKIM). DKIM es un método para validar que un mensaje se envió desde el dominio donde dice que se originó, y que no ha sido suplantado por otra persona. Vincula un mensaje de correo electrónico a la organización responsable de enviarlo y forma parte de un paradigma más grande del cifrado de correo electrónico. Para obtener más información acerca de las tres partes de este paradigma, vea:

- [Configurar SPF para ayudar a evitar la suplantación de identidad](/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado](/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [Usar DMARC para validar el correo electrónico](/office365/SecurityCompliance/use-dmarc-to-validate-email)