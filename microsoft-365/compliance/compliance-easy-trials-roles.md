---
title: Roles de usuario para iniciar pruebas de Microsoft 365
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: landing-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre qué roles de usuario son necesarios para registrarse para obtener una evaluación de los productos de Microsoft 365 Purview, Priva y seguridad.
ms.openlocfilehash: d4613faf7815ca5d8f705a9b1efe76b5f75c435e
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67599788"
---
# <a name="user-roles-for-starting-microsoft-365-trials"></a>Roles de usuario para iniciar pruebas de Microsoft 365

En este artículo se describen los roles de usuario necesarios para inscribir su organización en una prueba de Microsoft 365.

## <a name="who-can-start-all-trials"></a>Quién puede iniciar todas las pruebas

Un usuario con uno de los roles que se enumeran a continuación puede iniciar cualquier prueba de Microsoft 365.
 
| Rol | Grupo de roles | Dónde asignar | 
| :------------- | :-------------: | :------------: |
| Administrador global | Administrador global   | Portal de cumplimiento de Purview > Permisos > roles de > de Azure AD |
| Administración de facturación | Administrador de facturación | Portal de cumplimiento de Purview > Permisos > soluciones de Purview > Roles |

## <a name="roles-for-starting-specific-trials"></a>Roles para iniciar pruebas específicas

Las pruebas de Purview, Priva y Defender permiten a los usuarios con roles específicos, además de Administrador global y Administración de facturación, iniciar sus pruebas. Consulte las tablas siguientes para obtener más información.

#### <a name="purview-trials"></a>Pruebas de Purview

Las pruebas de Purview incluyen la prueba de **soluciones de Microsoft Purview** y la evaluación **premium del Administrador de cumplimiento** . 

| Rol | Grupo de roles | Dónde asignar | 
| :------------- | :-------------: | :------------: |
| Administrador de cumplimiento | Administrador de cumplimiento   | Portal de cumplimiento de Purview > Permisos > soluciones de Purview > Roles |
| Administración de cumplimiento dlp, Information Protection Administración, administración de registros, administración de retención y administrador de etiquetas de confidencialidad | Administrador de datos de cumplimiento | Portal de cumplimiento de Purview > Permisos > soluciones de Purview > Roles |

#### <a name="priva-trials"></a>Pruebas privadas

Las pruebas priva incluyen la prueba **de Administración de riesgos de privacidad** y la evaluación **de solicitudes de derechos del sujeto** .

| Rol | Grupo de roles | Dónde asignar | 
| :------------- | :-------------: | :------------: |
| Administración de administración de privacidad | Administradores de administración de privacidad   | Portal de cumplimiento de Purview > Permisos > soluciones de Purview > Roles |
| Solicitud de derechos del sujeto Administración | Administradores de solicitudes de derechos de sujeto | Portal de cumplimiento de Purview > Permisos > soluciones de Purview > Roles |

#### <a name="security-trials"></a>Pruebas de seguridad

Las pruebas de seguridad incluyen la prueba **de Administración de vulnerabilidades de Defender** y la prueba **del complemento De administración de vulnerabilidades de Defender** . Los usuarios necesitarán un rol con uno de los permisos que se enumeran a continuación para iniciar una prueba.

| Permiso | Dónde asignar | 
| :------------- | :-------------: |
Operaciones de seguridad  | Microsoft 365 Defender portal > permisos > roles de puntos de conexión & grupos > roles  |
| Administración de amenazas y vulnerabilidades | Microsoft 365 Defender portal > permisos > roles de puntos de conexión & grupos > roles |

## <a name="how-to-assign-roles"></a>Cómo asignar roles

Para obtener más información sobre cómo asignar roles de usuario y permisos, consulte los artículos siguientes:

- **Roles de administrador de Microsoft 365**: [Acerca de los roles de administrador en el Centro de administración de Microsoft 365](../admin/add-users/about-admin-roles.md)
- **Microsoft Purview y Priva**: [permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md)
- **Microsoft 365 Defender**: [Creación y administración de roles para el control de acceso basado en rol](../security/defender-endpoint/user-roles.md)