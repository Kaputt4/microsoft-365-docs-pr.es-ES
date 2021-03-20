---
title: Crear registros DNS en OVH para Microsoft
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Aprenda a comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en OVH para Microsoft.
ms.openlocfilehash: a43593af80d2f651e4407de64ed9aab51f1c1ecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910071"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a>Crear registros DNS en OVH para Microsoft

[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml) si no encuentra lo que busca. 
  
Si OVH es su proveedor de hospedaje DNS, siga los pasos descritos en este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online, entre otros.
  
Estos son los registros principales que es necesario agregar. 
  
- [Crear registros DNS en OVH para Microsoft](#create-dns-records-at-ovh-for-microsoft)
    
- [Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Agregar los registros CNAME necesarios para Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Agregar los dos registros SRV necesarios para Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Después de agregar estos registros en OVH, el dominio se configurará para que funcione con los servicios de Microsoft.

  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="bkmk_txt"> </a>

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a la página dominios de OVH mediante [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. En **Dominios**, seleccione el nombre del dominio que desea editar.
    
    ![OVH Seleccionar el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Seleccione **zona DNS**.
    
    ![OVH seleccionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Seleccione **Agregar una entrada**.
    
    ![OVH Agregar una entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Seleccionar **TXT**
    
    ![OVH seleccionar entrada TXT](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente. Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto. 
    
    |**Tipo de registro**|**Subdominio**|**TTL**|**Valor**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(se deja en blanco)  <br/> |3600 (segundos)  <br/> |MS=msxxxxxxxx  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla.           [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Seleccione **Confirmar**. 
    
    ![OVH confirma TXT para verificación](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.
    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
    
  
3. En la página de **Configuración**, elija **Iniciar configuración**.
    
    
  
4. En la página **verificar dominio**, seleccione **verificar**.
    
    
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft
<a name="bkmk_mx"> </a>

1. Para empezar, vaya a la página dominios de OVH mediante [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. En **Dominios**, seleccione el nombre del dominio que desea editar.
    
    ![OVH Seleccionar el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Seleccione **zona DNS**.
    
    ![OVH seleccionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Seleccione **Agregar una entrada**.
    
    ![OVH Agregar una entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Seleccione **MX**.
    
    ![Tipo de registro MX de OVH](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente. Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto. 
    
    > [!NOTE]
    > De forma predeterminada, OVH usa notación relativa para el destino, que agrega el nombre de dominio al final del registro de destino. Para usar la notación absoluta en su lugar, agregue un punto al registro de destino como se muestra en la tabla siguiente. 
  
    |**Tipo de registro**|**Subdominio**|**TTL**|**Prioridad**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(se deja en blanco)  <br/> |3600 (segundos)  <br/> |10    <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml) <br/> |\<domain-key\>.mail.protection.outlook.com.  <br/> **Nota:** Obtener el  *\<domain-key\>*  de su cuenta de Microsoft.  [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![Registro MX de OVH para correo](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. Seleccione **Siguiente**.
    
    ![Registro MX de OVH seleccionar Siguiente](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. Seleccione **Confirmar**.
    
    ![Registro MX de OVH seleccione Confirmar](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. Si hay otros registros MX, elimínelos todos en la lista de la página **de zona DNS.** Seleccione cada registro y, a continuación, en la **columna Acciones,** seleccione el icono **eliminar** de la papelera. 
    
    ![Eliminar registro MX de OVH](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. Seleccione **Confirmar**.
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Agregar los registros CNAME necesarios para Microsoft
<a name="bkmk_cname"> </a>

1. Para empezar, vaya a la página dominios de OVH mediante [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. En **Dominios**, seleccione el nombre del dominio que desea editar.
    
    ![OVH Seleccionar el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Seleccione **zona DNS**.
    
    ![OVH seleccionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Seleccione **Agregar una entrada**.
    
    ![OVH Agregar una entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Seleccione **CNAME**.
    
    ![OVH agregar tipo de registro CNAME](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. Cree el primer registro CNAME.
    
    En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente. Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto. 
    
    |**Tipo de registro**|**Subdominio**|**Destino**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |3600 segundos  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> |3600 segundos  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |3600 segundos  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |3600 segundos  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |3600 segundos  <br/> |
   
    ![Registro CNAME de OVH](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. Seleccione **Siguiente**.
    
    ![OVH Agregar valores CNAME y seleccionar Siguiente](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. Seleccione **Confirmar**.
    
9. Repita los pasos anteriores para crear los otros cinco registros CNAME.
    
    Para cada registro, escriba o copie y pegue los valores de la siguiente fila de la tabla anterior en los cuadros de ese registro.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores. 
  
1. Para empezar, vaya a la página dominios de OVH mediante [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. En **Dominios**, seleccione el nombre del dominio que desea editar.
    
    ![OVH Seleccionar el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Seleccione **zona DNS**.
    
    ![OVH seleccionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Seleccione **Agregar una entrada**.
    
    ![OVH Agregar una entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Seleccione **TXT**.
    
6. In the boxes for the new record, type or copy and paste the following values.
    
    |**Tipo de registro**|**Subdominio**|**TTL**|**Valor TXT**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(se deja en blanco)  <br/> |3600 (segundos)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |
   
    ![OVH Agregar registro TXT para SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. Seleccione **Siguiente**.
    
    ![OVH Agregar registro TXT para SPF y seleccionar Siguiente](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. Seleccione **Confirmar**.
    
    ![OVH Agregar registro TXT para SPF y Confirmar](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Agregar los dos registros SRV necesarios para Microsoft
<a name="bkmk_srv"> </a>

1. Para empezar, vaya a la página dominios de OVH mediante [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Inicio de sesión de OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. En **Dominios**, seleccione el nombre del dominio que desea editar.
    
    ![OVH Seleccionar el dominio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Seleccione **zona DNS**.
    
    ![OVH seleccionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Seleccione **Agregar una entrada**.
    
    ![OVH Agregar una entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Seleccione **SRV**.
    
    ![Tipo de registro SRV seleccionado por OVH](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. Cree el primer registro SRV.
    
    En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente. Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y, a continuación, escriba el valor en el cuadro de texto. 
    
    |**Tipo de registro**|**Subdominio**|**Prioridad**|**Grosor**|**Puerto**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (servicio)  <br/> |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |3600 (segundos)  <br/> |sipdir.online.lync.com.  <br/> |
    |SRV (servicio)  <br/> |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |3600 (segundos)  <br/> |sipfed.online.lync.com.  <br/> |
       
    ![Registro SRV de OVH](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. Seleccione **Siguiente**.
    
    ![Registro SRV de OVH seleccione Siguiente](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. Seleccione **Confirmar**.
    
9. Repita los pasos anteriores para crear el otro registro SRV. Copie y pegue los valores de la segunda fila de la tabla anterior en los cuadros para el segundo registro.
    
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
