---
title: Crear registros DNS en Wix para Office 365
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Wix para Office 365.
ms.openlocfilehash: 43d2f2417153dd0c848c33736733237b1681c02c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246897"
---
# <a name="create-dns-records-at-wix-for-office-365"></a>Crear registros DNS en Wix para Office 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Si Wix es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.
  
Estos son los registros principales que es necesario agregar. 
  
- [Agregue un registro TXT para la comprobación](#add-a-txt-record-for-verification).
    
- [Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365).
    
- [Agregue los cinco registros CNAME necesarios para Office 365](#add-the-five-cname-records-that-are-required-for-office-365).
    
- [Agregue un registro TXT para SPF para ayudar a evitar el correo no deseado](#add-a-txt-record-for-spf-to-help-prevent-email-spam).
    
- [Agregue los dos registros SRV necesarios para Office 365](#add-the-two-srv-records-that-are-required-for-office-365).
    
Después de agregar estos registros a Wix, su dominio estará configurado para trabajar con los servicios de Office 365.
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_txt"> </a>

Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a su página de dominios en Wix a través de [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to log in first.
    
2. En la página **mis dominios** , en el área **avanzadas** , seleccione el botón **Editar DNS** . 
    
3. Seleccione **+ Agregar otro** en la fila **txt (texto)** del editor DNS. 
    
4. In the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**Host Name** <br/> |**Valor TXT** <br/> |**TTL** <br/> |
|Se rellena automáticamente  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** Este es un ejemplo. Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365.  [¿Cómo puedo encontrarlo?](../get-help-with-domains/information-for-dns-records.md)|1 Hour <br/> |          |
   
5. Seleccione el botón **Guardar DNS** en la parte superior del editor DNS. 
    
6. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .
    
2. En la página **dominios** , seleccione el dominio que desea comprobar. 
  
  
3. En la página **configuración** , seleccione **Iniciar configuración**.
   
  
4. En la página **comprobar dominio** , seleccione **comprobar**.
    
    
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365
<a name="BKMK_mx"> </a>

1. Para empezar, vaya a su página de dominios en Wix a través de [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to log in first.
    
2. En la página **mis dominios** , en el área **buzones de correo** , seleccione el vínculo configurar los **registros MX** . 
    
3. Elija **otro** en la lista desplegable **proveedor de correo electrónico** . 
    
4. Seleccione **+ Agregar otro**.
    
5. En los cuadros para el nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente:
    
|**Host Name**|**Señala a**|**Prioridad**|**TTL**|
|:-----|:-----|:-----|:-----|
|Se rellena automáticamente <br/> | *\< clave-de-dominio \>*  . mail.protection.outlook.com      <br/> **Nota:** Obtenga la * \<clave\> de dominio* de su cuenta de Office 365.   [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md) |comprendi  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83) | 1 Hour|
   
6. Si hay otros registros MX enumerados, elimínelos. 
    
7. Seleccione **Aceptar**.
    
8. En el cuadro de diálogo de confirmación, seleccione **Aceptar**.
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>Agregue los cinco registros CNAME necesarios para Office 365
<a name="BKMK_cname"> </a>

1. Para empezar, vaya a su página de dominios en Wix a través de [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.
    
2. En la página **mis dominios** , en el área **avanzadas** , seleccione el botón **Editar DNS** . 
    
3. Seleccione **+ Agregar otro** en la fila **CNAME (aliases)** del editor DNS para cada registro CNAME. 
    
4. En los cuadros para el nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente:
    
|**Host Name**|**Señala a**|**TTL**|
|:-----|:-----|:-----|
|autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 Hour  <br/> |
|sip  <br/> |sipdir.online.lync.com  <br/> |1 Hour <br/> |
|lyncdiscover  <br/> |webdir.online.lync.com   <br/> |1 Hour  <br/> |
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 hora <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 Hour  <br/> |
   
5. Seleccione el botón **Guardar DNS** en la parte superior del editor DNS. 
    
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="BKMK_spf"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.  
  
1. Para empezar, vaya a su página de dominios en Wix a través de [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to log in first.
    
2. En la página **mis dominios** , en el área **avanzadas** , seleccione el botón **Editar DNS** . 
    
3. Seleccione **+ Agregar otro** en la fila **txt (texto)** del editor DNS. 
    
4. En los cuadros para el nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente:
    
|**Host Name**|**Valor TXT**|**TTL**|
|:-----|:-----|:-----|
|[deje este cuadro en blanco]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.<br/> |TXT  <br/> | 1 Hour |
   
5. Seleccione el botón **Guardar DNS** en la parte superior del editor DNS. 
    
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Agregar los dos registros SRV necesarios para Office 365
<a name="BKMK_srv"> </a>

1. Para empezar, vaya a su página de dominios en Wix a través de [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to log in first.
    
2. En la página **mis dominios** , en el área **avanzadas** , seleccione el botón **Editar DNS** . 
    
3. Seleccione **+ Agregar otro** en la fila **SRV** del editor DNS. 
    
4. En los cuadros para el nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente:
    
|**Servicio**|**Protocolo**|**Nombre**|**Peso**|**Puerto**|**Destino**|**Prioridad**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|sip  |tls  |Se rellena automáticamente |1  |443   |sipdir.online.lync.com |100 |1 Hour |
|sipfed|tcp |Se rellena automáticamente|1 |5061 |sipfed.online.lync.com|100 | 1 Hour |
   
5. Seleccione el botón **Guardar DNS** en la parte superior del editor DNS. 
    
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  

