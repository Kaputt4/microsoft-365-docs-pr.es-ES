---
title: Crear registros DNS en Wix para Microsoft
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en Wix para Microsoft.
ms.openlocfilehash: 3ec2ea0dc24e1872ba22e591fae96b39a9a0deee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916111"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a>Crear registros DNS en Wix para Microsoft

**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
Si Wix es su proveedor de hospedaje DNS, siga los pasos descritos en este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online, entre otros.

Estos son los registros principales que es necesario agregar. 
  
- [Agregue un registro TXT para la comprobación](#add-a-txt-record-for-verification).
    
- [Agregue un registro MX para que el correo electrónico de su dominio se envíe a Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).
    
- [Agregue los cinco registros CNAME necesarios para Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).
    
- [Agregue un registro TXT para SPF para ayudar a evitar el correo no deseado de correo electrónico](#add-a-txt-record-for-spf-to-help-prevent-email-spam).
    
- [Agregue los dos registros SRV necesarios para Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).
    
Después de agregar estos registros en Wix, el dominio se configurará para que funcione con los servicios de Microsoft.
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_txt"> </a>

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 

> [!NOTE]
> WIX no admite entradas DNS para subdominios.
  
1. Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .
    
2. En la **página Mis dominios,** en el **área** Avanzadas, seleccione el botón **Editar DNS.** 
    
3. Seleccione **+ Agregar otro en** la fila TXT **(Texto)** del editor DNS. 
    
4. In the boxes for the new record, type or copy and paste the values from the following table. 
    
   ||||
   |:-----|:-----|:-----|
   | Nombre de host <br/> | TXT Value <br/> | TTL <br/> |
   |Rellenado automáticamente  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla.  [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|1 hora <br/> |          |
   
5. Seleccione el **botón Guardar DNS** en la parte superior del editor DNS. 
    
6. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.
    
2. En la página **Dominios**, elija el dominio que está verificando. 
  
3. En la página de **Configuración**, elija **Iniciar configuración**.
   
4. En la página **verificar dominio**, seleccione **verificar**.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft
<a name="BKMK_mx"> </a>

1. Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .
    
2. En la **página Mis dominios,** en el área **Buzones,** seleccione el vínculo Configurar los **registros MX.** 
    
3. Elija **Otro** en **la lista desplegable** Su proveedor de correo electrónico. 
    
4. Seleccione **+ Agregar otro**.
    
5. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente:
    
   | Nombre de host | Points to  | Prioridad | TTL |
   |:-----|:-----|:-----|:-----|
   |Rellenado automáticamente <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Nota:** Obtener el  *\<domain-key\>*  de su cuenta de Microsoft.   [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md) |0  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml) | 1 hora|
   
6. Si hay otros registros MX enumerados, elimine cada uno de ellos. 
    
7. Seleccione **Aceptar**.
    
8. En el cuadro de diálogo de confirmación, seleccione **Aceptar**.
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Agregar los cinco registros CNAME necesarios para Microsoft
<a name="BKMK_cname"> </a>

1. Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.
    
2. En la **página Mis dominios,** en el **área** Avanzadas, seleccione el botón **Editar DNS.** 
    
3. Seleccione **+ Agregar otro en** la fila **CNAME (Alias)** del editor DNS para cada registro CNAME. 
    
4. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente:
    
   | Nombre de host | Points to  | TTL |
   |:-----|:-----|:-----|
   |autodescubrir  <br/> |autodiscover.outlook.com  <br/> |1 hora  <br/> |
   |sip  <br/> |sipdir.online.lync.com  <br/> |1 hora <br/> |
   |lyncdiscover  <br/> |webdir.online.lync.com   <br/> |1 hora  <br/> |
   |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 hora <br/> |
   |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 Hour  <br/> |
   
5. Seleccione el **botón Guardar DNS** en la parte superior del editor DNS. 
    
6. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="BKMK_spf"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores.  
  
1. Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .
    
2. En la **página Mis dominios,** en el **área** Avanzadas, seleccione el botón **Editar DNS.** 
    
3. Seleccione **+ Agregar otro en** la fila TXT **(Texto)** del editor DNS. 
    
4. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente:
    
   | Nombre de host | TXT Value | TTL |
   |:-----|:-----|:-----|
   |[Deje esto en blanco]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.<br/> |TXT  <br/> | 1 Hour |
   
5. Seleccione el **botón Guardar DNS** en la parte superior del editor DNS. 
    
6. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Agregar los dos registros SRV necesarios para Microsoft
<a name="BKMK_srv"> </a>

1. Para empezar, vaya a la página de dominios de Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .
    
2. En la **página Mis dominios,** en el **área** Avanzadas, seleccione el botón **Editar DNS.** 
    
3. Seleccione **+ Agregar otro** en la fila **SRV** del editor DNS. 
    
4. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente:
    
   | Servicio | Protocolo | Nombre | Peso | Puerto | Target | Prioridad | TTL |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |sip  |tls  |Rellenado automáticamente |1  |443   |sipdir.online.lync.com |100 |1 Hour |
   |sipfed|tcp |Rellenado automáticamente|1 |5061 |sipfed.online.lync.com|100 | 1 Hour |
   
5. Seleccione el **botón Guardar DNS** en la parte superior del editor DNS. 
    
6. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
