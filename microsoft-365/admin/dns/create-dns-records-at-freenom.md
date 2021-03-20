---
title: Crear registros DNS en Freenom para Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en Freenom para Microsoft.
ms.openlocfilehash: 8332d63acf34a7f999b549467494b7819cebf092
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910359"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a>Crear registros DNS en Freenom para Microsoft

[Consulta las preguntas más frecuentes ](../setup/domains-faq.yml) sobre dominios si no encuentras lo que estás buscando. 
  
> [!CAUTION]
> El sitio web de Freenom no admite registros SRV, lo que significa que varias características de Skype Empresarial Online y Outlook Web App no funcionarán. Independientemente del plan de Microsoft que use, existen limitaciones de servicio importantes y es posible que desee cambiar a otro proveedor de hospedaje DNS. 
  
Si, a pesar de las limitaciones del servicio, elige administrar sus propios registros DNS de Microsoft en Freenom, siga los pasos descritos en este artículo para comprobar su dominio y configurar registros DNS para correo electrónico y otros servicios.
  
  
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="bkmk_txt"> </a>

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a la página dominios de Freenom mediante [este vínculo](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Inicio de sesión de Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Seleccione **Servicios** y, a continuación, **Mis dominios**.
    
    ![Freenom seleccione Servicios y Mis dominios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Para el dominio que desea editar, seleccione **Administrar dominio**.
    
    ![Freenom seleccione Administrar dominio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Seleccione **Administrar DNS de Freenom**.
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. En **Agregar registro**, en la columna **Tipo,** elija **TXT** en el menú. 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente. 
    
    |**Nombre**|**Tipo**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(se deja en blanco)  <br/> |TXT  <br/> |3600 (segundos)  <br/> |MS=msXXXXXXXX  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla.           [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Valores TXT de Freenom para verificación](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. Seleccione **Guardar cambios**.
    
    ![Registro TXT de Freenom Guardar cambios](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.

    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
    
  
3. En la página de **Configuración**, elija **Iniciar configuración**.
    
    
  
4. En la página **verificar dominio**, seleccione **verificar**.
    
    
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft
<a name="bkmk_mx"> </a>

1. Para empezar, vaya a la página dominios de Freenom mediante [este vínculo](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Inicio de sesión de Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Seleccione **Servicios** y, a continuación, **Mis dominios**.
    
    ![Freenom seleccione Servicios y Mis dominios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Para el dominio que desea editar, seleccione **Administrar dominio**.
    
    ![Freenom seleccione Administrar dominio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Establezca el nombre que sirve para su dominio en los servidores de nombres freenom predeterminados. Seleccione **Herramientas de administración** y, a continuación, seleccione Servidores de **nombres**.
    
    ![Configuración de servidores de nombres freenom](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. Asegúrese de **que Use default nameservers** está seleccionado y, a continuación, **seleccione Cambiar servidores de nombres**.
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. Seleccione **Administrar DNS de Freenom**.
    
    ![Freenom select Manage Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. En **Agregar registro**, en la columna **Tipo,** elija **MX** en el menú. 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente. 
    
    |**Nombre**|**Tipo**|**TTL**|**Target**|**Prioridad**|
    |:-----|:-----|:-----|:-----|:-----|
    |(se deja en blanco)  <br/> |MX (intercambiador de correo)  <br/> |3600 (segundos)  <br/> |\<domain-key\>.mail.protection.outlook.com  <br/> **Nota:** Obtener el  *\<domain-key\>*  de su cuenta de Microsoft.   [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md)          |10    <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml) <br/> |
   
   ![Registro MX de Freenom](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. Seleccione **Guardar cambios**.
    
    ![Registro MX de Freenom Guardar cambios](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. Si hay otros registros MX, elimínelos todos. Para cada registro, seleccione **Eliminar**. Cuando aparezca el **mensaje ¿Realmente desea quitar esta entrada?** seleccione **Aceptar**.
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Agregar los registros CNAME necesarios para Microsoft
<a name="bkmk_cname"> </a>

1. Para empezar, vaya a la página dominios de Freenom mediante [este vínculo](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Inicio de sesión de Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Seleccione **Servicios** y, a continuación, **Mis dominios**.
    
    ![Freenom seleccione Servicios y Mis dominios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Para el dominio que desea editar, seleccione **Administrar dominio**.
    
    ![Freenom seleccione Administrar dominio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Seleccione **Administrar DNS de Freenom**.
    
    ![Freenom select Manage Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. En **Agregar registro**, en la columna **Tipo,** elija **CNAME** en el menú. 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. Cree el primer registro CNAME. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente. 
    
    |**Nombre**|**Tipo de registro**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Valores CNAME de Freenom](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. Seleccione **Guardar cambios**.
    
    ![Freenom CNAME Guardar cambios](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. Repita los pasos anteriores para crear los otros cinco registros CNAME. 
    
    Para cada registro, escriba o copie y pegue los valores de la siguiente fila de la tabla anterior en los cuadros de ese registro.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores. 

1. Para empezar, vaya a la página dominios de Freenom mediante [este vínculo](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Inicio de sesión de Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Seleccione **Servicios** y, a continuación, **Mis dominios**.
    
    ![Freenom seleccione Servicios y Mis dominios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Para el dominio que desea editar, seleccione **Administrar dominio**.
    
    ![Freenom seleccione Administrar dominio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Seleccione **Administrar DNS de Freenom**.
    
    ![Freenom select Manage Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. En **Agregar registro**, en la columna **Tipo,** elija **TXT** en el menú. 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. In the boxes for the new record, type or copy and paste the following values. 
    
    |**Nombre**|**Tipo de registro**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(se deja en blanco)  <br/> |TXT  <br/> |3600 (segundos)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |
   
    ![Valores TXT de Freenom para SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. Seleccione **Guardar cambios**.
    
    ![Registro TXT de Freenom para SPF Guardar cambios](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
