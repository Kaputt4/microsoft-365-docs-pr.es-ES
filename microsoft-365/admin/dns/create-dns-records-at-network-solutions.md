---
title: Conectar los registros DNS en Network Solutions para Microsoft 365
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Obtenga información sobre cómo comprobar el dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en Network Solutions for Microsoft.
ms.openlocfilehash: f0599ef178e9a3dde097b94e7c3f980f59e88636
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586367"
---
# <a name="connect-your-dns-records-at-network-solutions-to-microsoft-365"></a>Conectar los registros DNS en Network Solutions para Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
Si Network Solutions es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.
    
Después de agregar estos registros en Network Solutions, el dominio se configurará para que funcione con servicios Microsoft.
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). Se le pedirá que inicie sesión.
  
1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. Active la casilla situada junto al dominio que desea modificar.
  
1. En **Acciones**, seleccione los tres puntos y, a continuación, **seleccione Administrar** en la lista desplegable.

    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::
  
1. Desplácese hacia abajo para **seleccionar Herramientas avanzadas** y, junto a Registros DNS **avanzados,** seleccione **ADMINISTRAR**.

    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

    Es posible que tenga que **seleccionar Continuar** para ir a la página Administrar registros DNS avanzados.
  
1. Seleccione **Continuar** y, en la página Administrar registros DNS avanzados, seleccione **+AGREGAR REGISTRO**.

1. En **Tipo**, seleccione **TXT** en la lista desplegable.
  
1. In the boxes for the new record, type or copy and paste the values in the following table.
    
    |**Hace referencia a**|**Valor TXT**|**TTL**|
    |:-----|:-----|:-----|
    |@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla.  [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md) |3600  <br/>    |
  
1. Seleccione **AGREGAR**.
  
    > [!NOTE]
    > Seleccione **Vista clásica** en la parte superior derecha para ver el registro TXT que creó.   
  
1. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
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
  
1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). Se le pedirá que inicie sesión.
  
1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. Active la casilla situada junto al dominio que desea modificar.
  
1. En **Acciones**, seleccione los tres puntos y, a continuación, **seleccione Administrar** en la lista desplegable.

    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::
  
1. Desplácese hacia abajo para **seleccionar Herramientas avanzadas** y, junto a Registros DNS **avanzados,** seleccione **ADMINISTRAR**.
    
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

    Es posible que tenga que **seleccionar Continuar** para ir a la página Administrar registros DNS avanzados.
    
1. En la página Administrar registros DNS avanzados, seleccione **+AGREGAR REGISTRO**.

1. En **Tipo**, seleccione **MX** en la lista desplegable.
  
1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.
    
    **Hace referencia a** |**Servidor de correo**|**Prioridad**|**TTL**|
    |:-----|:-----|:-----|:-----|
    | @ | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Este valor no puede terminar con un punto (.)** <br/> **Nota:** Obtener el  *\<domain-key\>*  de su cuenta de Microsoft. [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md) | 0  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml) <br/> | 1 hora  <br/> |  
  
1. Seleccione **AGREGAR**.
  
    > [!NOTE]
    > Seleccione **Vista clásica** en la parte superior derecha para ver el registro TXT que creó.  

1. Si hay otros registros MX, elimínelos todos seleccionando la herramienta de edición y, a continuación, **elimine** para cada registro. 
  
## <a name="add-the-cname-record-required-for-microsoft"></a>Agregar el registro CNAME necesario para Microsoft

1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). Se le pedirá que inicie sesión.
  
1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. Active la casilla situada junto al dominio que desea modificar.
  
1. En **Acciones**, seleccione los tres puntos y, a continuación, **seleccione Administrar** en la lista desplegable.

    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::
  
1. Seleccione **Herramientas avanzadas** y, junto a Registros DNS **avanzados,** seleccione **ADMINISTRAR**.
    
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

    Es posible que tenga que **seleccionar Continuar** para ir a la página Administrar registros DNS avanzados.

1. En la página Administrar registros DNS avanzados, seleccione **+AGREGAR REGISTRO**.

1. En **Tipo**, seleccione **CNAME** en la lista desplegable.
  
1. En los cuadros del registro CNAME, escriba o copie y pegue los valores de la tabla siguiente.
    
    |**Se refiere a | Nombre de host**|**Alias para**| **TTL** |
    |:-----|:-----|:-----|:-----|
    |Otro host| autodescubrir  <br/> | autodiscover.outlook.com Este **valor NO PUEDE terminar con un punto (.)** <br/> 1 Hour  <br/> |
  
1. Seleccione **AGREGAR**.

    > [!NOTE]
    > Seleccione **Vista clásica** en la parte superior derecha para ver el registro que creó.  
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores. 
  
1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). Se le pedirá que inicie sesión.
  
1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. Active la casilla situada junto al dominio que desea modificar.
    
1. En **Acciones**, seleccione los tres puntos y, a continuación, **seleccione Administrar** en la lista desplegable.
 
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::
 
1. Seleccione **Herramientas avanzadas** y, junto a Registros DNS **avanzados,** seleccione **ADMINISTRAR**.
    
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

    Es posible que tenga que **seleccionar Continuar** para ir a la página Administrar registros DNS avanzados.

1. En la página Administrar registros DNS avanzados, seleccione **+AGREGAR REGISTRO**.

1. En **Tipo**, seleccione **TXT** en la lista desplegable.

1. In the boxes for the new record, type or copy and paste the following values.
    
    |**Hace referencia a**|**Valor TXT**| **TTL**
    |:-----|:-----|:-----|
    |@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto. | 1 Hour  <br/> |
       
1. Seleccione **AGREGAR**.
  
    > [!NOTE]
    > Seleccione **Vista clásica** en la parte superior derecha para ver el registro que creó.  
  
## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial servicios de comunicación en línea como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita 4 registros: 2 registros SRV para la comunicación de usuario a usuario y 2 registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-the-two-required-srv-records"></a>Agregar los dos registros SRV necesarios

1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). Se le pedirá que inicie sesión.
  
1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. Active la casilla situada junto al dominio que desea modificar.
    
1. En **Acciones**, seleccione los tres puntos y, a continuación, **seleccione Administrar** en la lista desplegable.
  
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Seleccione **Herramientas avanzadas** y, junto a Registros DNS **avanzados,** seleccione **ADMINISTRAR**.
    
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

    Es posible que tenga que **seleccionar Continuar** para ir a la página Administrar registros DNS avanzados.

1. En la página Administrar registros DNS avanzados, seleccione **+AGREGAR REGISTRO**.

1. En los cuadros de los dos nuevos registros, escriba (o copie y pegue) los valores de la tabla siguiente.
    
    (Elija los valores **Servicio** y **Protocolo** de las listas desplegables). 
    
    | **Tipo** |**Servicio**|**Protocolo**|**Grosor**|**Puerto**|**Destino**|**Prioridad**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    | SRV |_sip  <br/> |_tls  <br/> |100  <br/> |443  <br/> |sipdir.online.lync.com  <br/> **Este valor NO PUEDE finalizar con un punto (.)** <br/> | 1  <br/> | 1 hora  <br/> |
    | SRV |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> **Este valor NO PUEDE finalizar con un punto (.)** <br/> |1  <br/> | 1 Hour  <br/> |
  
1. Seleccione **AGREGAR**.
 
    > [!NOTE]
    > Seleccione **Vista clásica** en la parte superior derecha para ver el registro que creó.  

1. Agregue el otro registro SRV eligiendo los valores de la segunda fila de la tabla.
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 

### <a name="add-the-two-required-cname-records"></a>Agregar los dos registros CNAME necesarios 
    
1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). Se le pedirá que inicie sesión.
  
1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. Active la casilla situada junto al dominio que desea modificar.
    
1. En **Acciones**, seleccione los tres puntos y, a continuación, **seleccione Administrar** en la lista desplegable.
 
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::
 
1. Seleccione **Herramientas avanzadas** y, junto a Registros DNS **avanzados,** seleccione **ADMINISTRAR**.
    
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

    Es posible que tenga que **seleccionar Continuar** para ir a la página Administrar registros DNS avanzados.

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.
    
1. Agregue el primer registro CNAME.
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    | **Tipo**|**Se refiere a | Nombre de host**|**Alias para**| **TTL** |
    |:-----|:-----|:-----|:-----|:-----|
    | CNAME | Otro host | sip  <br/> |sipdir.online.lync.com  <br/> **Este valor NO PUEDE finalizar con un punto (.)** <br/> |1 hora  <br/> |
    | CNAME| Otro host | lyncdiscover  <br/> |webdir.online.lync.com  <br/> **Este valor NO PUEDE finalizar con un punto (.)** <br/> | 1 Hour  <br/> |
   
1. Seleccione **AGREGAR**.
 
    > [!NOTE]
    > Seleccione **Vista clásica** en la parte superior derecha para ver el registro que creó.  
   
1. Agregue el otro registro CNAME eligiendo los valores de la segunda fila de la tabla.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Opción avanzada: Intune y Administración de dispositivos móviles para Microsoft 365

Este servicio le ayuda a proteger y administrar de forma remota dispositivos móviles que se conectan a su dominio. Mobile Device Management necesita 2 registros CNAME para que los usuarios puedan inscribir dispositivos en el servicio.

### <a name="add-the-two-required-cname-records"></a>Agregar los dos registros CNAME necesarios

1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). Se le pedirá que inicie sesión.
  
1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. Active la casilla situada junto al dominio que desea modificar.
    
1. En **Acciones**, seleccione los tres puntos y, a continuación, **seleccione Administrar** en la lista desplegable.
 
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::
 
1. Seleccione **Herramientas avanzadas** y, junto a Registros DNS **avanzados,** seleccione **ADMINISTRAR**.
    
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

    Es posible que tenga que **seleccionar Continuar** para ir a la página Administrar registros DNS avanzados.

1. En la página Administrar registros DNS avanzados, seleccione **+AGREGAR REGISTRO**.
  
1. Agregue el primer registro CNAME.
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    | **Tipo**|**Se refiere a | Nombre de host**|**Alias para**| **TTL** |
    |:-----|:-----|:-----|:-----|:-----|
    | CNAME | Otro host | enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> **Este valor NO PUEDE finalizar con un punto (.)** <br/> | 1 hora  <br/> |
    | CNAME | Otro host |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> **Este valor NO PUEDE finalizar con un punto (.)** <br/> | 1 Hour  <br/> |
   
1. Seleccione **AGREGAR**.
  
    > [!NOTE]
    > Seleccione **Vista clásica** en la parte superior derecha para ver el registro que creó.  

1. Agregue el otro registro CNAME eligiendo los valores de la segunda fila de la tabla.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).
  

  
