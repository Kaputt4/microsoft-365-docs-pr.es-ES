---
title: Evite usar caracteres no válidos en las reglas de filtro de correo no deseado y directiva de filtro de correo no deseado
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/24/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Proporciona ayuda a los administradores que tienen caracteres no válidos en la configuración contra correo no deseado y tienen problemas al intentar usar el centro &amp; de seguridad y cumplimiento.
ms.openlocfilehash: 5e6fa97a3f325b6fc6fdc449ba4a61282f67b644
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866722"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>Evitar caracteres no válidos en las reglas de filtro de correo no deseado y Directiva de filtro de correo no deseado 

Anteriormente, los administradores de Office 365 instalaron y configuraron reglas de filtro de correo no deseado y la Directiva de filtro de correo no deseado mediante el centro de administración de Exchange (EAC). Ahora, puede usar el centro &amp; de seguridad y cumplimiento para administrar la configuración contra correo no deseado. Los siguientes caracteres se admitiron en el EAC, pero no se admiten para su &amp; uso en el centro de seguridad y cumplimiento.  

**Caracteres no válidos:**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

Si las reglas de filtro de correo no deseado o la Directiva de filtro de correo no deseado contienen alguno de los caracteres no válidos, puede encontrarse alguno o todos estos problemas:
- Es posible que no pueda encontrar la Directiva o las reglas en el &amp; centro de seguridad y cumplimiento.
- Es posible que reciba errores al intentar obtener las reglas o la Directiva mediante Windows PowerShell.
- Es posible que la Directiva o la configuración no se ejecuten o no funcionen de la manera esperada.

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>Quitar los caracteres no válidos de la Directiva y reglas del filtro de correo no deseado

Una vez que haya identificado la Directiva y las reglas que contienen caracteres no válidos, puede cambiar los nombres con los cmdlets de Windows PowerShell. 

1. [Conéctese a Exchange online mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).
    
2. Para cambiar el nombre de la Directiva de filtro de correo no deseado, ejecute el cmdlet Set-HostedContentFilterPolicy de la siguiente manera:
    
    ```powershell
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. Para cambiar el nombre de una regla de filtro de correo no deseado, ejecute el cmdlet Set-HostedContentFilterRule de la siguiente manera:
    
    ```powershell
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>Más información

[Administración de amenazas en el &amp; centro de seguridad y cumplimiento](protect-against-threats.md)
  
[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)

[Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule)
