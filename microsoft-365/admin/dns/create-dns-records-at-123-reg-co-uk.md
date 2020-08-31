---
title: Crear registros DNS en 123-reg.co.uk para Microsoft
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en 123-reg.co.uk para Microsoft.
ms.openlocfilehash: 51542e1f00153a87ca06ec540d391de6ca621bab
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307036"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a>Crear registros DNS en 123-reg.co.uk para Microsoft

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Si 123-reg.co.uk es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.
  
Después de agregar estos registros a 123-reg.co.uk, su dominio estará configurado para funcionar con los servicios de Microsoft.
  
  
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_verify"> </a>

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** . 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Nombre de host** <br/> |**Tipo** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
   
6. Elija **Agregar**.
    
7. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará una búsqueda para el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.

    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
3. En la página de **Configuración**, elija ** Iniciar configuración**.
    
4. En la página**Verificar dominio**, elija **Verificar**.
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft
<a name="BKMK_add_MX"> </a>

1. Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** . 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nombre de host**|**Tipo**|**Prioridad**|**MX de destino**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1   <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*  . mail.protection.outlook.com.  <br/> **Este valor DEBE terminar en punto (.)** <br/> **Nota: ** Obtenga la \<domain-key\> desde su cuenta de Microsoft. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiar y pegar valores de la tabla](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. Seleccione **Agregar**.
    
    ![Seleccione Agregar.](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. Si hay otros registros MX, quítelos (para hacerlo, elija el icono **Eliminar [papelera]** de ese registro). 
    
    ![Seleccione Eliminar (el icono de la papelera)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Agregar los seis registros CNAME necesarios para Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** . 
    
5. Agregue el primero de los seis registros CNAME.
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nombre de host**|**Tipo**|**CNAME de destino**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Este valor DEBE terminar en punto (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |
   
    ![Copiar y pegar los valores de la tabla](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. Seleccione **Agregar**.
    
    ![Seleccione Agregar.](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. Cree los otros cinco registros CNAME.
    
    En la sección **DNS avanzado** , cree un registro con los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **Agregar** para completar ese registro. 
    
    Repita este proceso hasta crear los seis registros CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsfot. En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores. ¿Necesita ejemplos? Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** . 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nombre de host**|**Tipo**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |
   
    ![123Reg-BP-configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. Seleccione **Agregar**.
    
    ![Seleccione Agregar.](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Agregar los dos registros SRV necesarios para Microsoft
<a name="BKMK_add_SRV"> </a>

1. Para empezar, vaya a su página de dominios en 123-reg.co.uk a través de [este vínculo](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Se le pedirá que inicie sesión primero .
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. En la página **administrar el DNS** , seleccione la pestaña **DNS avanzado** . 
    
5. Agregue el primero de los dos registros SRV:
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |Nombre de host|Tipo|Prioridad|TTL|SRV de destino|
    |_sip._tls|SRV|100|3600|1 443 sipdir.online.lync.com. **Este valor DEBE terminar en punto (.)**<br> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |
    |_sipfederationtls._tcp|SRV|100|3600|1 5061 sipfed.online.lync.com. **Este valor DEBE terminar en punto (.)** <br> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |
   
    ![Copiar y pegar los valores de la tabla](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. Seleccione **Agregar**.
    
    ![Seleccione Agregar.](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. Para agregar el otro registro SRV:
    
    En la sección **DNS avanzado** , cree un registro (para hacerlo, use los valores de la segunda fila de la tabla y, después, vuelva a seleccionar **Agregar** para completar ese registro). 
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
