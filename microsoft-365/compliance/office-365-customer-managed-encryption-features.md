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
description: En este artículo, obtendrá información sobre las tecnologías de cifrado que puede administrar y configurar en Microsoft 365.
ms.openlocfilehash: 3c7050ba0417473b4b387937336aae02c1eba778
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033618"
---
# <a name="customer-managed-encryption-features"></a>Características de cifrado administradas por el cliente

Junto con las tecnologías de cifrado de Microsoft 365 administradas por Microsoft, Microsoft 365 también funciona con tecnologías de cifrado adicionales que puede administrar y configurar, como:

- [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)

- [Extensión de correo de Internet multipropósito segura](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Cifrado de mensajes de Office 365](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [Flujo de correo seguro con una organización asociada](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

Para obtener información adicional acerca de estas tecnologías, consulte las [descripciones](https://technet.microsoft.com/library/office-365-service-descriptions.aspx)de los servicios de 365 de Microsoft.

## <a name="azure-rights-management"></a>Azure Rights Management

[Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) (Azure RMS) es la tecnología de protección usada por [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection). Usa directivas de cifrado, identidades y autorización para ayudar a proteger los archivos y el correo electrónico en varias plataformas y dispositivos (teléfonos, tabletas y equipos). La información se puede proteger tanto dentro como fuera de la organización, ya que la protección se mantiene con los datos. Azure RMS proporciona protección persistente de todos los tipos de archivo, protege los archivos en cualquier lugar, admite la colaboración entre empresas y una amplia gama de dispositivos Windows y que no son Windows. La protección de Azure RMS también puede aumentar [las directivas de prevención de pérdida de datos (DLP)](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention). Para obtener más información sobre qué aplicaciones y servicios pueden usar el servicio Azure Rights Management desde Azure Information Protection, vea [cómo las aplicaciones admiten el servicio Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/applications-support).

Azure RMS se integra con Microsoft 365 y está disponible para todos los clientes. Para configurar Microsoft 365 para usar Azure RMS, vea [configure IRM to use Azure Rights Management y set up Information Rights Management (IRM) en el centro de administración de SharePoint](https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx). Si opera el servidor RMS local de Active Directory (AD), también puede [configurar IRM para usar un servidor AD RMS local](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server), pero le recomendamos encarecidamente que [MIGRE a Azure RMS](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) para usar nuevas características, como la colaboración segura con otras organizaciones.

Cuando se protegen los datos de los clientes con Azure RMS, Azure RMS usa una clave asimétrica RSA de 2048 bits con algoritmo de hash SHA-256 para la integridad para cifrar los datos. La clave simétrica para los documentos y el correo electrónico de Office es AES 128 bits (modo CBC con relleno PKCS # 7). Para cada documento o correo electrónico protegido por Azure RMS, Azure RMS crea una sola clave AES (la "clave de contenido"), y esa clave se inserta en el documento y se conserva a través de las ediciones del documento. La clave de contenido está protegida con la clave RSA de la organización (la "clave de espacio empresarial de Azure Information Protection") como parte de la Directiva en el documento, y la Directiva también está firmada por el autor del documento. Esta clave de espacio empresarial es común a todos los documentos y correos electrónicos protegidos por Azure RMS para la organización, y esta clave solo la puede cambiar un administrador de Azure Information Protection si la organización usa una clave de inquilino administrada por el cliente. Para obtener más información acerca de los controles criptográficos usados por Azure RMS, vea [¿Cómo funciona Azure RMS? Por debajo del capó](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work).

En una implementación de Azure RMS predeterminada, Microsoft genera y administra la clave raíz que es única para cada inquilino. Los clientes pueden administrar el ciclo de vida de su clave raíz en Azure RMS con Key Vault Services de Azure mediante un método de administración de claves denominado [traer su propia clave (BYOK)](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key) que le permita generar la clave en los HSM locales (módulos de seguridad de hardware) y mantener el control de esta clave después de transferir a los HSM validados de FIPS 140-2 de nivel 2 de Microsoft. No se proporciona acceso a la clave raíz a ningún personal, ya que las claves no se pueden exportar o extraer de los HSM que las protege. Además, puede tener acceso a un registro casi en tiempo real que muestre todo el acceso a la clave raíz en cualquier momento. Para obtener más información, vea [registro y análisis del uso de Azure Rights Management](https://docs.microsoft.com/azure/information-protection/log-analyze-usage).

Azure Rights Management ayuda a mitigar las amenazas como el acceso al cable, los ataques de tipo "Man in the Middle", el robo de datos y las violaciones involuntarias de las directivas de uso compartido de la organización. Al mismo tiempo, cualquier acceso no garantizado de los datos de clientes en tránsito o en reposo por parte de un usuario no autorizado que no tenga los permisos adecuados se evita por medio de las directivas que siguen a dichos datos, por lo que se mitiga el riesgo de que los datos que se encuentran en las manos equivocadas sean conscientes o sin saberlo y proporcionen funciones de prevención de pérdida de datos. Si se usa como parte de Azure Information Protection, Azure RMS también ofrece capacidades de clasificación y etiquetado de datos, marcado de contenido, seguimiento de acceso a documentos y capacidades de revocación de acceso. Para obtener más información acerca de estas funciones, consulte [What is Azure Information](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)Protection, [Azure Information Protection Deployment Roadmap](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)y [Quick Start tutorial para Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial).

## <a name="secure-multipurpose-internet-mail-extension"></a>Extensión de correo de Internet multipropósito segura

Secure/Multipurpose Internet Mail Extensions (S/MIME) es un estándar para el cifrado de claves públicas y la firma digital de datos MIME. S/MIME se define en RFC 3369, 3370, 3850, 3851 y otros. Permite a un usuario cifrar un correo electrónico y firmar digitalmente un correo electrónico. Un correo electrónico cifrado con S/MIME sólo puede ser descifrado por el destinatario del correo electrónico mediante su clave privada, que solo está disponible para ese destinatario. Como tal, los correos electrónicos no pueden ser descifrados por nadie que no sea el destinatario del correo electrónico.

[Microsoft admite S/MIME](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx). Los certificados públicos se distribuyen en Active Directory local del cliente y se almacenan en atributos que se pueden replicar en un inquilino de Microsoft 365. Las claves privadas que corresponden a las claves públicas permanecen locales y nunca se transmiten a Office 365. Los usuarios pueden componer, cifrar, descifrar, leer y firmar digitalmente los correos electrónicos entre dos usuarios de una organización mediante Outlook, Outlook en la web y los clientes de Exchange ActiveSync. Para obtener más información, vea [cifrado S/MIME ahora en Office 365](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/).

## <a name="office-365-message-encryption"></a>Cifrado de mensajes de Office 365

[Office 365 cifrado de mensajes](https://products.office.com/exchange/office-365-message-encryption) (OME) creado a partir de [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) (AIP) le permite enviar correo cifrado y protegido por derechos a cualquier usuario. OME mitiga las amenazas como el punteo del cable y los ataques de tipo "Man in the Middle", así como otras amenazas, como el acceso sin garantías de datos por un usuario no autorizado que no tiene los permisos adecuados. Hemos realizado inversiones que le proporcionan una experiencia de correo electrónico más sencilla, más intuitiva y segura que se basa en Azure Information Protection. Puede proteger los mensajes enviados por Microsoft 365 a cualquier persona dentro o fuera de la organización. Estos mensajes se pueden ver a través de un conjunto diverso de clientes de correo con cualquier identidad, incluidos Azure Active Directory, la cuenta de Microsoft y los identificadores de Google. Para obtener más información acerca de cómo su organización puede usar mensajes cifrados, consulte [Office 365 Message Encryption](https://support.office.com/article/F87CB016-7876-4317-AE3C-9169B311FF8A).

## <a name="transport-layer-security"></a>Seguridad de la capa de transporte

Si desea garantizar una comunicación segura con un asociado, puede usar conectores de entrada y de salida para proporcionar seguridad e integridad de mensajes. Puede configurar TLS forzado de entrada y de salida en cada conector mediante un certificado. El uso de un canal SMTP cifrado puede evitar que los datos se roben a través de un ataque de tipo "Man in the Middle". Para obtener más información, vea [Cómo Exchange online usa TLS para proteger las conexiones de correo electrónico](https://support.office.com/article/How-Exchange-Online-uses-TLS-to-secure-email-connections-in-Office-365-4CDE0CDA-3430-4DC0-B489-F2C0736C929F).

## <a name="domain-keys-identified-mail"></a>Correo identificado por claves de dominio

Exchange Online Protection (EOP) y Exchange Online admiten la validación de entrada de mensajes de Correo identificado con claves de dominio (DKIM). DKIM es un método para validar que un mensaje se envió desde el dominio donde dice que se originó, y que no ha sido suplantado por otra persona. Vincula un mensaje de correo electrónico a la organización responsable de enviarlo y forma parte de un mayor paradigma del cifrado de correo electrónico. Para obtener más información acerca de las tres partes de este paradigma, consulte:

- [Configurar SPF para ayudar a evitar la suplantación de identidad](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [Usar DMARC para validar el correo electrónico](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
