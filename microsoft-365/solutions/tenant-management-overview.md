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
ms.custom:
- Ent_Solutions
description: Información general sobre la planeación, la implementación y el funcionamiento continuo de los inquilinos de Microsoft 365.
ms.openlocfilehash: f7daeaed149b5b6199ac9012b3ffa3d811029099
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908763"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>Administración de inquilinos para Microsoft 365 para empresas

La creación de una ruta de acceso a la transformación digital de su organización con informática en la nube requiere una base firme en la que los trabajadores puedan confiar en la productividad, la colaboración, el rendimiento, la privacidad, el cumplimiento y la seguridad.

La configuración correcta de los inquilinos de Microsoft 365 proporciona esa base, dejando que los trabajadores se centren en realizar su trabajo y que su departamento de TI se centre en soluciones de un extremo a otro que proporcionen valor empresarial adicional. 

Esta solución le lleva a través de la configuración de esa base en estos pasos:

1. Determinar los inquilinos
2. Optimizar las redes
3. Sincronizar las identidades y aplicar inicios de sesión seguros
4. Migrar los dispositivos Windows, los clientes de Office y los datos y servidores de Office locales
5. Implementar la administración de dispositivos y aplicaciones

Pero primero, dedemos un momento para comprender qué es un inquilino y cómo es un inquilino que proporciona una base firme.

## <a name="a-microsoft-365-tenant-defined"></a>Un inquilino de Microsoft 365 definido

Un inquilino de Microsoft 365 es una instancia dedicada de los servicios de Microsoft 365 y los datos de su organización almacenados en una ubicación predeterminada específica, como Europa o Norteamérica. Esta ubicación se especifica al crear el inquilino para su organización. Cada inquilino de Microsoft 365 es distinto, único e independiente de todos los demás inquilinos de Microsoft 365. Crea un inquilino de Microsoft 365 al comprar uno o más productos de Microsoft, como Microsoft 365 E3 o E5, y un conjunto de licencias para cada uno.

El inquilino de Microsoft 365 también incluye un inquilino de Azure Active Directory (Azure AD), que es una instancia dedicada de Azure AD para cuentas de usuario, grupos y otros objetos. Cada inquilino de Azure AD es distinto, único e independiente de todos los demás inquilinos de Azure AD. Aunque su organización puede tener varios inquilinos de Azure AD que puede configurar con suscripciones de Azure, los inquilinos de Microsoft 365 solo pueden usar un único inquilino de Azure AD, el que se creó al crear el inquilino. 

Aquí le mostramos un ejemplo:

![Un ejemplo de inquilino de Microsoft 365 con su inquilino de Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

*La administración de* inquilinos es la planeación, implementación y funcionamiento continuo de los inquilinos de Microsoft 365. 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>Atributos de un inquilino operativo y bien diseñado

Además del nombre y la ubicación correctos para su espacio empresarial, hay elementos adicionales para planear, implementar y administrar para garantizar que las experiencias de usuario con aplicaciones de productividad en la nube como Microsoft Teams y Exchange Online sean eficaces, seguras y &mdash; &mdash; eficaces.

Estos son los elementos:

- Tiene el conjunto correcto de productos (suscripciones) y licencias.
  - El conjunto de productos se ajustará a las necesidades empresariales, de IT y de seguridad.
  - Hay un número adecuado de licencias para los trabajadores y cambios previstos en la personal.
- Para redes:
  - Ha configurado los nombres de dominio DNS correctos.
  - Para las redes empresariales, ha optimizado el tráfico de red a la red de Microsoft para los trabajadores in situ.
  - Ha optimizado el tráfico de red para los trabajadores remotos que usan un cliente VPN.
- Ha sincronizado sus cuentas, grupos y otros objetos de Servicios de dominio de Active Directory (AD DS).
  - Las cuentas de inquilino de Azure AD se asignan a buzones de Exchange Online con los dominios DNS correctos para las direcciones de correo electrónico.
  - A las cuentas de usuario se les han asignado las licencias correctas de los productos comprados correctos (como Microsoft 365 E3 o E5).
- Ha configurado una administración segura de identidades y acceso.
  - Necesita un inicio de sesión de usuario seguro con autenticación multifactor (MFA) o sin contraseña.
  - Tiene directivas de acceso condicional que aplican requisitos de inicio de sesión y restricciones para niveles más altos de seguridad.
- Los servidores de Office locales y sus datos se han migrado a aplicaciones en la nube o se usan en una configuración híbrida.
- Está realizando la administración de dispositivos con Intune o Movilidad y seguridad básica integrada en Microsoft 365.
  - Los dispositivos propiedad de la organización se inscriben y administran.
  - Las aplicaciones para dispositivos personales se administran.

Este es un ejemplo de un inquilino de Microsoft 365 con todos estos elementos en su lugar.

![Un ejemplo de inquilino de Microsoft 365](../media/tenant-management-overview/tenant-management-tenant-config.png)

En esta ilustración, el inquilino de Microsoft 365 incluye:

- Productos y licencias para Microsoft 365 E3 y E5.
- Aplicaciones de productividad de Microsoft 365.
- Intune con dispositivos inscritos y directivas de dispositivos y aplicaciones.
- Un inquilino de Azure AD que tiene una cuenta de usuario sincronizada (no se muestran grupos y otros objetos de directorio), dominios y directivas de acceso condicional.

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>Funcionalidades de inquilino para Microsoft 365 para empresas

En las siguientes secciones y tabla se indican las funciones clave y las licencias para los pasos de esta solución.

### <a name="tenant"></a>Tenant

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| Varios inquilinos | Cada inquilino de Microsoft 365 es distinto, único e independiente de todos los demás inquilinos de Microsoft 365. Con varios inquilinos, existen restricciones y consideraciones adicionales al administrarlos y proporcionar servicios a los usuarios. | Microsoft 365 E3 o E5 | 
| Migración de buzones de inquilinos cruzados | Los administradores de inquilinos pueden mover buzones entre inquilinos con dependencias de infraestructura mínimas en sus sistemas locales. Esto elimina la necesidad de incorporar buzones de correo. | Microsoft 365 E3 o E5 | 
| Multi-Geo | Su espacio empresarial puede almacenar datos en reposo en las otras ubicaciones geográficas del centro de datos que haya elegido para cumplir los requisitos de residencia de datos. | Microsoft 365 E3 o E5 | 
| Mover datos principales a una nueva ubicación geográfica del centro de datos | A medida que Microsoft agrega nuevas ubicaciones geográficas de centro de datos para recursos de cálculo y capacidad adicionales, puede solicitar un movimiento geográfico del centro de datos para la residencia de datos en la ubicación geográfica de los datos principales de los clientes. | Microsoft 365 E3 o E5 | 
||||

### <a name="networking"></a>Redes

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| Información de red | Métricas de rendimiento de red recopiladas de su inquilino de Microsoft 365 para ayudarle a diseñar perímetros de red para las ubicaciones de las oficinas. | Microsoft 365 E3 o E5 | 
| Automatizar actualizaciones de puntos de conexión | Automatice la configuración y las actualizaciones continuas de los puntos de conexión de Microsoft 365 en los archivos PAC del cliente y los dispositivos y servicios de red. | Microsoft 365 E3 o E5 | 
||||

### <a name="identity"></a>Identidad

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| Sincronizar los Servicios de dominio de Active Directory (AD DS) locales con el inquilino de Azure AD    | Aproveche el proveedor de identidades local para cuentas de usuario, grupos y otros objetos. | Microsoft 365 E3 o E5 |
| MFA aplicada en los valores predeterminados de seguridad   | Protege frente a ataques a identidades y dispositivos, pues obliga a usar una segunda forma de autenticación para iniciar sesión. Los valores predeterminados de seguridad requieren MFA para todas las cuentas de usuario.   | Microsoft 365 E3 o E5 |
| MFA aplicada con acceso condicional| Requerir MFA en función de los atributos del inicio de sesión con directivas de acceso condicional.    | Microsoft 365 E3 o E5 | 
| MFA aplicada con Acceso condicional basado en los riesgos   | Requerir la MFA según el riesgo de inicio de sesión del usuario con Microsoft Defender for Identity. | Microsoft 365 E5 o E3 con las licencias de Azure AD Premium P2 | 
| Autoservicio de restablecimiento de contraseña (SSPR)    | Permitir que los usuarios restablezcan o desbloqueen su contraseña o cuenta ellos mismos.  | Microsoft 365 E3 o E5 |
||||

### <a name="migration"></a>Migración

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| Migrar a Windows 10 | Migra los dispositivos que ejecutan Windows 7 o Windows 8.1 a Windows 10 Enterprise. | Licencias de Windows 10 Enterprise incluidas con Microsoft 365 E3 o E5 | 
| Migrar a Aplicaciones de Microsoft 365 para empresas | Migre las aplicaciones cliente de Office, como Word y PowerPoint, a las versiones instaladas desde la nube que se actualizan con nuevas características. | Microsoft 365 E3 o E5 | 
| Migrar datos y servidores locales a Microsoft 365 | Migre los buzones de Exchange, los sitios de SharePoint y Skype Empresarial Online a los servicios en la nube de Microsoft 365. | Microsoft 365 E3 o E5 | 
||||

### <a name="device-and-app-management"></a>Administración de dispositivos y aplicaciones

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| Microsoft Intune | Un servicio basado en la nube que proporciona administración de dispositivos móviles (MDM) y administración de aplicaciones móviles (MAM) para controlar cómo se usan la aplicación de la organización y los dispositivos, incluidos teléfonos móviles, tabletas y portátiles. | Microsoft 365 E3 o E5 | 
| Movilidad y seguridad básicas | Proteja y administre los dispositivos móviles de los usuarios, como iPhone, iPad, Android y teléfonos Windows con este servicio integrado.  | Microsoft 365 E3 o E5 | 
||||

## <a name="next-steps"></a>Pasos siguientes

Siga estos pasos para configurar y administrar los inquilinos de Microsoft 365.

1. [Determinar los inquilinos](tenant-management-tenants.md)
2. [Optimizar las redes](tenant-management-networking.md)
3. [Sincronizar las identidades y aplicar inicios de sesión seguros](tenant-management-identity.md)
4. [Migrar los datos y servidores de Office locales](tenant-management-migration.md)
5. [Implementar la administración de dispositivos y aplicaciones](tenant-management-device-management.md)

[![Pasos para implementar y administrar un inquilino de Microsoft 365](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

Cada paso describe las opciones de implementación, resume los resultados y las tareas de mantenimiento en curso.

Para comprender cómo una organización internacional ficticia pero representativa implementó los elementos de su inquilino de Microsoft 365, consulte el caso práctico [de Contoso.](../enterprise/contoso-case-study.md)
