---
title: Administración de inquilinos para Microsoft 365 para empresas
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- m365solution-overview
- tenant-management
ms.custom:
- Ent_Solutions
description: Información general sobre la planeación, la implementación y el funcionamiento continuo de los Microsoft 365 inquilinos.
ms.openlocfilehash: 42bde00fbd4ddc1cf92236f099a22b2260dbb980
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405683"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>Administración de inquilinos para Microsoft 365 para empresas

La creación de una ruta de acceso a la transformación digital de su organización con la informática en la nube requiere una base firme en la que los trabajadores puedan confiar en la productividad, la colaboración, el rendimiento, la privacidad, el cumplimiento y la seguridad.

La configuración correcta de los inquilinos de Microsoft 365 proporciona esa base, lo que deja a los trabajadores centrarse en realizar su trabajo y al departamento de TI para centrarse en soluciones integrales que proporcionan valor empresarial adicional. 

Esta solución le lleva a través de la configuración de esa base en estos pasos:

1. Determinar los inquilinos
2. Optimizar las redes
3. Sincronizar las identidades y aplicar inicios de sesión seguros
4. Migre Windows dispositivos, Office clientes y datos locales Office servidores y datos
5. Implementar la administración de dispositivos y aplicaciones

Pero primero, tomemos un momento para comprender lo que es un inquilino y cómo es un inquilino que proporciona una base firme.

## <a name="a-microsoft-365-tenant-defined"></a>Un Microsoft 365 definido

Un inquilino Microsoft 365 es una instancia dedicada de los servicios de Microsoft 365 y los datos de la organización almacenados en una ubicación predeterminada específica, como Europa o Norteamérica. Esta ubicación se especifica al crear el espacio empresarial para la organización. Cada Microsoft 365 inquilino es distinto, único y independiente del resto de Microsoft 365 inquilinos. Se crea un inquilino Microsoft 365 al comprar uno o varios productos de Microsoft, como Microsoft 365 E3 o E5, y un conjunto de licencias para cada uno.

El Microsoft 365 también incluye un inquilino de Azure Active Directory (Azure AD), que es una instancia dedicada de Azure AD para cuentas de usuario, grupos y otros objetos. Cada inquilino de Azure AD es distinto, único y independiente del resto de inquilinos de Azure AD. Aunque su organización puede tener varios inquilinos de Azure AD que puede configurar con suscripciones de Azure, los inquilinos de Microsoft 365 solo pueden usar un único inquilino de Azure AD, el que se creó al crear el inquilino. 

A continuación le mostramos un ejemplo:

![Un ejemplo Microsoft 365 inquilino con su inquilino de Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

*La administración de* inquilinos es la planeación, la implementación y el funcionamiento continuo de los Microsoft 365 inquilinos. 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>Atributos de un inquilino bien diseñado y operativo

Más allá del nombre y la ubicación correctos para el inquilino, hay elementos adicionales para planear, implementar y administrar para garantizar que las experiencias de usuario con aplicaciones de productividad en la nube como Microsoft Teams y Exchange Online sean eficaces, seguras y &mdash; &mdash; eficaces.

Estos son los elementos:

- Tiene el conjunto correcto de productos (suscripciones) y licencias.
  - El conjunto de productos coincide con sus necesidades de negocio, DEI y seguridad.
  - Hay un número adecuado de licencias para los trabajadores y cambios anticipados en el personal.
- Para redes:
  - Ha configurado los nombres de dominio DNS correctos.
  - Para las redes empresariales, ha optimizado el tráfico de red a la red de Microsoft para los trabajadores en el sitio.
  - Ha optimizado el tráfico de red para los trabajadores remotos que usan un cliente VPN.
- Has sincronizado tus cuentas, grupos y otros objetos de Servicios de dominio de Active Directory (AD DS).
  - Las cuentas de inquilino de Azure AD se asignan a Exchange Online buzones de correo con los dominios DNS correctos para las direcciones de correo electrónico.
  - A las cuentas de usuario se les han asignado las licencias correctas de los productos comprados correctos (como Microsoft 365 E3 o E5).
- Ha configurado una administración segura de identidades y acceso.
  - Necesita el inicio de sesión seguro del usuario con autenticación sin contraseña o multifactor (MFA).
  - Tiene directivas de acceso condicional que aplican los requisitos de inicio de sesión y las restricciones para niveles de seguridad más altos.
- Los servidores Office locales y sus datos se han migrado a aplicaciones en la nube o se usan en una configuración híbrida.
- Está realizando la administración de dispositivos con Intune o movilidad básica y seguridad integrada en Microsoft 365.
  - Los dispositivos propiedad de la organización se inscriben y administran.
  - Las aplicaciones para dispositivos personales se administran.

Este es un ejemplo de un inquilino Microsoft 365 con todos estos elementos en su lugar.

![Un ejemplo Microsoft 365 inquilino](../media/tenant-management-overview/tenant-management-tenant-config.png)

En esta ilustración, el Microsoft 365 incluye:

- Productos y licencias para Microsoft 365 E3 y E5.
- Microsoft 365 aplicaciones de productividad.
- Intune con dispositivos inscritos y directivas de dispositivos y aplicaciones.
- Un inquilino de Azure AD que tiene una cuenta de usuario sincronizada (no se muestran grupos ni otros objetos de directorio), dominios y directivas de acceso condicional.

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>Capacidades de inquilino para Microsoft 365 para empresas

En las siguientes secciones y tabla se indican las funciones clave y las licencias para los pasos de esta solución.

### <a name="tenant"></a>Tenant

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| Varios inquilinos | Cada Microsoft 365 inquilino es distinto, único y independiente del resto de Microsoft 365 inquilinos. Con varios inquilinos, existen restricciones y consideraciones adicionales al administrarlos y proporcionar servicios a los usuarios. | Microsoft 365 E3 o E5 | 
| Migración de buzones de inquilinos cruzados | Los administradores de inquilinos pueden mover buzones entre inquilinos con dependencias de infraestructura mínimas en sus sistemas locales. Esto quita la necesidad de retirar y incorporar buzones. | Microsoft 365 E3 o E5 | 
| Multi-Geo | El inquilino puede almacenar datos en reposo en las otras ubicaciones geográficas del centro de datos que haya elegido para cumplir los requisitos de residencia de datos. | Microsoft 365 E3 o E5 | 
| Mover datos principales a una nueva ubicación geográfica del centro de datos | A medida que Microsoft agrega nuevas geos del centro de datos para recursos de procesamiento y capacidad adicionales, puede solicitar un movimiento geográfico del centro de datos para la residencia de datos en geo para los datos principales del cliente. | Microsoft 365 E3 o E5 | 
||||

### <a name="networking"></a>Redes

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| Network Insights | Métricas de rendimiento de red recopiladas Microsoft 365 inquilino para ayudarle a diseñar perímetros de red para sus ubicaciones de oficina. | Microsoft 365 E3 o E5 | 
| Automatizar actualizaciones de puntos de conexión | Automatice la configuración y las actualizaciones continuas para los Microsoft 365 en los archivos PAC de cliente y los dispositivos y servicios de red. | Microsoft 365 E3 o E5 | 
||||

### <a name="identity"></a>Identidad

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| Sincronizar los Servicios de dominio de Active Directory locales (AD DS) con el inquilino de Azure AD    | Aproveche el proveedor de identidades local para cuentas de usuario, grupos y otros objetos. | Microsoft 365 E3 o E5 |
| MFA aplicada en los valores predeterminados de seguridad   | Protege frente a ataques a identidades y dispositivos, pues obliga a usar una segunda forma de autenticación para iniciar sesión. Los valores predeterminados de seguridad requieren MFA para todas las cuentas de usuario.   | Microsoft 365 E3 o E5 |
| MFA aplicada con acceso condicional| Requerir MFA en función de los atributos del inicio de sesión con directivas de acceso condicional.    | Microsoft 365 E3 o E5 | 
| MFA aplicada con Acceso condicional basado en los riesgos   | Requerir la MFA según el riesgo de inicio de sesión del usuario con Microsoft Defender for Identity. | Microsoft 365 E5 o E3 con las licencias de Azure AD Premium P2 | 
| Autoservicio de restablecimiento de contraseña (SSPR)    | Permitir que los usuarios restablezcan o desbloqueen su contraseña o cuenta ellos mismos.  | Microsoft 365 E3 o E5 |
||||

### <a name="migration"></a>Migración

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| Migrar a Windows 10 | Migre los dispositivos que Windows 7 o Windows 8.1 a Windows 10 Enterprise. | Windows 10 Enterprise licencias incluidas con Microsoft 365 E3 o E5 | 
| Migrar a Aplicaciones Microsoft 365 para empresas | Migre Office cliente como Word y PowerPoint a las versiones instaladas desde la nube que se actualizan con nuevas características. | Microsoft 365 E3 o E5 | 
| Migrar servidores y datos locales a Microsoft 365 | Migre Exchange buzones de correo, SharePoint web y Skype Empresarial Online a Microsoft 365 servicios en la nube. | Microsoft 365 E3 o E5 | 
||||

### <a name="device-and-app-management"></a>Datos de administración de dispositivos y aplicaciones

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| Microsoft Intune | Un servicio basado en la nube que proporciona administración de dispositivos móviles (MDM) y administración de aplicaciones móviles (MAM) para controlar cómo se usan la aplicación y los dispositivos de la organización, incluidos teléfonos móviles, tabletas y portátiles. | Microsoft 365 E3 o E5 | 
| Movilidad y seguridad básicas | Protege y administra los dispositivos móviles de tus usuarios como iPhones, iPads, Androids y Windows teléfonos con este servicio integrado.  | Microsoft 365 E3 o E5 | 
||||

## <a name="next-steps"></a>Pasos siguientes

Siga estos pasos para configurar y administrar sus Microsoft 365 inquilinos.

1. [Determinar los inquilinos](tenant-management-tenants.md)
2. [Optimizar las redes](tenant-management-networking.md)
3. [Sincronizar las identidades y aplicar inicios de sesión seguros](tenant-management-identity.md)
4. [Migrar los servidores y datos Office local](tenant-management-migration.md)
5. [Implementar la administración de dispositivos y aplicaciones](tenant-management-device-management.md)

[![Los pasos para implementar y administrar un Microsoft 365 inquilino](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

Cada paso describe las opciones de implementación, resume los resultados y las tareas de mantenimiento en curso.

Para comprender cómo una organización multinacionales ficticia pero representativa implementó los elementos de su Microsoft 365 inquilino, vea el [caso práctico de Contoso](../enterprise/contoso-case-study.md).
