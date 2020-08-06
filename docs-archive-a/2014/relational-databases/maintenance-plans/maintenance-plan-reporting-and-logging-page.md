---
title: Plan de mantenimiento (página de informes y registro) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.reportinglogging.f1
ms.assetid: 3a30b17a-3deb-446f-900a-62f88934a90f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c7a95a7092ce2cdac4aa0540a5cb57d86b48497
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671522"
---
# <a name="maintenance-plan-reporting-and-logging-page"></a><span data-ttu-id="12d08-102">Plan de mantenimiento (página de informes y registro)</span><span class="sxs-lookup"><span data-stu-id="12d08-102">Maintenance Plan (Reporting and Logging Page)</span></span>
  <span data-ttu-id="12d08-103">Use el cuadro de diálogo **Informes y registro** para configurar los informes y registros que se generan al ejecutar los planes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="12d08-103">Use the **Reporting and Logging** dialog box to configure the reports and logs that are generated when maintenance plans are executed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="12d08-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="12d08-104">Options</span></span>  
 <span data-ttu-id="12d08-105">**Generar un informe de archivo de texto**</span><span class="sxs-lookup"><span data-stu-id="12d08-105">**Generate a text file report**</span></span>  
 <span data-ttu-id="12d08-106">Especifique si quiere que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escriba un informe de archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="12d08-106">Specify if you want [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to write a text file report.</span></span>  
  
 <span data-ttu-id="12d08-107">**Crear un nuevo archivo**</span><span class="sxs-lookup"><span data-stu-id="12d08-107">**Create a new file**</span></span>  
 <span data-ttu-id="12d08-108">Crea un nuevo archivo de informe para cada una de las ejecuciones del plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="12d08-108">Create a new report file for each execution of the maintenance plan.</span></span> <span data-ttu-id="12d08-109">De forma predeterminada, los archivos de informe se escriben en el equipo que hospeda la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contiene este plan de mantenimiento, en la carpeta establecida como la carpeta de registro predeterminada durante la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="12d08-109">By default, the report files are written to the computer hosting the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains this maintenance plan, in the folder established as the default log folder during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup.</span></span> <span data-ttu-id="12d08-110">Para especificar una carpeta distinta, escriba la ruta de acceso completa de la carpeta en el cuadro de texto **Carpeta** o haga clic en el botón Examinar ( **...** ) y vaya a la carpeta deseada.</span><span class="sxs-lookup"><span data-stu-id="12d08-110">To specify a different folder, enter the full path of the folder in the **Folder** text box, or click the browse button (**...**) and navigate to the desired folder.</span></span>  
  
 <span data-ttu-id="12d08-111">**Anexar a archivo**</span><span class="sxs-lookup"><span data-stu-id="12d08-111">**Append to file**</span></span>  
 <span data-ttu-id="12d08-112">Anexe el informe de cada ejecución de planes al archivo especificado en el cuadro de texto **Nombre de archivo** .</span><span class="sxs-lookup"><span data-stu-id="12d08-112">Append the report from each plan execution to the file specified in the **File name** text box.</span></span> <span data-ttu-id="12d08-113">También puede especificar un archivo si hace clic en el botón examinar (&lt;ui&gt;...&lt;/ui&gt;) y selecciona un archivo del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="12d08-113">You may also specify a file by clicking the browse button and selecting a file from the dialog box.</span></span>  
  
 <span data-ttu-id="12d08-114">**Enviar informe a un destinatario de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="12d08-114">**Send report to an e-mail recipient**</span></span>  
 <span data-ttu-id="12d08-115">Transmite el resultado de la ejecución de un plan de mantenimiento a través de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="12d08-115">Transmit the outcome of a maintenance plan execution via e-mail.</span></span> <span data-ttu-id="12d08-116">Esta opción solo estará disponible si el correo electrónico de base de datos se ha habilitado y configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="12d08-116">This option is only available if Database Mail is enabled and properly configured.</span></span>  
  
 <span data-ttu-id="12d08-117">**Operador del agente**</span><span class="sxs-lookup"><span data-stu-id="12d08-117">**Agent operator**</span></span>  
 <span data-ttu-id="12d08-118">Seleccione un operador del agente de la lista para que sea destinatario del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="12d08-118">Select an agent operator from the list who will be the recipient of the e-mail.</span></span> <span data-ttu-id="12d08-119">Esta opción solo estará disponible si el correo se ha habilitado y configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="12d08-119">This option is only available if mail is enabled and properly</span></span>  
  
 <span data-ttu-id="12d08-120">**Registrar información adicional**</span><span class="sxs-lookup"><span data-stu-id="12d08-120">**Log extended information**</span></span>  
 <span data-ttu-id="12d08-121">Incluya más información en el registro.</span><span class="sxs-lookup"><span data-stu-id="12d08-121">Include more information in the log.</span></span> <span data-ttu-id="12d08-122">Si se incluye esta opción, aumentará el tamaño del historial del plan de mantenimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="12d08-122">Including this option will increase the size of the stored maintenance plan history.</span></span>  
  
 <span data-ttu-id="12d08-123">**Registrar en el servidor remoto**</span><span class="sxs-lookup"><span data-stu-id="12d08-123">**Log to remote server**</span></span>  
 <span data-ttu-id="12d08-124">Registra el historial del plan de mantenimiento en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="12d08-124">Logs maintenance plan history to a remote server.</span></span>  
  
 <span data-ttu-id="12d08-125">**Connection**</span><span class="sxs-lookup"><span data-stu-id="12d08-125">**Connection**</span></span>  
 <span data-ttu-id="12d08-126">Especifica la información de conexión que se va a usar al registrar en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="12d08-126">Specifies the connection information to use when logging to a remote server.</span></span>  
  
 <span data-ttu-id="12d08-127">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="12d08-127">**New**</span></span>  
 <span data-ttu-id="12d08-128">Muestra el cuadro de diálogo **Propiedades de conexión** .</span><span class="sxs-lookup"><span data-stu-id="12d08-128">Displays the **Connection Properties** dialog box.</span></span> <span data-ttu-id="12d08-129">Se usa para configurar información de conexión nueva para registrar en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="12d08-129">Used to configure new connection information for logging to a remote server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d08-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12d08-130">See Also</span></span>  
 <span data-ttu-id="12d08-131">[Planes de mantenimiento](maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="12d08-131">[Maintenance Plans](maintenance-plans.md) </span></span>  
 [<span data-ttu-id="12d08-132">Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="12d08-132">Database Mail</span></span>](../database-mail/database-mail.md)  
  
  
