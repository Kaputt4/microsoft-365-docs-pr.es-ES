---
title: Transferir un dominio de Microsoft a otro host
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Busque los pasos aquí para transferir un dominio de Microsoft a otro registrador. '
ms.openlocfilehash: f34e9733ab53c8bdc6f4432c96e6232ecc26ee06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126352"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Transferir un dominio de Microsoft a otro host

No puede transferir un dominio de Microsoft 365 a otro registrador durante 60 días después de comprar el dominio a Microsoft.

> [!NOTE]
> Una _consulta Whois_ muestra un registrador de dominios   comprado por Microsoft como Wild West Domains LLC. Sin embargo, solo microsoft debe ponerse en contacto con respecto a su dominio comprado de Microsoft 365.

Siga estos pasos para obtener un código en Microsoft 365 y, a continuación, vaya al otro sitio web del registrador de dominios para configurar la transferencia de su nombre de dominio al nuevo registrador.

## <a name="transfer-a-domain"></a>Transferir un dominio

1. En el centro de administración, vaya a   **Dominios**   >  **de configuración.**

2. En la **página Dominios,** seleccione el dominio de Microsoft 365 que desea transferir a otro registrador de dominios y, a continuación, **seleccione Comprobar estado.**

3. En la parte superior de la página, seleccione **Transferir dominio.**

4. En la **página Elegir dónde transferir el** dominio, seleccione Otro **registrador** y, a continuación, haga clic en **Siguiente.**

5. En la **página Desbloquear transferencia de** dominio, seleccione Desbloquear transferencia <**_su_ >** dominio y, a continuación, **seleccione Siguiente**.

6. Compruebe la información de contacto de transferencia de dominio y, a continuación, **seleccione Siguiente**.

7. Copie el código de autorización y espere unos 30  minutos para que  el estado de la transferencia de dominio cambie a Desbloqueado para su transferencia en la pestaña Registro antes de continuar con los pasos siguientes.

8. Vaya al sitio web del registrador de dominios que desea administrar en el futuro. Siga las instrucciones para transferir un dominio (busque ayuda en su sitio web). Esto suele significar pagar las tarifas de transferencia y dar el código de autenticación al nuevo registrador para que pueda iniciar la transferencia. Microsoft le enviará un correo electrónico para confirmar que hemos recibido la solicitud de transferencia y el dominio se transferirá en un plazo de 5 días.

    Puede encontrar la pestaña Registro del **código** de autorización en la  **página Dominios** de Microsoft 365.
    
    > [!TIP]
    > Los dominios .uk requieren un procedimiento diferente. Póngase en contacto con el soporte técnico de Microsoft y solicite un cambio de etiqueta **IPS** para que coincida con el registrador que desea administrar su dominio en el futuro. Una vez que la etiqueta cambia, el dominio se transfiere inmediatamente al nuevo registrador. A continuación, tendrá que trabajar con el nuevo registrador para completar la transferencia, probablemente pagando las tarifas de transferencia y agregando el dominio transferido a su cuenta con su nuevo registrador.

9. Una vez completada la transferencia, renovará el dominio en el nuevo registrador de dominios.

10. Para finalizar el proceso, vuelva a la página **Dominios** en el centro de administración y, a continuación, seleccione   **Completar transferencia de dominio.** Esto marcará el dominio como ya no comprado a Microsoft 365 y deshabilitará la suscripción de dominio. No quitará el dominio del inquilino y no afectará a los usuarios y buzones existentes del dominio.

> [!NOTE]
> Los dominios comprados de Microsoft 365 no son aptos para los cambios del servidor de nombres ni para transferir el dominio entre organizaciones de Microsoft 365. Si se requiere alguna de estas opciones, el registro de dominio debe transferirse a otro registrador.
