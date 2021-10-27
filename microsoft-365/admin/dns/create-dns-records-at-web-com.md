---
title: Conectar los registros DNS en web.com a Microsoft 365
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
description: Obtenga información sobre cómo comprobar el dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en web.com microsoft.
ms.openlocfilehash: b95fd5412b7ddc4363e8d5e4ea345c1f551feef8
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586806"
---
# <a name="connect-your-dns-records-at-webcom-to-microsoft-365"></a>Conectar los registros DNS en web.com a Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
Si web.com es su proveedor de hospedaje DNS, siga los pasos de este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online, y así sucesivamente.
  
Después de agregar estos registros en web.com, el dominio se configurará para que funcione con servicios Microsoft.

> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Cambiar los registros del servidor de nombres (o NS) de su dominio

> [!IMPORTANT]
> Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio. 
  
Cuando se inscribió en web.com, agregó un dominio mediante el web.com **de instalación.** 
  
Para comprobar y crear registros DNS para su dominio en Microsoft, primero debe cambiar los servidores de nombres en el registrador de dominios para que usen los servidores de nombres de web.com.
  
Para cambiar los servidores DNS del dominio en el sitio web del registrador de dominios usted mismo, haga lo siguiente:
  
1. En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.
    
2. Cree dos registros de servidor de nombres mediante los valores de la tabla siguiente o edite los registros existentes del servidor de nombres para que coincidan con estos valores.
    
    |||
    |:-----|:-----|
    |Primer servidor de nombres  <br/> |Use el valor de servidor de nombres proporcionado por web.com.  <br/> |
    |Segundo servidor de nombres  <br/> |Use el valor de servidor de nombres proporcionado por web.com.  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. Si hay otros servidores de nombres enumerados, debe eliminarlos. 
  
3. Guarde los cambios.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para funcionar con su dominio. 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.
  
1. En la página de aterrizaje, seleccione **Nombres de dominio**. 
  
1. En **Acciones**, seleccione los tres puntos y, a continuación, **seleccione Administrar** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable."::: 
  
1. Desplácese hacia abajo para **seleccionar Herramientas avanzadas** y, junto a Registros DNS **avanzados,** seleccione **ADMINISTRAR**.
    
    Es posible que tenga que **seleccionar Continuar** para ir a la página Administrar registros DNS avanzados.
  
    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

1. En **Tipo**, seleccione **TXT** en la lista desplegable.

1. Seleccione o copie y pegue los valores de la tabla siguiente. 
    
    |**Hace referencia a**|**Valor TXT**|**TTL**|
    |:-----|:-----|:----|
    |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla.  [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)    |1 hora  <br/> |
  
5. Seleccione **AGREGAR**.
  
6. Espere unos minutos antes de comprobar el nuevo registro TXT, para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro. Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
Para comprobar el registro en Microsoft 365:
  
1. En el Centro de administración, vaya a **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Domains**</a>.
    
1. En la página Dominios, seleccione el dominio que está comprobando y seleccione **Iniciar instalación**. 

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Seleccione Iniciar instalación.":::

1. Seleccione **Continuar**.
  
1. En la página **verificar dominio**, seleccione **verificar**.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft

1. Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.
  
1. En la página de aterrizaje, seleccione **Nombres de dominio**. 
  
1. En **Acciones**, seleccione los tres puntos y, a continuación, **seleccione Administrar** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::
  
1. Desplácese hacia abajo para **seleccionar Herramientas avanzadas** y, junto a Registros DNS **avanzados,** seleccione **ADMINISTRAR**.
    
    Es posible que tenga que **seleccionar Continuar** para ir a la página Administrar registros DNS avanzados.
  
    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

1. En **Tipo**, seleccione **MX** en la lista desplegable.

1. Seleccione o copie y pegue los valores de la tabla siguiente. 
    
    | **Hace referencia a** | **Servidor de correo**|**Prioridad**|**TTL**|
    |:-----|:-----|:-----|:-----| 
    | @ |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **Nota:** Obtener el  *\<domain-key\>*  del Centro de administración de Microsoft.   [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md) | Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml) <br/> 1| 1 Hour  <br/> |
   
1. Seleccione **AGREGAR**.
  
1. Si hay otros registros MX enumerados en la sección **Registros MX,** active la casilla situada junto al registro en **Eliminar** y **seleccione Guardar**. 

## <a name="add-the-cname-record-required-for-microsoft"></a>Agregar el registro CNAME necesario para Microsoft

1. Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.
  
1. En la página de aterrizaje, seleccione **Nombres de dominio**. 
  
1. En **Acciones**, seleccione los tres puntos y, a continuación, **seleccione Administrar** en la lista desplegable.
 
    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::
 
1. Desplácese hacia abajo para **seleccionar Herramientas avanzadas** y, junto a Registros DNS **avanzados,** seleccione **ADMINISTRAR**.
    
    Es posible que tenga que **seleccionar Continuar** para ir a la página Administrar registros DNS avanzados.
  
    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

1. En **Tipo**, seleccione **CNAME** en la lista desplegable.

1. Seleccione o copie y pegue los valores de la tabla siguiente. 
    
    |**Hace referencia a** | **Nombre de host** | **Alias para**|**TTL**|
    |:-----|:-----|:-----|:-----|
    | Otro host  <br/>| autodescubrir  <br/>| autodiscover.outlook.com  <br/> | 1 hora  <br/>  |
  
1. Seleccione **AGREGAR**.
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores. 
  
1. Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.
  
1. En la página de aterrizaje, seleccione **Nombres de dominio**. 
  
1. En **Acciones**, seleccione los tres puntos y, a continuación, **seleccione Administrar** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::
  
1. Desplácese hacia abajo para **seleccionar Herramientas avanzadas** y, junto a Registros DNS **avanzados,** seleccione **ADMINISTRAR**.
    
    Es posible que tenga que **seleccionar Continuar** para ir a la página Administrar registros DNS avanzados.
  
    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

1. En **Tipo**, seleccione **TXT** en la lista desplegable.

1. Seleccione o copie y pegue los valores de la tabla siguiente. 
    
    |**Hace referencia a**|**Valor TXT**|**TTL**|
    |:-----|:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.  | 1 Hour  <br/> 
 
5. Seleccione **AGREGAR**.
  
## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial servicios de comunicación en línea como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita 4 registros: 2 registros SRV para la comunicación de usuario a usuario y 2 registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-the-two-required-srv-records"></a>Agregar los dos registros SRV necesarios

1. Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.
  
1. En la página de aterrizaje, seleccione **Nombres de dominio**. 
  
1. En **Acciones**, seleccione los tres puntos y, a continuación, **seleccione Administrar** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::
  
1. Desplácese hacia abajo para **seleccionar Herramientas avanzadas** y, junto a Registros DNS **avanzados,** seleccione **ADMINISTRAR**.
    
    Es posible que tenga que **seleccionar Continuar** para ir a la página Administrar registros DNS avanzados.
  
    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

1. En **Tipo**, seleccione **SRV** en la lista desplegable.

1. Seleccione o copie y pegue los valores de la tabla siguiente. 
    
    | **Tipo** |**Servicio**|**Protocolo**|**Grosor**|**Puerto**|**Destino**|**Prioridad**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    | SRV |_sip  <br/> |TLS  <br/> |100  <br/> |443  <br/> |sipdir.online.lync.com  <br/> **Este valor NO PUEDE finalizar con un punto (.)** <br/> | 1  <br/> | 1 hora  <br/> |
    | SRV |_sipfederationtls  <br/> |TCP <br/> |100  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> **Este valor NO PUEDE finalizar con un punto (.)** <br/> |1  <br/> | 1 Hour  <br/> |
  
6. Seleccione **AGREGAR**.
  
7. Para agregar el otro registro SRV:
    
    En la **sección DNS** avanzado, cree un registro con los valores de la segunda fila de la tabla y, a continuación, vuelva a seleccionar **AGREGAR** para completar ese registro. 
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 

### <a name="add-the-two-required-cname-records"></a>Agregar los dos registros CNAME necesarios 
    
1. Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.
  
1. En la página de aterrizaje, seleccione **Nombres de dominio**. 
  
1. En **Acciones**, seleccione los tres puntos y, a continuación, **seleccione Administrar** en la lista desplegable.
 
    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::
 
1. Desplácese hacia abajo para **seleccionar Herramientas avanzadas** y, junto a Registros DNS **avanzados,** seleccione **ADMINISTRAR**.
  
    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

    Es posible que tenga que **seleccionar Continuar** para ir a la página Administrar registros DNS avanzados.

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

1. En **Tipo**, seleccione **CNAME** en la lista desplegable.

1. Seleccione o copie y pegue los valores de la tabla siguiente. 
    
    | **Tipo**|**Se refiere a | Nombre de host**|**Alias para**| **TTL** |
    |:-----|:-----|:-----|:-----|:-----|
    | CNAME | Otro host | sip  <br/> |sipdir.online.lync.com  <br/> **Este valor NO PUEDE finalizar con un punto (.)** <br/> |1 hora  <br/> |
    | CNAME| Otro host | lyncdiscover  <br/> |webdir.online.lync.com  <br/> **Este valor NO PUEDE finalizar con un punto (.)** <br/> | 1 Hour  <br/> |
  
1. Seleccione **AGREGAR**.
  
1. Mediante los pasos anteriores y los valores de la segunda fila de la tabla, agregue el otro registro CNAME.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Opción avanzada: Intune y Administración de dispositivos móviles para Microsoft 365

Este servicio le ayuda a proteger y administrar de forma remota dispositivos móviles que se conectan a su dominio. Mobile Device Management necesita 2 registros CNAME para que los usuarios puedan inscribir dispositivos en el servicio.

### <a name="add-the-two-required-cname-records"></a>Agregar los dos registros CNAME necesarios

1. Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.
  
1. En la página de aterrizaje, seleccione **Nombres de dominio**. 
  
1. En **Acciones**, seleccione los tres puntos y, a continuación, **seleccione Administrar** en la lista desplegable.
 
    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::
 
1. Desplácese hacia abajo para **seleccionar Herramientas avanzadas** y, junto a Registros DNS **avanzados,** seleccione **ADMINISTRAR**.
    
    Es posible que tenga que **seleccionar Continuar** para ir a la página Administrar registros DNS avanzados.
  
    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

1. En **Tipo**, seleccione **CNAME** en la lista desplegable.

1. Seleccione o copie y pegue los valores de la tabla siguiente. 
    
    | **Tipo**|**Se refiere a | Nombre de host**|**Alias para**| **TTL** |
    |:-----|:-----|:-----|:-----|:-----|
    | CNAME | Otro host | enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> **Este valor NO PUEDE finalizar con un punto (.)** <br/> | 1 hora  <br/> |
    | CNAME | Otro host |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> **Este valor NO PUEDE finalizar con un punto (.)** <br/> | 1 Hour  <br/> |
  
1. Seleccione **AGREGAR**.
  
1. Mediante los pasos anteriores y los valores de la segunda fila de la tabla, agregue el otro registro CNAME.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).