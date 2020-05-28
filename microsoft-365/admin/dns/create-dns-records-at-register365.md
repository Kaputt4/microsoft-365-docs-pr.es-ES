---
title: Crear registros DNS en Register365 para Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Register365 para Microsoft.
ms.openlocfilehash: e580779ce674375564c1b3ab6123ef1b19f50be0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400321"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a>Crear registros DNS en Register365 para Microsoft

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Si Register365 es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc. 
  
Estos son los registros principales que es necesario agregar.  
  
- [Agregar un registro TXT para verificación](#add-a-txt-record-for-verification)
    
- [Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Agregar los seis registros CNAME necesarios para Microsoft](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Agregar los dos registros SRV necesarios para Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Después de agregar estos registros a Microsoft, su dominio estará configurado para trabajar con los servicios de Microsoft.
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_verify"> </a>

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable. 
    
    (You may have to scroll down.)
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).
    
    (You may have to scroll down.)
    
    |**Nombre de host**|**Tipo**|**Resultado**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla.           [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Especificar valores en la página Agregar o modificar zona DNS](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. Haga clic en **Guardar**.
    
    (You may have to scroll down.)
    
    ![Seleccione Guardar](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.
    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
    
  
3. En la página de **Configuración**, elija ** Iniciar configuración**.
    
    
  
4. En la página**verificar dominio**, seleccione **verificar**.
    
    
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft
<a name="BKMK_add_MX"> </a>

1. Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable. 
    
    (You may have to scroll down.)
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. En la página **Add/Modify DNS Zone** (Agregar o modificar zona DNS), en la sección **Mail exchange records** (Registros Mail eXchange), en los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente. 
    
    (You may have to scroll down.)
    
    |**Nombre de host**|**Prioridad**|**Resultado**|
    |:-----|:-----|:-----|
    |(Deje este campo en blanco).  <br/> |1   <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*. mail.protection.outlook.com  <br/> **Nota:** Obtén tu *\<domain-key\>* cuenta de Microsoft.  [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Especificar valores en la página Agregar o modificar zona DNS](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. Haga clic en **Guardar**.
    
    (You may have to scroll down.)
    
    ![Seleccione Guardar](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. Si hay otros registros MX en la sección **Mail exchange records** (Registros Mail eXchange), elimínelos. Para hacerlo, selecciónelos y, después, pulse la tecla **Suprimir** en el teclado. 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. Haga clic en **Guardar**.
    
    (You may have to scroll down.)
    
    ![Seleccione Guardar](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Agregar los seis registros CNAME necesarios para Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable. 
    
    (You may have to scroll down.)
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. En la página **Add/Modify DNS Zone** (Agregar o modificar zona DNS), en la sección **A, CNAME, AAAA, TXT and NS records** (Registros A, CNAME, AAAA, TXT y NS), en los cuadros para los registros nuevos, escriba o copie y pegue los valores de la tabla siguiente. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).
    
    (Es posible que tenga que desplazarse hacia abajo).
    
    |****Nombre de host****|****Tipo****|****Resultado****|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |EnterpriseEnrollment-s.manage.microsoft.com  <br/> |
   
    ![Especificar valores en la página Agregar o modificar zona DNS](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. Haga clic en **Guardar**.
    
    ![Seleccione Guardar](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores. 
  
1. Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable. 
    
    (You may have to scroll down.)
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).
    
    (You may have to scroll down.)
    
    |**Nombre de host**|**Tipo**|**Resultado**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |
   
    ![Especificar valores en la página Agregar o modificar zona DNS](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. Haga clic en **Guardar**.
    
    (You may have to scroll down.)
    
    ![Seleccione Guardar](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Agregar los dos registros SRV necesarios para Microsoft
<a name="BKMK_add_SRV"> </a>

1. Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable. 
    
    (You may have to scroll down.)
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. En la página **Add/Modify DNS Zone** (Agregar o modificar zona DNS), en la sección **Service records** (Registros de servicio), en los cuadros de los registros nuevos, escriba o copie y pegue los valores de la tabla siguiente. 
    
    (Es posible que tenga que desplazarse hacia abajo).
    
    |**Nombre**|**Prioridad**|**Grosor**|**Puerto**|**Resultado**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls. _tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Introducción de valores en la sección de registros de servicio](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. Haga clic en **Guardar**.
    
    (You may have to scroll down.)
    
    ![Seleccione Guardar](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
