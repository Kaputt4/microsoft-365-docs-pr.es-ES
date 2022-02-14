---
title: Administrar reglas personalizadas para directivas de firewall en Microsoft Defender para empresas
description: Las reglas personalizadas proporcionan excepciones a las directivas de firewall. Puede usar reglas personalizadas para bloquear o permitir conexiones específicas en Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/07/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 2200c32d910a5afd20a8ff01c6e24625d72ae21c
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "62464595"
---
# <a name="manage-your-custom-rules-for-firewall-policies-in-microsoft-defender-for-business-preview"></a>Administrar las reglas personalizadas para directivas de firewall en Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Microsoft Defender para empresas ya está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Ten en cuenta que la vista previa se iniciará con un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 


Microsoft Defender para empresas (versión preliminar) incluye directivas de firewall que ayudan a proteger los dispositivos del tráfico de red no deseado. Puede usar reglas personalizadas para definir excepciones para las directivas de firewall. Es decir, puede usar reglas personalizadas para bloquear o permitir conexiones específicas.

Para obtener más información sobre las directivas y la configuración de firewall, consulte [Firewall in Microsoft Defender for Business (versión preliminar).](mdb-firewall.md).

**En este artículo se describe cómo**:

- [Crear una regla personalizada para una directiva de firewall](#create-a-custom-rule-for-a-firewall-policy)
- [Editar una regla personalizada para una directiva de firewall](#edit-a-custom-rule-for-a-firewall-policy)
- [Eliminar una regla personalizada](#delete-a-custom-rule)

## <a name="create-a-custom-rule-for-a-firewall-policy"></a>Crear una regla personalizada para una directiva de firewall

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Vaya a **Configuración de EndpointsDevice** >  y revise la lista de directivas.

3. En la **sección Firewall** , seleccione una directiva existente o agregue una nueva directiva.

4. En el **paso Configuración** , revise la configuración. Realice los cambios necesarios en **la red de dominio**, **la red pública** y **la red privada**.

5. Para crear una regla personalizada, siga estos pasos: 

   1. En **Reglas personalizadas**, elija **+ Agregar regla**. (Puede tener hasta 150 reglas personalizadas).
   2. En el **menú desplegable Crear nueva** regla, especifique un nombre y una descripción para la regla.
   3. Seleccione un perfil. (Sus opciones incluyen **Red de dominio**, **Red pública** o **Red privada**).
   4. En la **lista Tipo de dirección remota** , seleccione **IP** o **Ruta de acceso de archivo de aplicación**.
   5. En el **cuadro** Valor, especifique un valor adecuado. Según lo que haya seleccionado en el paso 6d, puede especificar una dirección IP, un intervalo de direcciones IP o una ruta de acceso de archivo de aplicación. (Consulte [Configuración del firewall](mdb-firewall.md)).
   6. En el **menú desplegable Crear nueva** regla, seleccione **Crear regla**. 

6. En la **pantalla Configuración** , elija **Siguiente**.

7. En la **pantalla Revisar la directiva** , revise los cambios realizados en la configuración de directiva de firewall. Realice los cambios necesarios y, a continuación, **elija Crear directiva**.

## <a name="edit-a-custom-rule-for-a-firewall-policy"></a>Editar una regla personalizada para una directiva de firewall

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Vaya a **Configuración de EndpointsDevice** >  y revise la lista de directivas.

3. En la **sección Firewall** , seleccione una directiva existente o agregue una nueva directiva.

4. En **Reglas personalizadas**, revise la lista de reglas.

5. Seleccione una regla y, a continuación, **elija Editar**. Se abre el menú desplegable.

6. Para editar la regla personalizada, siga estos pasos:

   1. En el **control desplegable Editar** regla, revise y edite el nombre y la descripción de la regla.
   2. Revise y, si es necesario, edite el perfil de la regla. (Sus opciones incluyen **Red de dominio**, **Red pública** o **Red privada**).
   3. En la **lista Tipo de dirección remota** , seleccione **IP** o **Ruta de acceso de archivo de aplicación**.
   4. En el **cuadro** Valor, especifique un valor adecuado. Según lo que haya seleccionado en el paso 6c, puede especificar una dirección IP, un intervalo de direcciones IP o una ruta de acceso de archivo de aplicación. (Consulte [Configuración del firewall](mdb-firewall.md)).
   5. Establezca **Habilitar regla en** **Activado** para activar la regla. O bien, para deshabilitar la regla, establezca el modificador en **Desactivado**.
   6. En el **control desplegable Editar** regla, seleccione **Actualizar regla**. 

7. En la **pantalla Configuración** , elija **Siguiente**.

8. En la **pantalla Revisar la directiva** , revise los cambios realizados en la configuración de directiva de firewall. Realice los cambios necesarios y, a continuación, **elija Crear directiva**.

## <a name="delete-a-custom-rule"></a>Eliminar una regla personalizada

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Vaya a **Configuración de EndpointsDevice** >  y revise la lista de directivas.

3. En la **sección Firewall** , seleccione una directiva existente o agregue una nueva directiva.

4. En **Reglas personalizadas**, revise la lista de reglas.

5. Seleccione una regla y, a continuación, **elija Eliminar**. Se abre el menú desplegable.

6. En la pantalla de confirmación, elija **Eliminar**. 

## <a name="next-steps"></a>Siguientes pasos

- [Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar)](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas en Microsoft Defender para empresas (versión preliminar)](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)