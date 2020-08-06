---
title: Cambiar las conexiones del control de código fuente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server Management Studio], source controls
- source controls [SQL Server Management Studio], connections
ms.assetid: 538e3beb-f99c-4095-bd65-6413e872d26e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 077a09cdca0c0aff777184f04467ca39592690aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674363"
---
# <a name="change-source-control-connections"></a><span data-ttu-id="35ed9-102">Cambiar las conexiones del control de código fuente</span><span class="sxs-lookup"><span data-stu-id="35ed9-102">Change Source Control Connections</span></span>
  <span data-ttu-id="35ed9-103">La primera vez que se agrega una solución al control de código fuente o se abre desde él, el proveedor de control de código fuente crea una asociación entre la carpeta raíz del directorio local de la solución y su correspondiente carpeta del servidor.</span><span class="sxs-lookup"><span data-stu-id="35ed9-103">The first time you add or open a solution from source control, your source control provider creates an association between the root folder of the local solution directory and its corresponding server folder.</span></span>  
  
 <span data-ttu-id="35ed9-104">La carpeta raíz (también denominada raíz unificada) reside en el cliente.</span><span class="sxs-lookup"><span data-stu-id="35ed9-104">The root folder (also called unified root) resides on the client.</span></span> <span data-ttu-id="35ed9-105">Es la carpeta en la que se pueden encontrar todos los archivos a los que hace referencia una solución o un proyecto.</span><span class="sxs-lookup"><span data-stu-id="35ed9-105">It is the folder beneath which all the files referenced by a solution or project can be found.</span></span> <span data-ttu-id="35ed9-106">Para buscar la última versión de una solución, su historial y su información de estado, busque la carpeta del servidor, que reside en el servidor de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="35ed9-106">To find the latest version of a solution, its history, and its status information, locate the server folder, which resides on the source control server.</span></span> <span data-ttu-id="35ed9-107">En [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, las carpetas del servidor se denominan proyectos.</span><span class="sxs-lookup"><span data-stu-id="35ed9-107">In [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, server folders are called projects.</span></span>  
  
 <span data-ttu-id="35ed9-108">En muchas situaciones, es necesario anular el enlace o desconectar una solución de su carpeta del servidor.</span><span class="sxs-lookup"><span data-stu-id="35ed9-108">In many situations, you need to unbind or disconnect a solution from its server folder.</span></span> <span data-ttu-id="35ed9-109">Por ejemplo, si el equipo en el que reside el proveedor de control de código fuente no está disponible, es posible conectar a un equipo auxiliar, volver a enlazar la solución a una carpeta del servidor con copia de seguridad y seguir trabajando normalmente.</span><span class="sxs-lookup"><span data-stu-id="35ed9-109">For example, if the computer on which your source control provider resides is unavailable, you can connect to a backup computer, rebind your solution to a backed-up server folder, and resume working normally.</span></span> <span data-ttu-id="35ed9-110">Además, si un proyecto de control de código fuente está bifurcado, quizás tenga que enlazar la solución a la carpeta del servidor en que reside la nueva versión del proyecto.</span><span class="sxs-lookup"><span data-stu-id="35ed9-110">Also, if a source control project is forked, you may have to bind your solution to the server folder where the new project version resides.</span></span>  
  
 <span data-ttu-id="35ed9-111">Utilice la interfaz de usuario del proveedor de control de código fuente para cambiar la carpeta del servidor a la que está enlazada una solución.</span><span class="sxs-lookup"><span data-stu-id="35ed9-111">Use the user interface of the source control provider to change the server folder that a solution is bound to.</span></span> <span data-ttu-id="35ed9-112">Puede abrir la interfaz de usuario del control de código fuente desde el entorno de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35ed9-112">You can open the source control user interface from within the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment.</span></span>  
  
#### <a name="to-open-the-source-control-user-interface-from-the-studio-environment"></a><span data-ttu-id="35ed9-113">Para abrir la interfaz de usuario del control de código fuente desde el entorno de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="35ed9-113">To open the source control user interface from the Studio environment</span></span>  
  
1.  <span data-ttu-id="35ed9-114">En el menú **archivo** , seleccione **control de código fuente**y, a continuación, haga clic en **iniciar Microsoft Visual SourceSafe**.</span><span class="sxs-lookup"><span data-stu-id="35ed9-114">On the **File** menu, point to **Source Control**, and then click **Launch Microsoft Visual SourceSafe**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35ed9-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35ed9-115">See Also</span></span>  
 <span data-ttu-id="35ed9-116">[Aspectos básicos del control de código fuente](../../2014/database-engine/source-control-basics.md) </span><span class="sxs-lookup"><span data-stu-id="35ed9-116">[Source Control Basics](../../2014/database-engine/source-control-basics.md) </span></span>  
 <span data-ttu-id="35ed9-117">[Establecer opciones de control de código fuente](../../2014/database-engine/set-source-control-options.md) </span><span class="sxs-lookup"><span data-stu-id="35ed9-117">[Set Source Control Options](../../2014/database-engine/set-source-control-options.md) </span></span>  
 [<span data-ttu-id="35ed9-118">Excluir archivos desde el control de código fuente</span><span class="sxs-lookup"><span data-stu-id="35ed9-118">Exclude Files from Source Control</span></span>](../../2014/database-engine/exclude-files-from-source-control.md)  
  
  
