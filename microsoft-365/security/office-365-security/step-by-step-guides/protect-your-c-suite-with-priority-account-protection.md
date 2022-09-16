---
title: Protección de c-suite con la protección de la cuenta prioritaria en Microsoft Defender para Office 365 Plan 2
description: Los pasos para proteger el conjunto de c con la protección de cuenta prioritaria. El etiquetado de una cuenta como una cuenta de prioridad habilitará la protección adicional optimizada para los patrones de flujo de correo dirigidos a ejecutivos de la empresa, junto con visibilidad adicional en informes, alertas e investigaciones.
search.product: ''
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: dbab9bd017bbd09f59d1a03efa49bf35a09361df
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67740893"
---
# <a name="protect-your-c-suite-with-priority-account-protection"></a>Proteja su c-suite con la protección de cuentas prioritaria

La protección de cuentas prioritaria ayuda a los equipos de TI y seguridad a garantizar una alta calidad de servicio y protección para las personas críticas de su organización. El etiquetado de una cuenta como una cuenta de prioridad habilitará la protección adicional optimizada para los patrones de flujo de correo dirigidos a ejecutivos de la empresa, junto con visibilidad adicional en informes, alertas e investigaciones.

## <a name="what-youll-need"></a>Lo que necesitará
- Microsoft Defender para Office 365 Plan 2 (incluido como parte de los planes E5)
- Permisos suficientes (rol administrador de seguridad)
- 5 minutos para realizar los pasos siguientes.

## <a name="tag-priority-users"></a>Usuarios con prioridad de etiquetas
1. Identifique los usuarios, grupos o dominios que desea etiquetar como cuentas de prioridad.
1. Inicie sesión en el [Portal de seguridad de Microsoft](https://security.microsoft.com/) y vaya a Configuración en la barra de navegación izquierda.
1. Seleccione Email & colaboración en la página que se carga y, a continuación, haga clic en Etiquetas de usuario.
1. En la página Etiquetas de usuario, seleccione la etiqueta Cuenta de prioridad y presione Editar etiqueta.
1. En el control flotante que aparece, seleccione Agregar miembros.
1. Busque los usuarios que desea etiquetar, seleccione uno o varios usuarios y presione Agregar.
1. Revise los miembros que ha seleccionado y presione Siguiente.
1. Presione Enviar para confirmar los cambios.

Para obtener información sobre las etiquetas de cuenta de prioridad, consulte [Administración y supervisión de cuentas de prioridad: administración de Microsoft 365 | Microsoft Docs](../../../admin/setup/priority-accounts.md).

## <a name="next-steps"></a>Pasos siguientes
[Revise la protección diferenciada para los usuarios etiquetados como cuentas de prioridad](../../office-365-security/configure-review-priority-account.md).

## <a name="powershell-configuration"></a>Configuración de PowerShell
Si desea realizar estos pasos a través de [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), puede hacerlo mediante los siguientes cmdlets:
1. Ver una lista de cuentas prioritarias: **Get-User -IsVIP | seleccionar Identidad**
1. Agregar usuario a la lista de cuentas de prioridad: **Set-User -VIP:$true -Identity \<Identity\>**
1. Quitar usuario de la lista de cuentas de prioridad: **Set-User -VIP:$false -Identity \<Identity\>**
