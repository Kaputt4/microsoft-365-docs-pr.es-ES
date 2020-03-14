---
title: Funcionamiento de los vínculos seguros de Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: La característica de vínculos seguros proporciona la comprobación del tiempo de clic de los hipervínculos en los documentos de Office y en los mensajes de correo electrónico. Lea este artículo para obtener información sobre cómo funciona el vínculo seguro ATP.
ms.openlocfilehash: c87eef2afbb3a694d9906de0c6c43bfeb576782b
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633978"
---
# <a name="how-office-365-atp-safe-links-works"></a>Funcionamiento de los vínculos seguros de Office 365 ATP
> [!IMPORTANT] 
> Para que los vínculos seguros de Office 365 ATP funcionen correctamente, todos los servicios de Office 365 deben estar en la misma versión.
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>Cómo funciona el vínculo seguro ATP con direcciones URL en el correo electrónico

En un nivel alto, aquí se muestra cómo funciona la protección de [vínculos seguros de ATP](atp-safe-links.md) para las direcciones URL en el correo electrónico (hospedado en Office 365, no en local):
  
1. Los usuarios reciben mensajes de correo electrónico, algunos de los cuales contienen direcciones URL.
    
2. Todo el correo electrónico se envía a través de Exchange Online Protection, donde se aplican los filtros de protocolo de Internet (IP) y sobre, protección contra malware basada en firmas, filtros de correo no deseado y antimalware. 
    
3. El correo electrónico llega a las bandejas de entrada de las personas.
    
4. Un usuario inicia sesión en Office 365 y se dirige a su bandeja de entrada de correo electrónico.
    
5. El usuario abre un mensaje de correo electrónico y hace clic en una dirección URL en el mensaje de correo electrónico.
    
6. La característica de vínculos seguros de ATP comprueba inmediatamente la dirección URL antes de abrir el sitio Web. La dirección URL se identifica como bloqueada, malintencionada o segura.
        
   - Si la dirección URL es un sitio web que se incluye en la [lista de direcciones URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-wtih-atp.md)de la organización, se abre una [Página de advertencia](atp-safe-links-warning-pages.md) . 
    
   - Si la dirección URL es un sitio web que se ha determinado que es malintencionado, se abre una [Página de advertencia](atp-safe-links-warning-pages.md) . 
    
   - Si la dirección URL va a un archivo descargable y las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) de la organización están configuradas para analizar dicho contenido, se comprueba el archivo descargable. 
    
   - Si se determina que la dirección URL es segura, se abrirá el sitio Web.
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Cómo funciona el vínculo seguro ATP con direcciones URL en documentos de Office 

En un nivel alto, aquí se muestra cómo funciona la protección de [vínculos seguros de ATP](atp-safe-links.md) para las direcciones URL en Office 365 ProPlus o en las aplicaciones de empresa Premium (versiones actuales de Word, Excel y PowerPoint en Windows, Mac o en un explorador, aplicaciones de Office en dispositivos iOS o Android, Visio en Windows, OneNote en un explorador):
  
1. Los usuarios tienen instalado Office 365 ProPlus o Business Premium en su equipo, smartphone o tableta. (O bien, usan Office en su explorador).
    
2. Un usuario abre una palabra, Excel, PowerPoint, OneNote (en el explorador) o Visio (en el escritorio) e inicia sesión en Office 365 Enterprise con su cuenta profesional o educativa. El documento contiene direcciones URL.
    
3. Cuando el usuario hace clic en una dirección URL del documento, el servicio de vínculos seguros de ATP comprueba el vínculo.
    
   - Si la dirección URL se redirigirá a un sitio web que se incluye en la [lista de direcciones URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-wtih-atp.md)de la organización, se dirigirá al usuario a una [Página de advertencia](atp-safe-links-warning-pages.md).
    
   - Si la dirección URL es un sitio web que se ha determinado que es malintencionado, se le dirigirá a una [Página de advertencia](atp-safe-links-warning-pages.md).
    
   - Si la dirección URL va a un archivo descargable y las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) están configuradas para analizar tales descargas, se comprueba el archivo descargable. 
    
   - Si la dirección URL se considera segura, el usuario se dirigirá al sitio Web.
      
   - Si se produce un error en la comprobación de la dirección URL, la protección de vínculos seguros no se activará. En los clientes de escritorio, el usuario recibirá una advertencia antes de continuar con el sitio.
      
> [!NOTE]
> Puede tardar varios segundos al principio de cada sesión para comprobar que el usuario tiene vínculos seguros ATP para Office habilitados. 
      
