---
title: Crear registros DNS en easyDNS para Microsoft
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en easyDNS para Microsoft.
ms.openlocfilehash: b7b29900108ab94f0fd99dcf3404cfa137ce92ff
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631362"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>Crear registros DNS en easyDNS para Microsoft

[Consulte preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md) si no encuentra lo que está buscando. 
  
Deberá agregar todos los registros DNS siguientes al sitio web del registrador para enrutar el correo a Microsoft, usar su dominio para Teams y Skype empresarial, y así sucesivamente.
  
Nota: Actualmente, los registros SRV no están disponibles en todos los paquetes del servicio de easyDNS. Es posible que necesite actualizar a un nivel de servicio superior con easyDNS para agregar los registros SRV necesarios para Skype empresarial.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Comprobar que es el propietario del dominio con un registro TXT

1. Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales. 
    
2. En el encabezado **todos los dominios** , seleccione **DNS.**
    
3. En el encabezado **registros txt** , selecciona el botón Editar (icono de llave inglesa). 
    
4. Escriba los siguientes registros en los campos de texto:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS = msXXXXXXXX (use el valor que se proporciona en la página de dominios del centro de administración)  <br/> |
   
5. Seleccione **siguiente**. 
    
6. Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**. 
    
7. Espere unos minutos antes de continuar, para que el registro que acaba de crear pueda propagarse a través de Internet y sea detectado por Microsoft.
    
8. Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará el registro.
    
9. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.
    
10. En la página **Dominios**, elija el dominio que está verificando. 
    
11. En la página **configuración** , seleccione **Iniciar configuración.**
    
12. En la página**verificar dominio**, seleccione **verificar**. 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>Agregar un registro MX para redirigir el correo electrónico a Microsoft

1. Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales. 
    
2. En el encabezado **todos los dominios** , seleccione **DNS.**
    
3. En el encabezado **registros MX** , selecciona el botón Editar (icono de llave inglesa). 
    
4. Escriba los siguientes registros en los campos de texto:
    
    |**CORREO PARA LA ZONA**|**SERVIDOR DE CORREO**|**DISTINGUIR**|
    |:-----|:-----|:-----|
    |@  <br/> |\<Domain-Key\>. mail.Protection.Outlook.com (obtener el \<valor de clave\> de dominio de la página de dominios del centro de administración)  <br/> |comprendi  <br/> |
   
2. Si desea guardar los demás registros MX para fines de copia de seguridad, cópielos en algún lugar. Antes de continuar, elimine todos los demás registros MX.
    
5. Seleccione **siguiente**. 
    
6. Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**. 
    
## <a name="add-the-required-cname-records"></a>Agregar los registros CNAME necesarios

1. Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales. 
    
2. En el encabezado **todos los dominios** , seleccione **DNS.**
    
3. En el encabezado **registros CNAME/alias** , selecciona el botón Editar (icono de llave inglesa). 
    
4. Escriba los siguientes registros en los campos de texto:


    |**HOST**|**Address (debe terminar con un ".")**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. Seleccione **siguiente**. 
    
6. Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**. 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

1. Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales. 
    
2. En el encabezado **todos los dominios** , seleccione **DNS.**
    
3. En el encabezado **registros txt** , selecciona el botón Editar (icono de llave inglesa). 
    
4. Escriba los siguientes registros en los campos de texto:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Seleccione **siguiente**. 
    
6. Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**. 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Agregar los dos registros SRV necesarios para Microsoft

Nota: Actualmente, los registros SRV no están disponibles en easyDNS ' dominio más nivel de servicio. Es posible que necesite actualizar a un nivel de servicio superior con easyDNS para agregar registros SRV 
  
1. Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales. 
    
2. En el encabezado **todos los dominios** , seleccione **DNS.**
    
3. En el encabezado **registros SRV** , selecciona el botón Editar (icono de llave inglesa). 
    
4. Escriba los siguientes registros en los campos de texto:
    
    |**SERVICIO**|**Protocolo**|**HOST**|**PRIORIDAD**|**WGT**|**PUERTO**|**DESTINO (debe terminar con ".")**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Seleccione **siguiente**. 
    
6. Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**. 
    

