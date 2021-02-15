---
title: Crear registros DNS en easyDNS para Microsoft
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at easyDNS for Microsoft.
ms.openlocfilehash: a971a722f071ef5df9ce0fba387cfacfeb409f5b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656824"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>Crear registros DNS en easyDNS para Microsoft

[Consulte las preguntas más frecuentes sobre ](../setup/domains-faq.yml) dominios si no encuentra lo que está buscando. 
  
Deberá agregar todos los siguientes registros DNS en el sitio web de su registrador para enrutar el correo a Microsoft, usar su dominio para Teams y Skype Empresarial, y así sucesivamente.
  
NOTA: Los registros SRV no están disponibles actualmente en todos los paquetes de servicio easyDNS. Es posible que tenga que actualizar a un nivel de servicio superior con easyDNS para agregar registros SRV necesarios para Skype Empresarial.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Comprobar que es el propietario del dominio con un registro TXT

1. Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales. 
    
2. En el **encabezado de todos los** dominios, seleccione **dns.**
    
3. En el **encabezado de registros TXT,** seleccione el botón editar (icono de llave inglesa). 
    
4. Escriba los siguientes registros en los campos de texto:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS=msXXXXXXXX (Use el valor que se le proporciona en la página Dominios del centro de administración)  <br/> |
   
5. Seleccione **SIGUIENTE**. 
    
6. Compruebe que el registro es correcto y, a continuación, seleccione **CONFIRMAR**. 
    
7. Espere unos minutos antes de continuar, para que el registro que acaba de crear se propague por Internet y microsoft lo detecte.
    
8. Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.
    
9. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.
    
10. En la página **Dominios**, elija el dominio que está verificando. 
    
11. En la **página Instalación,** seleccione **Iniciar configuración.**
    
12. En la página **Verificar dominio**, elija **Verificar**. 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>Agregar un registro MX para enrutar el correo electrónico a Microsoft

1. Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales. 
    
2. En el **encabezado de todos los** dominios, seleccione **dns.**
    
3. En el **encabezado de registros MX,** seleccione el botón editar (icono de llave inglesa). 
    
4. Escriba los siguientes registros en los campos de texto:
    
    |**CORREO PARA ZONA**|**SERVIDOR DE CORREO**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domain-key\>.mail.protection.outlook.com (obtenga su \<domain-key\> valor de la página Dominios del centro de administración)  <br/> |0  <br/> |
   
2. Si desea guardar los demás registros MX con fines de copia de seguridad, cópielos en algún lugar. Antes de seguir, quite todos los demás registros MX aquí.
    
5. Seleccione **SIGUIENTE**. 
    
6. Compruebe que el registro es correcto y, a continuación, seleccione **CONFIRMAR**. 
    
## <a name="add-the-required-cname-records"></a>Agregar los registros CNAME necesarios

1. Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales. 
    
2. En el **encabezado de todos los** dominios, seleccione **dns.**
    
3. En el **encabezado de registros CNAME/Alias,** seleccione el botón editar (icono llave inglesa). 
    
4. Escriba los siguientes registros en los campos de texto:


    |**HOST**|**Dirección (debe terminar con un ".")**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. Seleccione **SIGUIENTE**. 
    
6. Compruebe que el registro es correcto y, a continuación, seleccione **CONFIRMAR**. 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado

1. Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales. 
    
2. En el **encabezado de todos los** dominios, seleccione **dns.**
    
3. En el **encabezado de registros TXT,** seleccione el botón editar (icono de llave inglesa). 
    
4. Escriba los siguientes registros en los campos de texto:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Seleccione **SIGUIENTE**. 
    
6. Compruebe que el registro es correcto y, a continuación, seleccione **CONFIRMAR**. 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Agregar los dos registros SRV necesarios para Microsoft

NOTA: Los registros SRV no están disponibles actualmente en el nivel de servicio Dominio más de easyDNS. Es posible que deba actualizar a un nivel de servicio superior con easyDNS para agregar registros SRV 
  
1. Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales. 
    
2. En el **encabezado de todos los** dominios, seleccione **dns.**
    
3. En el encabezado **de registros SRV,** seleccione el botón editar (icono de llave inglesa). 
    
4. Escriba los siguientes registros en los campos de texto:
    
    |**SERVICIO**|**PROTO**|**HOST**|**PRI**|**WGT**|**PUERTO**|**TARGET(Debe terminar con un ".")**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Seleccione **SIGUIENTE**. 
    
6. Compruebe que el registro es correcto y, a continuación, seleccione **CONFIRMAR**. 
    

