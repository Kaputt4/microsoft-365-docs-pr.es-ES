---
title: Configuración de Azure AD para el contenido cifrado por Microsoft Purview Information Protection
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection: M365-security-compliance
description: Configuración del acceso entre inquilinos de Azure AD y directivas de acceso condicional para el contenido cifrado por Microsoft Purview Information Protection.
ms.openlocfilehash: 70594e80518a83a8f7aabf05ab2e53da6c8b85f5
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67735789"
---
# <a name="azure-ad-configuration-for-encrypted-content"></a>Configuración de Azure AD para contenido cifrado

Si protege elementos confidenciales como correos electrónicos y documentos mediante el cifrado del servicio Azure Rights Management desde [Microsoft Purview Information Protection](information-protection.md), hay algunas configuraciones de Azure Active Directory (Azure AD) que pueden impedir el acceso autorizado a este contenido cifrado.

De forma similar, si los usuarios reciben correo electrónico cifrado de otra organización o colaboran con otras organizaciones que cifran documentos mediante el servicio Azure Rights Management, es posible que los usuarios no puedan abrir ese correo electrónico o documento debido a cómo se configura Azure AD.

Por ejemplo:

- Un usuario no puede abrir el correo electrónico cifrado enviado desde otra organización. O bien, un usuario informa de que los destinatarios de otra organización no pueden abrir un correo electrónico cifrado que les enviaron.

- Su organización colabora con otra organización en un proyecto conjunto y los documentos del proyecto están protegidos mediante su cifrado, concediéndole acceso mediante grupos en Azure AD. Los usuarios no pueden abrir los documentos cifrados por los usuarios de la otra organización.

- Los usuarios pueden abrir correctamente un documento cifrado cuando están en la oficina, pero no cuando intentan acceder a este documento de forma remota y se les solicita la autenticación multifactor (MFA).

Para asegurarse de que el acceso al servicio de cifrado no está bloqueado involuntariamente, use las secciones siguientes para ayudar a configurar Azure AD de su organización o retransmitir la información a un administrador de Azure AD de otra organización. Sin acceso a este servicio, los usuarios no se pueden autenticar ni autorizar para abrir contenido cifrado.

## <a name="cross-tenant-access-settings-and-encrypted-content"></a>Configuración de acceso entre inquilinos y contenido cifrado

> [!IMPORTANT]
> La configuración de acceso entre inquilinos de otra organización puede ser responsable de que los usuarios no puedan abrir el contenido cifrado por los usuarios o de que los usuarios no puedan abrir el contenido cifrado por la otra organización.
> 
> El mensaje que ven los usuarios indica qué organización bloqueó el acceso. Es posible que tenga que dirigir al administrador de Azure AD desde otra organización a esta sección.

De forma predeterminada, no hay nada que configurar para que la autenticación entre inquilinos funcione cuando los usuarios protegen el contenido mediante el cifrado del servicio Azure Rights Management. Sin embargo, la organización puede restringir el acceso mediante la [configuración de acceso entre inquilinos de Identidades externas de](/azure/active-directory/external-identities/cross-tenant-access-overview) Azure AD. Por el contrario, otra organización también puede configurar estas opciones para restringir el acceso con los usuarios de la organización. Esta configuración afecta a la apertura de los elementos cifrados, que incluyen correos electrónicos cifrados y documentos cifrados.

Por ejemplo, otra organización podría tener configurada una configuración que impida que sus usuarios abran contenido cifrado por la organización. En este escenario, hasta que el administrador de Azure AD vuelva a configurar la configuración entre inquilinos, un usuario externo que intente abrir ese contenido verá un mensaje que le informa de que **la organización bloquea el acceso** con una referencia al **administrador de inquilinos**.

Mensaje de ejemplo para el usuario que inició sesión desde la organización de Fabrikam, Inc, cuando su instancia local de Azure AD bloquea el acceso:

![Mensaje de ejemplo cuando el inquilino local de Azure AD bloquea el acceso al contenido cifrado.](../media/blocked-by-your-org.png)

Los usuarios verán un mensaje similar cuando sea la configuración de Azure AD la que bloquee el acceso.

Desde la perspectiva del usuario que ha iniciado sesión, si es otra organización de Azure AD la responsable de bloquear el acceso, **la organización bloquea** los cambios de mensaje en Access y muestra el nombre de dominio de esa otra organización en el cuerpo del mensaje. Por ejemplo:

![Mensaje de ejemplo cuando otro inquilino de Azure AD bloquea el acceso al contenido cifrado.](../media/blocked-by-external-org.png)

Cada vez que la configuración de acceso entre inquilinos restringe el acceso por parte de las aplicaciones, se deben configurar para permitir el acceso a **Microsoft Azure Information Protection**, que tiene el siguiente identificador de aplicación:

````plaintext
00000012-0000-0000-c000-000000000000
````

Si no se permite este acceso, los usuarios no se pueden autenticar ni autorizar para abrir contenido cifrado. Esta configuración se puede establecer como una configuración predeterminada y como una configuración organizativa:

- Para permitir el uso compartido de contenido cifrado con otra organización, cree una configuración de entrada que permita el acceso a Microsoft Azure Information Protection (identificador: 00000012-0000-0000-c000-0000000000). 

- Para permitir el acceso al contenido cifrado que los usuarios reciben de otras organizaciones, cree una configuración de salida que permita el acceso a Microsoft Azure Information Protection (identificador: 00000012-0000-0000-c000-000000000000)

Cuando esta configuración se configura para Microsoft Azure Information Protection, la aplicación muestra **Microsoft Rights Management Services**.

Para obtener instrucciones sobre cómo configurar estas opciones de acceso entre inquilinos, consulte [Configuración del acceso entre inquilinos para la colaboración B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-collaboration).

Si también ha configurado directivas de acceso condicional de Azure AD que requieren autenticación multifactor (MFA) para los usuarios, consulte la sección siguiente sobre cómo configurar el acceso condicional para el contenido cifrado.

## <a name="conditional-access-policies-and-encrypted-documents"></a>Directivas de acceso condicional y documentos cifrados

Si su organización ha implementado [directivas de acceso condicional de Azure Active Directory](/azure/active-directory/conditional-access/overview) que incluyen **Microsoft Azure Information Protection** y la directiva se extiende a usuarios externos que necesitan abrir documentos cifrados por su organización:

- Para los usuarios externos que tienen una cuenta de Azure AD en su propio inquilino, se recomienda usar [la configuración de acceso entre inquilinos de identidades externas](/azure/active-directory/external-identities/cross-tenant-access-overview) para configurar la configuración de confianza para las notificaciones de MFA de una, muchas o todas las organizaciones externas de Azure AD.

- Para los usuarios externos que no están cubiertos por la entrada anterior, por ejemplo, los usuarios que no tienen una cuenta de Azure AD o que no han configurado la configuración de acceso entre inquilinos para la configuración de confianza, estos usuarios externos deben tener una cuenta de invitado en el inquilino.
    
Sin una de estas configuraciones, los usuarios externos no podrán abrir el contenido cifrado y verán un mensaje de error. El texto del mensaje podría informarles que su cuenta necesita ser agregada como usuario externo de el inquilino, con la instrucción incorrecta para este escenario para **Cerrar sesión y volver a iniciar sesión con una cuenta de usuario de Azure Active Directory diferente**.

Si no puede cumplir estos requisitos de configuración para los usuarios externos que necesitan abrir contenido cifrado por su organización, debe quitar microsoft Azure Information Protection de las directivas de acceso condicional o excluir usuarios externos de las directivas.

Para obtener más información, consulte la pregunta más frecuente, [consulte Azure Information Protection aparece como una aplicación en la nube disponible para el acceso condicional, ¿cómo funciona esto?](/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work)

## <a name="guest-accounts-for-external-users-to-open-encrypted-documents"></a>Cuentas de invitado para que los usuarios externos abran documentos cifrados

Es posible que necesite cuentas de invitado en el inquilino de Azure AD para que los usuarios externos abran documentos cifrados por su organización. Opciones para crear las cuentas de invitado:

- Cree estas cuentas de invitado usted mismo. Puede especificar cualquier dirección de correo electrónico que estos usuarios ya utilicen. Por ejemplo, su dirección de Gmail.
    
    La ventaja de esta opción es que puedes restringir el acceso y los derechos a usuarios específicos especificando su dirección de correo electrónico en la configuración de cifrado. El inconveniente es la sobrecarga administrativa para la creación de la cuenta y la coordinación con la configuración de la etiqueta.

- Use la [integración de SharePoint y OneDrive con Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration) para que las cuentas de invitado se creen automáticamente cuando los usuarios compartan vínculos.
    
    La ventaja de esta opción es que la carga administrativa es mínima, ya que las cuentas se crean automáticamente, y la configuración de las etiquetas es más sencilla. Para este escenario, debe seleccionar la opción de encriptación [Agregar cualquier usuario autentificado](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) porque no conocerá las direcciones de correo electrónico de antemano. El inconveniente es que esta configuración no permite restringir los derechos de acceso y uso a usuarios específicos.

Los usuarios externos también pueden utilizar una cuenta de Microsoft para abrir documentos encriptados cuando utilizan Windows y las Aplicaciones de Microsoft 365 ([las que antes eran aplicaciones de Office 365](/deployoffice/name-change)) o la edición independiente de Office 2019. Más recientemente, las cuentas de Microsoft también son compatibles con la apertura de documentos cifrados en macOS (Aplicaciones de Microsoft 365, versión 16.42+), Android (versión 16.0.13029+) e iOS (versión 2.42+). 

Por ejemplo, un usuario de su organización comparte un documento encriptado con un usuario externo a su organización, y la configuración de encriptación especifica una dirección de correo electrónico de Gmail para el usuario externo. Este usuario externo puede crear su propia cuenta de Microsoft que utiliza su dirección de correo electrónico de Gmail. A continuación, tras iniciar sesión con esta cuenta, pueden abrir el documento y editarlo, según las restricciones de uso especificadas para ellos. Para ver un ejemplo de este escenario, consulte [Abrir y editar el documento protegido](/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document).

> [!NOTE]
> La dirección de correo electrónico de la cuenta de Microsoft debe coincidir con la dirección de correo electrónico especificada para restringir el acceso a la configuración de cifrado.

Cuando un usuario con una cuenta de Microsoft abre un documento encriptado de esta manera, se crea automáticamente una cuenta de invitado para el inquilino si no existe ya una cuenta de invitado con el mismo nombre. Cuando existe una cuenta de invitado, se puede utilizar para abrir documentos en SharePoint y OneDrive utilizando Office en la web, además de abrir documentos encriptados desde las aplicaciones de escritorio y móviles de Office compatibles.

Sin embargo, la cuenta automática de invitado no se crea inmediatamente en este escenario, debido a la latencia de la replicación. Si especifica direcciones de correo electrónico personales como parte de la configuración de cifrado, se recomienda crear las cuentas de invitado correspondientes en Azure Active Directory. A continuación, comunique a estos usuarios que deben utilizar esta cuenta para abrir un documento cifrado de su organización.

> [!TIP]
> Dado que no puede estar seguro de que los usuarios externos vayan a utilizar una aplicación cliente de Office compatible, compartir enlaces desde SharePoint y OneDrive después de crear cuentas de invitado (para usuarios específicos) o cuando use la [integración de SharePoint y OneDrive con Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) (para cualquier usuario autenticado) es un método más fiable para admitir la colaboración segura con usuarios externos.

## <a name="next-steps"></a>Pasos siguientes

Para ver las configuraciones que puede necesitar para los servicios de infraestructura de red, consulte [Firewalls e infraestructura de red](/azure/information-protection/requirements#firewalls-and-network-infrastructure).

Si usa [etiquetas de confidencialidad](sensitivity-labels.md) para cifrar documentos y correos electrónicos, es posible que le interese [soporte técnico para usuarios externos y contenido etiquetado](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content) para comprender qué configuración de etiquetas se aplica a todos los inquilinos. Para obtener instrucciones de configuración para la configuración de cifrado de etiquetas, consulte [Restricción del acceso al contenido mediante etiquetas de confidencialidad para aplicar el cifrado](encryption-sensitivity-labels.md).

¿Le interesa saber cómo y cuándo se accede al servicio de cifrado? Consulte [Tutorial sobre cómo funciona Azure RMS: Primer uso, protección de contenido y consumo de contenido](/azure/information-protection/how-does-it-work#walkthrough-of-how-azure-rms-works-first-use-content-protection-content-consumption).




