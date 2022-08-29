---
title: Agregar usuarios y asignar licencias en Microsoft Defender para Empresas
description: Agregar usuarios y asignar licencias de Defender para empresas para proteger sus dispositivos
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/24/2022
ms.collection: M365-security-compliance
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.openlocfilehash: e2e6ec0fca05aabe49ad720f1991d1b846c1678a
ms.sourcegitcommit: 2d1302a6165b83cbbc8c2df2c608d43b6b0498b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2022
ms.locfileid: "67433689"
---
# <a name="add-users-and-assign-licenses-in-microsoft-defender-for-business"></a>Agregar usuarios y asignar licencias en Microsoft Defender para Empresas

En cuanto se haya registrado en Defender para empresas, el primer paso es agregar usuarios y asignar licencias. En este artículo se describe cómo agregar usuarios e incluye los pasos siguientes.

## <a name="add-users-and-assign-licenses"></a>Agregar usuarios y asignar licencias

> [!IMPORTANT]
> Debe ser administrador global para realizar esta tarea.  La persona que registró su empresa para Microsoft 365 o para Defender para empresas es un administrador global de forma predeterminada.

1. Vaya al Centro de administración de Microsoft 365 en [https://admin.microsoft.com](https://admin.microsoft.com) e inicie sesión.

2. Vaya a **Usuarios** > **usuarios activos** y, a continuación, seleccione **Agregar un usuario**.

3. En el **Configurar los conceptos básicos** panel, rellene la información básica del usuario y, a continuación, seleccione **Siguiente**.

   - **Nombre**: rellene el nombre y el apellido, el nombre para mostrar y el nombre de usuario.
   - **Dominio** Elija el dominio para la cuenta del usuario. Por ejemplo, si el nombre de usuario del usuario es `Pat`y el dominio es `contoso.com`, iniciarán sesión con `pat@contoso.com`.
   - **Configuración de contraseña**: elija si desea usar la contraseña generada automáticamente o crear su propia contraseña segura para el usuario. El usuario debe cambiar su contraseña después de 90 días. O bien, puede elegir la opción **Requerir que este usuario cambie su contraseña cuando inicie sesión por primera vez**. También puede elegir si desea enviar la contraseña del usuario por correo electrónico cuando se agrega el usuario.

4. En la página **Asignar licencias de producto**, seleccione Defender para empresas (o Microsoft 365 Empresa Premium). A continuación, elija **Siguiente**. 

   Si no cuenta con ninguna licencia disponible, todavía puede agregar un usuario y comprar licencias adicionales. Para obtener más información sobre cómo agregar usuarios, vea [Agregar usuarios y asignar licencias al mismo tiempo](../../admin/add-users/add-users.md).

5. En la página **Configuración opcional** , puede expandir **Información del perfil** y rellenar los detalles, como el puesto de trabajo del usuario, el departamento, la ubicación, etc. A continuación, elija **Siguiente**.

6. En la página **Revisar y finalizar** , revise los detalles y, a continuación, seleccione **Finalizar la adición** para agregar el usuario. Si necesita realizar cambios, elija **Atrás** para volver a una página anterior.

## <a name="next-steps"></a>Siguientes pasos

- [Visite el portal de Microsoft 365 Defender](mdb-get-started.md)
- [Use el asistente de configuración en Defender para empresas](mdb-use-wizard.md).
