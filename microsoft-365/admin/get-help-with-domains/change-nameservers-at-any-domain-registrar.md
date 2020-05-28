---
title: Cambiar los servidores DNS para configurar Microsoft 365 con cualquier registrador de dominios
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Obtenga información sobre cómo agregar y configurar el dominio en Microsoft 365 para que sus servicios como el correo electrónico y Skype empresarial online usen su propio nombre de dominio.
ms.openlocfilehash: 16e8699c1c8588a4368f04078fea44c165c13e29
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399997"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>Cambiar los servidores DNS para configurar Microsoft 365 con cualquier registrador de dominios

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Compruebe primero [la configuración del dominio (instrucciones específicas del host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) para ver si tenemos instrucciones para su registrador. 
  
Siga estas instrucciones para agregar y configurar el dominio en Microsoft 365 para que sus servicios como el correo electrónico y Skype empresarial online usen su propio nombre de dominio. Para ello, deberá comprobar el dominio y, a continuación, cambiar los servidores de nombres de dominio a Microsoft 365 para que se puedan configurar los registros DNS correctos. Siga estos pasos si la siguiente instrucción describe su situación:
  
- Tiene su propio dominio y desea configurarlo para que funcione con Microsoft 365.
    
- Desea que Microsoft 365 administre sus registros DNS por usted. (Si lo prefiere, puede [administrar sus propios registros DNS](../setup/add-domain.md)).
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>Agregar un registro TXT o MX para su verificación
<a name="BKMK_verify"> </a>

> [!NOTE]
> Sólo debe crear uno de los dos registros. TXT es el tipo de registro preferido, pero algunos proveedores de host DNS no lo admiten. De ser así, puede crear un registro MX. 
  
Antes de utilizar el dominio con Microsoft 365, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft 365 sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>Busque el área del sitio web de su proveedor de host DNS en la que puede crear un registro nuevo

1. Inicie sesión en el sitio web del proveedor de host DNS.
    
2. Elija su dominio.
    
3. Busque la página donde puede modificar los registros DNS para su dominio.
    
### <a name="create-the-record"></a>Crear el registro

En función de si se está creando un registro TXT o un registro MX, siga uno de los procedimientos siguientes:
  
**Si crea un registro TXT, utilice estos valores:**
    
|||||
|:-----|:-----|:-----|:-----|
|**Tipo de registro** <br/> |**Alias** o **Nombre de host** <br/> |**Valor** <br/> |**TTL** <br/> |
|TXT  <br/> |Realice una de las siguientes acciones: escriba **@**, deje el campo vacío o escriba el nombre de dominio.    <br/> > [!NOTE]> Los distintos hosts DNS tienen requisitos distintos para este campo.           
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> Esto es un ejemplo. Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365.           [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |Configure este valor como **1 hora** o el equivalente en minutos ( **60** ), segundos ( **3600** ), etc.  <br/> |
   
**Si crea un registro MX, utilice estos valores:**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Tipo de registro**|**Alias** o **Nombre de host**|**Valor**|**Prioridad**|**TTL**|
|MX|Escriba **@** o el nombre del dominio. |MS=ms *XXXXXXXX* > [!NOTE]> Esto es un ejemplo. Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365.           [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |Para**Prioridad**, para evitar conflictos con el registro MX usado para el flujo de correo, use una prioridad más baja que la prioridad de cualquier registro MX existente. Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.md#what-is-mx-priority) |Configure este valor como **1 hora** o el equivalente en minutos ( **60** ), segundos ( **3600** ), etc. |
   
### <a name="save-the-record"></a>Guardar el registro

Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro.
  
Cuando Microsoft 365 encuentre el registro TXT correcto, se comprobará su dominio.
  

1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.
    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
  
3. En la página de **Configuración**, elija ** Iniciar configuración**.
 
    
  
4. En la página**verificar dominio**, seleccione **verificar**.
    
    
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Cambiar los registros del servidor de nombres (o NS) de su dominio
<a name="BKMK_nameservers"> </a>

Cuando llegue al último paso del asistente de configuración de dominios de Microsoft 365, tiene una tarea restante. Para configurar el dominio con los servicios de Microsoft 365, como el correo electrónico, cambie los registros del servidor de nombres (o NS) de su dominio en su registrador de dominios para que apunten a los servidores de nombres principales y secundarios de Microsoft 365. A continuación, como Microsoft 365 hospeda el DNS, los registros DNS necesarios para los servicios se configuran automáticamente. Puede actualizar los registros NS usted mismo siguiendo los pasos que su registrador de dominios debe proporcionar en el apartado de ayuda de su sitio web. Si no está familiarizado con DNS, pónganse en contacto con el registrador del dominio.

::: moniker range="o365-worldwide"
  
Para cambiar los servidores DNS en el sitio web del registrador de dominios usted mismo, haga lo siguiente:
  
1. En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.
    
2. Cree dos registros de servidor DNS o modifique los existentes para que coincidan con los valores siguientes:
    
|||
|:-----|:-----|
|Primer servidor de nombres  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Segundo servidor de nombres  <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > Debe usar al menos dos registros de servidor de nombres. Si en la lista se muestran otros servidores DNS, puede eliminarlos o cambiarlos a **NS3.BDM.microsoftonline.com** y **NS4.BDM.microsoftonline.com**. 
  
3. Guarde los cambios.
    
> [!CAUTION]
> Al cambiar los registros NS de su dominio para que apunten a los servidores de nombres de Microsoft 365, se ven afectados todos los servicios que están actualmente asociados a su dominio. Si ha omitido algún paso del asistente, como añadir direcciones de correo electrónico, o si utiliza el dominio para blogs, cestas de compra u otros servicios, se necesitan realizar más pasos. De lo contrario, este cambio podría traducirse en una interrupción del servicio, como por ejemplo que no se pueda acceder al correo electrónico o a su sitio web. 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.
    
2. Cree dos registros de servidor DNS o modifique los existentes para que coincidan con los valores siguientes:
    
|||
|:-----|:-----|
|Primer servidor de nombres  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|Segundo servidor de nombres  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > Debe usar al menos dos registros de servidor de nombres. Si en la lista se muestran otros servidores DNS, puede eliminarlos o cambiarlos a **NS3.DNS.Partner.microsoftonline.cn** y **NS4.DNS.Partner.microsoftonline.cn**. 
  
3. Guarde los cambios.
    
> [!CAUTION]
> Al cambiar los registros NS de su dominio para que apunten a los servidores de nombres de Office 365 operados por 21Vianet, se ven afectados todos los servicios que están actualmente asociados a su dominio. Si ha omitido algún paso del asistente, como añadir direcciones de correo electrónico, o si utiliza el dominio para blogs, cestas de compra u otros servicios, se necesitan realizar más pasos. De lo contrario, este cambio podría traducirse en una interrupción del servicio, como por ejemplo que no se pueda acceder al correo electrónico o a su sitio web. 

::: moniker-end
  
Por ejemplo, aquí se indican algunos pasos adicionales que podrían ser necesarios para el hospedaje de correo electrónico y sitios web:
  
- Mueva todas las direcciones de correo electrónico que usan su dominio a Microsoft 365 antes de cambiar los registros NS.
    
- ¿Quiere agregar un dominio que se utiliza actualmente con una dirección de página web, como www.fourthcoffee.com? Puede seguir los pasos que se indican a continuación mientras agrega el dominio para mantener su sitio web hospedado donde se hospeda el sitio ahora, de modo que los usuarios puedan seguir teniendo acceso al sitio web después de cambiar los registros NS del dominio para que apunten a Microsoft 365.

1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.

3. En la página Dominios, seleccione un dominio.

4. En **configuración DNS**, seleccione **registros personalizados**y, a continuación, seleccione **nuevo registro personalizado**.

5. Seleccione el tipo de registro DNS que desea agregar y escriba la información para el nuevo registro.

6. Haga clic en **Guardar**.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio. 
  

