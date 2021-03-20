---
title: Crear registros DNS en Cloudflare para Microsoft
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
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en Cloudflare para Microsoft.
ms.openlocfilehash: 0a80cf059a3a69dcb8aa48251875410f35684286
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910383"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a>Crear registros DNS en Cloudflare para Microsoft

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
Si Cloudflare es su proveedor de hospedaje DNS, siga los pasos descritos en este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online, entre otros.
  
Después de agregar estos registros en Cloudflare, el dominio se configurará para que funcione con los servicios de Microsoft 365.
  
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Cambiar los registros del servidor de nombres (o NS) de su dominio
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio. 
  
Cuando te has registrado en Cloudflare, agregaste un dominio mediante el proceso de configuración **de** Cloudflare. 
  
El dominio que agregó se compró a Cloudflare o a un registrador de dominio independiente. Para comprobar y crear registros DNS para su dominio en Microsoft 365, primero debe cambiar los servidores de nombres en el registrador de dominios para que usen los servidores de nombres de Cloudflare.
  
Para cambiar los servidores DNS del dominio en el sitio web del registrador de dominios usted mismo, haga lo siguiente:
  
1. En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.
    
2. Cree dos registros de servidor de nombres mediante los valores de la tabla siguiente o edite los registros existentes del servidor de nombres para que coincidan con estos valores.
    
    |||
    |:-----|:-----|
    |Primer servidor de nombres  <br/> |Use el valor de servidor de nombres proporcionado por Cloudflare.  <br/> |
    |Segundo servidor de nombres  <br/> |Use el valor de servidor de nombres proporcionado por Cloudflare.  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. Si hay otros servidores de nombres enumerados, debe eliminarlos. 
  
3. Guarde los cambios.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para funcionar con su dominio. 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_verify"> </a>

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a la página dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .
  
2. En la **página principal,** seleccione el dominio que desea actualizar. 
  
3. En la **página Información** general del dominio, seleccione **DNS**.

  
4. En la **página administración de DNS,** haga clic **en Agregar registro** y, a continuación, seleccione los valores de la tabla siguiente. 
    
    | Tipo | Nombre | TTL automático | Contenido |
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 minutos  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla.           [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Seleccione **Guardar**.
  
  
9. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y buscará el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.

    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
    
  
3. En la página de **Configuración**, elija **Iniciar configuración**.
    
    
  
4. En la página **verificar dominio**, seleccione **verificar**.
    
    
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft
<a name="BKMK_add_MX"> </a>

1. Para empezar, vaya a la página dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .
  
2. En la **página principal,** seleccione el dominio que desea actualizar. 
  
3. En la **página Información** general del dominio, seleccione **DNS**.

  
4. En la **página administración de DNS,** haga clic **en Agregar registro** y, a continuación, seleccione los valores de la tabla siguiente. 
    
    | Tipo | Nombre | Servidor de correo | Prioridad | TTL |
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **Nota:** Obtenga el  *\<domain-key\>*  de su cuenta de Microsoft 365.   [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md) |1  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml) <br/>|30 minutos  <br/> |
   

  
5. Seleccione **Guardar**.
  
9. Si hay otros registros MX enumerados en la sección **Registros MX,** elimínelos seleccionando el icono Eliminar **(X).** 
  
10. En el cuadro de diálogo de confirmación, **seleccione Eliminar** para confirmar los cambios. 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Agregar los seis registros CNAME necesarios para Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para empezar, vaya a la página dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .
    
  
2. En la **página principal,** seleccione el dominio que desea actualizar. 
  
3. En la **página Información** general del dominio, seleccione **DNS**.

  
4. Agregue el primero de los cinco registros CNAME.
    
    En la **página administración de DNS,** haga clic **en Agregar registro** y, a continuación, seleccione los valores de la tabla siguiente.
    
    
    | Tipo | Nombre | Target | TTL |
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodescubrir  <br/> |autodiscover.outlook.com  <br/> |30 minutos  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 minutos  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 minutos  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 minutos  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30 minutos  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 minutos  <br/> |
    
  
5. Seleccione el **icono Tráfico DNS** (cambie la nube naranja a gris) para omitir los servidores de Cloudflare.
  
6. Seleccione **Guardar**.
  
7. Agregue los otros cinco registros CNAME.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft 365. En vez de eso, agregue los valores necesarios de Microsoft 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores. 
  
1. Para empezar, vaya a la página dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .
    
  
2. En la **página principal,** seleccione el dominio que desea actualizar. 
  
3. En la **página Información** general del dominio, seleccione **DNS**.

  
4. En la **página administración de DNS,** haga clic **en Agregar registro** y, a continuación, seleccione los valores de la tabla siguiente.  
    
    | Tipo | Nombre | TTL | Contenido |
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 minutos  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.   |

 
5. Seleccione **Guardar**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Agregar los dos registros SRV necesarios para Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Tenga en cuenta que Cloudflare es responsable de hacer que esta funcionalidad esté disponible. En caso de que vea discrepancias entre los pasos siguientes y la GUI de Cloudflare actual (interfaz gráfica de usuario), aproveche la [comunidad de Cloudflare](https://community.cloudflare.com/). 

1. Para empezar, vaya a la página dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .
      
2. En la **página principal,** seleccione el dominio que desea actualizar. 
  
3. En la **página Información** general del dominio, seleccione **DNS**.
  
4. Agregue el primero de los dos registros SRV.

    En la **página administración de DNS,** haga clic **en Agregar registro** y, a continuación, seleccione los valores de la primera fila de la tabla siguiente.
        
    | Tipo | Servicio | Protocolo | Nombre | TTL | Priority | Peso | Puerto | Target |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |Use el *domain_name*; por ejemplo, contoso.com  |30 minutos | 100|1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|Use el *domain_name*; por ejemplo, contoso.com   |30 minutos |100 |1 |5061 | sipfed.online.lync.com |

  
5. Seleccione **Guardar**.

  
6. Agregue el otro registro SRV eligiendo los valores de la segunda fila de la tabla. 

    
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
