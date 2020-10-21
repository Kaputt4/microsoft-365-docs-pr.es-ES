---
title: Infraestructura de ti y necesidades empresariales de Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda la estructura básica de la infraestructura de ti local de Contoso y cómo se satisfacen las necesidades empresariales de Microsoft 365 para la empresa.
ms.openlocfilehash: bc2b34254da01a3d49085082ab8ee8632df2d434
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637180"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a>Infraestructura de ti y necesidades empresariales de Contoso

Contoso está pasando de una infraestructura de ti centralizada local a una configuración de nube inclusiva que incorpora las cargas de trabajo y aplicaciones de productividad personal basadas en la nube.

## <a name="existing-contoso-it-infrastructure"></a>Infraestructura de TI existente de Contoso

Contoso usa una infraestructura de TI local mayoritariamente centralizada, con centros de datos de aplicaciones en la sede de París.

La figura 1 muestra la oficina central con centros de aplicaciones, una red perimetral e Internet.

![Infraestructura de TI existente de Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

**Figura 1: infraestructura de TI existente de Contoso**
 
En los centros de datos de aplicaciones locales se hospeda lo siguiente: 

- Aplicaciones de línea de negocio personalizadas que usan SQL Server y otras bases de datos de Linux.
- Un conjunto de servidores de SharePoint heredados.
- Servidores de nivel de equipo y de la organización para el almacenamiento de archivos.

Además, cada una de las oficinas centrales regionales es compatible con un conjunto de servidores que tiene un conjunto de aplicaciones similares. Estos servidores están bajo el control de los departamentos de TI regionales.

La capacidad de búsqueda entre las aplicaciones y los datos de todos estos centros de datos separados geográficamente sigue siendo un desafío.

En la DMZ de la sede central de Contoso, los distintos conjuntos de servidores proporcionan lo siguiente:

- Hospedaje para el sitio web público de Contoso, desde el que los clientes pueden solicitar productos, piezas, suministros y servicio.
- Hospedaje de la extranet de partners de Contoso para la colaboración y comunicación de los partners.
- Acceso remoto a la intranet de Contoso basado en VPN (Red privada virtual) y proxy web para los trabajadores de la sede de París.

## <a name="contoso-business-needs"></a>Necesidades empresariales de Contoso

Las necesidades empresariales de Contoso se dividen en cinco categorías principales:

**Productividad**

- Facilitar la colaboración

  Reemplace el correo electrónico y la colaboración basada en recursos compartidos de archivos con un modelo en línea que permita cambios en tiempo real en documentos, reuniones en línea más sencillas y conversaciones de conversación capturadas.
- Mejorar la productividad de los trabajadores remotos y móviles

  Con muchos empleados que trabajan desde casa o en el campo, reemplace la solución VPN con cuellos de botella por el acceso de tipo de Contoso a los datos y recursos de la nube.
- Aumentar la creatividad y la innovación

  Aproveche las ventajas de los métodos más recientes de aprendizaje visual y desarrollo de ideas, como la entrada manuscrita y la visualización 3D.

**Seguridad**

- Administración de identidad y acceso

  Exigir la autenticación multifactor y otras formas de autenticación y proteger las credenciales de las cuentas de usuario y administrador.

- Protección contra amenazas

  Proteja contra amenazas de seguridad externas, como el correo electrónico y el malware basado en el sistema operativo.

- Protección de la información

  Restrinja el acceso y cifre los activos digitales de gran valor, como los datos del cliente, las especificaciones de diseño y manufactura y la información de los empleados.

- Administración de seguridad

  Supervise el postura de seguridad y detecte y responda a amenazas en tiempo real.

**Acceso móvil y remoto, y socios comerciales**

- Mejorar la seguridad de los trabajadores remotos y móviles

  Implemente su propio dispositivo (BYOD) y la administración de dispositivos de propiedad de la empresa para garantizar el acceso seguro, el comportamiento correcto de las aplicaciones y la protección de datos de la empresa.

- Reducir la infraestructura de acceso remoto para los empleados

  Reducir los costos de mantenimiento y soporte técnico y mejorar el rendimiento de la solución de acceso remoto moviendo los recursos a los que se accede habitualmente a la nube.

- Proporcionar mejor conectividad y menor overhead para las transacciones de negocio a susiness (B2B)

  Reemplace una extranet de asociados con una detección de asociados con una solución basada en la nube que use la autenticación federada.

**Cumplimiento**

- Cumplir los requisitos normativos regionales

  Garantizar el cumplimiento de las regulaciones de la industria y la regional para el almacenamiento de datos, el cifrado, la privacidad de datos y las regulaciones de datos personales, como el Reglamento General de protección de datos (RGPD) para la Unión Europea.

**Administración**

- Reducir la sobrecarga de TI para administrar el software que se ejecuta en equipos y dispositivos cliente

  Automatizar la instalación de actualizaciones para el sistema operativo Windows y las aplicaciones de Microsoft 365 para empresas en toda la organización.

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>Asignación de las necesidades empresariales de Contoso a Microsoft 365 para empresas

El Departamento de TI de Contoso determinó la siguiente asignación de necesidades empresariales a las características de Microsoft 365 E5 antes de la implementación:


| Categoría | Necesidad empresarial | Microsoft 365 para productos o características de empresa |
|:-------|:-----|:-----|
| Productividad |  |  |
|  | Facilitar la colaboración | Microsoft Teams, SharePoint, OneDrive |
|  | Mejorar la productividad de los trabajadores remotos y móviles | Cargas de trabajo de Microsoft 365 y datos basados en la nube |
|  | Aumentar la creatividad y la innovación | Windows Ink, Cortana en el trabajo, PowerPoint |
| Seguridad |  |  |
|  | Administración de identidad y acceso | Cuentas de administrador global dedicadas con Azure multi-factor Authentication (MFA) y Azure Active Directory privileged Identity Management (PIM) <BR> MFA para todas las cuentas de usuario <BR> Acceso condicional <BR> Windows Hello <BR> Credential Guard de Windows Defender |
|  | Protección contra amenazas | Advanced Threat Analytics <BR> Windows Defender <BR> Protección contra amenazas avanzada <BR> Protección contra amenazas avanzada de Office 365 <BR> Respuesta y investigación de amenazas de Microsoft 365 <BR> |
|  | Protección de la información | Azure Information Protection <BR> Prevención de pérdida de datos (DLP) <BR> Windows Information Protection (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | Administración de seguridad | Azure Security Center  <BR> Centro de seguridad de Windows Defender |
| Acceso móvil y remoto, y socios comerciales |  |  |
|  | Mejorar la seguridad de los trabajadores remotos y móviles | Microsoft Intune |
|  | Reducir la infraestructura de acceso remoto para los empleados | Cargas de trabajo de Microsoft 365 y datos basados en la nube |
|  | Mejorar la conectividad y reducir la sobrecarga para las transacciones B2B | Autenticación federada y recursos basados en la nube |
| Cumplimiento |  |  |
|  | Cumplir los requisitos normativos regionales | Características de RGPD en Microsoft 365 |
| Administración |  |  |
|  | Reducir la sobrecarga de TI para instalar actualizaciones de cliente | Anillos de implementación <BR> Actualizaciones de Windows 10 Enterprise <BR> Actualizaciones para las aplicaciones de Microsoft 365 para empresas |
||||

## <a name="next-step"></a>Paso siguiente

[Obtenga información](contoso-networking.md) sobre la red local de Contoso Corporation y cómo se optimizó para el acceso y la latencia de los recursos basados en la nube de Microsoft 365.

## <a name="see-also"></a>Vea también

[Información general de Microsoft 365 para empresas](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)
