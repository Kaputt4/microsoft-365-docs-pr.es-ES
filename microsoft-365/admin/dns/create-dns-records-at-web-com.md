---
title: Crear registros DNS en web.com para Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en web.com para Office 365.
ms.openlocfilehash: eb231f85e568e81a5e229f0533d8176feb590f48
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249460"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a>Crear registros DNS en web.com para Office 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Si web.com es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.
  
Después de agregar estos registros a web.com, su dominio estará configurado para trabajar con los servicios de Office 365.
  
Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Cambiar los registros del servidor de nombres (o NS) de su dominio
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio. 
  
Cuando se registró para web.com, agregó un dominio mediante el proceso de **instalación** de Web.com. 
  
Para comprobar y crear registros DNS para su dominio en Office 365, primero debe cambiar los servidores de nombres en el registrador de dominios para que usen los servidores de nombres Web. com.
  
Para cambiar los servidores DNS del dominio en el sitio web del registrador de dominios usted mismo, haga lo siguiente:
  
1. En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.
    
2. Cree dos registros de servidor de nombres mediante los valores de la tabla siguiente o edite los registros de servidor de nombres existentes para que cumplan estos valores.
    
    |||
    |:-----|:-----|
    |Primer servidor de nombres  <br/> |Usar el valor de nameserver proporcionado por web.com.  <br/> |
    |Segundo servidor de nombres  <br/> |Usar el valor de nameserver proporcionado por web.com.  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. Si hay otros servidores de nombres enumerados, debe eliminarlos. 
  
3. Guarde los cambios.
    
> [!NOTE]
> Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, su correo electrónico y otros servicios de Office 365 estarán listos para funcionar con su dominio. 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_verify"> </a>

Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.
  
2. En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**. 
  
3. En * * administrar * mi dominio * * *, seleccione **Editar registros DNS avanzados**.

  
4. En la página **nombres de dominio** , en **texto (registros txt)**, haga clic en **Editar registros txt**y, a continuación, seleccione los valores de la tabla siguiente. 
    
    |**Host**|**TTL**|**Texto**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** Este es un ejemplo. Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365.           [¿Cómo puedo encontrarlo?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Seleccione **continuar**.
  
  
6. Espere unos minutos antes de comprobar el nuevo registro TXT, de modo que el registro que acaba de crear pueda actualizarse a través de Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .

    
2. En la página **dominios** , seleccione el dominio que desea comprobar. 
    
    
  
3. En la página **configuración** , seleccione **Iniciar configuración**.
    
    
  
4. En la página **comprobar dominio** , seleccione **comprobar**.
    
    
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365
<a name="BKMK_add_MX"> </a>

1. Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.
  
2. En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**. 
  
3. En * * administrar * mi dominio * * *, seleccione **Editar registros DNS avanzados**.

4. En **servidores de correo (registros MX)**, haga clic en **Editar registros MX**y, a continuación, seleccione los valores de la tabla siguiente. 
    
    |**Prioridad**|**TTL**|**Servidor de correo**|
    |:-----|:-----|:-----|
    |1  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |3600  <br/> |*\< clave-de-dominio \>*  . mail.protection.outlook.com      <br/> **Nota:** Obtenga la * \<clave\> de dominio* de su cuenta de Office 365.   [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md) |
   

5. Seleccione **Guardar**.
  
6. Si hay otros registros MX enumerados en la sección **registros MX** , active la casilla situada junto al registro en **eliminar**y seleccione **Guardar**. 
  
7. En la pantalla de confirmación, seleccione **Guardar cambios**. 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Agregue los seis registros CNAME necesarios para Office 365
<a name="BKMK_add_CNAME"> </a>

1. Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp). You'll be prompted to log in first.
     
2. En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**. 
  
3. En * * administrar * mi dominio * * *, seleccione **Editar registros DNS avanzados**.

4. Agregue el primero de los seis registros CNAME.
    
    En **alias de host (registros CNAME)**, haga clic en **Editar registros CNAME**y, a continuación, seleccione los valores de la tabla siguiente.
    
    
    |**Alias**|**TTL**|**Referencia a nombre de host**|**Otro host**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |@ (ninguno)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |3600  <br/> |@ (ninguno)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |3600  <br/> |@ (ninguno)  <br/> | webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |@ (ninguno)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |@ (ninguno)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
    |msoid  <br/> |3600  <br/> |@ (ninguno)  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    
  
5. Seleccione **continuar**.
  
6. Agregue los otros cinco registros CNAME.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores. 
  
1. Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.
    
  
2. En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**. 
  
3. En * * administrar * mi dominio * * *, seleccione **Editar registros DNS avanzados**.

  
4. En la página **nombres de dominio** , en **texto (registros txt)**, haga clic en **Editar registros txt**y, a continuación, seleccione los valores de la tabla siguiente.   
    
    |**Host**|**TTL**|**Texto**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.   |

 
5. Seleccione **continuar**.

6. Seleccione **Guardar cambios**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Agregar los dos registros SRV necesarios para Office 365
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Tenga en cuenta que web.com es responsable de hacer que esta funcionalidad esté disponible. En caso de que vea discrepancias entre los pasos siguientes y la interfaz gráfica de usuario (GUI) web.com actual, aproveche la [comunidad de Web.com](https://community.web.com.com/). 

1. Para empezar, vaya a su página de dominios en web.com a través de [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.
      
2. En la página **Administrador de cuentas** , seleccione **mis nombres de dominio**. 
  
3. En * * administrar * mi dominio * * *, seleccione **Editar registros DNS avanzados**.
  
4. Agregue el primero de los dos registros SRV.

    En **servicio (registros SRV)**, haga clic en **Editar registros SRV**y, a continuación, seleccione los valores de la tabla siguiente. 
        
    |**Servicio**|**Protocolo**|**TTL**|**Prioridad**|**Peso**|**Puerto**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1 |443 |sipfed.online.lync.com  |
    |_sipfederationtls |_tcp |3600 |100 |1 |5061 | sipfed.online.lync.com |

  
5. Agregue el otro registro SRV; para ello, elija los valores de la segunda fila de la tabla. 
  
6. Seleccione **continuar**.

7. Seleccione **Guardar cambios**.

    
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
