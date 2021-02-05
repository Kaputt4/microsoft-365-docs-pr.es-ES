---
title: Agregar un dominio a Microsoft 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Agregue su dominio a Microsoft 365 en el Centro de administración de Microsoft 365 agregando un registro DNS en su host DNS. El asistente de configuración le guiará a través del proceso.
ms.openlocfilehash: 5a3c86fb2b2f93e9da844c15a55555c5d0d7b5c1
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114266"
---
# <a name="add-a-domain-to-microsoft-365"></a>Agregar un dominio a Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

 **[Consulte Preguntas más frecuentes acerca de los dominios](domains-faq.yml)** si no encuentra lo que busca. 
  
 *Para agregar, modificar o quitar dominios, **debe** ser administrador **global** de un [plan empresarial o empresarial.](https://products.office.com/business/office) Estos cambios afectan a todo el inquilino, los administradores *personalizados* o los usuarios *normales* no podrán realizar estos cambios.*  

 Siga estos pasos para agregar, configurar o continuar configurando un dominio. 

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
    
2. Vaya a la **página Dominios**  >  **de** configuración. 

3. Seleccione **Agregar dominio.**
    
4. Escriba el nombre del dominio que desea agregar y, a continuación, **seleccione Siguiente**.
    
5. Elija cómo desea comprobar que es el propietario del dominio.
    
    1. Si el registrador de dominios usa [La](#domain-connect-registrars-integrating-with-microsoft-365)conexión de dominio, [Microsoft](../get-help-with-domains/domain-connect.md) configurará los registros automáticamente haciendo que inicie sesión en su registrador y confirme la conexión a Microsoft 365. Se te devolverá al centro de administración y Microsoft comprobará automáticamente tu dominio.
    2. Puede usar un registro TXT para comprobar su dominio. Seleccione esta opción y **seleccione Siguiente** para ver las instrucciones para agregar este registro DNS al sitio web del registrador. Esto puede tardar hasta 30 minutos en comprobarse después de agregar el registro. 
    3. Puede agregar un archivo de texto al sitio web de su dominio. Seleccione y descargue el archivo .txt desde el Asistente para instalación y, a continuación, cargue el archivo en la carpeta de nivel superior del sitio web. La ruta de acceso al archivo debe ser similar a: `http://mydomain.com/ms39978200.txt` . Confirmaremos que es el propietario del dominio mediante la búsqueda del archivo en su sitio web.
    
6. Elija cómo desea realizar los cambios de DNS necesarios para que Microsoft use su dominio.
    
    1. Elija **Agregar los** registros DNS si [](#domain-connect-registrars-integrating-with-microsoft-365)su registrador admite La conexión de dominio y [Microsoft](../get-help-with-domains/domain-connect.md) configurará los registros automáticamente haciendo que inicie sesión en su registrador y confirme la conexión a Microsoft 365.
    2. Elija **si desea** adjuntar solo servicios específicos de Microsoft 365 a su dominio o si desea omitir esto por ahora y hacerlo más adelante. **Elija esta opción si sabe exactamente lo que hace.**

7. Si decide agregar *registros DNS*  usted mismo, seleccione Siguiente y verá una página con todos los registros que necesita agregar a su sitio web de registradores para configurar su dominio. 

    Si el portal no reconoce el registrador, puede [seguir estas instrucciones generales.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Consulte nuestra lista de [instrucciones específicas del host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) para buscar su host y siga los pasos para agregar todos los registros que necesite. 
    
    Si no conoce el proveedor de host DNS o el registrador de dominios de su dominio, vea [Encuentre su registrador de dominios o proveedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).
    
    Si desea esperar más tarde, anule la selección de todos los servicios  y haga clic en Continuar **o,** en el paso de conexión de dominio anterior, elija Más opciones y seleccione Omitir esto **por ahora.**
    
8. Selecciona **Finalizar:** ya has terminado.

## <a name="add-or-edit-custom-dns-records"></a>Agregar o editar registros DNS personalizados

Siga los pasos siguientes para agregar un registro personalizado para un sitio web o un servicio de terceros.

1. Inicie sesión en el Centro de administración de Microsoft en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Vaya a la **página Dominios**   >  **de** configuración.

3. En la página **Dominios**, seleccione un dominio. 
    
4. En **Configuración dns,** seleccione **Registros personalizados;** a **continuación, seleccione Nuevo registro personalizado.**

5. Seleccione el tipo de registro DNS que desea agregar y escriba la información del nuevo registro.
    
6. Haga clic en **Guardar**.

## <a name="registrars-with-domain-connect"></a>Registradores con conexión de dominio

[Los registradores](https://www.domainconnect.org/) habilitados para Conectar dominio le permiten agregar su dominio a Microsoft 365 en un proceso de tres pasos que tarda minutos. 
  
En el asistente, solo confirmaremos que es el propietario del dominio y, a continuación, configuraremos automáticamente los registros de su dominio, por lo que el correo electrónico llega a Microsoft 365 y otros servicios de Microsoft 365, como Teams, a trabajar con su dominio.
  
> [!NOTE]
> Asegúrese de desactivar los bloqueadores de ventanas emergente en el explorador antes de iniciar el Asistente de configuración.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Registradores de Conexión de dominio que se integran con Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer o WildWestDomains (revendedores de GoDaddy que usan el hospedaje DNS de SecureServer)
    - Ejemplos:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>¿Qué sucede con mi correo electrónico y mi sitio web?

Una vez que termine la instalación, el registro MX de su dominio se actualizará para que apunte a Microsoft 365 y todo el correo electrónico de su dominio empezará a llegar a Microsoft 365. Asegúrese de que ha agregado usuarios y configurado buzones en Microsoft 365 para todos los usuarios que reciban correo electrónico en su dominio.
  
Si tiene un sitio web que usa con su empresa, seguirá funcionando como hasta ahora. Los pasos de configuración de Conexión de dominio no afectan a su sitio web.

## <a name="related-articles"></a>Artículos relacionados

[Preguntas más frecuentes de dominios](domains-faq.yml)

[¿Qué es un dominio?](../get-help-with-domains/what-is-a-domain.md)

[Comprar un nombre de dominio en Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Configurar su dominio (instrucciones específicas del host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
