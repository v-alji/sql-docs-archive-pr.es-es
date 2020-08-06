---
title: Usar Mis informes (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 49c3c1da-b106-41f6-9173-16ff225bade8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 91d44c0aa8471064753d9b4fb0ecc0de89aa8396
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670806"
---
# <a name="using-my-reports-report-builder-and-ssrs"></a><span data-ttu-id="6a365-102">Usar Mis informes (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="6a365-102">Using My Reports (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6a365-103">En un servidor de informes configurado en modo nativo, la carpeta Mis informes es un área de trabajo personal que puede usar para trabajar con sus informes y para almacenarlos.</span><span class="sxs-lookup"><span data-stu-id="6a365-103">On a report server configured in native mode, the My Reports folder is a personal workspace that you can use to store and work with reports that you own.</span></span> <span data-ttu-id="6a365-104">Otras carpetas del servidor de informes son públicas y suelen requerir que los usuarios dispongan de permisos avanzados para agregar o modificar su contenido.</span><span class="sxs-lookup"><span data-stu-id="6a365-104">Other report server folders are public and typically require users to have advanced permissions to add to or modify folder contents.</span></span> <span data-ttu-id="6a365-105">En cambio, la carpeta Mis informes es un área de trabajo que administra el propio usuario.</span><span class="sxs-lookup"><span data-stu-id="6a365-105">In contrast, the My Reports folder is a user-managed workspace.</span></span> <span data-ttu-id="6a365-106">Así, es posible agregar o quitar informes y carpetas, o guardar informes vinculados, con una configuración personalizada.</span><span class="sxs-lookup"><span data-stu-id="6a365-106">You can add or remove reports and folders and save linked reports with personalized settings.</span></span>  
  
 <span data-ttu-id="6a365-107">Conceptualmente, la carpeta Mis informes es similar a la carpeta Mis documentos del sistema de archivos Windows.</span><span class="sxs-lookup"><span data-stu-id="6a365-107">Conceptually, the My Reports folder is similar to the My Documents folder in the Windows file system.</span></span> <span data-ttu-id="6a365-108">Aunque cada usuario dispone de una carpeta denominada Mis informes, la carpeta a la que obtienen acceso cada uno de ellos es distinta de la de los demás.</span><span class="sxs-lookup"><span data-stu-id="6a365-108">Although each user has a folder called My Reports, the folder that each accesses is different from all other users.</span></span> <span data-ttu-id="6a365-109">A excepción de los administradores del servidor de informes, el resto de los usuarios no pueden obtener acceso a la carpeta Mis informes de otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="6a365-109">Except for report server administrators, other users cannot access the contents of the My Reports folder that belongs to you.</span></span>  
  
 <span data-ttu-id="6a365-110">La función Mis informes es opcional y los administradores del servidor de informes pueden deshabilitarla.</span><span class="sxs-lookup"><span data-stu-id="6a365-110">The My Reports feature is optional and can be disabled by a report server administrator.</span></span> <span data-ttu-id="6a365-111">Cuando está habilitada, la carpeta Mis informes aparece en la carpeta Inicio, a la que se puede tener acceso mediante el Administrador de informes o un explorador web.</span><span class="sxs-lookup"><span data-stu-id="6a365-111">If it is enabled, you will see a My Reports folder in the Home folder, which you can access using the Report Manager or a Web browser.</span></span> <span data-ttu-id="6a365-112">Para más información, vea [Buscar y ver informes en el Administrador de informes &#40;Generador de informes y SSRS&#41;](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6a365-112">For more information, see [Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="6a365-113">En un servidor de informes configurado en el modo integrado de SharePoint, no hay equivalente a la carpeta Mis informes.</span><span class="sxs-lookup"><span data-stu-id="6a365-113">On a report server configured in SharePoint integrated mode, there is no equivalent to the My Reports folder.</span></span> <span data-ttu-id="6a365-114">Para obtener más información, vea [Buscar, ver y administrar informes &#40;Generador de informes y SSRS&#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6a365-114">For more information, see [Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="ways-to-use-my-reports"></a><span data-ttu-id="6a365-115">Modos de empleo de Mis informes</span><span class="sxs-lookup"><span data-stu-id="6a365-115">Ways to Use My Reports</span></span>  
 <span data-ttu-id="6a365-116">La carpeta Mis informes está vacía hasta que se agregan informes, carpetas u otros elementos.</span><span class="sxs-lookup"><span data-stu-id="6a365-116">My Reports is empty until you add reports, folders, and other items.</span></span> <span data-ttu-id="6a365-117">A continuación se indican algunos métodos para agregar contenido a Mis informes.</span><span class="sxs-lookup"><span data-stu-id="6a365-117">Here are some ways to add content to My Reports.</span></span>  
  
-   <span data-ttu-id="6a365-118">Crear un informe vinculado personal y almacenarlo en Mis informes.</span><span class="sxs-lookup"><span data-stu-id="6a365-118">Create a personal linked report and store it in My Reports.</span></span> <span data-ttu-id="6a365-119">No todos los informes permiten la vinculación.</span><span class="sxs-lookup"><span data-stu-id="6a365-119">Not all reports are available for linking.</span></span> <span data-ttu-id="6a365-120">Para obtener más información, consulte [Crear un informe vinculado](../reports/create-a-linked-report.md).</span><span class="sxs-lookup"><span data-stu-id="6a365-120">For more information, see [Create a Linked Report](../reports/create-a-linked-report.md).</span></span>  
  
-   <span data-ttu-id="6a365-121">Cargar un archivo de definición de informe (.rdl), un archivo de modelo de informe (.smdl) u otros archivos del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="6a365-121">Upload a report definition (.rdl) file, report model (.smdl) file, or other files from the file system.</span></span> <span data-ttu-id="6a365-122">Puede cargarse cualquier archivo, pero el servidor de informes solamente procesa los archivos con la extensión .rdl o .smdl.</span><span class="sxs-lookup"><span data-stu-id="6a365-122">You can upload any file, but the report server only processes report files that have an .rdl or .smdl file extension.</span></span> <span data-ttu-id="6a365-123">Para más información, vea Definiciones de informe en la [documentación de Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) de los Libros en pantalla de SQL Server y [Cargar un archivo o un informe &#40;Administrador de informes&#41;](../reports/upload-a-file-or-report-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6a365-123">For more information, see Report Definitions" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online and [Upload a File or Report &#40;Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md).</span></span>  
  
-   <span data-ttu-id="6a365-124">Crear y publicar sus propios informes en Mis informes.</span><span class="sxs-lookup"><span data-stu-id="6a365-124">Create and publish your own reports to My Reports.</span></span> <span data-ttu-id="6a365-125">Para más información, vea [Vista de diseño de informe &#40;Generador de informes&#41;](report-design-view-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="6a365-125">For more information, see [Report Design View &#40;Report Builder&#41;](report-design-view-report-builder.md).</span></span>  
  
 <span data-ttu-id="6a365-126">Por lo general, los permisos para la carpeta Mis informes le permiten que sea usted mismo quien administre la carpeta.</span><span class="sxs-lookup"><span data-stu-id="6a365-126">Usually, permissions on My Reports allow you to manage the folder yourself.</span></span> <span data-ttu-id="6a365-127">Sin embargo, siempre es el administrador del servidor de informes quien determina en última instancia las tareas que pueden realizar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6a365-127">However, the report server administrator ultimately determines which tasks users can perform.</span></span> <span data-ttu-id="6a365-128">Si no tiene permisos suficientes para trabajar con la carpeta Mis informes, póngase en contacto con el administrador del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="6a365-128">If insufficient permissions prevent you from working with My Reports, see your report server administrator.</span></span>  
  
## <a name="searching-my-reports"></a><span data-ttu-id="6a365-129">Realizar búsquedas en Mis informes</span><span class="sxs-lookup"><span data-stu-id="6a365-129">Searching My Reports</span></span>  
 <span data-ttu-id="6a365-130">Al realizar búsquedas en una base de datos del servidor de informes, el contenido de la carpeta Mis informes también se incluye en la búsqueda y se excluye el de las carpetas Mis informes de los otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="6a365-130">When you search a report server database, the contents of your My Reports folder are included in the search, while the contents of other user's My Reports folders are excluded.</span></span> <span data-ttu-id="6a365-131">Los resultados de la búsqueda solo muestran los informes a los que se tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="6a365-131">Search results list only the reports to which you have access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a365-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6a365-132">See Also</span></span>  
 [<span data-ttu-id="6a365-133">Buscar, ver y administrar informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6a365-133">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  