---
title: Conectar los registros DNS en 123-reg.co.uk a Microsoft 365
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Aprenda a comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en 123-reg.co.uk microsoft.
ms.openlocfilehash: 2c9e917a7c63759d69e58ffda4dc8a35c76d04ca
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60556966"
---
# <a name="connect-your-dns-records-at-123-regcouk-to-microsoft-365"></a>Conectar los registros DNS en 123-reg.co.uk a Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
Si 123-reg.co.uk es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.
  
Después de agregar estos registros en 123-reg.co.uk, el dominio se configurará para que funcione con servicios Microsoft. 
  
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .
    
2. En la página Introducción al nombre de dominio, seleccione el nombre del dominio que desea comprobar. 
    
   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="Seleccione el dominio que desea comprobar.":::

3. En la página Administrar dominio, en **Configuración avanzada del dominio,** elija **Administrar DNS**.
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::
  
4. En la página Administrar su DNS, seleccione la **pestaña DNS** avanzado. 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="Seleccione la pestaña DNS avanzado.":::
  
5. En el **cuadro** Tipo del nuevo registro, elija **TXT/SPF** en la lista desplegable y, a continuación, escriba o copie y pegue los demás valores de la tabla siguiente. 
    
    ||||
    |:-----|:-----|:-----|
    |**Nombre de host** <br/> |**Tipo** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
   
6. Elija **Agregar**.
    
7. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará una búsqueda para el registro. Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
Para comprobar el registro en Microsoft 365:
  
1. En el Centro de administración, vaya a **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Domains**</a>.
    
2. En la página Dominios, seleccione el dominio que está comprobando y seleccione **Iniciar instalación**.   
  
3. En la página **verificar dominio**, seleccione **verificar**.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft

1. Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .
    
2. On the Domain name overview page, select the name of the domain that you want to edit. 
    
   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="Seleccione el nombre del dominio que desea editar.":::

3. En la página Administrar dominio, en **Configuración avanzada del dominio,** elija **Administrar DNS**.
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::
  
4. En la página Administrar su DNS, seleccione la **pestaña DNS** avanzado. 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="Seleccione la pestaña DNS avanzado.":::
    
5. En el **cuadro** Tipo del nuevo registro, elija **MX** en la lista desplegable y, a continuación, escriba o copie y pegue los demás valores de la tabla siguiente. 
    
    |**Nombre de host**|**Tipo**|**Prioridad**|**MX de destino**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml) <br/> | *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **Este valor DEBE terminar en punto (.)** <br/> **Nota:** Obtenga la \<domain-key\> desde su cuenta de Microsoft. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
  
6. Elija **Agregar**.
  
7. Si hay otros registros MX, quítelos (para hacerlo, elija el icono **Eliminar [papelera]** de ese registro). 
  
## <a name="add-the-cname-record-required-for-microsoft"></a>Agregar el registro CNAME necesario para Microsoft

1. Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .
    
2. On the Domain name overview page, select the name of the domain that you want to edit. 
    
   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="Seleccione el nombre del dominio que desea editar.":::

3. En la página Administrar dominio, en **Configuración avanzada del dominio,** elija **Administrar DNS**.
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::
  
4. En la página Administrar su DNS, seleccione la **pestaña DNS** avanzado. 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="Seleccione la pestaña DNS avanzado.":::
    
5. Agregue el registro CNAME.
    
    En el **cuadro Tipo** del nuevo registro, elija **CNAME** en la lista desplegable y, a continuación, escriba o copie y pegue los demás valores de la tabla siguiente. 
    
    |**Nombre de host**|**Tipo**|**CNAME de destino**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |
  
6. Seleccione **Agregar**.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro SPF para su dominio, no cree uno nuevo para Microsfot. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores. ¿Necesita ejemplos? Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](../../enterprise/external-domain-name-system-records.md). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml). 
  
1. Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .
    
2. On the Domain name overview page, select the name of the domain that you want to edit. 
    
   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="Seleccione el nombre del dominio que desea editar.":::

3. En la página Administrar dominio, en **Configuración avanzada del dominio,** elija **Administrar DNS**.
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::
  
4. En la página Administrar su DNS, seleccione la **pestaña DNS** avanzado. 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="Seleccione la pestaña DNS avanzado.":::
    
5. En el **cuadro** Tipo del nuevo registro, elija **TXT/SPF** en la lista desplegable y, a continuación, escriba o copie y pegue los demás valores de la tabla siguiente.
    
    |**Nombre de host**|**Tipo**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |
  
6. Seleccione **Agregar**.

## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial servicios de comunicación en línea como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita 4 registros: 2 registros SRV para la comunicación de usuario a usuario y 2 registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-the-two-required-srv-records"></a>Agregar los dos registros SRV necesarios

1. Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .
    
2. On the Domain name overview page, select the name of the domain that you want to edit. 
    
   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="Seleccione el nombre del dominio que desea editar.":::

3. En la página Administrar dominio, en **Configuración avanzada del dominio,** elija **Administrar DNS**.
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::
  
4. En la página Administrar su DNS, seleccione la **pestaña DNS** avanzado. 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="Seleccione la pestaña DNS avanzado.":::
    
5. Agregue el primero de los dos registros SRV:
    
   En el **cuadro** Tipo del nuevo registro, elija **SRV** en la lista desplegable y, a continuación, escriba o copie y pegue los demás valores de la tabla siguiente.
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |**Nombre de host**|**Tipo**|**Prioridad**|**TTL**|**SRV de destino**|
    |_sip._tls|SRV|100|3600|1 443 sipdir.online.lync.com. **Este valor DEBE terminar en punto (.)**<br> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |
    |_sipfederationtls._tcp|SRV|100|3600|1 5061 sipfed.online.lync.com. **Este valor DEBE terminar en punto (.)** <br> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |
  
6. Seleccione **Agregar**.
  
7. Para agregar el otro registro SRV.
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 

### <a name="add-the-two-required-cname-records"></a>Agregar los dos registros CNAME necesarios 
    
1. Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .

1. On the Domain name overview page, select the name of the domain that you want to edit. 
    
   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="Seleccione el nombre del dominio que desea editar.":::

1. En la página Administrar dominio, en **Configuración avanzada del dominio,** elija **Administrar DNS**.
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::
  
1. En la página Administrar su DNS, seleccione la **pestaña DNS** avanzado. 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="Seleccione la pestaña DNS avanzado.":::
    
1. Agregue el primer registro CNAME.
    
    En el **cuadro Tipo** del nuevo registro, elija **CNAME** en la lista desplegable y, a continuación, escriba o copie y pegue los demás valores de la tabla siguiente.
    
    | **Nombre de host** |**Tipo**|**CNAME de destino**|
    |:-----|:-----|:-----|
    |sip  <br/>|CNAME  <br/> |sipdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |
    |lyncdiscover  <br/>|CNAME  <br/> |webdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |
  
1. Seleccione **Agregar**.
  
1. Agregue el otro registro CNAME.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Opción avanzada: Intune y Administración de dispositivos móviles para Microsoft 365

Este servicio le ayuda a proteger y administrar de forma remota dispositivos móviles que se conectan a su dominio. Mobile Device Management necesita dos registros CNAME para que los usuarios puedan inscribir dispositivos en el servicio.

### <a name="add-the-two-required-cname-records"></a>Agregar los dos registros CNAME necesarios

1. Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .

2. On the Domain name overview page, select the name of the domain that you want to edit. 
    
   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="Seleccione el nombre del dominio que desea editar.":::

3. En la página Administrar dominio, en **Configuración avanzada del dominio,** elija **Administrar DNS**.
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::
  
4. En la página Administrar su DNS, seleccione la **pestaña DNS** avanzado. 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="Seleccione la pestaña DNS avanzado.":::
    
1. Agregue el primer registro CNAME.
    
    En el **cuadro Tipo** del nuevo registro, elija **CNAME** en la lista desplegable y, a continuación, escriba o copie y pegue los demás valores de la tabla siguiente.
    
 | **Nombre de host**|**Tipo**|**CNAME de destino**|
    |:-----|:-----|:-----|
    | enterpriseregistration <br/> | CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |
    |enterpriseenrollment  <br/> | CNAME  <br/> |enterpriseenrollment.manage.microsoft.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |
  
1. Seleccione **Agregar**.
  
1. Agregue el otro registro CNAME.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).
  
