---
title: Administrador de cumplimiento de Microsoft y el RGPD
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: El Administrador de cumplimiento de Microsoft es una herramienta gratuita de evaluación de riesgos basada en el flujo de trabajo que se encuentra dentro del Portal de confianza de servicios de Microsoft. El Administrador de cumplimiento le permite realizar un seguimiento, asignar y verificar las actividades de cumplimiento reglamentarias de su organización en relación con los servicios en la nube de Microsoft.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595807"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="47dec-104">Administrador de cumplimiento de Microsoft y el RGPD</span><span class="sxs-lookup"><span data-stu-id="47dec-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="47dec-105">El Reglamento general de protección de datos (RGPD), aprobado por la Unión Europea, puede afectar a la estrategia de cumplimiento e implantar acciones específicas para administrar la información del usuario y del cliente que se usa en el Administrador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="47dec-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="47dec-106">Configuración de privacidad del usuario</span><span class="sxs-lookup"><span data-stu-id="47dec-106">User Privacy settings</span></span>

<span data-ttu-id="47dec-107">Algunos reglamentos exigen que la organización sea capaz de eliminar los datos del historial del usuario.</span><span class="sxs-lookup"><span data-stu-id="47dec-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="47dec-108">El Administrador de cumplimiento proporciona las funciones de **Configuración de privacidad del usuario**, que permiten a los administradores:</span><span class="sxs-lookup"><span data-stu-id="47dec-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="47dec-109">Buscar un usuario</span><span class="sxs-lookup"><span data-stu-id="47dec-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="47dec-110">Exportar un informe de historial de datos de cuenta</span><span class="sxs-lookup"><span data-stu-id="47dec-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="47dec-111">Eliminar el historial de datos del usuario</span><span class="sxs-lookup"><span data-stu-id="47dec-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="47dec-112">Buscar un usuario</span><span class="sxs-lookup"><span data-stu-id="47dec-112">Search for a user</span></span>

<span data-ttu-id="47dec-113">Para buscar una cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="47dec-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="47dec-p103">Escriba el alias de la dirección de correo electrónico del usuario (la información a la izquierda del símbolo @) y, después, seleccione el nombre de dominio de la lista de sufijos de dominio en la parte derecha. En el caso de las organizaciones con varios dominios registrados, compruebe el sufijo del nombre de dominio para asegurarse de que sea el correcto.</span><span class="sxs-lookup"><span data-stu-id="47dec-p103">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right. For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="47dec-116">Después de especificar correctamente el nombre de usuario, seleccione **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="47dec-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="47dec-117">Para las cuentas de usuario que no se devuelven en la búsqueda, la página muestra **Usuario no encontrado**.</span><span class="sxs-lookup"><span data-stu-id="47dec-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="47dec-118">Revise la información de dirección de correo electrónico del usuario y realice las correcciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="47dec-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="47dec-119">Para reintentar, seleccione **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="47dec-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="47dec-120">Para las cuentas de usuario devueltas en la búsqueda, el texto del botón cambia de **Buscar** a **Borrar**.</span><span class="sxs-lookup"><span data-stu-id="47dec-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="47dec-121">Esto indica que la cuenta de usuario devuelta es el contexto operativo para las funciones adicionales, y que estas funciones se aplican a esta cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="47dec-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="47dec-122">Para borrar los resultados de la búsqueda y buscar otro usuario, seleccione **Borrar**.</span><span class="sxs-lookup"><span data-stu-id="47dec-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="47dec-123">Exportar un informe del historial de datos de la cuenta</span><span class="sxs-lookup"><span data-stu-id="47dec-123">Export a report of account data history</span></span>

<span data-ttu-id="47dec-p106">Para cada cuenta de usuario identificada, puede generar un informe de dependencias vinculadas a la cuenta. Esta información le permitirá reasignar las Acciones abiertas o garantizar el acceso a evidencias cargadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="47dec-p106">For each user account identified, you can generate a report of dependencies linked to the account. This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="47dec-126">Para generar y exportar un informe:</span><span class="sxs-lookup"><span data-stu-id="47dec-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="47dec-127">Seleccione **Exportar** para generar y descargar un informe de Acciones de control del Administrador de cumplimiento, que ya está asignado a la cuenta de usuario devuelta, así como para generar y descargar la lista de documentos que ha cargado el usuario.</span><span class="sxs-lookup"><span data-stu-id="47dec-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="47dec-128">Si no hay acciones asignadas ni documentos cargados, un mensaje de error indicará "No hay datos para este usuario".</span><span class="sxs-lookup"><span data-stu-id="47dec-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="47dec-129">El informe se descargará en segundo plano desde la ventana del explorador activa. Si no ve un mensaje emergente de descarga, consulte el historial de descargas del explorador.</span><span class="sxs-lookup"><span data-stu-id="47dec-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="47dec-130">Abra el documento para revisar los datos del informe.</span><span class="sxs-lookup"><span data-stu-id="47dec-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47dec-p108">Los datos del informe no son una lista histórica que conserva y muestra los cambios de estado en el historial de asignaciones de las Acciones. El informe generado es una instantánea de informe de las Acciones de control asignadas en el momento en que se ejecutó el informe (con la marca de fecha y hora escrita en el informe). Por ejemplo, si, posteriormente, se reasignan Acciones y vuelve a generarse el informe para el mismo usuario, se obtendrá una instantánea de informe con datos distintos.</span><span class="sxs-lookup"><span data-stu-id="47dec-p108">The report data is not a historical list that retains and displays state changes to Action Item assignment history. The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report). For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="47dec-134">Eliminar el historial de datos del usuario</span><span class="sxs-lookup"><span data-stu-id="47dec-134">Delete user data history</span></span>

<span data-ttu-id="47dec-135">Establece en "no asignadas" todas las Acciones de control asignadas al usuario devuelto.</span><span class="sxs-lookup"><span data-stu-id="47dec-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="47dec-136">Establece en "eliminado por el usuario" el valor **cargado por** para los documentos cargados por el usuario devuelto.</span><span class="sxs-lookup"><span data-stu-id="47dec-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="47dec-137">Para eliminar el historial de carga de documentos y las Acciones de la cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="47dec-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="47dec-138">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="47dec-138">Select **Delete**.</span></span>

    <span data-ttu-id="47dec-139">Se muestra un cuadro de diálogo de confirmación: "*Se eliminarán todas las asignaciones de Acciones de control y el historial de carga de documentos del usuario seleccionado. Esta acción no se puede deshacer. ¿Está seguro de que quiere continuar?*"</span><span class="sxs-lookup"><span data-stu-id="47dec-139">A confirmation dialog is displayed: "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="47dec-140">Para continuar, seleccione **Aceptar**, en caso contrario, seleccione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="47dec-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
