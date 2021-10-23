---
title: Conectar los registros DNS en GoDaddy para Microsoft 365
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Aprenda a comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en GoDaddy para Microsoft.
ms.openlocfilehash: 0db80de3ca34f34eaaaa8952f2b49c2c8da62046
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60556906"
---
# <a name="connect-your-dns-records-at-godaddy-to-microsoft-365"></a>Conectar los registros DNS en GoDaddy para Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Si GoDaddy es su proveedor de hosting DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.

## <a name="before-you-begin"></a>Antes de empezar

Tiene dos opciones para configurar registros DNS para su dominio:

- [**Usar dominio Conectar**](#use-domain-connect-to-verify-and-set-up-your-domain) Si no ha configurado el dominio con otro proveedor de servicios de correo electrónico, siga los pasos de Dominio Conectar para comprobar y configurar automáticamente el nuevo dominio para usarlo con Microsoft 365. 

OR

- [**Siga los pasos manuales**](#create-dns-records-with-manual-setup) Compruebe el dominio con los pasos manuales siguientes y elija cuándo y qué registros agregar al registrador de dominio. Esto le permite configurar nuevos registros MX (correo), por ejemplo, a su conveniencia. 

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>Usar dominio Conectar para comprobar y configurar el dominio

Siga estos pasos para comprobar y configurar automáticamente el dominio de Cloudflare con Microsoft 365:

1. En el Centro de administración de Microsoft 365, seleccione **Configuración**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**dominios**</a>y seleccione el dominio que desea configurar.

1. Seleccione los tres puntos (más acciones) > elija **Iniciar configuración**.

1. On the How do you want to connect your domain? página, seleccione **Continuar**.   

1. En la página Agregar registros DNS, seleccione **Agregar registros DNS**.

1. En la página de inicio de sesión de Cloudflare, inicie sesión en su cuenta y seleccione **Autorizar**.
    
    Esto completa la configuración de dominio para Microsoft 365. 

## <a name="create-dns-records-with-manual-setup"></a>Crear registros DNS con configuración manual

Después de agregar estos registros en GoDaddy, el dominio se configurará para que funcione con servicios Microsoft.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.

> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.

1. Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Es posible que se le pida que inicie sesión.

1. En **Dominios**, seleccione los tres puntos junto al dominio que desea comprobar y, a continuación, **seleccione Administrar DNS**.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

1. En **Registros**, seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="Seleccione AGREGAR.":::

1. Choose **TXT (Text)** from the drop-down list. 

1. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla.

    |**Tipo de registro** |**Host**|**Valor TXT**|**TTL** |
    |:-----|:-----|:-----|:-----|
    |TXT (texto)|@|MS=ms *XXXXXXXX*<br>**Nota:** Este es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|1 hora  <br>(Seleccione un valor de la lista desplegable).|

1. Seleccione **Guardar**.

1. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.

Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro. Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
Para comprobar el registro en Microsoft 365:
  
1. En el Centro de administración, vaya a **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Domains**</a>.
    
2. En la página Dominios, seleccione el dominio que está comprobando y seleccione **Iniciar instalación**.   
  
3. En la página **verificar dominio**, seleccione **verificar**.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft

1. Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Es posible que se le pida que inicie sesión.

2. En **Dominios**, seleccione los tres puntos junto al dominio que desea comprobar y, a continuación, **seleccione Administrar DNS**.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

3. En **Registros**, seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="Seleccione AGREGAR.":::

4. Elija **MX (Agente de intercambio de correo)** de la lista desplegable.

5. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

    (Elija el **valor TTL** de la lista desplegable).

    |**Tipo de registro**|**Host**|**Señala a**|**Prioridad**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX (intercambiador de correo)  <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Nota:** Obtener el  *\<domain-key\>*  de su cuenta de Microsoft.           [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml) <br/> |1 hora  <br/> |

6. Seleccione **Guardar**.

### <a name="add-the-cname-record-required-for-microsoft"></a>Agregar el registro CNAME necesario para Microsoft

1. Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Se le pedirá que inicie sesión.

2. En **Dominios**, seleccione los tres puntos junto al dominio que desea comprobar y, a continuación, **seleccione Administrar DNS**.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

3. En **Registros**, seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="Seleccione AGREGAR.":::

4. Elija **CNAME (Alias)** de la lista desplegable.

5. Cree el primer registro CNAME.

    En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.

    (Elija el **valor TTL** de la lista desplegable).

    |**Tipo de registro**|**Host**|**Señala a**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME (alias)  <br/> |autodescubrir <br/> |autodiscover.outlook.com  <br/> |1 hora  <br/> |

6. Seleccione **Guardar**.

### <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores.

1. Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Es posible que se le pida que inicie sesión.

2. En **Dominios**, seleccione los tres puntos junto al dominio que desea comprobar y, a continuación, **seleccione Administrar DNS**.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

3. En **Registros**, seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="Seleccione AGREGAR.":::

4. Choose **TXT (Text)** from the drop-down list.

5. In the boxes for the new record, type or copy and paste the following values.

    (Elija el **valor TTL** de las listas desplegables).

    |**Tipo de registro**|**Host**|**Valor TXT**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT (texto)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |1 hora  <br/> |

6. Seleccione **Guardar**.

## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial servicios de comunicación en línea como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita 4 registros: 2 registros SRV para la comunicación de usuario a usuario y 2 registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-the-two-required-srv-records"></a>Agregar los dos registros SRV necesarios

1. Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Es posible que se le pida que inicie sesión.

1. En **Dominios**, seleccione los tres puntos junto al dominio que desea comprobar y, a continuación, **seleccione Administrar DNS**.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

1. En **Registros**, seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="Seleccione AGREGAR.":::

1. Elija **SRV (Servicio)** en la lista desplegable.

1. Cree el primer registro SRV.

    En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.

    (Elija los **valores Record type** y **TTL** de las listas desplegables).

    |**Tipo de registro**|**Nombre**|**Destino**|**Protocolo**|**Servicio**|**Prioridad**|**Grosor**|**Puerto**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (servicio)  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hora  <br/> |
    |SRV (servicio)  <br/> |@  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 hora  <br/> |

1. Seleccione **Guardar**.

1. Agregue el otro registro SRV eligiendo los valores de la segunda fila de la tabla.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-the-two-required-cname-records"></a>Agregar los dos registros CNAME necesarios
  
1. Seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="Seleccione AGREGAR.":::

1. Elija **CNAME** en la lista desplegable.

1. En los cuadros vacíos de los nuevos registros, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.
    
    |**Tipo**|**Host**|**Valor**|**TTL**|
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

1. Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled). Es posible que se le pida que inicie sesión.

1. En **Dominios**, seleccione los tres puntos junto al dominio que desea comprobar y, a continuación, **seleccione Administrar DNS**.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

1. En **Registros**, seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="Seleccione AGREGAR.":::

1. Elija **CNAME (Alias)** de la lista desplegable.
  
1. En los cuadros vacíos de los nuevos registros, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.
    
    |**Tipo**|**Host**|**Valor**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |1 hora  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |1 Hour  <br/> |
  
1. Seleccione **Guardar**. 
  
1. Agregue el otro registro CNAME eligiendo los valores de la segunda fila de la tabla.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).
