---
title: Reconciliar un diagrama de base de datos con una base de datos modificada (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- updating diagram to match database
- reconciling database diagrams
- diagrams [SQL Server], reconciling changes
- updating database to match diagram
- database diagrams [SQL Server], reconciling changes
ms.assetid: eda8dea2-eedd-43a7-85aa-92bd97783b5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e5e5127ab613a6f791919a98899e40caa2ddac20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744946"
---
# <a name="reconcile-a-database-diagram-with-a-modified-database-visual-database-tools"></a><span data-ttu-id="ca330-102">Reconciliar un diagrama de base de datos con una base de datos modificada (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ca330-102">Reconcile a Database Diagram with a Modified Database (Visual Database Tools)</span></span>
  <span data-ttu-id="ca330-103">Debe guardar el diagrama de base de datos cuando esté preparado para actualizar la base de datos de forma que coincida con el diagrama.</span><span class="sxs-lookup"><span data-stu-id="ca330-103">You save your database diagram when you are ready to update the database to match your diagram.</span></span> <span data-ttu-id="ca330-104">Sin embargo, si otros usuarios han actualizado la base de datos desde que abrió el diagrama, los cambios que hayan realizado podrían afectar al diagrama y viceversa.</span><span class="sxs-lookup"><span data-stu-id="ca330-104">However, if other users have updated the database since you opened your diagram, their changes might affect your diagram and vice versa.</span></span>  
  
 <span data-ttu-id="ca330-105">Cuando guarde el diagrama, la base de datos se reconciliará con el diagrama, sobrescribiéndose los cambios de los otros usuarios de forma que la base de datos coincida con su diagrama.</span><span class="sxs-lookup"><span data-stu-id="ca330-105">Saving your diagram will reconcile the database with your diagram by overwriting other users' changes so that the database will match your diagram.</span></span>  
  
### <a name="to-update-a-database-to-match-your-diagram"></a><span data-ttu-id="ca330-106">Para actualizar una base de datos de forma que coincida con su diagrama</span><span class="sxs-lookup"><span data-stu-id="ca330-106">To update a database to match your diagram</span></span>  
  
1.  <span data-ttu-id="ca330-107">Guarde el diagrama de base de datos.</span><span class="sxs-lookup"><span data-stu-id="ca330-107">Save your database diagram.</span></span>  
  
     <span data-ttu-id="ca330-108">Si no guardó previamente el diagrama, escriba un nombre para el diagrama en el cuadro de diálogo **Guardar nuevo diagrama de base de datos** y elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca330-108">If you have not previously saved your diagram, type a name for the diagram in the **Save New Database Diagram** dialog box and choose **OK**.</span></span>  
  
2.  <span data-ttu-id="ca330-109">El cuadro de diálogo **Guardar** muestra las tablas que se verán afectadas cuando guarde el diagrama.</span><span class="sxs-lookup"><span data-stu-id="ca330-109">The **Save** dialog box lists the tables that will be affected when you save your diagram.</span></span> <span data-ttu-id="ca330-110">Elija **Sí** para continuar.</span><span class="sxs-lookup"><span data-stu-id="ca330-110">Choose **Yes** to continue.</span></span>  
  
3.  <span data-ttu-id="ca330-111">En el cuadro de diálogo **Se han detectado cambios en la base de datos** se muestran los objetos que se han modificado y que se van a cambiar para que coincidan con su diagrama.</span><span class="sxs-lookup"><span data-stu-id="ca330-111">The **Database Changes Detected** dialog box lists the objects that were modified and will be changed to match your diagram.</span></span> <span data-ttu-id="ca330-112">Elija **Sí** para guardar el diagrama y aceptar la lista de cambios.</span><span class="sxs-lookup"><span data-stu-id="ca330-112">Choose **Yes** to save the diagram and accept the list of changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca330-113">Si el diagrama contiene tablas y columnas que se eliminaron de la base de datos, solo se volverán a crear sus definiciones en la base de datos cuando guarde el diagrama.</span><span class="sxs-lookup"><span data-stu-id="ca330-113">If your diagram contains tables and columns that were deleted in the database, only their definitions are recreated in the database when you save your diagram.</span></span> <span data-ttu-id="ca330-114">Este proceso no restaura los datos que existían en estos objetos antes de su eliminación.</span><span class="sxs-lookup"><span data-stu-id="ca330-114">This process does not restore any data that existed in these objects before their deletion.</span></span>  
  
### <a name="to-update-your-diagram-to-match-a-modified-database"></a><span data-ttu-id="ca330-115">Para actualizar su diagrama de forma que coincida con una base de datos modificada</span><span class="sxs-lookup"><span data-stu-id="ca330-115">To update your diagram to match a modified database</span></span>  
  
1.  <span data-ttu-id="ca330-116">Cierre su diagrama sin guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="ca330-116">Close your diagram without saving changes.</span></span>  
  
2.  <span data-ttu-id="ca330-117">Haga clic con el botón secundario en el diagrama en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="ca330-117">Right-click the diagram in Object Explorer.</span></span>  
  
3.  <span data-ttu-id="ca330-118">En el menú contextual, haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="ca330-118">From the shortcut menu click **Refresh**.</span></span>  
  
4.  <span data-ttu-id="ca330-119">Vuelva a abrir el diagrama.</span><span class="sxs-lookup"><span data-stu-id="ca330-119">Reopen the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca330-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca330-120">See Also</span></span>  
 [<span data-ttu-id="ca330-121">Trabajar con diagramas de base de datos &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ca330-121">Work with Database Diagrams &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
