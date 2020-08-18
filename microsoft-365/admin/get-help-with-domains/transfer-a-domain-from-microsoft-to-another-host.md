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
ms.openlocfilehash: 7e00f5ae2c36a06803a3f7a8acd825dcab90805c
ms.sourcegitcommit: 6fb2a1c404ea3c3573b0f7803bf17459a9387891
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788991"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Transferir un dominio de Microsoft a otro host

No puede transferir un dominio de Microsoft 365 a otro registrador durante 60 días después de comprar el dominio de Microsoft.

> [!NOTE]
> Una consulta _Whois_   muestra un registrador de dominios comprado por Microsoft como dominios silvestres de Westn LLC. Sin embargo, solo se debe poner en contacto con Microsoft en relación con el dominio adquirido de Microsoft 365.

Siga estos pasos para obtener un código en Microsoft 365 y, a continuación, vaya al otro sitio web del registrador de dominios para configurar la transferencia de su nombre de dominio al nuevo registrador.

## <a name="transfer-a-domain"></a>Transferir un dominio

1. En el centro de administración, vaya a  **configuración**de   >  **dominios**.

2. <en la página **dominios** , seleccione el dominio 365 de Microsoft que desea transferir a otro registrador de dominios y, a continuación, seleccione **comprobar estado**.

3. En la parte superior de la página, seleccione **transferir dominio**.

4. En la página **Elija dónde desea transferir su dominio** , seleccione **un registrador diferente**y, a continuación, haga clic en **siguiente**.

5. En la página **desbloquear la transferencia del dominio** , seleccione **desbloquear transferencia para <_su dominio_ > **y, a continuación, seleccione **siguiente**.

6. Compruebe la información de contacto de transferencia de dominio y, a continuación, seleccione **siguiente**.

7. Copie el código de autorización y espere unos 30 minutos hasta que el estado de transferencia del dominio cambie a **desbloqueado para transferencia** en la ficha **registro** antes de continuar con los pasos siguientes.

8. Vaya al sitio web del registrador de dominios en el que desea administrar el nombre de dominio que se va a enviar. Siga las instrucciones para transferir un dominio (busque ayuda en su sitio web).

Puede encontrar la ficha **registro** de código de autorización en la página  **dominios** de Microsoft 365.

9. Una vez completada la transferencia, renovará su dominio en el nuevo registrador de dominios.

10. Para finalizar el proceso, vuelva a la página **dominios** en el centro de administración y, a continuación, seleccione  **transferencia de dominio completa**.

> [!NOTE]
> Los dominios adquiridos de Microsoft 365 no son válidos para los cambios de nameserver o para transferir el dominio entre las organizaciones de Microsoft 365. Si alguno de ellos es necesario, el registro de dominio debe transferirse a otro registrador.
