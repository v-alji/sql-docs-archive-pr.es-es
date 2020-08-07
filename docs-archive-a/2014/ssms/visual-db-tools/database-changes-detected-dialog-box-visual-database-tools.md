---
title: Se han detectado cambios en la base de datos (cuadro de diálogo, Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.schema.databasechangesdetected
- vdtsql.chm:65543
- vdtsql.chm:65554
ms.assetid: 91f13086-371f-46a2-9f46-804c1415f3ed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91d58e812b93f207d592d245d094b0fbeddcce72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745584"
---
# <a name="database-changes-detected-dialog-box-visual-database-tools"></a><span data-ttu-id="ced6f-102">Se han detectado cambios en la base de datos (cuadro de diálogo, Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ced6f-102">Database Changes Detected Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="ced6f-103">Este cuadro de diálogo aparece si intenta guardar un diagrama de base de datos o tablas seleccionadas y alguno de los objetos de la base de datos a los que va a afectar la acción de guardar no está actualizado en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ced6f-103">This dialog appears if you attempt to save a database diagram or selected tables but some of the database objects that will be affected by the save action are out of date with the database.</span></span> <span data-ttu-id="ced6f-104">Si acepta los cambios mostrados en este cuadro de diálogo, se actualizará la base de datos para que coincida con el diagrama y se sobrescribirán los cambios realizados por otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="ced6f-104">Accepting the changes shown in this dialog box updates the database to match your diagram and overwrites other users' changes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ced6f-105">Aunque no se pueden deshacer los cambios realizados en una tabla o un diagrama de base de datos, los cambios no se guardan en la base de datos hasta que se guarde la tabla o el diagrama.</span><span class="sxs-lookup"><span data-stu-id="ced6f-105">Although you cannot undo changes made to a table or database diagram, the changes are not saved to the database until you save the table or diagram.</span></span> <span data-ttu-id="ced6f-106">Para descartar los cambios no guardados, elija **No** y cierre todos los diagramas abiertos sin guardarlos.</span><span class="sxs-lookup"><span data-stu-id="ced6f-106">You can discard any unsaved changes by choosing **No** and closing all open diagrams without saving them.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ced6f-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="ced6f-107">Options</span></span>  
 <span data-ttu-id="ced6f-108">**Advertir sobre detección de diferencias**</span><span class="sxs-lookup"><span data-stu-id="ced6f-108">**Warn about difference detection**</span></span>  
 <span data-ttu-id="ced6f-109">Especifica si se mostrará este cuadro de diálogo la próxima vez que intente guardar un diagrama de base de datos o las tablas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="ced6f-109">Specify whether this dialog box appears the next time you attempt to save a database diagram or selected tables.</span></span> <span data-ttu-id="ced6f-110">Si esta opción está activada, el cuadro de diálogo aparecerá cada vez que guarde un diagrama o una tabla que no se haya actualizado aún en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ced6f-110">Checked means that the dialog box continues to appear each time you save a diagram or table that is out of date with the database.</span></span> <span data-ttu-id="ced6f-111">Si está desactivada, no se mostrará el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ced6f-111">Unchecked means that the dialog box does not appear.</span></span> <span data-ttu-id="ced6f-112">La opción está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ced6f-112">By default, this box is checked.</span></span> <span data-ttu-id="ced6f-113">Si desactiva esta opción, podrá volver a activarla en el cuadro de diálogo **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="ced6f-113">If you uncheck this option, you can recheck it in the **Options** dialog box.</span></span>  
  
 <span data-ttu-id="ced6f-114">**Sí**</span><span class="sxs-lookup"><span data-stu-id="ced6f-114">**Yes**</span></span>  
 <span data-ttu-id="ced6f-115">Actualiza la base de datos con todos los cambios mostrados en la lista.</span><span class="sxs-lookup"><span data-stu-id="ced6f-115">Update the database with all the changes shown in the list.</span></span>  
  
 <span data-ttu-id="ced6f-116">**No**</span><span class="sxs-lookup"><span data-stu-id="ced6f-116">**No**</span></span>  
 <span data-ttu-id="ced6f-117">Cancela la acción de guardar.</span><span class="sxs-lookup"><span data-stu-id="ced6f-117">Cancel the save action.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ced6f-118">Para actualizar el diagrama de forma que coincida con la base de datos, ciérrelo sin guardar los cambios, haga clic con el botón secundario en el diagrama del Explorador de servidores, haga clic en Actualizar y, a continuación, vuelva a abrir el diagrama.</span><span class="sxs-lookup"><span data-stu-id="ced6f-118">To refresh your diagram to match the database, close it without saving changes, right-click the diagram in Server Explorer and click Refresh, and then reopen the diagram.</span></span>  
  
 <span data-ttu-id="ced6f-119">**Guardar archivo de texto**</span><span class="sxs-lookup"><span data-stu-id="ced6f-119">**Save Text File**</span></span>  
 <span data-ttu-id="ced6f-120">Muestra el cuadro de diálogo **Guardar como** , que permite especificar una ubicación para el archivo de texto que contiene la lista de cambios efectuados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ced6f-120">Display the **Save As** dialog box, letting you specify a location for a text file containing a list of the database changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced6f-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ced6f-121">See Also</span></span>  
 <span data-ttu-id="ced6f-122">[Reconciliar un diagrama de base de datos con una base de datos modificada &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ced6f-122">[Reconcile a Database Diagram with a Modified Database &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="ced6f-123">Entornos multiusuario &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ced6f-123">Multiuser Environments &#40;Visual Database Tools&#41;</span></span>](multiuser-environments-visual-database-tools.md)  
  
  
