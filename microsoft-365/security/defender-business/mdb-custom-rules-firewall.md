---
title: Administrar reglas personalizadas para directivas de firewall en Microsoft Defender para empresas
description: Las reglas personalizadas proporcionan excepciones a las directivas de firewall. Puede usar reglas personalizadas para bloquear o permitir conexiones específicas en Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: c397bd1cee5392ce0f9de45f63d6bd11cb40b29f
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2021
ms.locfileid: "61423880"
---
# <a name="manage-your-custom-rules-for-firewall-policies-in-microsoft-defender-for-business-preview"></a>Administrar las reglas personalizadas para directivas de firewall en Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. En este artículo se incluyen vínculos al contenido en línea que podrían describir algunas características que no se incluyen en Microsoft Defender para empresas (versión preliminar).

Microsoft Defender para empresas (versión preliminar) incluye directivas de firewall que ayudan a proteger los dispositivos del tráfico de red no deseado. Puede usar reglas personalizadas para definir excepciones para las directivas de firewall. Es decir, puede usar reglas personalizadas para bloquear o permitir conexiones específicas.

Para obtener más información sobre las directivas y la configuración de firewall, vea [Firewall in Microsoft Defender for Business (versión preliminar).](mdb-firewall.md)

**En este artículo se describe cómo**:

- [Crear una regla personalizada para una directiva de firewall](#create-a-custom-rule-for-a-firewall-policy)
- [Editar una regla personalizada para una directiva de firewall](#edit-a-custom-rule-for-a-firewall-policy)
- [Eliminar una regla personalizada](#delete-a-custom-rule)

## <a name="create-a-custom-rule-for-a-firewall-policy"></a>Crear una regla personalizada para una directiva de firewall

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. Ve a **Configuración del dispositivo de** puntos  >  **de** conexión y revisa la lista de directivas.

3. En la **sección Firewall,** seleccione una directiva existente o agregue una nueva directiva.

4. En el **paso Configuración,** revise la configuración. Realice los cambios necesarios en **la red de dominio,** **la red pública** y la **red privada.**

5. Para crear una regla personalizada, siga estos pasos: 

   1. En **Reglas personalizadas,** elija **+ Agregar regla**. (Puede tener hasta 150 reglas personalizadas).
   2. En el **menú desplegable Crear nueva** regla, especifique un nombre y una descripción para la regla.
   3. Seleccione un perfil. (Las opciones incluyen **Red de dominio,** **Red pública** o Red **privada**).)
   4. En la **lista Tipo de dirección remota,** seleccione **IP** o Ruta de acceso de archivo **de aplicación.**
   5. En el **cuadro** Valor, especifique un valor adecuado. Según lo que haya seleccionado en el paso 6d, puede especificar una dirección IP, un intervalo de direcciones IP o una ruta de acceso de archivo de aplicación. (Vea [Configuración del firewall](mdb-firewall.md).)
   6. En el **menú desplegable Crear nueva regla,** seleccione Crear **regla**. 

6. En la **pantalla Configuración,** elija **Siguiente**.

7. En la **pantalla Revisar la directiva,** revise los cambios realizados en la configuración de directiva de firewall. Realice los cambios necesarios y, a continuación, **elija Crear directiva**.

## <a name="edit-a-custom-rule-for-a-firewall-policy"></a>Editar una regla personalizada para una directiva de firewall

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. Ve a **Configuración del dispositivo de** puntos  >  **de** conexión y revisa la lista de directivas.

3. En la **sección Firewall,** seleccione una directiva existente o agregue una nueva directiva.

4. En **Reglas personalizadas,** revise la lista de reglas.

5. Seleccione una regla y, a continuación, **elija Editar**. Se abre el menú desplegable.

6. Para editar la regla personalizada, siga estos pasos:

   1. En el **control desplegable Editar** regla, revise y edite el nombre y la descripción de la regla.
   2. Revise y, si es necesario, edite el perfil de la regla. (Las opciones incluyen **Red de dominio,** **Red pública** o Red **privada**).)
   3. En la **lista Tipo de dirección remota,** seleccione **IP** o Ruta de acceso de archivo **de aplicación.**
   4. En el **cuadro** Valor, especifique un valor adecuado. Según lo que haya seleccionado en el paso 6c, puede especificar una dirección IP, un intervalo de direcciones IP o una ruta de acceso de archivo de aplicación. (Vea [Configuración del firewall](mdb-firewall.md).)
   5. Establezca **Habilitar regla en** **Activado** para activar la regla. O bien, para deshabilitar la regla, establezca el modificador en **Desactivado**.
   6. En el **control desplegable Editar** regla, seleccione Actualizar **regla**. 

7. En la **pantalla Configuración,** elija **Siguiente**.

8. En la **pantalla Revisar la directiva,** revise los cambios realizados en la configuración de directiva de firewall. Realice los cambios necesarios y, a continuación, **elija Crear directiva**.

## <a name="delete-a-custom-rule"></a>Eliminar una regla personalizada

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. Ve a **Configuración del dispositivo de** puntos  >  **de** conexión y revisa la lista de directivas.

3. En la **sección Firewall,** seleccione una directiva existente o agregue una nueva directiva.

4. En **Reglas personalizadas,** revise la lista de reglas.

5. Seleccione una regla y, a continuación, **elija Eliminar**. Se abre el menú desplegable.

6. En la pantalla de confirmación, elija **Eliminar**. 

## <a name="next-steps"></a>Siguientes pasos

- [Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar)](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas en Microsoft Defender para empresas (versión preliminar)](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)