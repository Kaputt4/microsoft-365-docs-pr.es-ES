---
title: Crear registros DNS para Microsoft con DNS basado en Windows
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Obtenga información sobre cómo comprobar el dominio y configurar registros DNS para correo electrónico, Skype Empresarial En línea y otros servicios en DNS basado en Windows para Microsoft.
ms.openlocfilehash: 6d27a2ab9f7a1432e10533d677ea6dc705ba77d6
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68730676"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Crear registros DNS para Microsoft con DNS basado en Windows

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
   
Si hospeda sus propios registros DNS utilizando DNS basado en Windows, siga los pasos indicados en este artículo para configurar los registros para el correo electrónico, Skype Empresarial Online, y para otras tareas.
  
Para empezar, debe [buscar los registros DNS en DNS basado en Windows](#find-your-dns-records-in-windows-based-dns) para poder actualizarlos. Además, si tiene previsto sincronizar la Active Directory local con Microsoft, consulte [Dirección de correo electrónico no enrutable que se usa como UPN en active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory) local.
  
Problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solución de problemas después de cambiar el nombre de dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Buscar los registros DNS en DNS basado en Windows
<a name="BKMK_find_your_dns_1"> </a> Vaya a la página que tiene los registros DNS del dominio. Si trabaja en Windows Server 2008, vaya a **Iniciar** > **ejecución**. Si está trabajando en Windows Server 2012, presione la Tecla Windows y **r**. Escriba **dnsmgmnt.msc** y luego seleccione **Aceptar**. En el Administrador de DNS, expanda **\<DNS server name\>  \> Zonas de búsqueda directa**. Seleccione su dominio. Ya está listo para crear los registros DNS.
   
## <a name="add-mx-record"></a>Agregar registro MX
<a name="BKMK_add_MX"> </a>

Agregue un registro MX para que el correo electrónico de su dominio llegue a Microsoft.
- El registro MX que agregará incluye un valor (el valor **De puntos a dirección** ) que tiene un aspecto similar al siguiente: \<MX token\>.mail.protection.outlook.com, donde \<MX token\> es un valor como MSxxxxxxx. 
- En la fila MX de la sección Exchange Online de la página Agregar registros DNS de Microsoft, copie el valor que aparece en Puntos a la dirección. Usará este valor en el registro que va a crear en esta tarea. 
- En la página Administrador DNS del dominio, vaya a **Action** > **Mail Exchanger (MX)**. Para buscar esta página para el dominio, vea [Buscar los registros DNS en DNS basado en Windows](#find-your-dns-records-in-windows-based-dns).  
- En el **cuadro de diálogo Nuevo registro de recursos** , asegúrese de que los campos están establecidos con precisión en los siguientes valores: 
    - Nombre de host: 
    - @Address: pegue el valor De puntos a dirección que acaba de copiar de Microsoft aquí.  
    - Pref: 
- Seleccione **Guardar cambios**.
- Elimine los registros MX obsoletos. Si tiene registros MX antiguos para este dominio que enrutan el correo electrónico a otro lugar, active la casilla situada junto a cada registro antiguo y, a continuación, seleccione **Eliminar** > **aceptar**. 
   
## <a name="add-cname-records"></a>Agregar registros CNAME
<a name="BKMK_add_CNAME"> </a>

Agregue los registros CNAME necesarios para Microsoft. Si se muestran registros CNAME adicionales en Microsoft, agréguelos siguiendo los mismos pasos generales que se muestran aquí.
  
> [!IMPORTANT]
> Si tiene Mobile Administración de dispositivos (MDM) para Microsoft, debe crear dos registros CNAME adicionales. Siga el procedimiento que utilizó para los otros cuatro registros CNAME, pero suministre los valores de la siguiente tabla. (Si no tiene MDM, puede omitir este paso). 

- En la página Administrador DNS del dominio, vaya a **Acción** > **CNAME (CNAME)**.
- En el **cuadro de diálogo Nuevo registro de recursos** , asegúrese de que los campos están establecidos con precisión en los siguientes valores:  
    - Nombre de host: detección automática
    - Tipo: 
    - CNAMEAddress: autodiscover.outlook.com
- Seleccione **O** K.

Agregue registro CNAME SIP. 
- En la página Administrador DNS del dominio, vaya a **Acción** \> **CNAME (CNAME)**. 
- En el **cuadro de diálogo Nuevo registro de recursos** , asegúrese de que los campos están establecidos con precisión en los siguientes valores:  
    - Nombre de host: sip
    - Tipo: CNAME
    - Dirección: sipdir.online.lync.com
- Seleccione **Aceptar**.

Agregue el registro CNAME de detección automática de Skype Empresarial Online.  
- En la página Administrador DNS del dominio, vaya a **Acción** \> **CNAME (CNAME)**. En el **cuadro de diálogo Nuevo registro de recursos** , asegúrese de que los campos están establecidos con precisión en los siguientes valores:  
    - Nombre de host: lyncdiscover
    - Tipo: CNAME
    - Dirección: webdir.online.lync.com
- Seleccione **Aceptar**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Agregar dos registros CNAME para Mobile Administración de dispositivos (MDM) para Microsoft

> [!IMPORTANT]
> Si tiene Mobile Administración de dispositivos (MDM) para Microsoft, debe crear dos registros CNAME adicionales. Siga el procedimiento que utilizó para los otros cuatro registros CNAME, pero suministre los valores de la siguiente tabla. >(Si no tiene MDM, puede omitir este paso). 
  

Agregue el registro CNAME de MDM Enterpriseregistration.  
- En la página Administrador DNS del dominio, vaya a **Acción** \> **CNAME (CNAME)**. 
- En el **cuadro de diálogo Nuevo registro de recursos** , asegúrese de que los campos están establecidos con precisión en los siguientes valores:  
- Nombre de host: enterpriseregistration
- Tipo: CNAME
- Dirección: enterpriseregistration.windows.net
- Seleccione **Aceptar**. 

Agregue el registro CNAME de MDM Enterpriseenrollment. 
-  En la página Administrador DNS del dominio, vaya a **Acción** \> **CNAME (CNAME)**. 
-  En el **cuadro de diálogo Nuevo registro de recursos** , asegúrese de que los campos están establecidos con precisión en los siguientes valores:  
    - Nombre de host: enterpriseenrollment
    - Tipo: CNAME
    - Dirección: enterpriseenrollment-s.manage.microsoft.com
- Seleccione **Aceptar**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un  *único*  registro SPF que incluya ambos conjuntos de valores. 
  
Agregue el registro TXT de SPF para su dominio para prevenir el correo basura.
  
- You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine. Leave those strings in place and add this one, placing double-quotes around each string to separate them. 
- En la página Administrador DNS del dominio, vaya a Texto de **acción** \> **(TXT).** 
-  En el **cuadro de diálogo Nuevo registro de recursos** , asegúrese de que los campos están establecidos en los valores siguientes con precisión. 
 > [!IMPORTANT]
> En algunas versiones del Administrador de DNS de Windows, es posible que el dominio se haya configurado para que, al crear un registro txt, el nombre principal se establezca de forma predeterminada en el dominio primario. En esta situación, al agregar un registro TXT, establezca el nombre de host en blanco (ningún valor) en lugar de configurarlo para @ o el nombre de dominio. 

-  Tipo de host: @
-  Tipo de registro: TXT
-  Dirección: v=spf1 include:spf.protection.outlook.com -all 
         
-  Seleccione **Aceptar**.
   
## <a name="add-srv-records"></a>Agregar registros SRV
<a name="BKMK_add_SRV"> </a>

Agregue los dos registros SRV necesarios para Microsoft.

Agregue el registro SRV SIP para conferencias web de Skype Empresarial Online.  <br/> 
-  En la página Administrador dns del dominio, vaya a **Acción** \> **Otros registros nuevos**. 
-   En la ventana **Tipo de registro de recursos** , seleccione **Ubicación del servicio (SRV)** y, a continuación, seleccione **Crear registro**. 
-   En el **cuadro de diálogo Nuevo registro de recursos** , asegúrese de que los campos están establecidos con precisión en los siguientes valores:  
    -  Servicio: _sip
    -  Protocolo: _tls
    -  Prioridad: 100
    -  Peso: 1
    -  Puerto: 443
    -  Destino (nombre de host): sipdir.online.lync.com
-  Seleccione **Aceptar**. 


Agregue el registro SRV SIP para la federación de Skype Empresarial Online.  
-  En la página Administrador dns del dominio, vaya a **Acción** \> **Otros registros nuevos**.  
-  En la ventana **Tipo de registro de recursos** , seleccione **Ubicación del servicio (SRV)** y, a continuación, seleccione **Crear registro**. 
-   En el **cuadro de diálogo Nuevo registro de recursos** , asegúrese de que los campos están establecidos con precisión en los siguientes valores:  
    -  Servicio: _sipfederationtls
    -  Protocolo: _tcp
    -  Prioridad: 100
    -  Peso: 1
    -  Puerto: 5061
    -  Destino (nombre de host): sipfed.online.lync.com
-  Seleccione **Aceptar**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Agregar un registro para verificar que posee el dominio si todavía no lo ha hecho
<a name="BKMK_verify"> </a>

Antes de agregar los registros DNS para configurar los servicios de Microsoft, Microsoft debe confirmar que es el propietario del dominio que va a agregar. Para ello, debe agregar un registro, siguiendo los pasos que se indican a continuación.
  
> [!NOTE]
> Este registro solo se utiliza para comprobar que usted es el propietario del dominio; no afecta a nada más. 
  

1. Recopilar información de Microsoft.  <br/> 
2. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>. 
3. En la página **Dominios** , en la columna **Acciones** del dominio que está comprobando, seleccione **Iniciar configuración**. 
4. En la página **Agregar un dominio a Microsoft** , seleccione **Inicio paso 1**. 
5. En la página **Confirmar que posee su dominio** , en la lista desplegable **Ver instrucciones para realizar este paso con** , elija **Instrucciones generales**. 
6. En la tabla, copie el valor Destination or Points to Address. Lo necesitará en el siguiente paso. Se recomienda copiar y pegar este valor para que todo el espaciado sea correcto.

Agregue un registro TXT. 
-  En la página Administrador DNS del dominio, vaya a Texto de **acción** \> **(TXT).** 
-   En el **cuadro de diálogo Nuevo registro de recursos** , seleccione **Editar**.  
-  En el área **Nombres de host personalizados** del cuadro de diálogo **Nuevo registro de recursos** , asegúrese de que los campos están establecidos en los valores siguientes con precisión. 

> [!IMPORTANT] 
> En algunas versiones del Administrador de DNS de Windows, es posible que el dominio se haya configurado para que, al crear un registro txt, el nombre principal se establezca de forma predeterminada en el dominio primario. En esta situación, al agregar un registro TXT, establezca el nombre de host en blanco (ningún valor) en lugar de configurarlo para @ o el nombre de dominio. 

- Nombre de host: @
- Tipo: TXT
- Dirección: pegue el valor de Destino o Puntos a dirección que acaba de copiar de Microsoft aquí.  
- Seleccione **Aceptar** > **listo**.

Compruebe el dominio en Microsoft.  
> [!IMPORTANT]
> Espere unos 15 minutos antes de hacerlo, por lo que el registro que acaba de crear puede actualizarse a través de Internet.       

- Volver a Microsoft y siga los pasos siguientes para solicitar una comprobación. La comprobación busca el registro TXT que agregó en el paso anterior. Cuando encuentra el registro correcto TXT, el dominio se comprueba.  
1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a> **de instalación**\>.
2. En la página **Dominios** , en la columna **Acción** del dominio que está comprobando, seleccione **Iniciar configuración**. 
3. En la página **Confirmar que posee su dominio** , seleccione **Listo, compruebe ahora** y, en el cuadro de diálogo de confirmación, seleccione **Finalizar**. 
   
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Dirección de correo electrónico no enrutable usada como un UPN en su Active Directory local
<a name="BKMK_ADNote"> </a>

Si planea sincronizar el Active Directory local con Microsoft, querrá asegurarse de que el sufijo de nombre principal de usuario (UPN) de Active Directory sea un sufijo de dominio válido y no un sufijo de dominio no admitido, como @contoso.local. Si necesita cambiar el sufijo UPN, consulte [Preparación de un dominio no enrutable para la sincronización de directorios](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 

## <a name="related-content"></a>Contenido relacionado

[Transferencia de un dominio de Micrsoft 365 a otro host](../get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host.md) (artículo)\
[Pilotar Microsoft 365 desde mi dominio personalizado](../misc/pilot-microsoft-365-from-my-custom-domain.md) (artículo)\
[Preguntas más frecuentes sobre dominios](../setup/domains-faq.yml) (artículo)