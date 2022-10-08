---
title: Conexión de los registros DNS en OVH a Microsoft 365
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial En línea y otros servicios en OVH para Microsoft.
ms.openlocfilehash: 3caf1207f70d592a43e45b8210c5d18ff09662cc
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68207035"
---
# <a name="connect-your-dns-records-at-ovh-to-microsoft-365"></a>Conexión de los registros DNS en OVH a Microsoft 365

[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml) si no encuentra lo que busca.

Si OVH es el proveedor de hospedaje dns, siga los pasos de este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial en línea, etc.

Después de agregar estos registros en OVH, el dominio se configurará para trabajar con servicios de Microsoft.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.

> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.

1. Para empezar, vaya a la página dominios en OVH mediante [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.

    ![Inicio de sesión de OVH.](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. En la página de aterrizaje del panel, en **Ver toda mi actividad**, seleccione el nombre del dominio que desea editar.

1. Seleccione **Zona DNS**.

    ![OVH Seleccione zona DNS.](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)

1. Seleccione **Agregar una entrada**.

    ![OVH Agregue una entrada.](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. Seleccione **TXT.**

    ![OVH seleccione la entrada TXT.](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente. Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y escriba el valor en el cuadro de texto.

   |Tipo de registro|Subdominio|TTL|Valor|
   |---|---|---|---|
   |TXT|(se deja en blanco)|3600 (segundos)|MS=msxxxxxxxx  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla.  [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|

1. Seleccione **Siguiente**.

1. Seleccione **Confirmar**.

    ![OVH confirme TXT para la verificación.](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)

1. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.

Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro. Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.

Para comprobar el registro en Microsoft 365:

1. En el centro de administración, vaya a **Dominios de configuración**\>.<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a>

1. En la página Dominios, seleccione el dominio que está comprobando y seleccione **Iniciar configuración**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Seleccione Iniciar configuración.":::

1. Seleccione **Continuar**.

1. En la página **Verificar dominio**, elija **Verificar**.

> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft

1. Para empezar, vaya a la página dominios en OVH mediante [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.

    ![Inicio de sesión de OVH.](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. En la página de aterrizaje del panel, en **Ver toda mi actividad**, seleccione el nombre del dominio que desea editar.

1. Seleccione **Zona DNS**.

    ![OVH Seleccione zona DNS.](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)

1. Seleccione **Agregar una entrada**.

    ![OVH Agregue una entrada.](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. Seleccione **MX**.

    ![Tipo de registro MX de OVH.](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente. Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y escriba el valor en el cuadro de texto.

    > [!NOTE]
    > De forma predeterminada, OVH usa la notación relativa para el destino, que agrega el nombre de dominio al final del registro de destino. Para usar la notación absoluta en su lugar, agregue un punto al registro de destino, como se muestra en la tabla siguiente.

   |Subdominio|TTL|Prioridad|Target|
   |---|---|---|---|
   |(se deja en blanco)|3600 (segundos)|0  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)|\<domain-key\>.mail.protection.outlook.com.  <br/> **Nota:** Obtenga su *\<domain-key\>* de su cuenta Microsoft. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|

    ![Registro MX de OVH para correo.](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)

1. Seleccione **Siguiente**.

    ![Registro MX de OVH seleccione Siguiente.](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)

1. Seleccione **Confirmar**.

    ![Registro MX de OVH seleccione Confirmar.](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)

1. Elimine cualquier otro registro MX de la lista en la página **de zona DNS** . Seleccione cada registro y, en la columna **Acciones** , seleccione el icono **Eliminar** de papelera.

    ![OVH elimina el registro MX.](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)

1. Seleccione **Confirmar**.

## <a name="add-the-cname-record-required-for-microsoft"></a>Agregar el registro CNAME necesario para Microsoft

1. Para empezar, vaya a la página dominios en OVH mediante [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.

    ![Inicio de sesión de OVH.](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. En la página de aterrizaje del panel, en **Ver toda mi actividad**, seleccione el nombre del dominio que desea editar.

1. Seleccione **Zona DNS**.

    ![OVH Seleccione zona DNS.](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)

1. Seleccione **Agregar una entrada**.

    ![OVH Agregue una entrada.](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. Seleccione **CNAME**.

    ![OVH Agregar tipo de registro CNAME.](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente. Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y escriba el valor en el cuadro de texto.

   |Subdominio|TTL|Target|
   |---|---|---|
   |autodescubrir|3600 (segundos)|autodiscover.outlook.com.|

    ![Registro CNAME de OVH.](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)

1. Seleccione **Siguiente**.

    ![OVH Agregue valores CNAME y seleccione Siguiente.](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)

1. Seleccione **Confirmar**.

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un  *único*  registro SPF que incluya ambos conjuntos de valores.

1. Para empezar, vaya a la página dominios en OVH mediante [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.

    ![Inicio de sesión de OVH.](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. En la página de aterrizaje del panel, en **Ver toda mi actividad**, seleccione el nombre del dominio que desea editar.

1. Seleccione **Zona DNS**.

    ![OVH Seleccione zona DNS.](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)

1. Seleccione **Agregar una entrada**.

    ![OVH Agregue una entrada.](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. Seleccione **TXT**.

1. In the boxes for the new record, type or copy and paste the following values. Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y escriba el valor en el cuadro de texto.

   |Subdominio|TTL|Valor|
   |---|---|---|
   |(se deja en blanco)|3600 (segundos)|v=spf1 include:spf.protection.outlook.com -all <br/**Note:** Se recomienda copiar y pegar esta entrada para que todo el espaciado permanezca correcto.|

    ![OVH Agregar registro TXT para SPF.](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)

1. Seleccione **Siguiente**.

    ![OVH Add TXT record for SPF (Agregar registro TXT para SPF) y seleccione Siguiente.](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)

1. Seleccione **Confirmar**.

    ![OVH Agregar registro TXT para SPF y Confirmar.](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)

## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial para servicios de comunicación en línea, como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita 4 registros: 2 registros SRV para la comunicación de usuario a usuario y 2 registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-the-two-required-srv-records"></a>Agregar los dos registros SRV necesarios

1. Para empezar, vaya a la página dominios en OVH mediante [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.

    ![Inicio de sesión de OVH.](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. En la página de aterrizaje del panel, en **Ver toda mi actividad**, seleccione el nombre del dominio que desea editar.

1. Seleccione **Zona DNS**.

    ![OVH Seleccione zona DNS.](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)

1. Seleccione **Agregar una entrada**.

    ![OVH Agregue una entrada.](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. Seleccione **SRV**.

1. In the boxes for the new record, type or copy and paste the following values. Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y escriba el valor en el cuadro de texto.

   |Subdominio|TTL (Seconds)|Prioridad|Peso|Puerto|Target|
   |---|---|---|---|---|---|
   |_sip._tls|3600 (s.)|100|1|443|sipdir.online.lync.com. **Este valor DEBE terminar con un punto (.)**><br> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.|
   |_sipfederationtls._tcp|3600 (s.)|100|1|5061|sipfed.online.lync.com. **Este valor DEBE terminar en punto (.)**<br> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.|

1. Para agregar el otro registro SRV, seleccione **Agregar otro registro**, cree un registro con los valores de la fila siguiente de la tabla y, a continuación, seleccione **Crear registros**.

> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>Agregue los dos registros CNAME necesarios para Skype Empresarial

1. Para empezar, vaya a la página dominios en OVH mediante [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.

    ![Inicio de sesión de OVH.](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. En la página de aterrizaje del panel, en **Ver toda mi actividad**, seleccione el nombre del dominio que desea editar.

1. Seleccione **Zona DNS**.

    ![OVH Seleccione zona DNS.](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)

1. Seleccione **Agregar una entrada**.

    ![OVH Agregue una entrada.](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. Seleccione **CNAME**.

    ![OVH Agregar tipo de registro CNAME.](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente. Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y escriba el valor en el cuadro de texto.

   |Subdominio|TTL|Target|
   |---|---|---|
   |sip|3600 (s.)|sipdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)**|
   |lyncdiscover|3600 (s.)|webdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)**|

1. Seleccione **Siguiente**.

    ![OVH Agregue valores CNAME y seleccione Siguiente.](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)

1. Seleccione **Confirmar**.

1. Agregue el otro registro CNAME.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Opción avanzada: Intune y mobile Administración de dispositivos para Microsoft 365

Este servicio le ayuda a proteger y administrar de forma remota los dispositivos móviles que se conectan a su dominio. Mobile Administración de dispositivos necesita dos registros CNAME para que los usuarios puedan inscribir dispositivos en el servicio.

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>Agregue los dos registros CNAME necesarios para Mobile Administración de dispositivos

1. Para empezar, vaya a la página dominios en OVH mediante [este vínculo](https://www.ovh.com/manager/). You'll be prompted to log in.

    ![Inicio de sesión de OVH.](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. En la página de aterrizaje del panel, en **Ver toda mi actividad**, seleccione el nombre del dominio que desea editar.

1. Seleccione **Zona DNS**.

    ![OVH Seleccione zona DNS.](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)

1. Seleccione **Agregar una entrada**.

    ![OVH Agregue una entrada.](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. Seleccione **CNAME**.

    ![OVH Agregar tipo de registro CNAME.](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente. Para asignar un valor TTL, elija **Personalizado** en la lista desplegable y escriba el valor en el cuadro de texto.

   |Subdominio|TTL|Target|
   |---|---|---|
   |enterpriseregistration  <br/>|3600 (s.)|enterpriseregistration.windows.net.  <br/> **Este valor DEBE terminar en punto (.)**|
   |enterpriseenrollment|3600 (s.)|enterpriseenrollment-s.manage.microsoft.com.  <br/> **Este valor DEBE terminar en punto (.).**|

1. Seleccione **Siguiente**.

    ![OVH Agregue valores CNAME y seleccione Siguiente.](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)

1. Seleccione **Confirmar**.

1. Agregue el otro registro CNAME.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).