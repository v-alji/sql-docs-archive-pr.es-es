---
title: Copiar tablas de un diagrama de base de datos a otro (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- copying tables
- duplicating tables
ms.assetid: 155a4f09-9321-4887-a7d4-aa2ce6b51277
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7e90c8f324e80f7c59674def06a77e93a5bf0cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743843"
---
# <a name="copy-tables-from-one-database-diagrams-to-another-visual-database-tools"></a><span data-ttu-id="4a282-102">Copiar tablas de un diagrama de base de datos a otro (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4a282-102">Copy Tables from One Database Diagrams to Another (Visual Database Tools)</span></span>
  <span data-ttu-id="4a282-103">Puede copiar una tabla de un diagrama de base de datos a otro de una misma base de datos.</span><span class="sxs-lookup"><span data-stu-id="4a282-103">You can copy a table from one database diagram to another in the same database.</span></span>  
  
 <span data-ttu-id="4a282-104">Si copia una tabla de un diagrama de base de datos a otro, solo se agregará una referencia a la tabla del segundo diagrama.</span><span class="sxs-lookup"><span data-stu-id="4a282-104">Copying a table from one database diagram to another diagram adds a reference to the table in the second diagram.</span></span> <span data-ttu-id="4a282-105">No se duplica la tabla en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4a282-105">The table is not duplicated in your database.</span></span> <span data-ttu-id="4a282-106">Por ejemplo, si copia la tabla `authors` de un diagrama de base de datos a otro, cada diagrama hará referencia a la misma tabla `authors` de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4a282-106">For example, if you copy the `authors` table from one database diagram to another, each diagram references the same `authors` table in the database.</span></span>  
  
### <a name="to-copy-a-table-from-another-database-diagram"></a><span data-ttu-id="4a282-107">Para copiar una tabla de otro diagrama de base de datos</span><span class="sxs-lookup"><span data-stu-id="4a282-107">To copy a table from another database diagram</span></span>  
  
1.  <span data-ttu-id="4a282-108">Asegúrese de que está conectado a la base de datos cuya tabla desea copiar.</span><span class="sxs-lookup"><span data-stu-id="4a282-108">Make sure you are connected to the database whose table you want to copy.</span></span>  
  
2.  <span data-ttu-id="4a282-109">Abra los diagramas de base de datos de origen y de destino y, en el diagrama de origen, seleccione la tabla que desea copiar al diagrama de destino.</span><span class="sxs-lookup"><span data-stu-id="4a282-109">Open the source and target database diagrams and within the source diagram, select the table that you want to copy to the target diagram.</span></span>  
  
3.  <span data-ttu-id="4a282-110">Haga clic en el botón **Copiar** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="4a282-110">Click the **Copy** button on the toolbar.</span></span> <span data-ttu-id="4a282-111">Esta acción coloca la definición de la tabla seleccionada en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="4a282-111">This action places the selected table definition on the Clipboard.</span></span>  
  
4.  <span data-ttu-id="4a282-112">Cambie al diagrama de destino.</span><span class="sxs-lookup"><span data-stu-id="4a282-112">Switch to the target diagram.</span></span> <span data-ttu-id="4a282-113">Este diagrama debe estar en la misma base de datos que el diagrama de origen.</span><span class="sxs-lookup"><span data-stu-id="4a282-113">This diagram must be in the same database as the source diagram.</span></span>  
  
5.  <span data-ttu-id="4a282-114">Haga clic en el botón **Pegar** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="4a282-114">Click the **Paste** button on the toolbar.</span></span> <span data-ttu-id="4a282-115">El contenido del Portapapeles aparecerá en la nueva ubicación y permanecerá resaltado hasta que haga clic en otro punto.</span><span class="sxs-lookup"><span data-stu-id="4a282-115">The Clipboard contents appear at the new location and remain highlighted until you click elsewhere.</span></span> <span data-ttu-id="4a282-116">Si existen relaciones entre las tablas seleccionadas y otras tablas del diagrama de destino, las líneas de las relaciones se dibujarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4a282-116">If relationships exist between the selected tables and other tables in the target diagram, relationship lines are automatically drawn.</span></span>  
  
 <span data-ttu-id="4a282-117">Cuando edite la tabla en uno de los diagramas, los cambios se reflejarán en ambos.</span><span class="sxs-lookup"><span data-stu-id="4a282-117">When you edit the table in either diagram, your changes are reflected in both diagrams.</span></span> <span data-ttu-id="4a282-118">De forma similar, una vez guardada la tabla en cualquiera de los diagramas, la tabla ya no se considera "modificada" en ninguno de ellos.</span><span class="sxs-lookup"><span data-stu-id="4a282-118">Similarly, once you save the table in either diagram, the table is no longer considered "modified" in either diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a282-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a282-119">See Also</span></span>  
 <span data-ttu-id="4a282-120">[Trabajar con diagramas de base de datos &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4a282-120">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4a282-121">Agregar tablas a diagramas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4a282-121">Add Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](add-tables-to-diagrams-visual-database-tools.md)  
  
  
