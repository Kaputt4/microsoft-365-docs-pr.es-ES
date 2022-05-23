---
title: Infraestructura de TI y necesidades empresariales de Contoso
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda la estructura básica de la infraestructura de TI local de Contoso y cómo se satisfacen las necesidades empresariales de la empresa Microsoft 365 para la empresa.
ms.openlocfilehash: 793c867d47d76a03efad707d8447e04538c8ebb8
ms.sourcegitcommit: db1e48af88995193f15bbd5962f5101a6088074b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2022
ms.locfileid: "65637503"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a>Infraestructura de TI y necesidades empresariales de Contoso

Contoso está realizando la transición de una infraestructura de TI centralizada y local a una configuración inclusiva en la nube que incorpora aplicaciones y cargas de trabajo de productividad personal basadas en la nube.

## <a name="existing-contoso-it-infrastructure"></a>Infraestructura de TI de Contoso existente

Contoso usa una infraestructura de TI local mayoritariamente centralizada, con centros de datos de aplicaciones en la sede de París.

Esta es la oficina central con centros de datos de aplicaciones, una red perimetral e Internet.

![Infraestructura de TI de Contoso existente.](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

En los centros de datos de aplicaciones locales se hospeda lo siguiente: 

- Aplicaciones de línea de negocio personalizadas que usan SQL Server y otras bases de datos linux.
- Un conjunto de servidores de SharePoint heredados.
- Servidores de nivel de equipo y de la organización para el almacenamiento de archivos.

Además, cada una de las oficinas centrales regionales es compatible con un conjunto de servidores que tiene un conjunto de aplicaciones similares. Estos servidores están bajo el control de los departamentos de TI regionales.

La capacidad de búsqueda entre las aplicaciones y los datos de todos estos centros de datos separados geográficamente sigue siendo un desafío.

En la red perimetral de la sede central de Contoso, los distintos conjuntos de servidores proporcionan:

- Hospedaje para el sitio web público de Contoso, desde el que los clientes pueden pedir productos, piezas, suministros y servicio.
- Hospedaje de la extranet de partners de Contoso para la colaboración y comunicación de los partners.
- Acceso remoto a la intranet de Contoso basado en VPN (Red privada virtual) y proxy web para los trabajadores de la sede de París.

## <a name="contoso-business-needs"></a>Necesidades empresariales de Contoso

Las necesidades empresariales de Contoso se dividen en cinco categorías principales:

**Productividad**

- Facilitar la colaboración

  Reemplace la colaboración basada en correo electrónico y recurso compartido de archivos por un modelo en línea que permita cambios en tiempo real en documentos, reuniones en línea más sencillas y subprocesos de conversación capturados.
- Mejorar la productividad de los trabajadores remotos y móviles

  Con muchos empleados trabajando desde casa o en el campo, reemplace la solución VPN con cuellos de botella por un acceso eficaz a los datos y recursos de Contoso en la nube.
- Aumentar la creatividad y la innovación

  Aproveche las ventajas de los métodos más recientes de aprendizaje visual y desarrollo de ideas, como la entrada manuscrita y la visualización 3D.

**Seguridad**

- Administración de identidad y acceso

  Aplique multifactor y otras formas de autenticación y proteja las credenciales de cuenta de usuario y administrador.

- Protección contra amenazas

  Proteja contra amenazas de seguridad externas, como el correo electrónico y el malware basado en el sistema operativo.

- Protección de la información

  Restrinja el acceso y cifre los activos digitales de gran valor, como los datos del cliente, las especificaciones de diseño y manufactura y la información de los empleados.

- Administración de seguridad

  Supervise la posición de seguridad y detecte y responda a las amenazas en tiempo real.

**Acceso móvil y remoto, y socios comerciales**

- Mejora de la seguridad de los trabajadores remotos y móviles

  Implemente bring your own device (BYOD) y administración de dispositivos propiedad de la empresa para garantizar el acceso protegido, el comportamiento correcto de la aplicación y la protección de datos de la empresa.

- Reducir la infraestructura de acceso remoto para los empleados

  Reduzca los costos de mantenimiento y soporte técnico y mejore el rendimiento de la solución de acceso remoto mediante el traslado de recursos de acceso frecuente a la nube.

- Proporcionar una mejor conectividad y una menor sobrecarga para las transacciones de negocio a negocio (B2B)

  Reemplace una extranet de asociado envejecida y costosa por una solución basada en la nube que use la autenticación federada.

**Cumplimiento**

- Cumplir los requisitos normativos regionales

  Garantizar el cumplimiento de las regulaciones regionales y del sector para el almacenamiento de datos, el cifrado, la privacidad de los datos y las regulaciones de datos personales, como el Reglamento general de protección de datos (RGPD) para la Unión Europea.

**Administración**

- Reducción de la sobrecarga de TI para administrar el software que se ejecuta en equipos y dispositivos cliente

  Automatice la instalación de actualizaciones en el sistema operativo Windows y Aplicaciones Microsoft 365 para empresas en toda la organización.

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>Asignación de las necesidades empresariales de Contoso para Microsoft 365 para empresas

El departamento de TI de Contoso determinó la siguiente asignación de las necesidades empresariales para Microsoft 365 E5 características antes de la implementación:


| Categoría | Necesidad empresarial | Microsoft 365 para productos o características empresariales |
|:-------|:-----|:-----|
| Productividad |  |  |
|  | Facilitar la colaboración | Microsoft Teams, SharePoint, OneDrive |
|  | Mejorar la productividad de los trabajadores remotos y móviles | Cargas de trabajo de Microsoft 365 y datos basados en la nube |
|  | Aumentar la creatividad y la innovación | Windows Ink, Cortana en el trabajo, PowerPoint |
| Seguridad |  |  |
|  | Administración de identidad y acceso | Cuentas de administrador global dedicadas con Azure AD Multi-Factor Authentication (MFA) y Azure AD Privileged Identity Management (PIM) <br> MFA para todas las cuentas de usuario <br> Acceso condicional <br> Lector de seguridad <br> Windows Hello <br> Credential Guard de Windows Defender |
|  | Protección contra amenazas | Advanced Threat Analytics <br> Windows Defender <br> Defender para Office 365 <br> Microsoft Defender para Office 365 <br> Microsoft 365 investigación y respuesta de amenazas <br> |
|  | Protección de la información | Azure Information Protection <br> Prevención de pérdida de datos (DLP) <br> Windows Information Protection (WIP) <br> Microsoft Defender for Cloud Apps <br> Microsoft Intune |
|  | Administración de seguridad | Microsoft Defender for Cloud  <br> Centro de seguridad de Windows Defender |
| Acceso móvil y remoto, y socios comerciales |  |  |
|  | Mejorar la seguridad de los trabajadores remotos y móviles | Microsoft Intune |
|  | Reducir la infraestructura de acceso remoto para los empleados | Cargas de trabajo de Microsoft 365 y datos basados en la nube |
|  | Mejora de la conectividad y menor sobrecarga para las transacciones B2B | Autenticación federada y recursos basados en la nube |
| Cumplimiento |  |  |
|  | Cumplir los requisitos normativos regionales | Características del RGPD en Microsoft 365 |
| Administración |  |  |
|  | Reducción de la sobrecarga de TI para instalar actualizaciones de cliente | Actualizaciones de Windows 10 Enterprise <br> Actualizaciones para las aplicaciones de Microsoft 365 para empresas |
||||

## <a name="next-step"></a>Paso siguiente

Obtenga información sobre la [red local](contoso-networking.md) de Contoso Corporation y cómo se ha optimizado para el acceso y la latencia para Microsoft 365 recursos basados en la nube.

## <a name="see-also"></a>Recursos adicionales

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)
