---
title: Conexión de los registros DNS en web.com a Microsoft 365
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial En línea y otros servicios en web.com para Microsoft.
ms.openlocfilehash: 06b1374916bcf2105db09715b125d84992bac069
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68198105"
---
# <a name="connect-your-dns-records-at-webcom-to-microsoft-365"></a>Conexión de los registros DNS en web.com a Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Si web.com es el proveedor de hospedaje dns, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial En línea, etc.

Después de agregar estos registros en web.com, el dominio se configurará para trabajar con servicios de Microsoft.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

## <a name="change-your-domains-nameserver-ns-records"></a>Cambiar los registros del servidor de nombres (o NS) de su dominio

> [!IMPORTANT]
> Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio.

Al registrarse para web.com, agregó un dominio mediante el proceso de **instalación** de web.com.

Para comprobar y crear registros DNS para su dominio en Microsoft, primero debe cambiar los servidores de nombres en el registrador de dominios para que usen los servidores de nombres de web.com.

Para cambiar los servidores DNS del dominio en el sitio web del registrador de dominios usted mismo, haga lo siguiente:

1. En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.

2. Cree dos registros de servidor de nombres mediante los valores de la tabla siguiente o edite los registros de nameserver existentes para que coincidan con estos valores.

    |Tipo|Valor|
    |---|---|
    |Primer servidor de nombres|Use el valor nameserver proporcionado por web.com.|
    |Segundo servidor de nombres|Use el valor nameserver proporcionado por web.com.|

    > [!TIP]
    > You should use at least two name server records. Si aparece algún otro servidor de nombres, debe eliminarlos.

3. Guarde los cambios.

> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para que funcionen con su dominio.

## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.

> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.

1. Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.

1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. En **Acciones**, seleccione los tres puntos y, a continuación, seleccione **Administrar** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Desplácese hacia abajo para seleccionar **Herramientas avanzadas** y, junto a **Registros DNS avanzados**, seleccione **ADMINISTRAR**.

    Es posible que tenga que seleccionar **Continuar** para acceder a la página Administrar registros DNS avanzados.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="Seleccione + AGREGAR REGISTRO.":::

1. En **Tipo**, seleccione **TXT** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-TXT.png" alt-text="Seleccione TXT en la lista desplegable Tipo.":::

1. Seleccione o copie y pegue los valores de la tabla siguiente.

    |Se nombra|Valor TXT|TTL|
    |---|---|:----|
    |@|MS=ms *XXXXXXXX* <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|1 Hour|

1. Seleccione **AGREGAR**.

    Espere unos minutos antes de comprobar el nuevo registro TXT para que el registro que acaba de crear pueda actualizarse a través de Internet.

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

1. Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.

1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. En **Acciones**, seleccione los tres puntos y, a continuación, seleccione **Administrar** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Desplácese hacia abajo para seleccionar **Herramientas avanzadas** y, junto a **Registros DNS avanzados**, seleccione **ADMINISTRAR**.

    Es posible que tenga que seleccionar **Continuar** para acceder a la página Administrar registros DNS avanzados.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="Seleccione + AGREGAR REGISTRO.":::

1. En **Tipo**, seleccione **MX** en la lista desplegable.

1. Seleccione o copie y pegue los valores de la tabla siguiente.

    |Hace referencia a|Servidor de correo|Prioridad|TTL|
    |---|---|---|---|
    |@|*\<domain-key\>*.mail.protection.outlook.com <br/> **Nota:** Obtenga el del *\<domain-key\>* Centro de administración de Microsoft. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml) <br/> 1|1 Hour|

1. Seleccione **AGREGAR**.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-mx-add.png" alt-text="Seleccione AGREGAR.":::

1. Si hay otros registros MX, elimínelos seleccionando la herramienta de edición y, a continuación, **Eliminar** para cada registro.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-edit.png" alt-text="Seleccione Editar.":::

## <a name="add-the-cname-record-required-for-microsoft"></a>Agregar el registro CNAME necesario para Microsoft

1. Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.

1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. En **Acciones**, seleccione los tres puntos y, a continuación, seleccione **Administrar** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Desplácese hacia abajo para seleccionar **Herramientas avanzadas** y, junto a **Registros DNS avanzados**, seleccione **ADMINISTRAR**.

    Es posible que tenga que seleccionar **Continuar** para acceder a la página Administrar registros DNS avanzados.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="Seleccione + AGREGAR REGISTRO.":::

1. En **Tipo**, seleccione **CNAME** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname.png" alt-text="Seleccione CNAME en la lista desplegable Tipo.":::

1. Seleccione o copie y pegue los valores de la tabla siguiente.

    |Hace referencia a|Nombre de host|Alias para|TTL|
    |---|---|---|---|
    |Otro host|autodescubrir|autodiscover.outlook.com|1 Hour|

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname-values.png" alt-text="Escriba o copie y pegue los valores de CNAME en la ventana.":::

1. Seleccione **AGREGAR**.

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un *único* registro SPF que incluya ambos conjuntos de valores.

1. Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.

1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. En **Acciones**, seleccione los tres puntos y, a continuación, seleccione **Administrar** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Desplácese hacia abajo para seleccionar **Herramientas avanzadas** y, junto a **Registros DNS avanzados**, seleccione **ADMINISTRAR**.

    Es posible que tenga que seleccionar **Continuar** para acceder a la página Administrar registros DNS avanzados.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="Seleccione + AGREGAR REGISTRO.":::

1. En **Tipo**, seleccione **TXT** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-TXT.png" alt-text="Seleccione TXT en la lista desplegable Tipo.":::

1. Seleccione o copie y pegue los valores de la tabla siguiente.

    |Hace referencia a|Valor TXT|TTL|
    |---|---|---|
    |@|v=spf1 include:spf.protection.outlook.com -all <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.|1 Hour|

1. Seleccione **AGREGAR**.

## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial para servicios de comunicación en línea, como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita 4 registros: 2 registros SRV para la comunicación de usuario a usuario y 2 registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-the-two-required-srv-records"></a>Agregar los dos registros SRV necesarios

1. Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.

1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. En **Acciones**, seleccione los tres puntos y, a continuación, seleccione **Administrar** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Desplácese hacia abajo para seleccionar **Herramientas avanzadas** y, junto a **Registros DNS avanzados**, seleccione **ADMINISTRAR**.

    Es posible que tenga que seleccionar **Continuar** para acceder a la página Administrar registros DNS avanzados.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="Seleccione + AGREGAR REGISTRO.":::

1. En **Tipo**, seleccione **SRV** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-srv.png" alt-text="Seleccione SRV en la lista desplegable Tipo.":::

1. Seleccione o copie y pegue los valores de la tabla siguiente.

    |Tipo|Servicio|Protocolo|Peso|Puerto|Target|Prioridad|TTL|
    |---|---|---|---|---|---|---|---|
    |SRV|_sip|TLS|100|443|sipdir.online.lync.com <br/> **Este valor NO PUEDE terminar con un punto (.)**|1|1 Hour|
    |SRV|_sipfederationtls|TCP|100|5061|sipfed.online.lync.com <br/> **Este valor NO PUEDE terminar con un punto (.)**|1|1 Hour|

    :::image type="content" source="../../media/dns-webcom/webcom-domains-srv-add.png" alt-text="Escriba o copie y pegue los valores de la tabla en la ventana de registro SRV.":::

1. Seleccione **AGREGAR**.

1. Agregue el otro registro SRV copiando los valores de la segunda fila de la tabla.

> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>Agregue los dos registros CNAME necesarios para Skype Empresarial

1. Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.

1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. En **Acciones**, seleccione los tres puntos y, a continuación, seleccione **Administrar** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Desplácese hacia abajo para seleccionar **Herramientas avanzadas** y, junto a **Registros DNS avanzados**, seleccione **ADMINISTRAR**.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

    Es posible que tenga que seleccionar **Continuar** para acceder a la página Administrar registros DNS avanzados.

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="Seleccione + AGREGAR REGISTRO.":::

1. En **Tipo**, seleccione **CNAME** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname.png" alt-text="Seleccione CNAME en la lista desplegable Tipo.":::

1. Seleccione o copie y pegue los valores de la tabla siguiente.

    |Tipo|Hace referencia a|Nombre de host|Alias para|TTL|
    |---|---|---|---|---|
    |CNAME|Otro host|sip|sipdir.online.lync.com <br/> **Este valor NO PUEDE terminar con un punto (.)**|1 Hour|
    |CNAME|Otro host|lyncdiscover|webdir.online.lync.com <br/> **Este valor NO PUEDE terminar con un punto (.)**|1 Hour|

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname-values.png" alt-text="Escriba o copie y pegue los valores de CNAME en la ventana.":::

1. Seleccione **AGREGAR**.

1. Agregue el otro registro CNAME copiando los valores de la segunda fila de la tabla.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Opción avanzada: Intune y mobile Administración de dispositivos para Microsoft 365

Este servicio le ayuda a proteger y administrar de forma remota los dispositivos móviles que se conectan a su dominio. Mobile Administración de dispositivos necesita 2 registros CNAME para que los usuarios puedan inscribir dispositivos en el servicio.

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>Agregue los dos registros CNAME necesarios para Mobile Administración de dispositivos

1. Para empezar, vaya a la página dominios en web.com mediante [este vínculo](https://checkout.web.com/manage-it/index.jsp). Inicie sesión primero.

1. En la página de aterrizaje, seleccione **Nombres de dominio**.

1. En **Acciones**, seleccione los tres puntos y, a continuación, seleccione **Administrar** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="Seleccione Administrar en la lista desplegable.":::

1. Desplácese hacia abajo para seleccionar **Herramientas avanzadas** y, junto a **Registros DNS avanzados**, seleccione **ADMINISTRAR**.

    Es posible que tenga que seleccionar **Continuar** para acceder a la página Administrar registros DNS avanzados.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="Junto a Registros DNS avanzados, seleccione ADMINISTRAR.":::

1. En la página Administrar registros DNS avanzados, seleccione **+ AGREGAR REGISTRO**.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="Seleccione + AGREGAR REGISTRO.":::

1. En **Tipo**, seleccione **CNAME** en la lista desplegable.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname.png" alt-text="Seleccione CNAME en la lista desplegable Tipo.":::

1. Seleccione o copie y pegue los valores de la tabla siguiente.

    |Tipo|Hace referencia a|Nombre de host|Alias para|TTL|
    |---|---|---|---|---|
    |CNAME|Otro host|enterpriseregistration|enterpriseregistration.windows.net <br/> **Este valor NO PUEDE terminar con un punto (.)**|1 Hour|
    |CNAME|Otro host|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com <br/> **Este valor NO PUEDE terminar con un punto (.)**|1 Hour|

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname-values.png" alt-text="Escriba o copie y pegue los valores de CNAME de la tabla en la ventana.":::

1. Seleccione **AGREGAR**.

1. Agregue el otro registro CNAME copiando los valores de la segunda fila de la tabla.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).
