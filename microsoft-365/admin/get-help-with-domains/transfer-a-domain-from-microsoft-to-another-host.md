---
title: Transferir un dominio de Microsoft a otro host
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
ms.openlocfilehash: 192e9c1e14666f80fb670c5c8e268ae54ece0c64
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316777"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Transferir un dominio de Microsoft a otro host

No puede transferir un dominio de Microsoft 365 a otro registrador durante 60 días después de comprar el dominio a Microsoft.

> [!NOTE]
> Una _whoisquery_  muestra un registrador de dominio comprado por Microsoft como Wild West Domains LLC. Sin embargo, solo se debe ponerse en contacto con Microsoft con respecto a su dominio adquirido de Microsoft 365.

Siga estos pasos para obtener un código en Microsoft 365 y, a continuación, vaya al otro sitio web del registrador de dominios para configurar la transferencia del nombre de dominio al nuevo registrador.

## <a name="transfer-a-domain"></a>Transferir un dominio

1. En el Centro de administración, vaya   **aSettingsDomains** > .

2. En la **página Dominios** , seleccione el dominio de Microsoft 365 que desea transferir a otro registrador de dominio y, a continuación, **seleccione Comprobar estado**.

3. En la parte superior de la página, seleccione **Transferir dominio**.

4. En la **página Elegir dónde transferir el** dominio, seleccione **Otro registrador** y, a continuación, haga clic en **Siguiente**.

5. En la **página Desbloquear transferencia de** dominio, seleccione **Desbloquear la transferencia <_el dominio_>** y, a continuación, seleccione **Siguiente**.

6. Compruebe la información de contacto de transferencia de dominio y, a continuación, **seleccione Siguiente**.

7. Copie el código de autorización y espere unos 30 minutos para que el estado de la transferencia de  dominio cambie a Desbloqueado para  su transferencia en la pestaña Registro antes de continuar con los pasos siguientes.

8. Vaya al sitio web del registrador de dominios que desea administrar su nombre de dominio en el futuro. Siga las instrucciones para transferir un dominio (busque ayuda en su sitio web). Esto suele significar pagar las tasas de transferencia y dar el Authcode al nuevo registrador para que pueda iniciar la transferencia. Microsoft le enviará un correo electrónico para confirmar que hemos recibido la solicitud de transferencia y que el dominio se transferirá en un plazo de 5 días.

    Puede encontrar la pestaña Registro del código **de** autorización en la  **página Dominios** de Microsoft 365.
    
    > [!TIP]
    > Los dominios .uk requieren un procedimiento diferente. Póngase en contacto con el soporte técnico de Microsoft y solicite un cambio **de etiqueta IPS** para que coincida con el registrador que desea administrar su dominio en el futuro. Una vez que cambia la etiqueta, el dominio se transfiere inmediatamente al nuevo registrador. A continuación, tendrá que trabajar con el nuevo registrador para completar la transferencia, probablemente pagando las tarifas de transferencia y agregando el dominio transferido a su cuenta con su nuevo registrador.

9. Una vez completada la transferencia, renovará el dominio en el nuevo registrador de dominios.

10. Para finalizar el proceso, vuelva a la página **Dominios** del centro de administración y, a continuación,   **seleccioneCompletar transferencia de dominio**. Esto marcará el dominio como ya no comprado en Microsoft 365 y deshabilitará la suscripción de dominio. No quitará el dominio del inquilino y no afectará a los usuarios y buzones existentes en el dominio.

> [!NOTE]
> Los dominios adquiridos por Microsoft 365 no son aptos para cambios en el servidor de nombres ni para transferir el dominio entre organizaciones de Microsoft 365. Si cualquiera de estos requisitos es necesario, el registro de dominio debe transferirse a otro registrador.
