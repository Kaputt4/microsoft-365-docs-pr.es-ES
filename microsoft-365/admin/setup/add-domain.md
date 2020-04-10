---
title: Agregar un dominio a Office 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Agregue su dominio a Office 365 en el centro de administración de Microsoft 365 agregando un registro DNS en su host DNS. El Asistente para la instalación le guiará por el proceso.
ms.openlocfilehash: 746163b83190a73326ad589b8e3bc9377ddaa9b4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43209645"
---
# <a name="add-a-domain-to-office-365"></a>Agregar un dominio a Office 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](domains-faq.md)** si no encuentra lo que busca. 
  
 *Para agregar, modificar o quitar dominios, **debe** ser **administrador global** de un [plan empresarial o](https://products.office.com/business/office)empresarial. Estos cambios afectan a todo el espacio empresarial, los *administradores personalizados* o *los usuarios normales* no podrán realizar estos cambios.*  

 Siga estos pasos para agregar, configurar o seguir configurando un dominio. 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end
::: moniker range="o365-germany"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end
    
2. Vaya a la página de **configuración** > de**dominios** . 

3. Seleccione **Agregar dominio**.
    
4. Escriba el nombre del dominio que desea agregar y, a continuación, seleccione **siguiente**.
    
5. Elija cómo desea comprobar que es el propietario del dominio.
    
    1. Si su dominio está registrado en Godaddy o 1&amp;1, seleccione **iniciar sesión en** > el**siguiente** y Office 365 [configurará los registros automáticamente](../get-help-with-domains/domain-connect.md).
    
    2. Puede hacer que le envíen un correo electrónico al contacto registrado para el dominio con un código de comprobación. Si no reconoce o tiene acceso al correo electrónico en el registro, puede usar la tercera opción.
    
    3. Puede usar un registro TXT para comprobar su dominio. Seleccione esta y seleccione **siguiente** para ver instrucciones sobre cómo agregar este registro DNS al sitio web de su registrador. Esto puede tardar hasta 30 minutos en comprobarse después de agregar el registro. 
    
6. Elija cómo desea realizar los cambios de DNS necesarios para que Office use su dominio.
    
    1. Elija **Agregar los registros DNS para mí** si desea que Office configure el DNS de forma automática. 
    
  
    2. Elija **voy a agregar los registros DNS yo mismo** si solo quiere adjuntar servicios específicos de Office 365 a su dominio o si desea omitir este por ahora y hacerlo más adelante. **Elija esta opción si sabe exactamente lo que hace.**
    
7. Si eligió *Agregar los registros DNS* , seleccione **siguiente** y verá una página con todos los registros que necesita agregar al sitio web de sus registradores para configurar el dominio. 
    
  
  
    Si el portal no reconoce el registrador, puede [seguir estas instrucciones generales.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Consulte nuestra lista de [instrucciones específicas del host](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) para buscar su host y siga los pasos para agregar todos los registros que necesite. 
    
    Si no conoce el proveedor de host DNS o el registrador de dominios de su dominio, vea [Encuentre su registrador de dominios o proveedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).
    
    Si desea esperar más tarde, desplácese hasta la parte inferior y seleccione **omitir este paso**.
    
8. Haga clic en **Finalizar** (ya está listo). 

## <a name="related-articles"></a>Artículos relacionados

[Preguntas más frecuentes de dominios](domains-faq.md)

[¿Qué es un dominio?](../get-help-with-domains/what-is-a-domain.md)

[Comprar un nombre de dominio en Office 365](../get-help-with-domains/buy-a-domain-name.md)

[Configurar su dominio (instrucciones específicas del host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[Obtener ayuda con Office 365 dominios](../get-help-with-domains/get-help-with-domains.md)
