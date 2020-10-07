---
title: Transferir un dominio de Microsoft a otro host
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Busque aquí los pasos para transferir un dominio de Microsoft a otro registrador. '
ms.openlocfilehash: d960b57a2c82b804d61ead1c672c00f0543b3ae8
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370329"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Transferir un dominio de Microsoft a otro host

No puede transferir un dominio de Microsoft 365 a otro registrador durante 60 días después de comprar el dominio de Microsoft.

> [!NOTE]
> Una consulta _Whois_   muestra un registrador de dominios comprado por Microsoft como dominios silvestres de Westn LLC. Sin embargo, solo se debe poner en contacto con Microsoft en relación con el dominio adquirido de Microsoft 365.

Siga estos pasos para obtener un código en Microsoft 365 y, a continuación, vaya al otro sitio web del registrador de dominios para configurar la transferencia de su nombre de dominio al nuevo registrador.

## <a name="transfer-a-domain"></a>Transferir un dominio

1. En el centro de administración, vaya a  **configuración**de   >  **dominios**.

2. En la página **dominios** , seleccione el dominio 365 de Microsoft que desea transferir a otro registrador de dominios y, a continuación, seleccione **comprobar estado**.

3. En la parte superior de la página, seleccione **transferir dominio**.

4. En la página **Elija dónde desea transferir su dominio** , seleccione **un registrador diferente**y, a continuación, haga clic en **siguiente**.

5. En la página **desbloquear la transferencia del dominio** , seleccione **desbloquear transferencia para <_su dominio_ > **y, a continuación, seleccione **siguiente**.

6. Compruebe la información de contacto de transferencia de dominio y, a continuación, seleccione **siguiente**.

7. Copie el código de autorización y espere unos 30 minutos hasta que el estado de transferencia del dominio cambie a **desbloqueado para transferencia** en la ficha **registro** antes de continuar con los pasos siguientes.

8. Vaya al sitio web del registrador de dominios en el que desea administrar el nombre de dominio que se va a enviar. Siga las instrucciones para transferir un dominio (busque ayuda en su sitio web). Normalmente, esto significa pagar cuotas de transferencia y conceder el AuthCode al nuevo registrador para que puedan iniciar la transferencia. Microsoft le enviará un correo electrónico para confirmar que hemos recibido la solicitud de transferencia y que el dominio se transferirá en un plazo de 5 días.

    Puede encontrar la ficha **registro** de código de autorización en la página  **dominios** de Microsoft 365.
    
    > [!TIP]
    > los dominios de. uk requieren un procedimiento diferente. Póngase en contacto con el soporte técnico de Microsoft y solicite un **cambio de etiqueta IPS** para que se ajuste al registrador que desea para administrar su dominio en adelante. Una vez que la etiqueta cambia, el dominio se transfiere inmediatamente al nuevo registrador. A continuación, tendrá que trabajar con el nuevo registrador para completar la transferencia, probablemente pagaremos cuotas de transferencia y agregar el dominio transferido a su cuenta con su nuevo registrador.

9. Una vez completada la transferencia, renovará su dominio en el nuevo registrador de dominios.

10. Para finalizar el proceso, vuelva a la página **dominios** en el centro de administración y, a continuación, seleccione  **transferencia de dominio completa**. Esto marcará el dominio como ya no comprado de Microsoft 365 y deshabilitará la suscripción de dominio. No se quitará el dominio del espacio empresarial y no afectará a los usuarios y buzones existentes en el dominio.

> [!NOTE]
> Los dominios adquiridos de Microsoft 365 no son válidos para los cambios de nameserver o para transferir el dominio entre las organizaciones de Microsoft 365. Si alguno de ellos es necesario, el registro de dominio debe transferirse a otro registrador.
