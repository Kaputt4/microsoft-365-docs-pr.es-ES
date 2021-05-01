---
title: Microsoft 365 Empresa Premium seguridad y cumplimiento normativo
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Obtenga información sobre las características de seguridad que se incluyen Microsoft 365 Empresa Premium para ayudar a proteger sus datos en equipos, teléfonos y tabletas.
ms.openlocfilehash: 974204e100d3228f78406aca4acce67a889b08c3
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113474"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Microsoft 365 Empresa Premium seguridad y cumplimiento normativo

Microsoft 365 Empresa Premium ofrece características de seguridad simplificadas para ayudar a proteger los datos en equipos, teléfonos y tabletas.
    
## <a name="microsoft-365-admin-center-security-features"></a>Microsoft 365 de seguridad del Centro de administración

Puedes administrar muchas de las Microsoft 365 Empresa Premium de seguridad en el Centro de administración, lo que te ofrece una forma simplificada de activar o desactivar estas características. En el Centro de administración, puede hacer lo siguiente:
  
- [Establecer la configuración de administración de aplicaciones para dispositivos Android o iOS](app-protection-settings-for-android-and-ios.md) . 
    
    Esta configuración incluye eliminar archivos de un dispositivo inactivo después de un período establecido, cifrar archivos de trabajo, requerir que los usuarios establezcan un PIN, y así sucesivamente.
    
- [Establecer la configuración de protección de aplicaciones para Windows 10 dispositivos](protection-settings-for-windows-10-devices.md) . 
    
    Esta configuración se puede aplicar a los datos de la empresa en dispositivos de propiedad de la empresa o de propiedad personal.
    
- [Establecer la configuración de protección de dispositivos Windows 10 dispositivos](protection-settings-for-windows-10-pcs.md) . 
    
    Puedes habilitar el [cifrado BitLocker](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions) para ayudar a proteger los datos en caso de que se pierda o robe un dispositivo, y habilitar Windows [Exploit Guard](/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) para proporcionar protección avanzada contra ransomware. 
    
- [Eliminar datos de la empresa de dispositivos](remove-company-data.md)
    
    Puedes borrar de forma remota los datos de la compañía si un dispositivo se pierde, se roba o un empleado deja la empresa.
    
- [Restablecer Windows 10 dispositivos a la configuración de fábrica](reset-devices-to-factory-settings.md) . 
    
    Puedes restablecer cualquier dispositivo Windows 10 que tengan aplicada la configuración de protección de dispositivos.
    
## <a name="additional-security-features"></a>Características de seguridad adicionales 

Las características avanzadas de Microsoft 365 Empresa Premium están disponibles para ayudarle a proteger su empresa frente a amenazas cibernéticos y proteger la información confidencial.
  
- **[Microsoft Defender para Office 365](../security/office-365-security/defender-for-office-365.md)**
    
    Microsoft Defender para Office 365 ayuda a proteger su empresa contra ataques sofisticados de suplantación de identidad (phishing) y ransomware diseñados para poner en peligro la información de los empleados o clientes. Entre las características se incluyen:
    
  - Análisis de datos adjuntos sofisticados y análisis basados en inteligencia artificial para detectar y descartar mensajes peligrosos.
    
  - Comprobaciones automáticas de vínculos en el correo electrónico para evaluar si forman parte de un esquema de suplantación de identidad. Esto le mantiene a salvo del acceso a sitios web no seguros.

- **[Las funcionalidades completas de Intune en Azure Portal](/mem/intune/fundamentals/what-is-intune)**
    
    El acceso al Centro de administración de Intune en Azure Portal le permite configurar características de seguridad adicionales, como la administración de dispositivos MacOS, iPhone y dispositivos Android, junto con la administración avanzada de dispositivos para Windows, que no están disponibles Microsoft 365 través de un centro de administración.
- **El [mismo acceso condicional](/azure/active-directory/conditional-access/overview) que Azure AD Premium plan P1**


    El acceso condicional puede ayudar a proteger la organización contra el riesgo de inicio de sesión, los intentos de acceso desde una red o configuración regional inesperadas, los intentos de acceso de tipos de dispositivos riesgosos, y así sucesivamente. Las directivas de acceso condicional se aplican una vez completada la primera autenticación y usan señales del primer evento de autenticación para determinar si el intento de acceso debe aprobarse, denegarse o si se necesita más prueba (como una segunda forma de identificación).

    Las características de acceso condicional incluidas son:

    - Acceso basado en el nombre de usuario, el grupo y el rol
    - Acceso [basado en una aplicación](/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Acceso en función de la ubicación;](/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration)  solo permitir el acceso desde rangos IP de confianza o países específicos 
    - Requerir MFA para obtener acceso
    - Bloquear el acceso a aplicaciones que usan [autenticación heredada](/azure/active-directory/conditional-access/block-legacy-authentication)
    - Requerir que las aplicaciones usen [la protección de aplicaciones de Intune](/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Autenticación personalizada como MFA con proveedores de terceros, por ejemplo DUO.
   
    Otras características:
    - [Restablecimiento de contraseñas de autoservicio](/azure/active-directory/authentication/concept-sspr-customization) para Azure AD híbrido
    
## <a name="compliance-features"></a>Características de cumplimiento

Su Microsoft 365 Empresa Premium incluye características que le ayudan a mantener los estándares normativos y de cumplimiento normativo.

- **[Obtenga información sobre la prevención de pérdida de datos](../compliance/dlp-learn-about-dlp.md))** (DLP). 
    
    Puede configurar DLP para detectar automáticamente información confidencial, como números de tarjeta de crédito, números de seguridad social, entre otros, para evitar que compartan de forma involuntaria fuera de su empresa.
    
- **[Archivado de Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Archivado de Exchange Online licencia permite que los mensajes se archiven fácilmente con copias de seguridad de datos continuas. Almacena todos los correos electrónicos de un usuario, incluidos los elementos eliminados, en caso de que se necesiten más adelante para su detección o restauración. Además, puede usar diferentes directivas de retención para conservar los datos de correo electrónico para retención por juicio, exhibición de documentos electrónicos o para cumplir los requisitos de cumplimiento.
    
- **[Etiquetas de confidencialidad](../compliance/sensitivity-labels.md)**

   Microsoft 365 Empresa Premium incluye todas las características del [Plan 1](https://go.microsoft.com/fwlink/p/?linkid=871407)de Azure Information Protection . Con este plan,  puede crear etiquetas de confidencialidad que le permitan controlar el acceso a información confidencial en el correo electrónico y documentos, con controles como "No reenviar" y "No copiar". También puede clasificar la información confidencial como "Confidencial" y especificar cómo se puede compartir información clasificada fuera y dentro de la empresa. Enterprise cifrado de categoría superior es fácil de aplicar al correo electrónico y a los documentos para mantener la información privada. También puede instalar el complemento cliente de Azure Information Protection para Office aplicaciones. Para obtener más información, vea [Cliente de etiquetado unificado de Azure Information Protection](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history). Para etiquetas de confidencialidad, **instale elAzInfoProtection_UL.exe**.

Puedes administrar estas características en el Centro de seguridad &amp; y el Centro de administración de Intune. Con el tiempo, los controles simplificados se agregarán al centro Microsoft 365 administración.
  
    
## <a name="faq"></a>Preguntas más frecuentes

 ### <a name="are-these-security-features-available-in-all-markets"></a>¿Están disponibles estas características de seguridad en todos los mercados?
  
Sí, estas características están disponibles en todos los mercados donde Microsoft 365 Empresa Premium se vende.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>¿Cómo puedo encontrar el Centro de &amp; cumplimiento de seguridad?
  
1. [Inicie sesión en Microsoft 365 Empresa Premium](https://portal.microsoft.com/) con sus credenciales de administrador. 
    
2. En la navegación izquierda, busque **Centros de administración** y expándalo. 
    
    ![En el panel de navegación izquierdo del centro Microsoft 365 administración, elija Centros de administración.](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Elija **Cumplimiento &amp; de seguridad** para ir al Centro de cumplimiento de &amp; seguridad.
