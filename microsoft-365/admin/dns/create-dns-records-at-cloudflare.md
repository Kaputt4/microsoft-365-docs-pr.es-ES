---
title: Conectar los registros DNS de Cloudflare a Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Aprenda a comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en Cloudflare para Microsoft.
ms.openlocfilehash: 80c7a3dded1da9c52f0baf215fcd1c39cd90d4f3
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586854"
---
# <a name="connect-your-dns-records-at-cloudflare-to-microsoft-365"></a>Conectar los registros DNS de Cloudflare a Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 

Si Cloudflare es su proveedor de hospedaje DNS, siga los pasos de este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online, y así sucesivamente.

## <a name="before-you-begin"></a>Antes de empezar

Tiene dos opciones para configurar registros DNS para su dominio:

- [**Usar dominio Conectar**](#use-domain-connect-to-verify-and-set-up-your-domain) Si no ha configurado el dominio con otro proveedor de servicios de correo electrónico, siga los pasos de Dominio Conectar para comprobar y configurar automáticamente el nuevo dominio para usarlo con Microsoft 365. 

    OR

- [**Siga los pasos manuales**](#create-dns-records-with-manual-setup) Compruebe el dominio con los pasos manuales siguientes y elija cuándo y qué registros agregar al registrador de dominio. Esto le permite configurar nuevos registros MX (correo), por ejemplo, a su conveniencia. 

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>Usar dominio Conectar para comprobar y configurar el dominio

Siga estos pasos para comprobar y configurar automáticamente el dominio de Cloudflare con Microsoft 365:

1. En el Centro de administración de Microsoft 365, seleccione **Configuración**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**dominios**</a>y seleccione el dominio que desea configurar.

1. Seleccione los tres puntos (más acciones) > elija **Iniciar configuración**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Seleccione Iniciar instalación.":::

1. On the How do you want to connect your domain? página, seleccione **Continuar**.   

1. En la página Agregar registros DNS, seleccione **Agregar registros DNS**.

1. En la página de inicio de sesión de Cloudflare, inicie sesión en su cuenta y seleccione **Autorizar**.
    
    Esto completa la configuración de dominio para Microsoft 365. 

## <a name="create-dns-records-with-manual-setup"></a>Crear registros DNS con configuración manual

Después de agregar estos registros en Cloudflare, el dominio se configurará para que funcione con Microsoft 365 servicios.

> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
### <a name="change-your-domains-nameserver-ns-records"></a>Cambiar los registros del servidor de nombres (o NS) de su dominio

> [!IMPORTANT]
> Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio. 
  
Cuando te has registrado en Cloudflare, agregaste un dominio mediante el proceso de configuración de Cloudflare. 
  
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
  
### <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a la página dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .
  
1. En la página principal, seleccione el dominio que desea actualizar. 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="Seleccione el dominio que desea actualizar.":::
 
1. En la página Información general del dominio, seleccione **DNS**.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="Seleccione DNS.":::
  
1. En la página administración de DNS, seleccione **+Agregar registro** y, a continuación, escriba o copie y pegue los valores de la tabla. 
    
    | **Tipo** | **Nombre** | **TTL** | **Contenido** |
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 minutos  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)    |
    
1. Seleccione **Guardar**.
  
1. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y buscará el registro. Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
Para comprobar el registro en Microsoft 365:
  
1. En el Centro de administración, vaya a **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Domains**</a>.
    
1. En la página Dominios, seleccione el dominio que está comprobando y seleccione **Iniciar instalación**. 

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Seleccione Iniciar instalación.":::

1. Seleccione **Continuar**.
  
1. En la página **verificar dominio**, seleccione **verificar**.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
    
### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft

1. Para empezar, vaya a la página dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .
  
2. En la página principal, seleccione el dominio que desea actualizar. 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="Seleccione el dominio que desea actualizar.":::
 
3. En la página Información general del dominio, seleccione **DNS**.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="Seleccione DNS.":::

4. En la página administración de DNS, seleccione **+Agregar registro** y, a continuación, escriba o copie y pegue los valores de la tabla. 
    
    | **Tipo** | **Nombre** | **Servidor de correo** |  **TTL** | **Prioridad** |
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **Nota:** Obtenga el *\<domain-key\>* de su cuenta Microsoft 365 usuario.   [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md) |30 minutos  <br/> | 1  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml) <br/>|
   
5. Seleccione **Guardar**.
  
6. Si hay otros registros MX enumerados en la sección **Registros MX,** elimínelos **seleccionando Editar** y, a continuación, **seleccione Eliminar**. 
  
7. En el cuadro de diálogo de confirmación, **seleccione Eliminar** para confirmar los cambios. 

### <a name="add-the-cname-record-required-for-microsoft"></a>Agregar el registro CNAME necesario para Microsoft

1. Para empezar, vaya a la página dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .
      
2. En la página principal, seleccione el dominio que desea actualizar. 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="Seleccione el dominio que desea actualizar.":::
 
3. En la página Información general del dominio, seleccione **DNS**.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="Seleccione DNS.":::

4. Agregue el registro CNAME.
    
    En la **página administración de DNS,** seleccione **+Agregar registro** y, a continuación, escriba o copie y pegue los valores de la tabla.

    | Tipo | Nombre | Target | TTL |
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodescubrir  <br/> |autodiscover.outlook.com  <br/> |30 minutos  <br/> |> |
  
6. Seleccione **Guardar**.
    
### <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft 365. En vez de eso, agregue los valores necesarios de Microsoft 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores. 
  
1. Para empezar, vaya a la página dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .  
  
2. En la página principal, seleccione el dominio que desea actualizar. 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="Seleccione el dominio que desea actualizar.":::
 
3. En la página Información general del dominio, seleccione **DNS**.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="Seleccione DNS.":::

4. En la página administración de DNS, seleccione **+Agregar registro** y, a continuación, seleccione los valores de la tabla siguiente.  
    
    | Tipo | Nombre | TTL | Contenido |
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 minutos  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.   |
 
5. Seleccione **Guardar**.
  
## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial servicios de comunicación en línea como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita 4 registros: 2 registros SRV para la comunicación de usuario a usuario y 2 registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-the-two-required-srv-records"></a>Agregar los dos registros SRV necesarios

> [!IMPORTANT]
> Ten en cuenta que Cloudflare es responsable de hacer que esta funcionalidad esté disponible. En caso de que vea discrepancias entre los pasos siguientes y la GUI de Cloudflare actual (interfaz gráfica de usuario), aproveche la interfaz de usuario [de Cloudflare Community](https://community.cloudflare.com/). 

1. Para empezar, vaya a la página dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .
      
2. En la página principal, seleccione el dominio que desea actualizar. 

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="Seleccione el dominio que desea actualizar.":::
  
3. En la página Información general del dominio, seleccione **DNS**.
  
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="Seleccione DNS.":::

4. Agregue el primero de los dos registros SRV.

    En la página administración de DNS, seleccione **+Agregar registro** y, a continuación, seleccione o copie y pegue los valores de la primera fila de la tabla.
        
    | **Tipo** | **Nombre** | **Servicio** | **Protocolo** |  **TTL** | **Prioridad** | **Grosor** | **Puerto** | **Destino** |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip | Use el *domain_name*; por ejemplo, contoso.com  ||TLS |30 minutos | 100|1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|Use el *domain_name*; por ejemplo, contoso.com   |30 minutos |100 |1 |5061 | sipfed.online.lync.com |
  
5. Seleccione **Guardar**.

6. Agregue el otro registro SRV eligiendo los valores de la segunda fila de la tabla. 
 
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 

### <a name="add-the-two-required-cname-records"></a>Agregar los dos registros CNAME necesarios
  
1. Para empezar, vaya a la página dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .
      
2. En la página principal, seleccione el dominio que desea actualizar. 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="Seleccione el dominio que desea actualizar.":::
 
3. En la página Información general del dominio, seleccione **DNS**.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="Seleccione DNS.":::

4. Agregue el primer registro CNAME.
    
    En la página administración de DNS, seleccione **+Agregar registro** y, a continuación, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.
    
    |**Tipo**|**Nombre**|**Destino**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |1 hora  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |1 Hour  <br/> |
  
1. Seleccione **guardar**. 
  
1. Agregue el otro registro CNAME eligiendo los valores de la segunda fila de la tabla.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Opción avanzada: Intune y Administración de dispositivos móviles para Microsoft 365

Este servicio le ayuda a proteger y administrar de forma remota dispositivos móviles que se conectan a su dominio. Mobile Device Management necesita 2 registros CNAME para que los usuarios puedan inscribir dispositivos en el servicio.

### <a name="add-the-two-required-cname-records"></a>Agregar los dos registros CNAME necesarios

1. Para empezar, vaya a la página dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .
      
2. En la página principal, seleccione el dominio que desea actualizar. 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="Seleccione el dominio que desea actualizar.":::
 
3. En la página Información general del dominio, seleccione **DNS**.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="Seleccione DNS.":::

4. Agregue el primer registro CNAME.
    
    En la página administración de DNS, seleccione **+Agregar registro** y, a continuación, escriba o copie y pegue los valores de la primera fila de la tabla.
    
    |**Tipo**|**Nombre**|**Destino**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |1 hora  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |1 Hour  <br/> |
  
8. Seleccione **Guardar**. 
  
9. Agregue el otro registro CNAME eligiendo los valores de la segunda fila de la tabla.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 

  
