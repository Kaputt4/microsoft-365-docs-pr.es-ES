---
title: Registradores de dominios con limitaciones de configuración
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- MET150
ROBOTS: NOINDEX
description: Algunos registradores de dominios ofrecen servicios limitados, lo que significa que no todas las características de Microsoft funcionarán con todos los dominios.
ms.openlocfilehash: 7fe6b047773e47964b5a00728b8c1443bdeef36e
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774597"
---
# <a name="domain-registrars-with-setup-limitations"></a>Registradores de dominios con limitaciones de configuración

[Crear registros DNS en DNSMadeEasy para Microsoft](#create-dns-records-at-dnsmadeeasy-for-microsoft)\
[Crear registros DNS en easyDNS para Microsoft](#create-dns-records-at-easydns-for-microsoft)\
[Crear registros DNS en Freenom para Microsoft](#create-dns-records-at-freenom-for-microsoft)\
[Crear registros DNS en MyDomain para Microsoft](#create-dns-records-at-mydomain-for-microsoft)\
[Crear registros DNS para Microsoft con DNS basado en Windows](#create-dns-records-for-microsoft-using-windows-based-dns)\
[Crear registros DNS cuando Google (eNom) administra su dominio](#create-dns-records-when-your-domain-is-managed-by-google-enom)\
[Crear registros DNS en 1&1 IONOS para Microsoft](#create-dns-records-at-11-ionos-for-microsoft)

Algunos registradores de dominios tienen limitaciones de servicio significativas, lo que significa que no todas las características de Microsoft funcionarán con todos los dominios. En este artículo se identifican limitaciones específicas para algunos registradores. 

## <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a>Crear registros DNS en DNSMadeEasy para Microsoft

Para las cuentas de DNSMadeEasy, el dominio que agregó se compró de un registrador de dominios separado. DNSMadeEasy no ofrece servicios de registro de dominios. Su capacidad para iniciar sesión en DNSMadeEasy y crear el registro DNS es una prueba suficiente de que es el propietario.

## <a name="create-dns-records-at-easydns-for-microsoft"></a>Crear registros DNS en easyDNS para Microsoft

Los registros SRV no están disponibles actualmente en ningún paquete de servicio easyDNS. Es posible que tenga que actualizar a un nivel de servicio superior con easyDNS para agregar registros SRV necesarios para Teams.

## <a name="create-dns-records-at-freenom-for-microsoft"></a>Crear registros DNS en Freenom para Microsoft

El sitio web de Freenom no admite la adición de registros SRV, lo que significa que varias características de Teams y Correo electrónico no funcionarán. Independientemente del plan de Microsoft que use, existen limitaciones de servicio significativas y es posible que desee cambiar a otro proveedor de host DNS.

## <a name="create-dns-records-at-mydomain-for-microsoft"></a>Crear registros DNS en MyDomain para Microsoft

El sitio web MyDomain no admite registros SRV, lo que significa que varias características de Teams y Correo electrónico no funcionarán. Independientemente del plan de Microsoft que use, si administra los registros DNS en MyDomain, existen limitaciones de servicio significativas y es posible que quiera cambiar a otro proveedor de host DNS.

## <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Crear registros DNS para Microsoft con DNS basado en Windows

Vaya a la página donde están los registros DNS del dominio. Si está trabajando en Windows Server 2008, vaya a **Inicio**, **Ejecutar**. Si está trabajando en Windows Server 2012, presione la **Tecla Windows** y **r**. Escriba **dnsmgmnt.msc** y luego seleccione **Aceptar**. En el Administrador de DNS, expanda **Nombre del servidor DNS**, **Zonas de búsqueda directa**. Seleccione su dominio. Ya está listo para crear los registros DNS.

## <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>Crear registros DNS cuando Google (eNom) administra su dominio

Si compró el dominio a través de Google mientras se registraba en su cuenta profesional de Google Apps, Google administra los registros DNS, aunque se registren con eNom. Puede acceder al eNom y crear un DNS a través de la página Google Domains.

## <a name="create-dns-records-at-11-ionos-for-microsoft"></a>Crear registros DNS en 1&1 IONOS para Microsoft

1&1 IONOS no permite que un dominio tenga un registro MX y un registro Autodiscover CNAME de nivel superior. Esto limita las formas en que puede configurar Exchange Online para Microsoft. Hay una solución alternativa, pero le recomendamos que recurra a ella solo si ya tiene experiencia con la creación de subdominios en 1&1 IONOS.

Si a pesar de esta limitación de servicio, decide administrar sus propios registros DNS de Microsoft en 1&1 IONOS, siga los pasos de este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online, etc.

1&1 IONOS requiere una solución alternativa para que pueda usar un registro MX junto con los registros CNAME necesarios para los servicios de correo electrónico de Microsoft. Esta solución alternativa requiere que cree un conjunto de subdominios en 1&1 IONOS y que los asigne a registros CNAME.

> [!NOTE]
> Asegúrese de que tiene al menos dos subdominios disponibles antes de iniciar este procedimiento. Se recomienda esta solución solo si ya tiene experiencia con la creación de subdominios en 1&1 IONOS.

### <a name="basic-cname-records"></a>Registros CNAME básicos

1.  Para empezar, vaya a la página de dominios en 1&1 IONOS. Se le pedirá que inicie sesión.

1.  Seleccione **Administrar dominios**.

1.  En la página Centro de dominios, busque el dominio que desea actualizar y, a continuación, seleccione **Administrar subdominios**. Ahora creará dos subdominios y establecerá un valor de **Alias** para cada uno (esto es necesario porque 1&1 IONOS solo admite un registro CNAME de nivel superior, pero Microsoft requiere varios registros CNAME).

1.  En primer lugar, deberá crear el subdominio Autodiscover. En la sección **Información general de subdominio**, elija **Crear subdominio**.

1.  En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).

    |Crear subdominio|Alias|
    |:----|:----|
    |autodescubrir|autodiscover.outlook.com|

1.  Seleccione **Crear subdominio**.

1.  En la sección **Información general de subdominio**, localice el subdominio autodescubrir que acaba de crear y, a continuación, seleccione el panel de (v) control para ese subdominio.

1.  En el área **Configuración del subdominio**, seleccione **Editar configuración DNS**.

1.  En la sección **Registros A/AAAA (direcciones IP)**, en el área **Dirección IP (registro A)**, seleccione **CNAME**.

1. En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.

    |Crear subdominio|Alias|
    |:----|:----|
    |autodescubrir|autodiscover.outlook.com|

1. Active la casilla del aviso de declinación de responsabilidades **Soy consciente**.

1. Seleccione **Guardar**.

### <a name="additional-cname-records"></a>Registros CNAME adicionales

Los registros CNAME adicionales del procedimiento siguiente habilitan los servicios de Skype Empresarial Online. Siga los mismos pasos que usó para los dos registros CNAME que ya ha creado.

**Cree el tercer subdominio (Lyncdiscover)**

1.  En la sección **Información general de subdominio**, seleccione **Crear subdominio**.

1.  En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).

    |Crear subdominio|Alias|
    |:----|:----|
    |lyncdiscover|webdir.online.lync.com|

1.  Seleccione **Crear subdominio**.

1.  En la página Centro de dominios, seleccione **Administrar subdominios**.

1.  En la sección **Información general de subdominio**, localice el subdominio lyncdiscover que acaba de crear y, a continuación, seleccione el Panel de (v) control para ese subdominio. En el área **Configuración del subdominio**, seleccione **Editar configuración DNS**.

1.  En la sección **Registros A/AAAA (direcciones IP)**, en el área **Dirección IP (registro A)**, seleccione **CNAME**.

1.  En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.

    |Crear subdominio|Alias|
    |:----|:----|
    |lyncdiscover|webdir.online.lync.com|

1.  Active la casilla de verificación **Soy consciente** del aviso de declinación de responsabilidades y, a continuación, seleccione **Guardar**.

1.  En el cuadro de diálogo **Editar configuración DNS**, seleccione **Sí**.

**Crear el cuarto subdominio (SIP)**

1.  En la sección **Información general de subdominio**, elija **Crear subdominio**.

1.  En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).

    |Crear subdominio|Alias|
    |:----|:----|
    |sip|sipdir.online.lync.com|  

1.  Seleccione **Crear subdominio**.

1.  En la página Centro de dominios, seleccione **Administrar subdominios**.

1.  En la sección **Información general de subdominio**, localice el subdominio sip que acaba de crear y, a continuación, seleccione el Panel de (v) control para ese subdominio. <br/> En el área **Configuración del subdominio**, seleccione **Editar configuración DNS**.

1.  En la sección **Registros A/AAAA (direcciones IP)**, en el área **Dirección IP (registro A)**, seleccione **CNAME**.

1.  En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.

    |Crear subdominio|Alias|
    |:----|:----|
    |sip|sipdir.online.lync.com|

1.  Active la casilla de verificación **Soy consciente** del aviso de declinación de responsabilidades y, a continuación, seleccione **Guardar**.

1.  En el cuadro de diálogo **Editar configuración DNS**, seleccione **Sí**.

### <a name="cname-records-needed-for-mdm"></a>Registros CNAME necesarios para MDM

Siga el procedimiento que usó para los otros cuatro registros CNAME, pero proporcione estos valores:

|Crear subdominio|Alias|
|:----|:----|
|enterpriseregistration|enterpriseregistration.windows.net|
|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com|
