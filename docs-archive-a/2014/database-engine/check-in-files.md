---
title: Proteger archivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourceControl.CheckInDialog
helpviewer_keywords:
- checking in files
ms.assetid: 0657a387-8411-4406-bef9-d262a5bfa269
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 070c1dfa5dd057cf777980f7022752a97a4dc84c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674360"
---
# <a name="check-in-files"></a><span data-ttu-id="0b239-102">Proteger archivos</span><span class="sxs-lookup"><span data-stu-id="0b239-102">Check In Files</span></span>
  <span data-ttu-id="0b239-103">Para poner los archivos controlados por código fuente a disposición de otros usuarios, es necesario proteger esos archivos en el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="0b239-103">To make source-controlled files that you have modified available to other users, you must check the files into source control.</span></span> <span data-ttu-id="0b239-104">Al proteger un archivo, la versión que se protege se escribe en el proveedor de control de código fuente y se convierte en la última versión del archivo.</span><span class="sxs-lookup"><span data-stu-id="0b239-104">When you check in a file, the version you check in is written to the source control provider and becomes the latest version of the file.</span></span>  
  
 <span data-ttu-id="0b239-105">Para proteger los archivos se puede utilizar el comando **Proteger** .</span><span class="sxs-lookup"><span data-stu-id="0b239-105">You can use the **Check In** command to check in files.</span></span> <span data-ttu-id="0b239-106">Si usa este comando para proteger una solución o un proyecto, todos los archivos de la solución o el proyecto también se protegen.</span><span class="sxs-lookup"><span data-stu-id="0b239-106">If you use this command to check in a solution or project, all the files in the solution or project are also checked in.</span></span> <span data-ttu-id="0b239-107">No obstante, el hecho de proteger un archivo de código fuente individual no da lugar a la protección del proyecto o la solución a los que pertenece.</span><span class="sxs-lookup"><span data-stu-id="0b239-107">However, checking in an individual source code file does not result in the check-in of the project or solution to which it belongs.</span></span>  
  
### <a name="to-check-in-a-file"></a><span data-ttu-id="0b239-108">Para proteger un archivo</span><span class="sxs-lookup"><span data-stu-id="0b239-108">To check in a file</span></span>  
  
1.  <span data-ttu-id="0b239-109">En el Explorador de soluciones, haga clic con el botón secundario en el archivo que desea proteger y, a continuación, haga clic en **Proteger**.</span><span class="sxs-lookup"><span data-stu-id="0b239-109">In Solution Explorer, right-click the file to check in, and then click **Check In**.</span></span>  
  
2.  <span data-ttu-id="0b239-110">Si aparece el cuadro de diálogo **Proteger** , seleccione las opciones adecuadas y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0b239-110">If the **Check In** dialog box appears, select the appropriate options, and then click **OK**.</span></span>  
  
     <span data-ttu-id="0b239-111">**Check-in**</span><span class="sxs-lookup"><span data-stu-id="0b239-111">**Check In**</span></span>  
     <span data-ttu-id="0b239-112">Protege todos los elementos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="0b239-112">Check in all the selected items.</span></span>  
  
     <span data-ttu-id="0b239-113">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="0b239-113">**Columns**</span></span>  
     <span data-ttu-id="0b239-114">Identifique las columnas que se van a mostrar y el orden en que lo hacen.</span><span class="sxs-lookup"><span data-stu-id="0b239-114">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="0b239-115">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="0b239-115">**Comments**</span></span>  
     <span data-ttu-id="0b239-116">Agregue un comentario para asociarlo a la operación de protección.</span><span class="sxs-lookup"><span data-stu-id="0b239-116">Add a comment to associate with the check-in operation.</span></span>  
  
     <span data-ttu-id="0b239-117">**No mostrar el cuadro de diálogo Proteger al proteger elementos**</span><span class="sxs-lookup"><span data-stu-id="0b239-117">**Don't show Check in dialog box when checking in items**</span></span>  
     <span data-ttu-id="0b239-118">Suprime el cuadro de diálogo en las operaciones de protección.</span><span class="sxs-lookup"><span data-stu-id="0b239-118">Suppress the dialog box during check-in operations.</span></span>  
  
     <span data-ttu-id="0b239-119">**Vista plana**</span><span class="sxs-lookup"><span data-stu-id="0b239-119">**Flat View**</span></span>  
     <span data-ttu-id="0b239-120">Muestra los archivos que protege como listas planas en su conexión de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="0b239-120">Display the files you are checking in as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="0b239-121">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="0b239-121">**Name**</span></span>  
     <span data-ttu-id="0b239-122">Muestra los nombres de los elementos que se protegen.</span><span class="sxs-lookup"><span data-stu-id="0b239-122">Displays the names of the items to check in.</span></span> <span data-ttu-id="0b239-123">Los elementos aparecen con las casillas que se encuentran junto a ellos activadas.</span><span class="sxs-lookup"><span data-stu-id="0b239-123">Items appear with the check boxes next to them selected.</span></span> <span data-ttu-id="0b239-124">Si no desea proteger un elemento determinado, desactive su casilla.</span><span class="sxs-lookup"><span data-stu-id="0b239-124">If you do not want to check in a particular item, clear its check box.</span></span>  
  
     <span data-ttu-id="0b239-125">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="0b239-125">**Options**</span></span>  
     <span data-ttu-id="0b239-126">Si hace clic en la flecha situada a la derecha del botón, se mostrarán opciones de protección específicas del complemento de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="0b239-126">Displays source control plug-in-specific check-in options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="0b239-127">**Sort**</span><span class="sxs-lookup"><span data-stu-id="0b239-127">**Sort**</span></span>  
     <span data-ttu-id="0b239-128">Ordena la visualización de columnas.</span><span class="sxs-lookup"><span data-stu-id="0b239-128">Sort the order of the display columns.</span></span>  
  
     <span data-ttu-id="0b239-129">**Vista de árbol**</span><span class="sxs-lookup"><span data-stu-id="0b239-129">**Tree View**</span></span>  
     <span data-ttu-id="0b239-130">Muestra la jerarquía de carpeta y archivo de los elementos que se protegen.</span><span class="sxs-lookup"><span data-stu-id="0b239-130">Display the folder and file hierarchy for the items you are checking in.</span></span>  
  
 <span data-ttu-id="0b239-131">Si el archivo que ha protegido no forma parte de una desprotección compartida, el entorno de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] lo protege inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="0b239-131">If the file you have checked in is not part of a shared checkout, the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment checks in the file immediately.</span></span> <span data-ttu-id="0b239-132">De lo contrario, es posible que se le pida que combine su versión con las versiones creadas por otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="0b239-132">Otherwise, it may prompt you to merge your version with versions created by other users.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b239-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b239-133">See Also</span></span>  
 <span data-ttu-id="0b239-134">[Ver una lista de archivos modificados](../../2014/database-engine/view-a-list-of-modified-files.md) </span><span class="sxs-lookup"><span data-stu-id="0b239-134">[View a List of Modified Files](../../2014/database-engine/view-a-list-of-modified-files.md) </span></span>  
 [<span data-ttu-id="0b239-135">Administrar protecciones</span><span class="sxs-lookup"><span data-stu-id="0b239-135">Manage Checkins</span></span>](../../2014/database-engine/manage-checkins.md)  
  
  
