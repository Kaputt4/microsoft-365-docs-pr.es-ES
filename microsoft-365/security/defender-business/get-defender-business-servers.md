---
title: Obtener servidores Microsoft Defender para Empresas
description: Obtenga información sobre cómo obtener Microsoft Defender para Empresas servidores, actualmente en versión preliminar.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: none
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security-compliance
ms.openlocfilehash: 416fe2501b6e3a30f3384d443327d801002e7284
ms.sourcegitcommit: 511d15831b97d02e5a0f5e11834ad52617abd0f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67600452"
---
# <a name="how-to-get-microsoft-defender-for-business-servers-preview"></a>Obtención de servidores Microsoft Defender para Empresas (versión preliminar)

Microsoft Defender para Empresas servidores (versión preliminar) permite incorporar un dispositivo que ejecuta Windows Server o Linux Server a Defender para empresas o Microsoft 365 Empresa Premium. Cuando la licencia de Microsoft Defender para Empresas servidores esté disponible con carácter general, necesitará una licencia para cada instancia de servidor.

A continuación se muestra cómo obtener servidores de Microsoft Defender para Empresas (versión preliminar):

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. 

2. Active la configuración de vista previa. 

   1. En el panel de navegación, seleccione **Configuración** \> **Puntos de conexión Características avanzadas** \> **Características** \> **en versión preliminar.** 
   2. Active la configuración **y, a** continuación, seleccione **Guardar preferencias**.

3. Active el ámbito de cumplimiento para Windows Server. 

   1. Vaya a **Configuración** \> Ámbito de **administración de** \> configuración de **puntos** \> de conexión **.** 
   2. Seleccione **Usar MDE para aplicar la configuración de seguridad desde MEM**, seleccione  **Windows Server** y, luego, **Guardar**.

4. Siga las instrucciones de Windows Server y Linux Server en [Incorporación de dispositivos para Microsoft Defender para Empresas](mdb-onboard-devices.md).

> [!IMPORTANT]
> Microsoft Defender para Empresas servidores está actualmente en versión preliminar. Cuando esté disponible con carácter general (GA), se ofrecerá como complemento para Microsoft 365 Empresa Premium y la versión independiente de Defender para empresas. En disponibilidad general, los servidores de Microsoft Defender para Empresas tendrán un precio de 3 USD por instancia de servidor.

## <a name="see-also"></a>Vea también

- [Consulte el cuaderno de estrategias de prueba: Microsoft Defender para Empresas](trial-playbook-defender-business.md).
- [Use el asistente de instalación en Microsoft Defender para Empresas](mdb-use-wizard.md).
- [Consulte el proceso de configuración y configuración de Defender para empresas](mdb-setup-configuration.md).
- [Vea cómo obtener ayuda y soporte técnico para Defender para empresas](mdb-get-help.md) (por si necesita ayuda).