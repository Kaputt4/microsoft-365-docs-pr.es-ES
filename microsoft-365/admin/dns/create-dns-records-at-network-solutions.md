---
title: Conexión de los registros DNS en Soluciones de red a Microsoft 365
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
- Tier2
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial En línea y otros servicios en Soluciones de red para Microsoft.
ms.openlocfilehash: f108bf8caef2485c35ded7af9de888798764cadd
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68727595"
---
# <a name="connect-your-dns-records-at-network-solutions-to-microsoft-365"></a>Conexión de los registros DNS en Soluciones de red a Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Si Network Solutions es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.

Después de agregar estos registros en Soluciones de red, el dominio se configurará para trabajar con servicios de Microsoft.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.

> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.

1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). You'll be prompted to log in.

1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. Active la casilla situada junto al dominio que desea modificar.

1. En **Acciones**, seleccione los tres puntos y, a continuación, seleccione **Administrar** en la lista desplegable.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Desplácese hacia abajo para seleccionar **Herramientas avanzadas** y, junto a **Registros DNS avanzados**, seleccione **ADMINISTRAR**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

   Es posible que tenga que seleccionar **Continuar** para acceder a la página Administrar registros DNS avanzados.

1. En la página Administrar registros DNS avanzados, seleccione **+AGREGAR REGISTRO**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add-record.png" alt-text="Seleccione +AGREGAR REGISTRO.":::

1. En **Tipo**, seleccione **TXT** en la lista desplegable.

1. In the boxes for the new record, type or copy and paste the values in the following table.

   |Hace referencia a|TXT Value|TTL|
   |---|---|---|
   |@  <br/> (The system will change this value to **@ (None)** when you save the record.)|MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla.  [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|3600|

1. Seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add.png" alt-text="Seleccione AGREGAR.":::

   > [!NOTE]
   > Seleccione **Vista clásica** en la esquina superior derecha para ver el registro TXT que ha creado.

   Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.

Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro. Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.

Para comprobar el registro en Microsoft 365:

1. En el centro de administración, vaya a **Dominios de configuración**\>.<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a>

1. En la página Dominios, seleccione el dominio que está comprobando y seleccione **Iniciar configuración**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Seleccione Iniciar configuración.":::

1. Seleccione **Continuar**.

1. En la página **Verificar dominio**, elija **Verificar**.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft

1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). You'll be prompted to log in.

1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. Active la casilla situada junto al dominio que desea modificar.

1. En **Acciones**, seleccione los tres puntos y, a continuación, seleccione **Administrar** en la lista desplegable.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Desplácese hacia abajo para seleccionar **Herramientas avanzadas** y, junto a **Registros DNS avanzados**, seleccione **ADMINISTRAR**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

   Es posible que tenga que seleccionar **Continuar** para acceder a la página Administrar registros DNS avanzados.

1. En la página Administrar registros DNS avanzados, seleccione **+AGREGAR REGISTRO**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add-record.png" alt-text="Seleccione +AGREGAR REGISTRO.":::

1. En **Tipo**, seleccione **MX** en la lista desplegable.

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

   |Hace referencia a|Servidor de correo|Prioridad|TTL|
   |---|---|---|---|
   |@|*\<domain-key\>*.mail.protection.outlook.com  <br/> **Este valor NO PUEDE terminar con un punto (.)** <br/> **Nota:** Obtenga su *\<domain-key\>* de su cuenta Microsoft. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|0  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)|1 Hour|

1. Seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-MX-add.png" alt-text="Seleccione AGREGAR.":::

   > [!NOTE]
   > Seleccione **Vista clásica** en la esquina superior derecha para ver el registro TXT que ha creado.

1. Si hay otros registros MX, elimínelos seleccionando la herramienta de edición y, a continuación, **Eliminar** para cada registro.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-edit.png" alt-text="Seleccione la herramienta Editar.":::

## <a name="add-the-cname-record-required-for-microsoft"></a>Agregar el registro CNAME necesario para Microsoft

1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). You'll be prompted to log in.

1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. Active la casilla situada junto al dominio que desea modificar.

1. En **Acciones**, seleccione los tres puntos y, a continuación, seleccione **Administrar** en la lista desplegable.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Seleccione **Herramientas avanzadas** y, junto a **Registros DNS avanzados**, seleccione **ADMINISTRAR**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

   Es posible que tenga que seleccionar **Continuar** para acceder a la página Administrar registros DNS avanzados.

1. En la página Administrar registros DNS avanzados, seleccione **+AGREGAR REGISTRO**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add-record.png" alt-text="Seleccione +AGREGAR REGISTRO.":::

1. En **Tipo**, seleccione **CNAME** en la lista desplegable.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-cname.png" alt-text="Seleccione CNAME type (Tipo de CNAME) en la lista desplegable.":::

1. En los cuadros del registro CNAME, escriba o copie y pegue los valores de la tabla siguiente.

   |Hace referencia a|Nombre de host|Alias para|TTL|
   |---|---|---|---|
   |Otro host|autodescubrir|autodiscover.outlook.com **Este valor no puede terminar con un punto (.)** <br/> 1 Hour|

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-cname-values.png" alt-text="Escriba o copie y pegue los valores de CNAME de la tabla en la ventana.":::

1. Seleccione **AGREGAR**.

   > [!NOTE]
   > Seleccione **Vista clásica** en la esquina superior derecha para ver el registro que ha creado.

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un  *único*  registro SPF que incluya ambos conjuntos de valores.

1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). You'll be prompted to log in.

1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. Active la casilla situada junto al dominio que desea modificar.

1. En **Acciones**, seleccione los tres puntos y, a continuación, seleccione **Administrar** en la lista desplegable.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Seleccione **Herramientas avanzadas** y, junto a **Registros DNS avanzados**, seleccione **ADMINISTRAR**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

   Es posible que tenga que seleccionar **Continuar** para acceder a la página Administrar registros DNS avanzados.

1. En la página Administrar registros DNS avanzados, seleccione **+AGREGAR REGISTRO**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add-record.png" alt-text="Seleccione +AGREGAR REGISTRO.":::

1. En **Tipo**, seleccione **TXT** en la lista desplegable.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-TXT.png" alt-text="Seleccione TXT en la lista desplegable Tipo.":::

1. In the boxes for the new record, type or copy and paste the following values.

   |Hace referencia a|TXT Value|TTL
   |---|---|---|
   |@  <br/> (The system will change this value to **@ (None)** when you save the record.)|v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.|1 Hour|

1. Seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add.png" alt-text="Seleccione AGREGAR.":::

   > [!NOTE]
   > Seleccione **Vista clásica** en la esquina superior derecha para ver el registro que ha creado.

## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial para servicios de comunicación en línea, como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita 4 registros: 2 registros SRV para la comunicación de usuario a usuario y 2 registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-the-two-required-srv-records"></a>Agregar los dos registros SRV necesarios

1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). You'll be prompted to log in.

1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. Active la casilla situada junto al dominio que desea modificar.

1. En **Acciones**, seleccione los tres puntos y, a continuación, seleccione **Administrar** en la lista desplegable.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Seleccione **Herramientas avanzadas** y, junto a **Registros DNS avanzados**, seleccione **ADMINISTRAR**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

   Es posible que tenga que seleccionar **Continuar** para acceder a la página Administrar registros DNS avanzados.

1. En la página Administrar registros DNS avanzados, seleccione **+AGREGAR REGISTRO**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add-record.png" alt-text="Seleccione +AGREGAR REGISTRO.":::

1. En **Tipo**, seleccione **SRV** en la lista desplegable.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-srv.png" alt-text="Seleccione SRV en la lista desplegable Tipo.":::

1. En los cuadros de los dos nuevos registros, escriba (o copie y pegue) los valores de la tabla siguiente.

   (Elija los valores **Servicio** y **Protocolo** de las listas desplegables).

   |Tipo|Servicio|Protocolo|Peso|Puerto|Target|Prioridad|TTL|
   |---|---|---|---|---|---|---|---|
   |SRV|_sip|TLS|100|443|sipdir.online.lync.com  <br/> **Este valor NO PUEDE terminar con un punto (.)**|1|1 Hour|
   |SRV|_sipfederationtls|TCP|100|5061|sipfed.online.lync.com  <br/> **Este valor NO PUEDE terminar con un punto (.)**|1|1 Hour|

1. Seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-srv-add.png" alt-text="Seleccione AGREGAR.":::

   > [!NOTE]
   > Seleccione **Vista clásica** en la esquina superior derecha para ver el registro que ha creado.

1. Agregue el otro registro SRV copiando los valores de la segunda fila de la tabla.

> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>Agregue los dos registros CNAME necesarios para Skype Empresarial

1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). You'll be prompted to log in.

1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. Active la casilla situada junto al dominio que desea modificar.

1. En **Acciones**, seleccione los tres puntos y, a continuación, seleccione **Administrar** en la lista desplegable.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Seleccione **Herramientas avanzadas** y, junto a **Registros DNS avanzados**, seleccione **ADMINISTRAR**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

   Es posible que tenga que seleccionar **Continuar** para acceder a la página Administrar registros DNS avanzados.

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add-record.png" alt-text="Seleccione +AGREGAR REGISTRO.":::

1. En **Tipo**, seleccione **CNAME** en la lista desplegable.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-cname.png" alt-text="Seleccione CNAME type (Tipo de CNAME) en la lista desplegable.":::

1. En los cuadros del registro CNAME, escriba o copie y pegue los valores de la tabla siguiente.

   |Tipo|Hace referencia a|Nombre de host|Alias para|TTL|
   |---|---|---|---|---|
   |CNAME|Otro host|sip|sipdir.online.lync.com  <br/> **Este valor NO PUEDE terminar con un punto (.)**|1 Hour|
   |CNAME|Otro host|lyncdiscover|webdir.online.lync.com  <br/> **Este valor NO PUEDE terminar con un punto (.)**|1 Hour|

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-cname-values.png" alt-text="Escriba o copie y pegue los valores de CNAME de la tabla en la ventana.":::

1. Seleccione **AGREGAR**.

   > [!NOTE]
   > Seleccione **Vista clásica** en la esquina superior derecha para ver el registro que ha creado.

1. Agregue el otro registro CNAME copiando los valores de la segunda fila de la tabla.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Opción avanzada: Intune y mobile Administración de dispositivos para Microsoft 365

Este servicio le ayuda a proteger y administrar de forma remota los dispositivos móviles que se conectan a su dominio. Mobile Administración de dispositivos necesita 2 registros CNAME para que los usuarios puedan inscribir dispositivos en el servicio.

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>Agregue los dos registros CNAME necesarios para Mobile Administración de dispositivos

1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). You'll be prompted to log in.

1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. Active la casilla situada junto al dominio que desea modificar.

1. En **Acciones**, seleccione los tres puntos y, a continuación, seleccione **Administrar** en la lista desplegable.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Seleccione **Herramientas avanzadas** y, junto a **Registros DNS avanzados**, seleccione **ADMINISTRAR**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

   Es posible que tenga que seleccionar **Continuar** para acceder a la página Administrar registros DNS avanzados.

1. En la página Administrar registros DNS avanzados, seleccione **+AGREGAR REGISTRO**.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add-record.png" alt-text="Seleccione +AGREGAR REGISTRO.":::

1. En **Tipo**, seleccione **CNAME** en la lista desplegable.

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-cname.png" alt-text="Seleccione CNAME type (Tipo de CNAME) en la lista desplegable.":::

1. En los cuadros del registro CNAME, escriba o copie y pegue los valores de la tabla siguiente.

   |Tipo|Hace referencia a|Nombre de host|Alias para|TTL|
   |---|---|---|---|---|
   |CNAME|Otro host|enterpriseregistration|enterpriseregistration.windows.net  <br/> **Este valor NO PUEDE terminar con un punto (.)**|1 Hour|
   |CNAME|Otro host|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com  <br/> **Este valor NO PUEDE terminar con un punto (.)**|1 Hour|

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-cname-values.png" alt-text="Escriba o copie y pegue los valores de CNAME de la tabla en la ventana.":::

1. Seleccione **AGREGAR**.

   > [!NOTE]
   > Seleccione **Vista clásica** en la esquina superior derecha para ver el registro que ha creado.

1. Agregue el otro registro CNAME copiando los valores de la segunda fila de la tabla.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

