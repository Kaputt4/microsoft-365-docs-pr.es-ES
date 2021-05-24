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
description: Use el Asistente para la instalación para agregar el dominio Microsoft 365 en el centro de administración de Microsoft 365 agregando un registro DNS en el host DNS.
ms.openlocfilehash: 152144737b0ff8cb8b0c27db2a4fc1051fb2a8a7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635683"
---
# <a name="add-a-domain-to-microsoft-365"></a>Agregar un dominio a Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](domains-faq.yml)** si no encuentra lo que busca. 
  
 *Para agregar, modificar o quitar dominios, **debe ser** administrador **global** de un plan empresarial [o empresarial.](https://products.office.com/business/office) Estos cambios afectan a todo el inquilino, los administradores *personalizados* o los usuarios *normales* no podrán realizar estos cambios.*  

 ## <a name="add-a-domain"></a>Agregar un dominio

Siga estos pasos para agregar, configurar o seguir configurando un dominio. 

::: moniker range="o365-worldwide"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end
::: moniker range="o365-germany"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end
    
2. Vaya a la **página Configuración**  >  **dominios.** 

3. Seleccione **Agregar dominio**.
    
4. Escriba el nombre del dominio que desea agregar y, a continuación, **seleccione Siguiente**.
    
5. Elija cómo desea comprobar que es el propietario del dominio.
    
    1. Si el registrador de dominio usa [dominio Conectar,](#domain-connect-registrars-integrating-with-microsoft-365) [Microsoft](../get-help-with-domains/domain-connect.md) configurará los registros automáticamente al tener que iniciar sesión en el registrador y confirmar la conexión a Microsoft 365. Se te devolverá al Centro de administración y Microsoft comprobará automáticamente tu dominio.
    2. Puede usar un registro TXT para comprobar su dominio. Seleccione esto y **seleccione Siguiente** para ver instrucciones sobre cómo agregar este registro DNS al sitio web del registrador. Esto puede tardar hasta 30 minutos en comprobarse después de agregar el registro. 
    3. Puede agregar un archivo de texto al sitio web de su dominio. Seleccione y descargue el archivo .txt del asistente para la instalación y, a continuación, cargue el archivo en la carpeta de nivel superior del sitio web. La ruta de acceso al archivo debe ser similar a: `http://mydomain.com/ms39978200.txt` . Confirmaremos que es el propietario del dominio mediante la búsqueda del archivo en su sitio web.
    
6. Elija cómo desea realizar los cambios DNS necesarios para que Microsoft use su dominio.
    
    1. Elija **Agregar los** registros DNS para mí si su registrador admite dominio [Conectar](#domain-connect-registrars-integrating-with-microsoft-365)y [Microsoft](../get-help-with-domains/domain-connect.md) configurará los registros automáticamente si inicia sesión en su registrador y confirma la conexión a Microsoft 365.
    2. Elija **Agregaré los** registros DNS yo mismo si desea adjuntar solo servicios de Microsoft 365 específicos a su dominio o si desea omitir esto por ahora y hacerlo más adelante. **Elija esta opción si sabe exactamente lo que hace.**

7. Si decide agregar *registros DNS*  usted mismo, seleccione Siguiente y verá una página con todos los registros que necesita agregar al sitio web de registradores para configurar su dominio. 

    Si el portal no reconoce el registrador, puede [seguir estas instrucciones generales.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Consulte nuestra lista de [instrucciones específicas del host](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) para buscar su host y siga los pasos para agregar todos los registros que necesite. 
    
    Si no conoce el proveedor de host DNS o el registrador de dominios de su dominio, vea [Encuentre su registrador de dominios o proveedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).
    
    Si desea esperar más tarde, anule la selección de todos los servicios  y haga clic en Continuar **o,** en el paso de conexión de dominio anterior, elija Más opciones y seleccione **Omitir esto por ahora**.
    
8. Selecciona **Finalizar:** ya has terminado.

## <a name="add-or-edit-custom-dns-records"></a>Agregar o editar registros DNS personalizados

Siga los pasos siguientes para agregar un registro personalizado para un sitio web o un servicio de terceros.

1. Inicie sesión en el Centro de administración de Microsoft en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Vaya a la **página Configuración**   >  **dominios.**

3. En la página **Dominios**, seleccione un dominio. 
    
4. En **Configuración dns,** seleccione **Registros personalizados;** a **continuación, seleccione Nuevo registro personalizado**.

5. Seleccione el tipo de registro DNS que desea agregar y escriba la información del nuevo registro.
    
6. Seleccione **Guardar**.

## <a name="registrars-with-domain-connect"></a>Registradores con dominio Conectar

[Los Conectar](https://www.domainconnect.org/) registradores habilitados permiten agregar el dominio a Microsoft 365 en un proceso de tres pasos que tarda minutos. 
  
En el asistente, solo confirmaremos que es el propietario del dominio y, a continuación, configuraremos automáticamente los registros de su dominio, de modo que el correo electrónico llegue a Microsoft 365 y otros servicios de Microsoft 365, como Teams, trabajen con su dominio.
  
> [!NOTE]
> Asegúrese de desactivar los bloqueadores de ventanas emergente en el explorador antes de iniciar el Asistente de configuración.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Registradores Conectar de dominio que se integran con Microsoft 365

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

Después de finalizar la instalación, el registro MX del dominio se actualiza para que apunte a Microsoft 365 y todo el correo electrónico de su dominio empezará a llegar a Microsoft 365. Asegúrese de que ha agregado usuarios y configurado buzones en Microsoft 365 para todos los usuarios que reciban correo electrónico en su dominio.
  
Si tiene un sitio web que usa con su empresa, seguirá funcionando como hasta ahora. Los pasos Conectar configuración del dominio no afectan al sitio web.

## <a name="related-content"></a>Contenido relacionado

[Preguntas más frecuentes](domains-faq.yml) sobre dominios (artículo)\
[¿Qué es un dominio?](../get-help-with-domains/what-is-a-domain.md) (artículo)\
[Comprar un nombre de dominio en Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (artículo)\
[Configurar el dominio](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) (artículo)