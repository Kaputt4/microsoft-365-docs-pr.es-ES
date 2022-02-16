---
title: Agregar el dominio de Google Workspace
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Aprende a mover tu dominio de Google Workspace a Microsoft 365 para empresas.
ms.openlocfilehash: b41fdf304d0f0b9680f87f40a4564573593d6e75
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825671"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Agregar el dominio de Google Workspace a Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Agrega tu dominio de Google Workspace a Microsoft 365 para empresas para que puedas seguir usando tu dirección de correo electrónico empresarial.

## <a name="try-it"></a>¿Se atreve?

1. Vaya al [Centro de administración de Microsoft 365](https://admin.microsoft.com).
1. En la Centro de administración de Microsoft 365, en la navegación izquierda, seleccione **Mostrar todos** >  **los Configuración** >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Dominios**</a>.
1. Elija **Agregar dominio**, escriba su nombre de dominio y seleccione **Usar este dominio**. 
1. Elija, **Agregue un registro TXT a los registros DNS de dominios**, **seleccione Continuar** y copie el valor TXT. 
1. Vuelva a la [Consola de administración de Google](https://admin.google.com), elija **Dominios, Administrar** **dominios,** **Ver** detalles, **Administrar** dominio, **DNS** y, a continuación, desplácese hacia abajo hasta **Registros de recursos personalizados**. 
1. Abra el tipo de registro desplegable, elija **TXT**, pegue el valor TXT que copió y, a continuación, **seleccione Agregar**. 

    Por lo general, la actualización toma un hecho en unos minutos, pero puede tardar hasta 48 horas. 
1. Vuelva al Centro <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">de administración</a>, seleccione **Comprobar** y, a continuación, **Cerrar**. 
1. Para establecer el dominio como el correo electrónico principal de los usuarios, en el panel de navegación izquierdo, seleccione [**UsuariosActivos**](https://go.microsoft.com/fwlink/p/?linkid=834822) > . 
1. Elija un usuario, seleccione **Administrar nombre de usuario y correo** electrónico, **Editar**, seleccione su dominio en la lista desplegable y, a continuación, **seleccione Listo** **y Guardar cambios**. 
1. Repita este proceso para cada usuario. 

    Cuando haya terminado, estará listo para instalar aplicaciones Office y migrar el correo electrónico y los elementos del calendario a Microsoft 365. 