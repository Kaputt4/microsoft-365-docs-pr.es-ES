---
title: Características de seguridad y cumplimiento de Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Obtenga información sobre las características de seguridad incluidas en Microsoft 365 Business.
ms.openlocfilehash: bd61ad3bf1b34635a7b80f1c9ccf63fa98d31915
ms.sourcegitcommit: 274af83139ad7da3aa33366c3323d533d95c7db4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2019
ms.locfileid: "35017530"
---
# <a name="microsoft-365-business-security-and-compliance-features"></a>Características de seguridad y cumplimiento de Microsoft 365 Business

Microsoft 365 Business ofrece características de seguridad simplificadas para ayudarle a proteger sus datos en equipos, teléfonos y tabletas.
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Características de seguridad del centro de administración de Microsoft 365 Business

![Pancarta que apunta a https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

Puede administrar muchas de las características de seguridad empresarial de Microsoft 365 en el centro de administración, lo que le proporciona una forma simplificada de activar o desactivar estas características. En el centro de administración, puede hacer lo siguiente:
  
  
- [Establezca la configuración de administración de aplicaciones para dispositivos Android o iOS](app-protection-settings-for-android-and-ios.md) . 
    
    Estas configuraciones incluyen la eliminación de archivos de un dispositivo inactivo después de un período de tiempo determinado, el cifrado de archivos de trabajo, lo que requiere que los usuarios establezcan un PIN, etc.
    
- [Establezca la configuración de protección de aplicaciones para dispositivos con Windows 10](protection-settings-for-windows-10-devices.md) . 
    
    Esta configuración se puede aplicar a los datos de la empresa en dispositivos de propiedad de la empresa o de propiedad personal.
    
- [Establezca la configuración de protección de dispositivos para dispositivos con Windows 10](protection-settings-for-windows-10-pcs.md) . 
    
    Puede habilitar el cifrado de [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) para ayudar a proteger los datos en caso de pérdida o robo de un dispositivo, y habilitar la protección contra [ataques de Windows](https://go.microsoft.com/fwlink/p/?linkid=871404) para proporcionar protección avanzada contra ransomware. 
    
- [Eliminar datos de la empresa de dispositivos](remove-company-data.md)
    
    Puede borrar datos de la empresa de forma remota si un dispositivo se pierde, si es robado o si un empleado abandona la compañía.
    
- [Restablece los dispositivos con Windows 10 a su configuración de fábrica](reset-devices-to-factory-settings.md) . 
    
    Puede restablecer cualquier dispositivo de Windows 10 que tenga aplicada la configuración de protección de dispositivos.
    
## <a name="additional-security-features"></a>Características de seguridad adicionales 

Hay disponibles características avanzadas de Microsoft 365 Business para ayudarle a proteger su negocio de las amenazas cibernéticos y salvaguardar la información confidencial.
  
- **[Protección contra amenazas avanzada de Office 365](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    La protección contra amenazas avanzada (ATP) ayuda a proteger su empresa contra ataques de suplantación de identidad y ataque de ransomware sofisticados, diseñados para comprometer la información de empleados o clientes Entre las características se incluyen:
    
  - Análisis sofisticado de archivos adjuntos y análisis con tecnología de AI para detectar y descartar mensajes peligrosos.
    
  - Comprobaciones automáticas de los vínculos del correo electrónico para evaluar si forman parte de un esquema de suplantación de identidad. Esto le impide tener acceso a sitios web no seguros.

- **[Todas las capacidades de Intune en Azure portal](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    El acceso al centro de administración de Intune en Azure portal le permite configurar características de seguridad adicionales, como la administración de dispositivos de MacOS, dispositivos iPhone y Android junto con la administración avanzada de dispositivos para Windows, que no están disponibles a través de Microsoft 365 centro de administración empresarial.
- **Mismo [acceso condicional](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/overview) que el plan de Azure ad P1**

    El acceso condicional puede ayudar a proteger su organización del riesgo de inicio de sesión, a los intentos de acceso desde una red o configuración regional inesperada, a que los intentos de acceso forman tipos de dispositivos peligrosos y así sucesivamente. Las directivas de acceso condicional se aplican una vez completada la primera autenticación y se usan señales del primer evento de autenticación para determinar si el intento de acceso debe ser aprobado, denegado o f (como una segunda forma de identificación) Obligatorio.

    Las características de acceso condicional incluidas son:

    - Acceso basado en nombre de usuario, grupo y rol
    - Acceso [basado en una aplicación](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Acceso basado en la ubicación](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration);  permitir el acceso solo desde rangos IP de confianza o países específicos 
    - Requerir MFA para el acceso
    - Bloquear el acceso a las aplicaciones que usan la [autenticación heredada](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)
    - Requerir TP de aplicaciones-usar [protección de aplicaciones](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access) de Intune
    - Autenticación personalizada como MFA con proveedores de terceros, por ejemplo, DUO.
   
    Otras características:
    - [Restablecimiento de contraseña](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization) de autoservicio para Azure ad híbrido
    
## <a name="compliance-features"></a>Características de cumplimiento

Su suscripción de Microsoft 365 Business incluye características que le ayudarán a mantener los estándares de cumplimiento normativo.

- **[Introducción a las directivas de prevención de pérdida de datos](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    Puede configurar DLP para que detecte automáticamente información confidencial, como números de tarjetas de crédito, números de la seguridad social, etc., para evitar que se comparta involuntariamente fuera de la compañía.
    
- **[Archivado de Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    La licencia de archivado de Exchange Online permite archivar fácilmente los mensajes con una copia de seguridad de datos continua. Almacena todos los correos electrónicos de un usuario, incluidos los elementos eliminados, en caso de que se necesiten más adelante para su detección o restauración. Además, puede usar directivas de retención diferentes para conservar los datos de correo electrónico para retenciones por juicio, eDiscovery o para cumplir con los requisitos de cumplimiento.
    
- **[Azure Information Protection](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    La protección de la información le ayuda a controlar el acceso a la información confidencial en correos electrónicos y documentos con controles como "no reenviar" y "no copiar". También puede clasificar la información confidencial como "confidencial" y especificar cómo se puede compartir la información clasificada fuera y dentro de la empresa. El cifrado de nivel empresarial es fácil de aplicar en el correo electrónico y los documentos para mantener la privacidad de la información. Microsoft 365 Business incluye todas las características del [plan 1 de Azure Information Protection](https://go.microsoft.com/fwlink/p/?linkid=871407). También puede instalar el complemento cliente de Azure Information Protection para aplicaciones de Office. Para obtener más información, consulte la [Guía del administrador del cliente de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide).

Puede administrar estas características en el centro de &amp; seguridad y cumplimiento y en el centro de administración de Intune. Con el tiempo, los controles simplificados se agregarán al centro de administración de Microsoft 365 Business.
  
    
## <a name="faq"></a>Preguntas frecuentes

 ### <a name="are-these-security-features-available-in-all-markets"></a>¿Estas características de seguridad están disponibles en todos los mercados?
  
Sí, estas características están disponibles en todos los mercados en los que se vende Microsoft 365 Business.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>¿Cómo encuentro el centro de &amp; seguridad y cumplimiento?
  
1. [Inicie sesión en Microsoft 365 Business](https://portal.microsoft.com/) mediante sus credenciales de administrador. 
    
2. En el panel de navegación izquierdo, busque **centros de administración** y expándalo. 
    
    ![En el panel de navegación izquierdo del centro de administración de Microsoft 365, elija centros de administración.](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Elija **cumplimiento &amp; de seguridad** para ir al &amp; centro de seguridad y cumplimiento.