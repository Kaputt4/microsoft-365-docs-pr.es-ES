---
title: Crear registros DNS para Microsoft con DNS basado en Windows
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en DNS basado en Windows para Microsoft.
ms.openlocfilehash: 8f65a397552813f22d4bde82f7fcd51c478d82bd
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400249"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Crear registros DNS para Microsoft con DNS basado en Windows

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
   
Si hospeda sus propios registros DNS utilizando DNS basado en Windows, siga los pasos indicados en este artículo para configurar los registros para el correo electrónico, Skype Empresarial Online, y para otras tareas.
  
Para empezar, necesita [encontrar los registros DNS en DNS basado en Windows](#find-your-dns-records-in-windows-based-dns) para poder actualizarlos. Además, si tiene previsto sincronizar su Active Directory local con Microsoft, consulte [dirección de correo electrónico no enrutable usada como un UPN en su Active Directory local](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).
  
Problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [solucionar problemas después de cambiar el nombre de dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Buscar los registros DNS en DNS basado en Windows
<a name="BKMK_find_your_dns_1"> </a> Vaya a la página que contiene los registros DNS de su dominio. Si está trabajando en Windows Server 2008, vaya a **Inicio**de la  >  **ejecución**. Si está trabajando en Windows Server 2012, presione las teclas Windows y **r**. Escriba **dnsmgmnt. msc**y, a continuación, seleccione **Aceptar**. En el administrador de DNS, expanda ** \<DNS server name\> \> zonas de búsqueda directa  **. Seleccione su dominio. Ya está listo para crear los registros DNS.
   
## <a name="add-mx-record"></a>Agregar registro MX
<a name="BKMK_add_MX"> </a>

Agregar un registro MX para que el correo electrónico del dominio llegue a Microsoft.
- El registro MX que agregará incluye un valor (el valor de **dirección de destino** ) con un aspecto similar a este: \<MX token\> . mail.Protection.Outlook.com, donde \<MX token\> es un valor como MSxxxxxxx. 
- En la fila MX de la sección Exchange online de la página agregar registros DNS de Microsoft, copie el valor que aparece en puntos a la dirección. Este valor se usará en el registro que se está creando en esta tarea. 
- En la página del administrador de DNS del dominio, vaya a **Action**  >  **interchanger mail (mx)**. Para buscar esta página para el dominio, vea [Buscar los registros DNS en DNS basado en Windows](#find-your-dns-records-in-windows-based-dns).  
- En el cuadro de diálogo **nuevo registro de recursos** , asegúrese de que los campos se configuran exactamente con los valores siguientes: 
    - Nombre de host: 
    - @Address: pegue el valor de dirección de destino que acaba de copiar desde Microsoft aquí.  
    - Distinguir 
- Seleccione **Guardar cambios**.
- Elimine los registros MX obsoletos. Si tiene registros MX antiguos para este dominio que redirigen el correo electrónico a otro lugar, active la casilla situada junto a cada registro antiguo y, a continuación, seleccione **eliminar**  >  **Aceptar**. 
   
## <a name="add-cname-records"></a>Agregar registros CNAME
<a name="BKMK_add_CNAME"> </a>

Agregue los registros CNAME necesarios para Microsoft. Si los registros CNAME adicionales aparecen en Microsoft, agréguelos siguiendo los mismos pasos generales que se muestran aquí.
  
> [!IMPORTANT]
> Si tiene administración de dispositivos móviles (MDM) para Microsoft, debe crear dos registros CNAME adicionales. Siga el procedimiento que utilizó para los otros cuatro registros CNAME, pero suministre los valores de la siguiente tabla. (Si no tiene MDM, puede omitir este paso). 

- En la página del administrador de DNS del dominio, vaya a **acción**  >  **CNAME (CNAME)**.
- En el cuadro de diálogo **nuevo registro de recursos** , asegúrese de que los campos se configuran exactamente con los valores siguientes:  
    - Nombre de host: detección automática
    - Tipo: 
    - Cnamedirección: autodiscover.outlook.com
- Seleccione **O**K.

Agregue registro CNAME SIP. 
- En la página del administrador de DNS del dominio, vaya a **acción** \> **CNAME (CNAME)**. 
- En el cuadro de diálogo **nuevo registro de recursos** , asegúrese de que los campos se configuran exactamente con los valores siguientes:  
    - Nombre de host: SIP
    - Tipo: CNAME
    - Dirección: sipdir.online.lync.com
- Seleccione **ACEPTAR**.

Agregue el registro CNAME de detección automática de Skype Empresarial Online.  
- En la página del administrador de DNS del dominio, vaya a **acción** \> **CNAME (CNAME)**. En el cuadro de diálogo **nuevo registro de recursos** , asegúrese de que los campos se configuran exactamente con los valores siguientes:  
    - Nombre de host: lyncdiscover
    - Tipo: CNAME
    - Dirección: webdir.online.lync.com
- Seleccione **ACEPTAR**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Agregar dos registros CNAME para la administración de dispositivos móviles (MDM) para Microsoft

> [!IMPORTANT]
> Si tiene administración de dispositivos móviles (MDM) para Microsoft, debe crear dos registros CNAME adicionales. Siga el procedimiento que utilizó para los otros cuatro registros CNAME, pero suministre los valores de la siguiente tabla. > (si no tiene MDM, puede omitir este paso). 
  

Agregue el registro CNAME de MDM Enterpriseregistration.  
- En la página del administrador de DNS del dominio, vaya a **acción** \> **CNAME (CNAME)**. 
- En el cuadro de diálogo **nuevo registro de recursos** , asegúrese de que los campos se configuran exactamente con los valores siguientes:  
- Nombre de host: enterpriseregistration
- Tipo: CNAME
- Dirección: enterpriseregistration.windows.net
- Seleccione **ACEPTAR**. 

Agregue el registro CNAME de MDM Enterpriseenrollment. 
-  En la página del administrador de DNS del dominio, vaya a **acción** \> **CNAME (CNAME)**. 
-  En el cuadro de diálogo **nuevo registro de recursos** , asegúrese de que los campos se configuran exactamente con los valores siguientes:  
    - Nombre de host: enterpriseenrollment
    - Tipo: CNAME
    - Dirección: enterpriseenrollment-s.manage.microsoft.com
- Seleccione **ACEPTAR**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores. 
  
Agregue el registro TXT de SPF para su dominio para prevenir el correo basura.
  
- Es posible que ya tenga otras cadenas en el valor TXT para este registro (como las cadenas de correo electrónico de marketing), es correcto. Deje estas cadenas en su lugar y agregue la siguiente, colocando comillas dobles alrededor de cada cadena para separarlas. 
- En la página del administrador de DNS de su dominio, vaya a **acción** \> **texto (txt)**. 
-  En el cuadro de diálogo **nuevo registro de recursos** , asegúrese de que los campos se configuran exactamente con los valores siguientes. 
 > [!IMPORTANT]
> En algunas versiones del administrador de DNS de Windows, es posible que el dominio se haya configurado de modo que, al crear un registro TXT, el nombre del domicilio predeterminado sea el dominio primario. En esta situación, al agregar un registro TXT, establezca el nombre de host en blanco (ningún valor) en lugar de configurarlo para @ o el nombre de dominio. 

-  Tipo de host: @
-  Tipo de registro: TXT
-  Dirección: v = spf1 include include SPF. Protection. Outlook. com-All 
         
-  Seleccione **ACEPTAR**.
   
## <a name="add-srv-records"></a>Agregar registros SRV
<a name="BKMK_add_SRV"> </a>

Agregue los dos registros SRV necesarios para Microsoft.

Agregue el registro SRV SIP para conferencias web de Skype Empresarial Online.  <br/> 
-  En la página del administrador de DNS de su dominio, vaya a **acción** \> **otros registros nuevos**. 
-   En la ventana **tipo de registro de recursos** , seleccione ubicación de **servicio (SRV)** y, a continuación, seleccione **crear registro**. 
-   En el cuadro de diálogo **nuevo registro de recursos** , asegúrese de que los campos se configuran exactamente con los valores siguientes:  
    -  Servicio: _sip
    -  Protocolo: _tls
    -  Prioridad: 100
    -  Peso: 1
    -  Puerto: 443
    -  Destino (nombre de host): sipdir.online.lync.com
-  Seleccione **ACEPTAR**. 


Agregue el registro SRV SIP para la federación de Skype Empresarial Online.  
-  En la página del administrador de DNS de su dominio, vaya a **acción** \> **otros registros nuevos**.  
-  En la ventana **tipo de registro de recursos** , seleccione ubicación de **servicio (SRV)** y, a continuación, seleccione **crear registro**. 
-   En el cuadro de diálogo **nuevo registro de recursos** , asegúrese de que los campos se configuran exactamente con los valores siguientes:  
    -  Servicio: _sipfederationtls
    -  Protocolo: _tcp
    -  Prioridad: 100
    -  Peso: 1
    -  Puerto: 5061
    -  Destino (nombre de host): sipfed.online.lync.com
-  Seleccione **ACEPTAR**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Agregar un registro para verificar que posee el dominio si todavía no lo ha hecho
<a name="BKMK_verify"> </a>

Antes de agregar los registros DNS para configurar los servicios de Microsoft, Microsoft tiene que confirmar que es el propietario del dominio que está agregando. Para ello, debe agregar un registro, siguiendo los pasos que se indican a continuación.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio. 
  

1. Recopilar información de Microsoft.  <br/> 
2. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>. 
3. En la página **dominios** , en la columna **acciones** del dominio que está comprobando, seleccione **Iniciar configuración**. 
4. En la página **Agregar un dominio a Microsoft** , seleccione **iniciar paso 1**. 
5. En la página **confirme que es el propietario de su dominio** , en la lista desplegable **vea las instrucciones para realizar este paso con** , seleccione **instrucciones generales**. 
6. En la tabla, copie el valor Destination or Points to Address. Lo necesitará en el siguiente paso. Se recomienda copiar y pegar este valor para que todo el espaciado sea correcto.

Agregue un registro TXT. 
-  En la página del administrador de DNS de su dominio, vaya a **acción** \> **texto (txt)**. 
-   En el cuadro de diálogo **nuevo registro de recursos** , seleccione **Editar**.  
-  En el área **nombres de host personalizados** del cuadro de diálogo **nuevo registro de recursos** , asegúrese de que los campos se configuran exactamente con los valores siguientes. 

> [!IMPORTANT] 
> En algunas versiones del administrador de DNS de Windows, es posible que el dominio se haya configurado de modo que, al crear un registro TXT, el nombre del domicilio predeterminado sea el dominio primario. En esta situación, al agregar un registro TXT, establezca el nombre de host en blanco (ningún valor) en lugar de configurarlo para @ o el nombre de dominio. 

- Nombre de host: @
- Tipo: TXT
- Address: pegue el valor de destino o dirección de destino que acaba de copiar desde Microsoft aquí.  
- Seleccione **Aceptar**  >  **listo**.

Compruebe su dominio en Microsoft.  
> [!IMPORTANT]
> Espere unos 15 minutos antes de hacerlo, de modo que el registro que acaba de crear pueda actualizarse a través de Internet.       

- Vuelva a Microsoft y siga los pasos que se indican a continuación para solicitar una comprobación. La comprobación busca el registro TXT que agregó en el paso anterior. Cuando encuentra el registro correcto TXT, el dominio se comprueba.  
1. En el centro de administración, vaya a la página de **configuración** de \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .
2. En la página **dominios** , en la columna **acción** del dominio que está comprobando, seleccione **Iniciar configuración**. 
3. En la página **confirmar que es el propietario de su dominio** , seleccione **listo, comprobar ahora**y, a continuación, en el cuadro de diálogo de confirmación, seleccione **Finalizar**. 
   
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Dirección de correo electrónico no enrutable usada como un UPN en su Active Directory local
<a name="BKMK_ADNote"> </a>

Si tiene previsto sincronizar su Active Directory local con Microsoft, querrá asegurarse de que el sufijo de nombre principal de usuario (UPN) de Active Directory es un sufijo de dominio válido y no un sufijo de dominio no admitido, como @contoso. local. Si necesita cambiar el sufijo UPN, vea [Cómo preparar un dominio no enrutable para la sincronización de directorios](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
