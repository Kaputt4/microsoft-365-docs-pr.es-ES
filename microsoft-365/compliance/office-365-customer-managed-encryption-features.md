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
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- purview-compliance
- tier3
ms.custom:
- seo-marvel-mar2020
description: En este artículo, obtendrá información sobre las tecnologías de cifrado que puede administrar y configurar en Microsoft 365.
ms.openlocfilehash: c6346a6dd271bca88cff96b72fa73ed1eecb0d6d
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68620577"
---
# <a name="customer-managed-encryption-features"></a>Características de cifrado administradas por el cliente

- [Azure Rights Management](/azure/information-protection/what-is-azure-rms)

- [Cifrado de mensajes de Microsoft Purview](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [Protección del flujo de correo con una organización asociada](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

Para obtener más información sobre estas tecnologías, consulte las [descripciones del servicio de Microsoft 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library).

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="azure-rights-management"></a>Azure Rights Management

[Azure Rights Management](/azure/information-protection/what-is-azure-rms) (Azure RMS) es la tecnología de protección que usa [Azure Information Protection](/information-protection/understand-explore/what-is-information-protection). Usa directivas de cifrado, identidad y autorización para ayudar a proteger los archivos y el correo electrónico en varias plataformas y dispositivos: teléfonos, tabletas y equipos. La información se puede proteger dentro y fuera de la organización porque la protección permanece con los datos. Azure RMS proporciona protección persistente de todos los tipos de archivos, protege los archivos en cualquier lugar, admite la colaboración entre empresas y una amplia gama de dispositivos Windows y que no son de Windows. La protección de Azure RMS también puede aumentar [las directivas de prevención de pérdida de datos (DLP).](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) Para obtener más información sobre qué aplicaciones y servicios pueden usar el servicio de Azure Rights Management de Azure Information Protection, consulte [Cómo las aplicaciones admiten el servicio Azure Rights Management](/information-protection/understand-explore/applications-support).

Azure RMS se integra con Microsoft 365 y está disponible para todos los clientes. Para configurar Microsoft 365 para usar Azure RMS, consulte [Configuración de IRM para usar Azure Rights Management y Configuración de Information Rights Management (IRM) en el Centro de administración de SharePoint](../enterprise/activate-rms-in-microsoft-365.md). Si trabaja con un servidor rms de Active Directory (AD) local, también puede [configurar IRM para usar un servidor de AD RMS local](/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server), pero se recomienda [encarecidamente migrar a Azure RMS](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) para usar nuevas características, como la colaboración segura con otras organizaciones.

Cuando se protegen los datos de los clientes con Azure RMS, Azure RMS usa una clave asimétrica RSA de 2048 bits con algoritmo hash SHA-256 para que la integridad cifre los datos. La clave simétrica para documentos y correo electrónico de Office es AES de 128 bits. Para cada documento o correo electrónico protegido por Azure RMS, Azure RMS crea una única clave de AES (la "clave de contenido") y esa clave se inserta en el documento y se conserva a través de ediciones del documento. La clave de contenido está protegida con la clave RSA de la organización (la "clave de inquilino de Azure Information Protection") como parte de la directiva del documento, y la directiva también está firmada por el autor del documento. Esta clave de inquilino es común a todos los documentos y correos electrónicos protegidos por Azure RMS para la organización y esta clave solo la puede cambiar un administrador de Azure Information Protection si la organización usa una clave de inquilino administrada por el cliente. Para obtener más información sobre los controles criptográficos que usa Azure RMS, consulte [¿Cómo funciona Azure RMS? Bajo el capó](/information-protection/understand-explore/how-does-it-work).

En una implementación predeterminada de Azure RMS, Microsoft genera y administra la clave raíz que es única para cada inquilino. Los clientes pueden administrar el ciclo de vida de su clave raíz en Azure RMS con Azure कि भल्ट Services mediante un método de administración de claves denominado [Bring Your Own Key (BYOK)](/azure/information-protection/plan-implement-tenant-key) que le permite generar la clave en HSM locales (módulos de seguridad de hardware) y mantener el control de esta clave después de la transferencia a los HSM de nivel 2 de FIPS 140-2 validados de Microsoft. El acceso a la clave raíz no se concede a ningún personal, ya que las claves no se pueden exportar ni extraer de los HSM que las protegen. Además, puede acceder a un registro casi en tiempo real que muestre todo el acceso a la clave raíz en cualquier momento. Para obtener más información, consulte [Registro y análisis del uso de Azure Rights Management](/azure/information-protection/log-analyze-usage).

Azure Rights Management ayuda a mitigar amenazas como la escucha de cables, los ataques man-in-the-middle, el robo de datos y las infracciones involuntarias de las directivas de uso compartido de la organización. Al mismo tiempo, cualquier acceso injustificado a los datos del cliente en tránsito o en reposo por parte de un usuario no autorizado que no tenga los permisos adecuados se impide a través de directivas que siguen a esos datos, mitigando así el riesgo de que esos datos caigan en manos equivocadas, ya sea a sabiendas o sin saberlo, y proporcionando funciones de prevención de pérdida de datos. Si se usa como parte de Azure Information Protection, Azure RMS también proporciona funcionalidades de clasificación y etiquetado de datos, marcado de contenido, seguimiento de acceso a documentos y capacidades de revocación de acceso. Para más información sobre estas funcionalidades, consulte [¿Qué es Azure Information Protection](/information-protection/understand-explore/what-is-information-protection)?, Hoja de [ruta de implementación de Azure Information Protection](/information-protection/plan-design/deployment-roadmap) y [Tutorial de inicio rápido para Azure Information Protection](/information-protection/get-started/infoprotect-quick-start-tutorial).

## <a name="secure-multipurpose-internet-mail-extension"></a>Protección de la extensión multipropósito de correo de Internet

Las extensiones de correo de Internet seguras o multipropósito (S/MIME) son un estándar para el cifrado de claves públicas y la firma digital de datos MIME. S/MIME se define en RFC 3369, 3370, 3850, 3851 y otros. Permite a un usuario cifrar un correo electrónico y firmar digitalmente un correo electrónico. El destinatario del correo electrónico solo puede descifrar un correo electrónico cifrado mediante S/MIME mediante su clave privada, que solo está disponible para ese destinatario. Por lo tanto, los correos electrónicos no pueden ser descifrados por nadie que no sea el destinatario del correo electrónico.

[Microsoft admite S/MIME](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx). Los certificados públicos se distribuyen a Active Directory local del cliente y se almacenan en atributos que se pueden replicar en un inquilino de Microsoft 365. Las claves privadas que corresponden a las claves públicas permanecen en el entorno local y nunca se transmiten a Office 365. Los usuarios pueden redactar, cifrar, descifrar, leer y firmar digitalmente correos electrónicos entre dos usuarios de una organización mediante Outlook, Outlook en la Web y Exchange ActiveSync clientes. Para obtener más información, consulte [Cifrado S/MIME ahora en Office 365](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/).

## <a name="office-365-message-encryption"></a>Cifrado de mensajes de Office 365

[Office 365 Cifrado de mensajes](https://products.office.com/exchange/office-365-message-encryption) (OME) basado en [Azure Information Protection](/information-protection/understand-explore/what-is-information-protection) (AIP) permite enviar correo cifrado y protegido por derechos a cualquier persona. OME mitiga amenazas como los ataques por cable y los ataques man-in-the-middle, y otras amenazas, como el acceso injustificado a los datos por parte de un usuario no autorizado que no tiene los permisos adecuados. Hemos realizado inversiones que le proporcionan una experiencia de correo electrónico más sencilla, intuitiva y segura basada en Azure Information Protection. Puede proteger los mensajes enviados desde Microsoft 365 a cualquier persona dentro o fuera de su organización. Estos mensajes se pueden ver en un conjunto diverso de clientes de correo mediante cualquier identidad, incluidos Azure Active Directory, la cuenta microsoft y los identificadores de Google. Para obtener más información sobre cómo su organización puede usar mensajes cifrados, consulte [Office 365 Cifrado de mensajes](./ome.md).

## <a name="transport-layer-security"></a>Seguridad de la capa de transporte

Si desea garantizar una comunicación segura con un asociado, puede usar conectores entrantes y salientes para proporcionar seguridad e integridad de mensajes. Puede configurar TLS de entrada y salida forzadas en cada conector mediante un certificado. El uso de un canal SMTP cifrado puede impedir que se roben datos a través de un ataque man-in-the-middle. Para obtener más información, vea [Cómo Exchange Online usa TLS para proteger las conexiones de correo electrónico](./exchange-online-uses-tls-to-secure-email-connections.md).

## <a name="domain-keys-identified-mail"></a>Correo identificado de claves de dominio

Exchange Online Protection (EOP) y Exchange Online admiten la validación de entrada de mensajes de Correo identificado con claves de dominio (DKIM). DKIM es un método para validar que se envió un mensaje desde el dominio desde el que dice que se originó y que no fue suplantado por otra persona. Vincula un mensaje de correo electrónico a la organización responsable de enviarlo y forma parte de un paradigma más grande del cifrado de correo electrónico. Para obtener más información sobre las tres partes de este paradigma, consulte:

- [Configurar SPF para ayudar a evitar la suplantación de identidad](/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado](/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [Usar DMARC para validar el correo electrónico](/office365/SecurityCompliance/use-dmarc-to-validate-email)
