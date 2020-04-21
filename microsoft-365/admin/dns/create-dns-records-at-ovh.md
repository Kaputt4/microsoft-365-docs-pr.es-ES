---
title: Crear registros DNS en OVH para Microsoft
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en OVH para Microsoft.
ms.openlocfilehash: 01c455f54a7ee2efc6114dba1c01170b97ea5f71
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629292"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a>Crear registros DNS en OVH para Microsoft

[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md) si no encuentra lo que busca. 
  
Si OVH es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.
  
Estos son los registros principales que es necesario agregar. 
  
- [Crear registros DNS en OVH para Microsoft](#create-dns-records-at-ovh-for-microsoft)
    
- [Agregar un registro MX para que el correo electrónico del dominio llegue a Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Agregar los registros CNAME necesarios para Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Agregar los dos registros SRV necesarios para Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Después de agregar estos registros a OVH, su dominio estará configurado para funcionar con los servicios de Microsoft.
  
Para obtener más información sobre WebHosting y DNS para sitios web con Microsoft, vea [usar un sitio web público con Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="bkmk_txt"> </a>

Antes de usar el dominio con Microsoft, debemos asegurarnos de que es el propietario. Su capacidad para iniciar sesión en su cuenta en el registrador de dominios y crear el registro DNS es la que se demuestre a Microsoft que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. En **dominios**, seleccione el nombre del dominio que desea editar.
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Seleccione **zona DNS**.
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Seleccione **Agregar una entrada**.
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Seleccionar **txt**
    
    ![OVH seleccione la entrada TXT](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente. Para asignar un valor TTL, elija **personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto. 
    
    |**Tipo de registro**|**Subdominio**|**TTL**|**Valor**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(se deja en blanco)  <br/> |3600 (segundos)  <br/> |MS = msxxxxxxxx  <br/> **Nota:** esto es un ejemplo. Use aquí su **destino específico o** el valor de dirección de destino de la tabla.           [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Seleccione **confirmar**. 
    
    ![OVH confirmar TXT para verificación](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará el dominio.
  
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.
    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
    
  
3. En la página de **Configuración**, elija ** Iniciar configuración**.
    
    
  
4. En la página**verificar dominio**, seleccione **verificar**.
    
    
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio llegue a Microsoft
<a name="bkmk_mx"> </a>

1. Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. En **dominios**, seleccione el nombre del dominio que desea editar.
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Seleccione **zona DNS**.
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Seleccione **Agregar una entrada**.
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Seleccione **mx**.
    
    ![Tipo de registro MX de OVH](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente. Para asignar un valor TTL, elija **personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto. 
    
    > [!NOTE]
    > De forma predeterminada OVH usa la notación relativa para el destino, que agrega el nombre de dominio al final del registro de destino. Para usar la notación absoluta en su lugar, agregue un punto al registro de destino, como se muestra en la siguiente tabla. 
  
    |**Tipo de registro**|**Subdominio**|**TTL**|**Prioridad**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(se deja en blanco)  <br/> |3600 (segundos)  <br/> |10   <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |\<Domain-Key\>. mail.Protection.Outlook.com.  <br/> **Nota:** Obtén tu * \<clave\> de dominio* de tu cuenta de Microsoft.  [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH registro MX para correo](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. Seleccione **Siguiente**.
    
    ![OVH registro MX Seleccione siguiente](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. Seleccione **confirmar**.
    
    ![OVH seleccionar confirmar registro MX](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. Si hay otros registros MX, elimínelos en la lista de la página **zona DNS** . Seleccione cada registro y, a continuación, en la columna **acciones** , seleccione el icono de papelera de **eliminación** . 
    
    ![Eliminar registro MX de OVH](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. Seleccione **confirmar**.
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Agregar los registros CNAME necesarios para Microsoft
<a name="bkmk_cname"> </a>

1. Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. En **dominios**, seleccione el nombre del dominio que desea editar.
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Seleccione **zona DNS**.
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Seleccione **Agregar una entrada**.
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Seleccione **CNAME**.
    
    ![OVH agregar tipo de registro CNAME](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. Cree el primer registro CNAME.
    
    En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente. Para asignar un valor TTL, elija **personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto. 
    
    |**Tipo de registro**|**Subdominio**|**Destino**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |de 3600 segundos  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> |de 3600 segundos  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |de 3600 segundos  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |de 3600 segundos  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |de 3600 segundos  <br/> |
   
    ![Registro CNAME de OVH](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. Seleccione **Siguiente**.
    
    ![OVH agregar valores CNAME y seleccionar siguiente](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. Seleccione **confirmar**.
    
9. Repita los pasos anteriores para crear los otros cinco registros CNAME.
    
    Para cada registro, escriba (o copie y pegue) los valores de la siguiente fila de la tabla anterior en los cuadros para ese registro.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores. 
  
1. Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. En **dominios**, seleccione el nombre del dominio que desea editar.
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Seleccione **zona DNS**.
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Seleccione **Agregar una entrada**.
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Seleccione **txt**.
    
6. In the boxes for the new record, type or copy and paste the following values.
    
    |**Tipo de registro**|**Subdominio**|**TTL**|**Valor TXT**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(se deja en blanco)  <br/> |3600 (segundos)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |
   
    ![OVH agregar registro TXT para SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. Seleccione **Siguiente**.
    
    ![OVH agregar registro TXT para SPF y seleccionar siguiente](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. Seleccione **confirmar**.
    
    ![OVH agregar registro TXT para SPF y confirmar](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Agregar los dos registros SRV necesarios para Microsoft
<a name="bkmk_srv"> </a>

1. Para empezar, vaya a su página de dominios en OVH a través de [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. En **dominios**, seleccione el nombre del dominio que desea editar.
    
    ![OVH Seleccione el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Seleccione **zona DNS**.
    
    ![OVH seleccionar la zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Seleccione **Agregar una entrada**.
    
    ![Agregar una entrada a OVH](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Seleccione **SRV**.
    
    ![OVH Seleccione el tipo de registro SRV](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. Cree el primer registro SRV.
    
    En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente. Para asignar un valor TTL, elija **personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto. 
    
    |**Tipo de registro**|**Subdominio**|**Prioridad**|**Grosor**|**Puerto**|**TTL**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (servicio)  <br/> |_sip. _tls  <br/> |100  <br/> |1  <br/> |443  <br/> |3600 (segundos)  <br/> |sipdir.online.lync.com.  <br/> |
    |SRV (servicio)  <br/> |_sipfederationtls. _tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |3600 (segundos)  <br/> |sipfed.online.lync.com.  <br/> |
       
    ![Registro SRV de OVH](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. Seleccione **Siguiente**.
    
    ![OVH de la selección de registro SRV siguiente](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. Seleccione **confirmar**.
    
9. Repita los pasos anteriores para crear el otro registro SRV. Copie y pegue los valores de la segunda fila de la tabla anterior en los cuadros para el segundo registro.
    
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
