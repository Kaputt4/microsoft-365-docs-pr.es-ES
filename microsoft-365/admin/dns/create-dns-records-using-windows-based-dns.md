---
title: Crear registros DNS para Microsoft con DNS basado en Windows
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Obtenga información sobre cómo comprobar el dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en DNS basado en Windows para Microsoft.
ms.openlocfilehash: fd7c56b6db9fe5f5dbb0637ad5abcb40a64bef8f
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876354"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Crear registros DNS para Microsoft con DNS basado en Windows

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
   
Si hospeda sus propios registros DNS utilizando DNS basado en Windows, siga los pasos indicados en este artículo para configurar los registros para el correo electrónico, Skype Empresarial Online, y para otras tareas.
  
Para empezar, debes buscar los [registros DNS](#find-your-dns-records-in-windows-based-dns) en DNS basado en Windows para que puedas actualizarlos. Además, si está planeando sincronizar su Active Directory local con Microsoft, vea Dirección de correo electrónico no enrutable usada como [UPN](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)en su Active Directory local.
  
Problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea Solucionar problemas después de cambiar el nombre de [dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Buscar los registros DNS en DNS basado en Windows
<a name="BKMK_find_your_dns_1"></a> Vaya a la página que tiene los registros DNS de su dominio. Si estás trabajando en Windows Server 2008, ve a **Iniciar**  >  **ejecución**. Si estás trabajando en Windows Server 2012, presiona la tecla Windows y **r**. Escriba **dnsmgmnt.msc y,** a continuación, seleccione **Aceptar**. En el Administrador dns, expanda **\<DNS server name\> \> Zonas de búsqueda directa**. Seleccione su dominio. Ya está listo para crear los registros DNS.
   
## <a name="add-mx-record"></a>Agregar registro MX
<a name="BKMK_add_MX"> </a>

Agregue un registro MX para que el correo electrónico de su dominio se envíe a Microsoft.
- El registro MX que agregará incluye un valor (el valor **Points to address)** que tiene un aspecto similar al siguiente: .mail.protection.outlook.com, donde es un valor como \<MX token\> \<MX token\> MSxxxxxxx. 
- En la fila MX de la sección Exchange Online de la página Agregar registros DNS en Microsoft, copie el valor que aparece en Puntos para la dirección. Usará este valor en el registro que está creando en esta tarea. 
- En la página Administrador dns del dominio, vaya a **Exchanger de** correo de  >  **acción (MX).** Para encontrar esta página para el dominio, consulta [Buscar los registros DNS en DNS basado en Windows](#find-your-dns-records-in-windows-based-dns).  
- En el **cuadro de diálogo Nuevo registro de** recursos, asegúrese de que los campos están establecidos exactamente en los siguientes valores: 
    - Nombre de host:  
    - @Address: pegue el valor points to address que acaba de copiar de Microsoft aquí.  
    - Pref: 
- Seleccione **Guardar cambios**.
- Elimine los registros MX obsoletos. Si tiene registros MX antiguos para este dominio que enrutar el correo electrónico en otro lugar, active la casilla situada junto a cada registro antiguo y, a continuación, **seleccione**  >  **Eliminar aceptar**. 
   
## <a name="add-cname-records"></a>Agregar registros CNAME
<a name="BKMK_add_CNAME"> </a>

Agregue los registros CNAME necesarios para Microsoft. Si se enumeran registros CNAME adicionales en Microsoft, agregue los siguientes pasos generales que se muestran aquí.
  
> [!IMPORTANT]
> Si tienes Administración de dispositivos móviles (MDM) para Microsoft, debes crear dos registros CNAME adicionales. Siga el procedimiento que utilizó para los otros cuatro registros CNAME, pero suministre los valores de la siguiente tabla. (Si no tienes MDM, puedes omitir este paso). 

- En la página Administrador dns del dominio, vaya a **Action**  >  **CNAME (CNAME)**.
- En el **cuadro de diálogo Nuevo registro de** recursos, asegúrese de que los campos están establecidos exactamente en los siguientes valores:  
    - Nombre de host: detección automática
    - Tipo: 
    - CNAMEAddress: autodiscover.outlook.com
- Seleccione **O** K.

Agregue registro CNAME SIP. 
- En la página Administrador dns del dominio, vaya a **Action** \> **CNAME (CNAME)**. 
- En el **cuadro de diálogo Nuevo registro de** recursos, asegúrese de que los campos están establecidos exactamente en los siguientes valores:  
    - Nombre de host: sip
    - Tipo: CNAME
    - Dirección: sipdir.online.lync.com
- Seleccione **Aceptar**.

Agregue el registro CNAME de detección automática de Skype Empresarial Online.  
- En la página Administrador dns del dominio, vaya a **Action** \> **CNAME (CNAME)**. En el **cuadro de diálogo Nuevo registro de** recursos, asegúrese de que los campos están establecidos exactamente en los siguientes valores:  
    - Nombre de host: lyncdiscover
    - Tipo: CNAME
    - Dirección: webdir.online.lync.com
- Seleccione **Aceptar**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Agregar dos registros CNAME para administración de dispositivos móviles (MDM) para Microsoft

> [!IMPORTANT]
> Si tienes Administración de dispositivos móviles (MDM) para Microsoft, debes crear dos registros CNAME adicionales. Siga el procedimiento que utilizó para los otros cuatro registros CNAME, pero suministre los valores de la siguiente tabla. >(Si no tienes MDM, puedes omitir este paso). 
  

Agregue el registro CNAME de MDM Enterpriseregistration.  
- En la página Administrador dns del dominio, vaya a **Action** \> **CNAME (CNAME)**. 
- En el **cuadro de diálogo Nuevo registro de** recursos, asegúrese de que los campos están establecidos exactamente en los siguientes valores:  
- Nombre de host: enterpriseregistration
- Tipo: CNAME
- Dirección: enterpriseregistration.windows.net
- Seleccione **Aceptar**. 

Agregue el registro CNAME de MDM Enterpriseenrollment. 
-  En la página Administrador dns del dominio, vaya a **Action** \> **CNAME (CNAME)**. 
-  En el **cuadro de diálogo Nuevo registro de** recursos, asegúrese de que los campos están establecidos exactamente en los siguientes valores:  
    - Nombre de host: enterpriseenrollment
    - Tipo: CNAME
    - Dirección: enterpriseenrollment-s.manage.microsoft.com
- Seleccione **Aceptar**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores. 
  
Agregue el registro TXT de SPF para su dominio para prevenir el correo basura.
  
- Es posible que ya tenga otras cadenas en el valor TXT para este registro (como las cadenas de correo electrónico de marketing), es correcto. Deje estas cadenas en su lugar y agregue la siguiente, colocando comillas dobles alrededor de cada cadena para separarlas. 
- En la página Administrador dns del dominio, vaya a **Texto de** \> **acción (TXT)**. 
-  En el **cuadro de diálogo Nuevo registro de** recursos, asegúrese de que los campos están establecidos exactamente en los siguientes valores. 
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
-  En la página Administrador dns del dominio, vaya a **Acción** \> **Otros nuevos registros**. 
-   En la **ventana Tipo de registro de** recursos, seleccione Ubicación de servicio **(SRV)** y, a continuación, **seleccione Crear registro**. 
-   En el **cuadro de diálogo Nuevo registro de** recursos, asegúrese de que los campos están establecidos exactamente en los siguientes valores:  
    -  Servicio: _sip
    -  Protocolo: _tls
    -  Prioridad: 100
    -  Peso: 1
    -  Puerto: 443
    -  Destino (nombre de host): sipdir.online.lync.com
-  Seleccione **Aceptar**. 


Agregue el registro SRV SIP para la federación de Skype Empresarial Online.  
-  En la página Administrador dns del dominio, vaya a **Acción** \> **Otros nuevos registros**.  
-  En la **ventana Tipo de registro de** recursos, seleccione Ubicación de servicio **(SRV)** y, a continuación, **seleccione Crear registro**. 
-   En el **cuadro de diálogo Nuevo registro de** recursos, asegúrese de que los campos están establecidos exactamente en los siguientes valores:  
    -  Servicio: _sipfederationtls
    -  Protocolo: _tcp
    -  Prioridad: 100
    -  Peso: 1
    -  Puerto: 5061
    -  Destino (nombre de host): sipfed.online.lync.com
-  Seleccione **Aceptar**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Agregar un registro para verificar que posee el dominio si todavía no lo ha hecho
<a name="BKMK_verify"> </a>

Antes de agregar los registros DNS para configurar los servicios de Microsoft, Microsoft debe confirmar que es el propietario del dominio que está agregando. Para ello, debe agregar un registro, siguiendo los pasos que se indican a continuación.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio. 
  

1. Recopilar información de Microsoft.  <br/> 
2. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>. 
3. En la **página Dominios,** en la columna **Acciones** del dominio que está comprobando, seleccione **Iniciar instalación**. 
4. En la **página Agregar un dominio a Microsoft,** seleccione Iniciar paso **1**. 
5. On the **Confirm that you own your domain** page, in the See instructions for performing this step **with** drop-down list, choose **General instructions**. 
6. En la tabla, copie el valor Destination or Points to Address. Lo necesitará en el siguiente paso. Se recomienda copiar y pegar este valor para que todo el espaciado sea correcto.

Agregue un registro TXT. 
-  En la página Administrador dns del dominio, vaya a **Texto de** \> **acción (TXT)**. 
-   En el **cuadro de diálogo Nuevo registro de** recursos, seleccione **Editar**.  
-  En el área Nombres  **de host** personalizados del cuadro de diálogo Nuevo registro de recursos, asegúrese de que los campos están establecidos exactamente en los siguientes valores. 

> [!IMPORTANT] 
> En algunas versiones del Administrador de DNS de Windows, es posible que el dominio se haya configurado para que, al crear un registro txt, el nombre principal se establezca de forma predeterminada en el dominio primario. En esta situación, al agregar un registro TXT, establezca el nombre de host en blanco (ningún valor) en lugar de configurarlo para @ o el nombre de dominio. 

- Nombre de host: @
- Tipo: TXT
- Dirección: pegue aquí el valor Destino o Puntos a dirección que acaba de copiar de Microsoft.  
- Seleccione **Aceptar**  >  **listo**.

Compruebe su dominio en Microsoft.  
> [!IMPORTANT]
> Espere unos 15 minutos antes de hacerlo, para que el registro que acaba de crear pueda actualizarse en Internet.       

- Vuelva a Microsoft y siga los pasos siguientes para solicitar una comprobación de verificación. La comprobación busca el registro TXT que agregó en el paso anterior. Cuando encuentra el registro correcto TXT, el dominio se comprueba.  
1. En el Centro de administración, vaya a la página **Dominios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">de</a> instalación.
2. En la **página Dominios,** en la columna **Acción** del dominio que está comprobando, seleccione **Iniciar configuración**. 
3. En la **página Confirmar que es el** propietario de su dominio, seleccione **listo,** compruebe ahora y, a continuación, en el cuadro de diálogo de confirmación, seleccione **Finalizar**. 
   
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Dirección de correo electrónico no enrutable usada como un UPN en su Active Directory local
<a name="BKMK_ADNote"> </a>

Si está planeando sincronizar su Active Directory local con Microsoft, querrá asegurarse de que el sufijo de nombre principal de usuario (UPN) de Active Directory sea un sufijo de dominio válido y no un sufijo de dominio no compatible como @contoso.local. Si necesita cambiar el sufijo UPN, vea [How to prepare a non-routable domain for directory synchronization](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 

## <a name="related-content"></a>Contenido relacionado

[Transferir un dominio de Micrsoft 365 a otro host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host) (artículo)

[Piloto de Microsoft 365 desde mi dominio personalizado](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain) (artículo)

[Preguntas más frecuentes sobre](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) dominios (artículo)