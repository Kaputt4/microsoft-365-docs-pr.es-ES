---
title: Administración de inquilinos para Microsoft 365 para empresas
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- m365solution-overview
- tenant-management
ms.custom:
- Ent_Solutions
description: Información general sobre el planeamiento, la implementación y el funcionamiento continuo de los inquilinos de Microsoft 365.
ms.openlocfilehash: eff083147d4d11e3bcb2837a12cfb9dad487c1c0
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585034"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>Administración de inquilinos para Microsoft 365 para empresas

La creación de una ruta de acceso a la transformación digital de su organización con informática en la nube requiere una base firme en la que los trabajadores puedan confiar en la productividad, la colaboración, el rendimiento, la privacidad, el cumplimiento y la seguridad.

La configuración correcta de los inquilinos de Microsoft 365 proporciona esa base, lo que deja que los trabajadores se centren en realizar su trabajo y que el departamento de TI se centre en soluciones integrales que proporcionan valor empresarial adicional.

Esta solución le lleva a través de la configuración de esa base en estos pasos:

1. Determinación de los inquilinos
2. Optimización de las redes
3. Sincronizar las identidades y aplicar inicios de sesión seguros
4. Migración de los dispositivos Windows, clientes de Office y datos y servidores de Office locales
5. Implementación de la administración de dispositivos y aplicaciones

Pero en primer lugar, vamos a tomar un momento para comprender qué es un inquilino y qué aspecto tiene un inquilino que proporciona una base firme.

## <a name="a-microsoft-365-tenant-defined"></a>Un inquilino de Microsoft 365 definido

Un inquilino de Microsoft 365 es una instancia dedicada de los servicios de Microsoft 365 y los datos de su organización almacenados en una ubicación predeterminada específica, como Europa o Norteamérica. Esta ubicación se especifica al crear el inquilino para su organización. Cada inquilino de Microsoft 365 es distinto, único e independiente de todos los demás inquilinos de Microsoft 365. Crea un inquilino de Microsoft 365 al comprar uno o varios productos de Microsoft, como Microsoft 365 E3 o E5, y un conjunto de licencias para cada uno.

El inquilino de Microsoft 365 también incluye un inquilino de Azure Active Directory (Azure AD), que es una instancia dedicada de Azure AD para cuentas de usuario, grupos y otros objetos. Cada inquilino de Azure AD es distinto, único e independiente de todos los demás inquilinos de Azure AD. Aunque su organización puede tener varios inquilinos de Azure AD que puede configurar con suscripciones de Azure, los inquilinos de Microsoft 365 solo pueden usar un único inquilino de Azure AD, el que se creó cuando creó el inquilino.

A continuación le mostramos un ejemplo:

![Un inquilino de Microsoft 365 de ejemplo con su inquilino de Azure AD.](../media/tenant-management-overview/tenant-management-example-tenant.png)

*La administración de inquilinos* es el planeamiento, la implementación y el funcionamiento continuo de los inquilinos de Microsoft 365.

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>Atributos de un inquilino operativo y bien diseñado

Más allá del nombre y la ubicación correctos del inquilino, hay elementos adicionales para planear, implementar y administrar para asegurarse de que las experiencias del usuario con aplicaciones&mdash;de productividad en la nube como Microsoft Teams y Exchange Online&mdash; sean eficaces, seguras y eficaces.

Estos son los elementos:

- Tiene el conjunto correcto de productos (suscripciones) y licencias.
  - El conjunto de productos se ajusta a sus necesidades empresariales, de TI y de seguridad.
  - Hay un número adecuado de licencias para sus trabajadores y cambios previstos en el personal.
- Para redes:
  - Ha configurado los nombres de dominio DNS correctos.
  - En el caso de las redes empresariales, ha optimizado el tráfico de red a la red de Microsoft para los trabajadores in situ.
  - Ha optimizado el tráfico de red para los trabajadores remotos que usan un cliente VPN.
- Ha sincronizado las cuentas de Servicios de dominio de Active Directory (AD DS), los grupos y otros objetos.
  - Las cuentas de inquilino de Azure AD se asignan a Exchange Online buzones con los dominios DNS correctos para las direcciones de correo electrónico.
  - A las cuentas de usuario se les han asignado las licencias correctas de los productos comprados correctamente (por ejemplo, Microsoft 365 E3 o E5).
- Ha configurado una administración segura de identidades y acceso.
  - Necesita un inicio de sesión de usuario seguro con autenticación multifactor o sin contraseña (MFA).
  - Tiene directivas de acceso condicional que aplican requisitos de inicio de sesión y restricciones para niveles más altos de seguridad.
- Los servidores de Office locales y sus datos se han migrado a aplicaciones en la nube o se usan en una configuración híbrida.
- Está realizando la administración de dispositivos con Intune o movilidad y seguridad básicas integradas en Microsoft 365.
  - Los dispositivos propiedad de la organización están inscritos y administrados.
  - Las aplicaciones para dispositivos personales se administran.

Este es un ejemplo de un inquilino de Microsoft 365 con todos estos elementos en su lugar.

![Un inquilino de Microsoft 365 de ejemplo.](../media/tenant-management-overview/tenant-management-tenant-config.png)

En esta ilustración, el inquilino de Microsoft 365 incluye:

- Productos y licencias para Microsoft 365 E3 y E5.
- Aplicaciones de productividad de Microsoft 365.
- Intune con dispositivos inscritos y directivas de dispositivos y aplicaciones.
- Un inquilino de Azure AD que tiene una cuenta de usuario sincronizada (no se muestran grupos ni otros objetos de directorio), dominios y directivas de acceso condicional.

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>Funcionalidades de inquilino para Microsoft 365 para empresas

En las secciones siguientes y en la tabla se enumeran las funcionalidades clave y las licencias para los pasos de esta solución.

### <a name="tenant"></a>Tenant

|Funcionalidad o característica|Description|Licencias|
|---|---|---|
|Varios inquilinos|Cada inquilino de Microsoft 365 es distinto, único e independiente de todos los demás inquilinos de Microsoft 365. Con varios inquilinos, hay restricciones y consideraciones adicionales al administrarlos y proporcionar servicios a los usuarios.|Microsoft 365 E3 o E5|
|Migración de buzones de inquilinos cruzados|Los administradores de inquilinos pueden mover buzones entre inquilinos con dependencias de infraestructura mínimas en sus sistemas locales. Esto elimina la necesidad de incorporar buzones de correo fuera del panel e incorporarlos.|Microsoft 365 E3 o E5|
|Multi-Geo|El inquilino puede almacenar datos en reposo en las otras ubicaciones geográficas del centro de datos que ha elegido para cumplir los requisitos de residencia de datos.|Microsoft 365 E3 o E5|
|Traslado de datos principales a una nueva ubicación geográfica del centro de datos|A medida que Microsoft agrega nuevas zonas geográficas de centros de datos para recursos de capacidad y proceso adicionales, puede solicitar un traslado geográfico del centro de datos para la residencia de datos en la ubicación geográfica para los datos principales del cliente.|Microsoft 365 E3 o E5|
||||

### <a name="networking"></a>Redes

|Funcionalidad o característica|Description|Licencias|
|---|---|---|
|Network Insights|Métricas de rendimiento de red recopiladas de su inquilino de Microsoft 365 para ayudarle a diseñar perímetros de red para las ubicaciones de su oficina.|Microsoft 365 E3 o E5|
|Automatización de actualizaciones de puntos de conexión|Automatice la configuración y las actualizaciones continuas de los puntos de conexión de Microsoft 365 en los archivos PAC de cliente y los dispositivos y servicios de red.|Microsoft 365 E3 o E5|
||||

### <a name="identity"></a>Identidad

|Funcionalidad o característica|Description|Licencias|
|---|---|---|
|Sincronizar Active Directory local Domain Services (AD DS) con el inquilino de Azure AD|Aproveche el proveedor de identidades local para cuentas de usuario, grupos y otros objetos.|Microsoft 365 E3 o E5|
|MFA aplicada en los valores predeterminados de seguridad|Protege frente a ataques a identidades y dispositivos, pues obliga a usar una segunda forma de autenticación para iniciar sesión. Los valores predeterminados de seguridad requieren MFA para todas las cuentas de usuario.|Microsoft 365 E3 o E5|
|MFA aplicada con acceso condicional|Requerir MFA en función de los atributos del inicio de sesión con directivas de acceso condicional.|Microsoft 365 E3 o E5|
|MFA aplicada con Acceso condicional basado en los riesgos|Requerir la MFA según el riesgo de inicio de sesión del usuario con Microsoft Defender for Identity.|Microsoft 365 E5 o E3 con las licencias de Azure AD Premium P2|
|Autoservicio de restablecimiento de contraseña (SSPR)|Permitir que los usuarios restablezcan o desbloqueen su contraseña o cuenta ellos mismos.|Microsoft 365 E3 o E5|
||||

### <a name="migration"></a>Migración

|Funcionalidad o característica|Description|Licencias|
|---|---|---|
|Migrar a Windows 10|Migre los dispositivos que ejecutan Windows 7 o Windows 8.1 a Windows 10 Enterprise.|licencias de Windows 10 Enterprise incluidas con Microsoft 365 E3 o E5|
|Migración a Aplicaciones Microsoft 365 para empresas|Migre las aplicaciones cliente de Office, como Word y PowerPoint, a las versiones instaladas desde la nube que se actualizan con nuevas características.|Microsoft 365 E3 o E5|
|Migración de datos y servidores locales a Microsoft 365|Migre los buzones de Exchange, los sitios de SharePoint y Skype Empresarial Online a los servicios en la nube de Microsoft 365.|Microsoft 365 E3 o E5|
||||

### <a name="device-and-app-management"></a>Administración de dispositivos y aplicaciones

|Funcionalidad o característica|Description|Licencias|
|---|---|---|
|Microsoft Intune|Un servicio basado en la nube que proporciona administración de dispositivos móviles (MDM) y administración de aplicaciones móviles (MAM) para controlar cómo se usan la aplicación de su organización y los dispositivos, incluidos teléfonos móviles, tabletas y portátiles.|Microsoft 365 E3 o E5|
|Movilidad y seguridad básicas|Proteja y administre los dispositivos móviles de los usuarios como iPhones, iPads, Android y teléfonos Windows con este servicio integrado.|Microsoft 365 E3 o E5|
||||

## <a name="next-steps"></a>Pasos siguientes

Siga estos pasos para configurar y administrar los inquilinos de Microsoft 365.

1. [Determinación de los inquilinos](tenant-management-tenants.md)
2. [Optimización de las redes](tenant-management-networking.md)
3. [Sincronizar las identidades y aplicar inicios de sesión seguros](tenant-management-identity.md)
4. [Migración de los datos y servidores de Office locales](tenant-management-migration.md)
5. [Implementación de la administración de dispositivos y aplicaciones](tenant-management-device-management.md)

[![Pasos para implementar y administrar un inquilino de Microsoft 365.](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

Cada paso describe las opciones de implementación, resume los resultados y las tareas de mantenimiento en curso.

Para comprender cómo una organización multinacional ficticia pero representativa implementó los elementos de su inquilino de Microsoft 365, consulte el [caso práctico de Contoso](../enterprise/contoso-case-study.md).
