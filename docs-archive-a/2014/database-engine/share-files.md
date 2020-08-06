---
title: Compartir archivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- sharing files
- file sharing [SQL Server]
- version control services [SQL Server], file sharing
ms.assetid: 645f5c0a-e949-4e87-8988-85e4d6128464
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 79909fcdb09e349798edfe285475f8a898c3bf04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750118"
---
# <a name="share-files"></a><span data-ttu-id="71f28-102">Compartir archivos</span><span class="sxs-lookup"><span data-stu-id="71f28-102">Share Files</span></span>
  <span data-ttu-id="71f28-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] se puede utilizar para compartir elementos entre proyectos de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="71f28-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to share items across source control projects.</span></span> <span data-ttu-id="71f28-104">Cuando se comparte un elemento, los cambios realizados en éste se reflejan en todos los proyectos que comparten ese elemento.</span><span class="sxs-lookup"><span data-stu-id="71f28-104">When you share an item, any changes to the item are reflected in every project to which the item is shared.</span></span>  
  
 <span data-ttu-id="71f28-105">El compartir elementos ofrece una serie de ventajas a los usuarios del control de código fuente:</span><span class="sxs-lookup"><span data-stu-id="71f28-105">Item sharing provides the following advantages to source control users:</span></span>  
  
-   <span data-ttu-id="71f28-106">Hace innecesario que cada proyecto que utiliza el elemento compartido almacene una copia independiente del mismo, con lo que se ahorra espacio en disco tanto en el cliente como en el servidor de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="71f28-106">Makes it unnecessary for each project that uses the shared item to store a separate copy of the item, conserving disk space on both the source control client and server.</span></span> <span data-ttu-id="71f28-107">El proveedor de control de código fuente almacena el elemento compartido en una ubicación central. Cada proyecto almacena un puntero a esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="71f28-107">The source control provider stores the shared item in one central location, and every project to which it is shared stores a pointer to that location.</span></span>  
  
-   <span data-ttu-id="71f28-108">Evita las incompatibilidades entre versiones.</span><span class="sxs-lookup"><span data-stu-id="71f28-108">Avoids version incompatibilities.</span></span> <span data-ttu-id="71f28-109">Puesto que cada proyecto que comparte el elemento utiliza la misma versión de éste, se evitan los conflictos que surgen cuando cada copia de un elemento cambia de forma independiente en varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="71f28-109">Because every project to which the item is shared uses the same version of the item, you avoid the conflicts that arise when each copy of an item is changing independently within multiple projects.</span></span>  
  
### <a name="to-share-an-item"></a><span data-ttu-id="71f28-110">Para compartir un elemento</span><span class="sxs-lookup"><span data-stu-id="71f28-110">To share an item</span></span>  
  
1.  <span data-ttu-id="71f28-111">En el Explorador de soluciones, seleccione la carpeta o proyecto en que desea colocar los archivos compartidos.</span><span class="sxs-lookup"><span data-stu-id="71f28-111">In Solution Explorer, select either the folder or project in which you want to place the shared files.</span></span>  
  
2.  <span data-ttu-id="71f28-112">En el menú **archivo** , seleccione **control de código fuente**y, a continuación, haga clic en **compartir**.</span><span class="sxs-lookup"><span data-stu-id="71f28-112">On the **File** menu, point to **Source Control**, and then click **Share**.</span></span>  
  
3.  <span data-ttu-id="71f28-113">En el cuadro de diálogo **compartir con** , busque en la lista de directorios el elemento que desea compartir y haga clic en ese elemento.</span><span class="sxs-lookup"><span data-stu-id="71f28-113">In the **Share with** dialog box, browse the directory list for the item you want to share, and click that item.</span></span>  
  
4.  <span data-ttu-id="71f28-114">Haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="71f28-114">Click **Share**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f28-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71f28-115">See Also</span></span>  
 [<span data-ttu-id="71f28-116">Fundamentos del control de código fuente</span><span class="sxs-lookup"><span data-stu-id="71f28-116">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)  
  
  
