---
title: Transferencia de un dominio de Microsoft a otro host
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
description: 'Busque los pasos que se indican aquí para transferir un dominio de Microsoft a otro registrador. '
ms.openlocfilehash: 18f2b6502268b757b651abe08585cc06b63d7129
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782487"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Transferencia de un dominio de Microsoft a otro host

No puede transferir un dominio de Microsoft 365 a otro registrador durante 60 días después de comprar el dominio de Microsoft.

> [!NOTE]
> Una consulta _whois_ muestra un registrador de dominio comprado por Microsoft como Wild West Domains LLC. Sin embargo, solo se debe ponerse en contacto con Microsoft con respecto a su dominio Microsoft 365 comprado.

Siga estos pasos para obtener un código en Microsoft 365 y, a continuación, vaya al otro sitio web del registrador de dominio para configurar la transferencia del nombre de dominio al nuevo registrador.

## <a name="transfer-a-domain"></a>Transferencia de un dominio

1. En el centro de administración, vaya a **Dominios de Configuración** \> **.**

2. En la página **Dominios**, seleccione el dominio de Microsoft 365 que desea transferir a otro registrador de dominios y, a continuación, seleccione **Comprobar estado**.

3. En la parte superior de la página, seleccione **Transferir dominio**.

4. En la página **Elegir dónde transferir el dominio** , seleccione **Un registrador diferente** y, a continuación, haga clic en **Siguiente**.

5. En la página **Desbloquear transferencia de dominio** , seleccione **Desbloquear transferencia para <_el dominio_>** y, a continuación, seleccione **Siguiente**.

6. Compruebe la información de contacto de transferencia de dominio y, a continuación, seleccione **Siguiente**.

7. Copie el código de autorización y espere unos 30 minutos para que el estado de la transferencia de dominio cambie a **Desbloqueado para la transferencia** en la pestaña **Registro** antes de continuar con los pasos siguientes.

8. Vaya al sitio web del registrador de dominio en el que desea administrar su nombre de dominio en el futuro. Siga las instrucciones para transferir un dominio (busque ayuda en su sitio web). Esto suele significar pagar las tasas de transferencia y dar el código de autenticación al nuevo registrador para que pueda iniciar la transferencia. Microsoft le enviará un correo electrónico para confirmar que hemos recibido la solicitud de transferencia y el dominio se transferirá en un plazo de 5 días.

    Puede encontrar la pestaña **Registro** de código de autorización en la página **Dominios** de Microsoft 365.

    > [!TIP]
    > Los dominios .uk requieren un procedimiento diferente. Póngase en contacto con Soporte técnico de Microsoft y solicite un **cambio de etiqueta IPS** para que coincida con el registrador que desea administrar en el futuro. Una vez que cambia la etiqueta, el dominio se transfiere inmediatamente al nuevo registrador. A continuación, tendrá que trabajar con el nuevo registrador para completar la transferencia, probablemente pagando las tarifas de transferencia y agregando el dominio transferido a su cuenta con su nuevo registrador.

9. Una vez completada la transferencia, renovará el dominio en el nuevo registrador de dominios.

10. Para finalizar el proceso, vuelva a la página **Dominios** del Centro de administración y, a continuación, seleccione **Completar transferencia de dominio**. Esto marcará el dominio como ya no comprado de Microsoft 365 y deshabilitará la suscripción de dominio. No quitará el dominio del inquilino y no afectará a los usuarios y buzones existentes en el dominio.

> [!NOTE]
> Microsoft 365 dominios comprados no son aptos para cambios en el servidor de nombres ni para transferir el dominio entre Microsoft 365 organizaciones. Si se requiere cualquiera de ellos, el registro de dominio debe transferirse a otro registrador.
