---
title: Administración de reglas personalizadas para directivas de firewall en Microsoft Defender para Empresas
description: Las reglas personalizadas proporcionan excepciones a las directivas de firewall. Puede usar reglas personalizadas para bloquear o permitir conexiones específicas en Defender para empresas.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 38b4b70e3ad2c1de098f1b608d0470faa51e1604
ms.sourcegitcommit: 511d15831b97d02e5a0f5e11834ad52617abd0f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67600255"
---
# <a name="manage-your-custom-rules-for-firewall-policies-in-microsoft-defender-for-business"></a>Administrar las reglas personalizadas para directivas de firewall en Microsoft Defender para Empresas

Defender for Business incluye directivas de firewall que ayudan a proteger los dispositivos del tráfico de red no deseado. Puede usar reglas personalizadas para definir excepciones para las directivas de firewall. Es decir, puede usar reglas personalizadas para bloquear o permitir conexiones específicas.

Para más información sobre las directivas y la configuración del firewall, consulte [Firewall en Defender para empresas](mdb-firewall.md).

**En este artículo se describe cómo**:

- [Creación de una regla personalizada para una directiva de firewall](#create-a-custom-rule-for-a-firewall-policy)
- [Edición de una regla personalizada para una directiva de firewall](#edit-a-custom-rule-for-a-firewall-policy)
- [Eliminación de una regla personalizada](#delete-a-custom-rule)


## <a name="create-a-custom-rule-for-a-firewall-policy"></a>Creación de una regla personalizada para una directiva de firewall

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Vaya a **Configuración del dispositivo** **de puntos** >  de conexión y revise la lista de directivas.

3. En la sección **Firewall** , seleccione una directiva existente o agregue una nueva.

4. En el paso **Configuración** , revise la configuración. Realice los cambios necesarios en **Red de dominio**, **Red pública** y **Red privada**.

5. Para crear una regla personalizada, siga estos pasos: 

   1. En **Reglas personalizadas**, elija **+ Agregar regla**. (Puede tener hasta 150 reglas personalizadas).
   2. En el control flotante **Crear nueva regla** , especifique un nombre y una descripción para la regla.
   3. Seleccione un perfil. (Las opciones incluyen **Red de dominio**, **Red pública** o **Red privada**).
   4. En la lista **Tipo de dirección remota** , seleccione **IP** o **Ruta de acceso del archivo de aplicación**.
   5. En el cuadro **Valor** , especifique un valor adecuado. En función de lo que haya seleccionado en el paso 6d, puede especificar una dirección IP, un intervalo de direcciones IP o una ruta de acceso del archivo de aplicación. (Consulte [Configuración del firewall](mdb-firewall.md)).
   6. En el control flotante **Crear nueva regla** , seleccione **Crear regla**. 

6. En la pantalla **Configuración** , elija **Siguiente**.

7. En la pantalla **Revisar la directiva** , revise los cambios realizados en la configuración de la directiva de firewall. Realice los cambios necesarios y, a continuación, elija **Crear directiva**.

## <a name="edit-a-custom-rule-for-a-firewall-policy"></a>Edición de una regla personalizada para una directiva de firewall

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Vaya a **Configuración del dispositivo** **de puntos** >  de conexión y revise la lista de directivas.

3. En la sección **Firewall** , seleccione una directiva existente o agregue una nueva.

4. En **Reglas personalizadas**, revise la lista de reglas.

5. Seleccione una regla y, a continuación, elija **Editar**. Se abre el control flotante.

6. Para editar la regla personalizada, siga estos pasos:

   1. En el control flotante **Editar regla** , revise y edite el nombre y la descripción de la regla.
   2. Revise y, si es necesario, edite el perfil de la regla. (Las opciones incluyen **Red de dominio**, **Red pública** o **Red privada**).
   3. En la lista **Tipo de dirección remota** , seleccione **IP** o **Ruta de acceso del archivo de aplicación**.
   4. En el cuadro **Valor** , especifique un valor adecuado. En función de lo que haya seleccionado en el paso 6c, puede especificar una dirección IP, un intervalo de direcciones IP o una ruta de acceso del archivo de aplicación. (Consulte [Configuración del firewall](mdb-firewall.md)).
   5. Establezca **Habilitar regla** **en Activado** para que la regla esté activa. O bien, para deshabilitar la regla, establezca el modificador en **Desactivado**.
   6. En el control flotante **Editar regla** , seleccione **Actualizar regla**. 

7. En la pantalla **Configuración** , elija **Siguiente**.

8. En la pantalla **Revisar la directiva** , revise los cambios realizados en la configuración de la directiva de firewall. Realice los cambios necesarios y, a continuación, elija **Crear directiva**.

## <a name="delete-a-custom-rule"></a>Eliminación de una regla personalizada

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Vaya a **Configuración del dispositivo** **de puntos** >  de conexión y revise la lista de directivas.

3. En la sección **Firewall** , seleccione una directiva existente o agregue una nueva.

4. En **Reglas personalizadas**, revise la lista de reglas.

5. Seleccione una regla y, a continuación, elija **Eliminar**. Se abre el control flotante.

6. En la pantalla de confirmación, elija **Eliminar**. 

## <a name="next-steps"></a>Pasos siguientes

- [Visualización y administración de incidentes en Defender para empresas](mdb-view-manage-incidents.md)
- [Respuesta y mitigación de amenazas en Defender para empresas](mdb-respond-mitigate-threats.md)
- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)