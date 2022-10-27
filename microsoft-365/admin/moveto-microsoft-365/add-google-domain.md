---
title: Adición del dominio de Google Workspace
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- adminvideo
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo mover el dominio de Google Workspace a Microsoft 365 para empresas.
ms.openlocfilehash: 3ffd496a1a0d02362515bf6c83cb1f1ca9f2e00b
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68728519"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Agregue su dominio de Google Workspace a Microsoft 365

Consulte [ayuda de Microsoft 365 para pequeñas empresas](https://go.microsoft.com/fwlink/?linkid=2197659) en YouTube.

## <a name="watch-add-google-workspace-domain"></a>Inspección: Adición de un dominio de Área de trabajo de Google

Consulte este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198105).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Agregue el dominio de Google Workspace a Microsoft 365 para empresas para que pueda seguir usando su dirección de correo electrónico empresarial.

1. Ve al [Centro de administración de Microsoft 365](https://admin.microsoft.com).
1. En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, seleccione **Mostrar todos los** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**dominios**</a> **de configuración** > .
1. Elija **Agregar dominio**, escriba el nombre de dominio y seleccione **Usar este dominio**. 
1. Elija **Agregar un registro TXT a los registros DNS de dominios**, seleccione **Continuar** y copie el valor TXT. 
1. Volver a la [consola de Google Administración](https://admin.google.com), elija **Dominios**, **Administrar dominios**, **Ver detalles**, **Administrar dominio**, **DNS** y, a continuación, desplácese hacia abajo hasta **Registros de recursos personalizados**. 
1. Abra la lista desplegable tipo de registro, elija **TXT**, pegue el valor TXT que copió y seleccione **Agregar**. 

    La actualización suele tardar un hecho en unos minutos, pero puede tardar hasta 48 horas. 
1. Vuelva al <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración</a>, seleccione **Comprobar** y, a continuación, **Cerrar**. 
1. Para establecer el dominio como el correo electrónico principal para los usuarios, en el panel de navegación izquierdo, seleccione **Usuarios** > [**usuarios activos**](https://go.microsoft.com/fwlink/p/?linkid=834822). 
1. Elija un usuario, seleccione **Administrar nombre de usuario y correo electrónico**, **Editar**, seleccione su dominio en la lista desplegable y, a continuación, seleccione **Listo** y **Guardar cambios**. 
1. Repita este proceso para cada usuario. 

    Cuando haya terminado, estará listo para instalar aplicaciones de Office y migrar los elementos de correo electrónico y calendario a Microsoft 365. 