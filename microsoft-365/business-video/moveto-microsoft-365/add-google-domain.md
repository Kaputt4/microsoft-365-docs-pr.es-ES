---
title: Agregar el dominio de Google Workspace
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo mover su dominio de Google Workspace a Microsoft 365 para empresas.
ms.openlocfilehash: 1abc05867147d2b52e26804918e8247053b5e1d5
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794748"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Agregar el dominio de Google Workspace a Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Agregue su dominio de Google Workspace a Microsoft 365 para empresas para que pueda seguir usando su dirección de correo electrónico empresarial.

## <a name="try-it"></a>¿Se atreve?

1. Vaya al Centro [de administración de Microsoft 365.](https://admin.microsoft.com)
1. En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, seleccione **Mostrar todo** **,** Configuración y, a continuación, **Dominios.**
1. Elija **Agregar dominio,** escriba su nombre de dominio y, a continuación, **seleccione Usar este dominio.** 
1. Elija, **agregue un registro TXT a los registros DNS** de dominios, seleccione **Continuar** y copie el valor TXT. 
1. Vuelva a la Consola de administración de [Google,](https://admin.google.com)elija Dominios **,** Administrar dominios **,** Ver **detalles,** **Administrar** dominio , **DNS** y, a continuación, desplácese hacia abajo hasta Registros **de recursos personalizados.** 
1. Abra la lista desplegable del tipo de registro, elija **TXT**, pegue el valor TXT que copió y, a continuación, **seleccione Agregar**. 

    La actualización normalmente toma un hecho en unos minutos, pero puede tardar hasta 48 horas. 
1. Vuelva al Centro de administración de Microsoft 365, seleccione **Comprobar** y, a continuación, **cierre**. 
1. Para establecer el dominio como el correo electrónico principal para los usuarios, en el panel de navegación izquierdo, seleccione **Usuarios**  >  **activos.** 
1. Elija un usuario, seleccione Administrar nombre de usuario y correo **electrónico,** Editar **,** seleccione su dominio en la lista desplegable y, a continuación, seleccione **Listo** y **Guardar cambios.** 
1. Repita este proceso para cada usuario. 

    Cuando haya terminado, estará listo para instalar aplicaciones de Office y migrar el correo electrónico y los elementos de calendario a Microsoft 365. 