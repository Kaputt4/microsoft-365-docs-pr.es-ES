---
title: Conexión de los registros DNS en Namecheap a Microsoft 365
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial en línea y otros servicios en Namecheap para Microsoft.
ms.openlocfilehash: 8af8b88cc2bdd0c819f349e2820d637b99e6d730
ms.sourcegitcommit: 8cd230e243eba452b27f725d66152becb6aff49b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563349"
---
# <a name="connect-your-dns-records-at-namecheap-to-microsoft-365"></a>Conexión de los registros DNS en Namecheap a Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Si Namecheap es el proveedor de hospedaje DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial En línea, etc.

Después de agregar estos registros en Namecheap, el dominio se configurará para trabajar con servicios de Microsoft.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.

> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.

1. Para empezar, vaya a la página de dominios en Namecheap mediante [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Se le pedirá que inicie sesión y continúe.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Inicie sesión en Namecheap.":::

1. En la página de aterrizaje, en **Cuenta**, elija **Lista de dominios** en la lista desplegable.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Seleccione Lista de dominios en la lista desplegable.":::

1. En la página Lista de dominios, seleccione el dominio que desea editar y, a continuación, seleccione **Administrar**.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Seleccione Administrar.":::

1. Seleccione **DNS avanzado**.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Seleccione DNS avanzado.":::

1. En la sección **REGISTROS DE HOST** , seleccione **AGREGAR NUEVO REGISTRO**.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="Seleccione AGREGAR NUEVO REGISTRO.":::

1. En la lista desplegable **Tipo** , seleccione **Registro TXT**.

    > [!NOTE]
    > La lista desplegable **Tipo** aparece automáticamente al seleccionar **AGREGAR NUEVO REGISTRO**.

     :::image type="content" source="../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png" alt-text="Seleccione Registro TXT.":::

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

    (Elija el valor **de TTL** en la lista desplegable).

    |Tipo|Host|Valor|TTL|
    |---|---|---|---|
    |TXT|@|MS=ms *XXXXXXXX*  <br/>**Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla.  [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|30 min|

     :::image type="content" source="../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png" alt-text="Copie y pegue los valores de la tabla.":::

1. Seleccione el control **Guardar cambios** (marca de verificación).

     :::image type="content" source="../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png" alt-text="Seleccione el control Guardar cambios.":::

1. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.

Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro. Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.

Para comprobar el registro en Microsoft 365:

1. En el centro de administración, vaya a **Dominios de configuración**\>.<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a>

1. En la página Dominios, seleccione el dominio que está comprobando y seleccione **Iniciar configuración**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Seleccione Iniciar configuración.":::

1. Seleccione **Continuar**.

1. En la página **verificar dominio**, seleccione **verificar**.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft

1. Para empezar, vaya a la página de dominios en Namecheap mediante [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Se le pedirá que inicie sesión y continúe.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Inicie sesión en Namecheap.":::

1. En la página de aterrizaje, en **Cuenta**, elija **Lista de dominios** en la lista desplegable.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Elija Lista de dominios en la lista desplegable.":::

1. En la página **Lista de** dominios, seleccione el dominio que desea editar y, a continuación, seleccione **Administrar**.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Seleccione Administrar.":::

1. Seleccione **DNS avanzado**.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Seleccione DNS avanzado.":::

1. En la sección **CONFIGURACIÓN DE CORREO** , seleccione **MX personalizado** en la lista desplegable **Reenvío de correo electrónico** .

    (Es posible que tenga que desplazarse hacia abajo).

     :::image type="content" source="../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png" alt-text="Seleccione MX personalizado.":::

1. Seleccione **Agregar nuevo registro**.

     :::image type="content" source="../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png" alt-text="AGREGAR NUEVO REGISTRO.":::

1. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

    (El cuadro **Prioridad** es el cuadro sin nombre situado a la derecha del cuadro **Valor** . Elija el valor **de TTL** en la lista desplegable).

    |Tipo|Host|Valor|Prioridad|TTL|
    |---|---|---|---|---|
    |Registro MX|@|\<*domain-key*\>.mail.protection.outlook.com.  <br/> **Este valor DEBE terminar en punto (.)** <br/> **Nota:** Obtenga su *\<domain-key\>* de su cuenta Microsoft.  [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md)|0  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)|30 min|

     :::image type="content" source="../../media/f3b76d62-5022-48c1-901b-8615a8571309.png" alt-text="Copie y pegue los valores de la tabla.":::

1. Seleccione el control **Guardar cambios** (marca de verificación).

     :::image type="content" source="../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png" alt-text="Seleccione el control Guardar cambios.":::

1. Si existen otros registros MX, quite cada uno de ellos usando el procedimiento de dos pasos siguiente:

    En primer lugar, seleccione **Eliminar** (papelera) para el registro que desea quitar.

     :::image type="content" source="../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png" alt-text="Seleccione Eliminar.":::

    En segundo lugar, seleccione **Sí** para confirmar la eliminación.

     :::image type="content" source="../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png" alt-text="Seleccione Sí.":::

    Quite todos los registros MX excepto el que agregó anteriormente en este procedimiento.

## <a name="add-the-cname-record-required-for-microsoft"></a>Agregar el registro CNAME necesario para Microsoft

1. Para empezar, vaya a la página de dominios en Namecheap mediante [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Se le pedirá que inicie sesión y continúe.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Inicie sesión en Namecheap.":::

1. En la página de aterrizaje, en **Cuenta**, elija **Lista de dominios** en la lista desplegable.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Seleccione Lista de dominios.":::

1. En la página **Lista de** dominios, seleccione el dominio que desea editar y, a continuación, seleccione **Administrar**.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Seleccione Administrar.":::

1. Seleccione **DNS avanzado**.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Seleccione DNS avanzado.":::

1. En la sección **REGISTROS DE HOST** , seleccione **AGREGAR NUEVO REGISTRO**.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="Seleccione AGREGAR NUEVO REGISTRO.":::

1. En la lista desplegable **Tipo** , seleccione **Registro CNAME**.

    > [!NOTE]
    > La lista desplegable **Tipo** aparece automáticamente al seleccionar **AGREGAR NUEVO REGISTRO**.

     :::image type="content" source="../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png" alt-text="Seleccione Registro CNAME.":::

1. En los cuadros vacíos para el nuevo registro, seleccione **CNAME** para el **Tipo de registro** y, a continuación, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.

    |Tipo|Host|Valor|TTL|
    |---|---|---|---|
    |CNAME|autodiscover|autodiscover.outlook.com.  <br/> **Este valor DEBE terminar en punto (.)**|Automático|

     :::image type="content" source="../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png" alt-text="Copie y pegue los valores de la tabla.":::

1. Seleccione el control **Guardar cambios** (marca de verificación).

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="Seleccione el control Guardar cambios.":::

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un *único*  registro SPF que incluya ambos conjuntos de valores.

1. Para empezar, vaya a la página de dominios en Namecheap mediante [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Se le pedirá que inicie sesión y continúe.

1. En la página de aterrizaje, en **Cuenta**, elija **Lista de dominios** en la lista desplegable.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Seleccione Lista de dominios.":::

1. En la página **Lista de** dominios, seleccione el dominio que desea editar y, a continuación, seleccione **Administrar**.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Seleccione Administrar.":::

1. Seleccione **DNS avanzado**.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Seleccione DNS avanzado.":::

1. En la sección **REGISTROS DE HOST** , seleccione **AGREGAR NUEVO REGISTRO**.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="Seleccione AGREGAR NUEVO REGISTRO.":::

1. En la lista desplegable **Tipo** , seleccione **Registro TXT**.

    > [!NOTE]
    > La lista desplegable **Tipo** aparece automáticamente al seleccionar **AGREGAR NUEVO REGISTRO**.

     :::image type="content" source="../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png" alt-text="Seleccione Registro TXT.":::

1. En los cuadros del nuevo registro, escriba o copie y pegue los siguientes valores de la tabla siguiente.

    (Elija el valor **de TTL** en la lista desplegable).

    |Tipo|Host|Valor|TTL|
    |---|---|---|---|
    |TXT|@|v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.|30 min|

     :::image type="content" source="../../media/ea0829f1-990b-424b-b26e-9859468318dd.png" alt-text="Copie y pegue los valores de la tabla.":::

1. Seleccione el control **Guardar cambios** (marca de verificación).

     :::image type="content" source="../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png" alt-text="Seleccione el control Guardar cambios.":::

## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial para servicios de comunicación en línea, como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita 4 registros: 2 registros SRV para la comunicación de usuario a usuario y 2 registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-the-two-required-srv-records"></a>Agregar los dos registros SRV necesarios

1. Para empezar, vaya a la página de dominios en Namecheap mediante [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to sign in.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Inicie sesión en Namecheap.":::

1. En la página de aterrizaje, en **Cuenta**, elija **Lista de dominios** en la lista desplegable.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Elija Lista de dominios.":::

1. En la página **Lista de** dominios, seleccione el dominio que desea editar y, a continuación, seleccione **Administrar**.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Seleccione Administrar.":::

1. Seleccione **DNS avanzado**.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Seleccione DNS avanzado.":::

1. En la sección **REGISTROS DE HOST** , seleccione **AGREGAR NUEVO REGISTRO**.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="Seleccione AGREGAR NUEVO REGISTRO.":::

1. En la lista desplegable **Tipo** , seleccione **Registro SRV**.

    > [!NOTE]
    > La lista desplegable **Tipo** aparece automáticamente al seleccionar **AGREGAR NUEVO REGISTRO**.

     :::image type="content" source="../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png" alt-text="Seleccione el tipo de registro SRV.":::

1. En los cuadros vacíos de los nuevos registros, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.

    |Servicio|Protocolo|Prioridad|Peso|Puerto|Target|TTL|
    |---|---|---|---|---|---|---|
    |_sip|_tls|100|1 |443|sipdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)**|Automático|
    |_sipfederationtls|_tcp|100|1 |5061|sipfed.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.).**|Automático|

     :::image type="content" source="../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png" alt-text="Copie y pegue los valores de la tabla.":::

1. Seleccione el control **Guardar cambios** (marca de verificación).

     :::image type="content" source="../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png" alt-text="Seleccione el control Guardar cambios.":::

1. Agregue el otro registro SRV eligiendo los valores de la segunda fila de la tabla.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>Agregue los dos registros CNAME necesarios para Skype Empresarial

1. En la sección **REGISTROS DE HOST** , seleccione **AGREGAR NUEVO REGISTRO**.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="Seleccione AGREGAR NUEVO NOMBRE.":::

1. En la lista desplegable **Tipo** , seleccione **CNAME**.

    > [!NOTE]
    > La lista desplegable **Tipo** aparece automáticamente al seleccionar **AGREGAR NUEVO REGISTRO**.

     :::image type="content" source="../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png" alt-text="Seleccione CNAME.":::

1. En los cuadros vacíos de los nuevos registros, escriba o copie y pegue los valores de la primera fila de la tabla.

    |Tipo|Host|Valor|TTL|
    |---|---|---|---|
    |CNAME|sip|sipdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)**|Automático|
    |CNAME|lyncdiscover|webdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)**|Automático|

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="Copie y pegue los valores de CNAME de la tabla.":::

1. Seleccione el control **Guardar cambios** (marca de verificación).

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="Seleccione el control Guardar cambios.":::

1. Agregue el otro registro CNAME eligiendo los valores de la segunda fila de la tabla.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Opción avanzada: Intune y mobile Administración de dispositivos para Microsoft 365

Este servicio le ayuda a proteger y administrar de forma remota los dispositivos móviles que se conectan a su dominio. Mobile Administración de dispositivos necesita dos registros CNAME para que los usuarios puedan inscribir dispositivos en el servicio.

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>Agregue los dos registros CNAME necesarios para Mobile Administración de dispositivos

1. Para empezar, vaya a la página de dominios en Namecheap mediante [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to sign in.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Inicie sesión en Namecheap.":::

1. En la página de aterrizaje, en **Cuenta**, elija **Lista de dominios** en la lista desplegable.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Seleccione Lista de dominios.":::

1. En la página **Lista de** dominios, seleccione el dominio que desea editar y, a continuación, seleccione **Administrar**.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Seleccione Administrar.":::

1. Seleccione **DNS avanzado**.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Seleccione Administrar registros DNS en la lista desplegable.":::

1. En la sección **REGISTROS DE HOST** , seleccione **AGREGAR NUEVO REGISTRO**.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="Seleccione AGREGAR NUEVO REGISTRO.":::

1. En la lista desplegable **Tipo** , seleccione **Registro CNAME**.

    > [!NOTE]
    > La lista desplegable **Tipo** aparece automáticamente al seleccionar **AGREGAR NUEVO REGISTRO**.

     :::image type="content" source="../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png" alt-text="Seleccione Registro CNAME.":::

1. En los cuadros vacíos de los nuevos registros, escriba o copie y pegue los valores de la primera fila de la tabla.

    |Tipo|Host|Valor|TTL|
    |---|---|---|---|
    |CNAME|enterpriseregistration|enterpriseregistration.windows.net.  <br/> **Este valor DEBE terminar en punto (.)**|Automático|
    |CNAME|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com.  <br/> **Este valor DEBE terminar en punto (.).**|Automático|

     :::image type="content" source="../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png" alt-text="Copie y pegue los valores de la tabla.":::

1. Seleccione el control **Guardar cambios** .

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="Seleccione el control Guardar cambios.":::

1. Agregue el otro registro CNAME eligiendo los valores de la segunda fila de la tabla.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).
