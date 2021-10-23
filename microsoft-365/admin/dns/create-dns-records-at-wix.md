---
title: Conectar los registros DNS en Wix para Microsoft 365
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Aprenda a comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en Wix para Microsoft.
ms.openlocfilehash: ba5b814278c601c6fd6e9599075d4e297b87db58
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557049"
---
# <a name="connect-your-dns-records-at-wix-to-microsoft-365"></a>Conectar los registros DNS en Wix para Microsoft 365

**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
Si Wix es su proveedor de hospedaje DNS, siga los pasos de este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online, y así sucesivamente.

Después de agregar estos registros en Wix, el dominio se configurará para que funcione con servicios Microsoft.
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
 
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 

> [!NOTE]
> WIX no admite entradas DNS para subdominios.
  
1. Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .
    
2. Seleccione **Dominios**  >  **...** y, a continuación, **seleccione Administrar** registros DNS en la lista desplegable. 

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="Seleccione Administrar registros DNS en la lista desplegable.":::
    
3. Seleccione **+ Agregar registro** en la fila TXT **(texto)** del editor DNS. 
    
4. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente. 
    
   ||||
   |:-----|:-----|:-----|
   | **Nombre de host **<br/> | **Valor TXT** <br/> | **TTL** <br/> |
   |Rellenado automáticamente (dejar en blanco)  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla.  [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|1 hora <br/> |          |
   
5. Seleccione **Guardar**. 
    
6. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro. Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio. 

Para comprobar el registro en Microsoft 365:
  
1. En el Centro de administración, vaya a **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Domains**</a>.
    
2. En la página Dominios, seleccione el dominio que está comprobando y seleccione **Iniciar instalación**.   
  
3. En la página **verificar dominio**, seleccione **verificar**.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft

1. Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .
    
1. Seleccione **Dominios**  >  **...** y, a continuación, **seleccione Administrar** registros DNS en la lista desplegable. 
    
   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="Seleccione Administrar registros DNS en la lista desplegable.":::

1. En **MX (Intercambio de correo),** seleccione **Editar registros MX**. 

1. Elija **Otro** en la lista desplegable y seleccione **+ Agregar registro**.
    
1. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente:
    
   | **Host Name** | **Señala a** | **Prioridad** | **TTL** |
   |:-----|:-----|:-----|:-----|
   |Rellenado automáticamente <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Nota:** Obtener el  *\<domain-key\>*  de su cuenta de Microsoft.   [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md) |0  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml) | 1 hora|
   
1. Si hay otros registros MX enumerados, elimine cada uno de ellos. 
    
6. Seleccione **Guardar**.
    
## <a name="add-the-cname-record-required-for-microsoft"></a>Agregar el registro CNAME necesario para Microsoft

1. Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .
    
2. Seleccione **Dominios**  >  **...** y, a continuación, **seleccione Administrar** registros DNS en la lista desplegable. 

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="Seleccione Administrar registros DNS en la lista desplegable.":::

3. Seleccione **+ Agregar otro en** la fila **CNAME (Alias)** del editor DNS para el registro CNAME. 
    
4. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente:
    
   | **Nombre de host** | **Valor** | **TTL** |
   |:-----|:-----|:-----|
   |autodescubrir  <br/> |autodiscover.outlook.com  <br/> |1 hora  <br/> |
   
5. Seleccione **Guardar**. 
    
6. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores.  
  
1. Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .
    
2. Seleccione **Dominios**  >  **...** y, a continuación, **seleccione Administrar** registros DNS en la lista desplegable. 

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="Seleccione Administrar registros DNS en la lista desplegable.":::
    
3. Seleccione **+ Agregar registro** en la fila TXT **(texto)** del editor DNS. 

   **Nota:** Wix proporciona una fila SPF en el editor DNS. Ignore esa fila y use la **fila TXT (Text)** para escribir los valores de SPF siguientes. 
    
4. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente:
    
   | **Nombre de host** | **Valor** | **TTL** |
   |:-----|:-----|:-----|
   |[Deje esto en blanco]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.<br/> | 1 Hour |
   
5. Seleccione **Guardar**. 
    
6. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.

## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial servicios de comunicación en línea como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita 4 registros: 2 registros SRV para la comunicación de usuario a usuario y 2 registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-the-two-required-srv-records"></a>Agregar los dos registros SRV necesarios

1. Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .
    
1. Seleccione **Dominios**  >  **...** y, a continuación, **seleccione Administrar** registros DNS en la lista desplegable. 
 
   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="Seleccione Administrar registros DNS en la lista desplegable.":::
   
1. Seleccione **+ Agregar registro** en la fila **SRV** del editor DNS. 
 
1. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla:
    
   | **Servicio** | **Protocolo** | **Nombre** | **Grosor** | **Puerto** | **Destino** | **Prioridad** | **TTL** |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |sip  |tls  |Rellenado automáticamente |1  |443   |sipdir.online.lync.com |100 |1 Hour |
   |sipfed|tcp |Rellenado automáticamente|1 |5061 |sipfed.online.lync.com|100 | 1 Hour |
   
1. Seleccione **Guardar**. 
  
1. Agregue el otro registro SRV eligiendo los valores de la segunda fila de la tabla.
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 

### <a name="add-the-two-required-cname-records"></a>Agregar los dos registros CNAME necesarios 

1. Seleccione **+ Agregar otro en** la fila **CNAME (Alias)** del editor DNS y escriba los valores de la primera fila de la tabla siguiente. 
    
   |**Tipo**|**Host**|**Valor**|**TTL**|
   |:-----|:-----|:-----|:-----|
   |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |1 hora  <br/> |
   |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |1 Hour  <br/> |
  
1. Seleccione **Guardar**.
  
1. Agregue el otro registro CNAME eligiendo los valores de la segunda fila de la tabla.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Opción avanzada: Intune y Administración de dispositivos móviles para Microsoft 365

Este servicio le ayuda a proteger y administrar de forma remota dispositivos móviles que se conectan a su dominio. Mobile Device Management necesita dos registros CNAME para que los usuarios puedan inscribir dispositivos en el servicio.

### <a name="add-the-two-required-cname-records"></a>Agregar los dos registros CNAME necesarios

1. Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .
    
2. Seleccione **Dominios**  >  **...** y, a continuación, **seleccione Administrar** registros DNS en la lista desplegable. 

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="Seleccione Administrar registros DNS en la lista desplegable.":::

3. Seleccione **+ Agregar otro en** la fila **CNAME (Alias)** del editor DNS y escriba los valores de la primera fila de la tabla siguiente. 
    
    |**Tipo**|**Host**|**Valor**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |enterpriseregistration <br/> |enterpriseregistration.windows.net.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |1 hora  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |1 Hour  <br/> |
  
1. Seleccione **Guardar**.
  
1. Agregue el otro registro CNAME eligiendo los valores de la segunda fila de la tabla.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).
  
